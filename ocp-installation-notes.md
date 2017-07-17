# OCP Installation Notes

## Resources
https://access.redhat.com/documentation/en-us/reference_architectures/2017/html-single/deploying_openshift_container_platform_3.5_on_amazon_web_services/

https://docs.openshift.com/container-platform/3.5/

https://docs.openshift.com/container-platform/3.5/install_config/configuring_aws.html#install-config-configuring-aws

## Temporary Quick OCP Installation

Cluster looks like this:

* 1 Master: bahgmm-ocp-master
* 3 Nodes: bahgmm-ocp-node-0/1/2

All are m4.xls with 150GB of EBS storage using RHEL 7.3 AMI

Installation Steps:
1.  Create Instances
2.  run yum update:
2.1 (optional) install vim - `sudo yum install vim`
3.  Configure DNS - Route 53, wild card Record Set for the service routes, dns record set for console access.  Both routing to the ip of the Master
4.  Follow the following steps to prepare the host:
https://docs.openshift.com/container-platform/3.5/install_config/install/host_preparation.html

  NOTE: For step `Configuring Docker Storage`, do nothing...

5.  Generate an ssh-key on the machine that will be running the installer, distribute they key to other nodes (into authorized_users)

6.  run the quick installer

  Wrote atomic-openshift-installer config: /root/.config/openshift/installer.cfg.yml
  Wrote Ansible inventory: /root/.config/openshift/hosts

7.  perform what's next
https://docs.openshift.com/container-platform/3.5/install_config/install/quick_install.html#quick-install-whats-next

oadm policy add-cluster-role-to-user cluster-reader system:serviceaccount:default:router
