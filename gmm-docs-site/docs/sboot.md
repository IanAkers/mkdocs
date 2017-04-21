- Set up a new repository: `https://bitbucket.org/account/user/oneglobe/projects/BGM`
  - Select Create Repository from Repositories menu.
  - Select oneglobe as owner.
  - Select bahgmm project.
  - Enter service name in following format bahgmm-svc-[servicename]
 - Select Create Repository button
- Copy template files from bahgmm-templates
  - Copy spring-template directory from bahgmm-templates
  - Modify dockerfile and pom file if needed
    - Ensure that the POM file contains
                <start-class>[package].[main class name]</start-class> in the properties section
                and
                <mainClass>[package].[main class name]</mainClass> in the maven-assembly-plugin section
    - Ensure Dockerfile entry point jar matches the artifactId and version from the POM file
    - Configure the environment variables in the docker file
    - To enable tests ensure that the POM file contains
                <runSuite>**/[main test class name].class</runSuite>
                                and
                <include>${runSuite}</include> in the maven-surefire-plugin section

- Create Dev, Test, and Prod branches

- Create new service in OpenShift
  - Run `oc login` from terminal
  - Login to openshift using OC tools
  - Run `oc projects` to view the list of available projects in openshift.
  - Run `oc project <projectname>` to select desired project.
  - Run `oc new-app https://ogjenkins:ogjenkins@bitbucket.org/oneglobe/[repositoryName].git --context-dir=[patToDockerfileFolder]` to launch a new app
  - Example: `oc new-app https://ogjenkins:ogjenkins@bitbucket.org/oneglobe/bahgmm-spring-pipeline.git --context-dir=spring-template`

NOTE: if you are getting the following error: `yaml: line 3: mapping values are not allowed in this context`
*Attempt to clone the repository locally,
*cd to the repository folder,
*run `oc new-app .` to generate resources using your local repo
*from openshift gui edit the newly created build configuration with the full repository link mentioned in steps above
*start the build again from openshift

- Create route for new service in OpenShift
  - Use web browser to log into Openshift console `https://master.gmm.bahincubator.com:8443`
  - Select the desired project form the list of available projects.
  - Locate and select the service name link for the services you wish to create the route for.
  - Once on the service details page select either the create route link located in the details section or select create route from the `Actions` drop-down menu in the top right corner of the page.
  - Enter the route in the `Hostname` field in the following format `[serviceName].apps.gmm.bahincubator.com` and click the create button at the bottom of the page.

- Create Jenkins job for new service
  - Log into GMM jenkins: `http://jenkins.gmm.bahincubator.com/`
  - Select `New Item` from the menu on the left side of the page.
  - Enter a name for the service in the following format `bahgmm-svc-[serviceName]`.
  - Select `Multibranch Pipline` and click `OK`
  - Once on the configuration page enter a `Display Name` if desired.
  - Select the `Add source` drop-down and select the appropriate source for your repository (in this case bitbucket)
  - Select `ogjenkins` for the scan credentials
  - Enter `oneglobe` in the Owner field
  - Enter the repository name in the Repository Name field
  - Select the Auto-register webhook checkbox
  - Click Save to save the configuration and start the job
