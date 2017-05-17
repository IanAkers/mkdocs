## Service Accounts

- Regular users can authenticate to the Openshift API by using their personal access token which are automatically rotated everyday. Service accounts allow us to authenticate to the Openshift API with a permanent access token. One was created for Jenkins to manage the pipeline without constantly swapping the access token in the Jenkinsfile.

- Create a jenkins service account in the default namespace:
```
oc create serviceaccount jenkins -n default
```

- The jenkins service account needs to be assigned the 'edit' cluster role:
```
oc adm policy add-cluster-role-to-user edit -z jenkins
```

- Copy the service account's token:
```
oc serviceaccounts get-token jenkins
```

- Save the token in Jenkins as a Global Credential: 
    - http://jenkins.gmm.bahincubator.com/credentials/store/system/domain/_/
        - Kind: Secret text
        - Secret: Paste token here
        - ID: OPENSHIFT_AUTH_TOKEN

- Modify Jenkinsfile to set credential as a global environment variable:
    - See: https://jenkins.io/doc/pipeline/tour/environment/
    - Insert at top of pipeline{}: ``` 
environment {
    OPENSHIFT_AUTH_TOKEN = credentials('OPENSHIFT_AUTH_TOKEN')
}
```
    - Invoke with: ```"${env.OPENSHIFT_AUTH_TOKEN}"```

