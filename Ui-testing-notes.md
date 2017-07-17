## Where to Run the Tests:

## Which Browsers to use


Tasks:
* Machine: Linux - T2 Large -
Things to install:
`yum update`
`yum install vim`
`yum install wget`
install java
`yum search java | grep openjdk`
`yum install java-1.8.0-openjdk*`
set java Home
`vim /etc/profile.d/java.sh`


get ghostdriver
`wget https://bitbucket.org/ariya/phantomjs/downloads/phantomjs-2.1.1-linux-x86_64.tar.bz2`
untar
`yum install bzip2`
`tar -xvjf phantomjs-2.1.1-linux-x86_64.tar.bz2`

install maven
https://tecadmin.net/install-apache-maven-on-centos/

mvn achetype:generate
848 serenity: junit jbehave
`mvn clean test serenity:aggregate`

aggregate
results are stored in target/site/serenity/index.html
* add chrome driver to user bin
