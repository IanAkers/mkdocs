# Grant Management Modernization

## Overview

Grant Management Application consist of three major components:

  - NodeJS + Angular Front End
  - SpringBoot Microservice Back End
  - Activiti BPM

**Microservices:**

  - Application - application submission service
  - Task Data - ???
  - Utility - ???
  - Config - ???
  - Activiti - interface to the Activiti BPM

**Infrastructure:**

Containerized application running on OpenShift cluster in AWS.  With Jenkins as the automation tool.

## Developer Onboarding

### Installations
Make sure you have the following installed:

- JDK
- GIT (including gitbash)
- Eclipse or IntelliJ (community edition does not support NodeJS)
- Python (optional)

### Request Access:

1.  Request project access:
    - Go to `selfserviceportal.boozallencsn.com`
    - Hit `Request Access``
    - Fill out the form, team: `JHT-ACCT-GROUP`, project `GMM-Grants Management Modernization`

2. Get your IP whitelisted
    - Send an email with your public ip to Brian or Arsenie to get Jenkins & openshift Access

3. Request bitbucket access (temporary)

4. After you are granted project or/and bitbucket access, configure github/bitbucket for ssh access (see github/bitbucket help articles on ssh keys)

5. Clone repositories
