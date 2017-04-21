# DevOps Team

### Three Perspectives
- Client, as a proposal → slide deck
- Timebox driven → Step 1: Demo, Step 2: ???, Step 3 Profit
- Investment → task list

### SLIDE DECK:
### Guiding Principles
- Everything as a Service - consume as is, do not have to worry about the internals
- Everything is Interchangeable - out of a box, replace pieces based on agency requirements
- [Across the Board] Visibility - transparency, into what?? (devops piplines, environments, dev status).  Visibility for checking the boxes, updated/automated governance

### Features Slide
- Continuous Integration and Deployment
- Scalability and Performance
-Fault Tolerance and Catastrophe-Preparedness
- Security and Monitoring
- Governance and Monitoring
- Deployment to an Agency

### NOTE: Dev vs Ops perspectives (for each section talk about each perspective)
### Continuous Integration and Deployment
- jenkins pipelines magic

### Scalability and Performance
- openshift and aws magic

### Fault Tolerance and Catastrophe-Preparedness
- 3 prongs: attempt to stay up, get back up, be able to see what went wrong
- translates to HA, scripting, and logging

### Security and Monitoring
- Monitoring
  - Elk Stack
- Security
  - Code Scans
  - Image Scans
  - App Scans
  - DB Scans
  - Infrastructure Scans
- Locking down the AWS console

### Governance and Monitoring
- Governance Suggestions
  - Team Roles
  - CI/CD - pipeline architecture enforces software engineering processes/policies/regulations
    - example: failing builds on code coverage
    - navigation of the software change through the pipeline enforces ^
  - Ops
  - Microservice Documentation
  - Microservice Development Standards
- Monitoring
  - Pipeline Deployment Dashboard
  - Infrastructure Health Dashboard
    - node alarms / notifications
    - automated response
  - Service Health Dashboard - performance contract
  - Development Dashboard - not in DevOps scope?
  - Microservice Production Readieness Dashboard

### Deployment to an Agency
- How it affects current organization
  - Policy
  - People
  - Infrastructure
  - Uncategorized:
    - big bang vs in sections
    - automation vs manual, create efficiency?
    - Retraining staff
    - Tie in change management staff (pipeline and monitoring dashboards)
- Rolling out the DevOps Process
  - Policy
  - People
  - Infrastructure
  - Uncategorized:
    - minimum viable product
    - then add lifecycle events (system governance) - proccess is the process, customize the pipeline, ability to have manual steps in the pipeline
    - notifications
    - custom tools, that are already at the agency
    - perform recommended organizational changes
      - prove that all of the boxes are checked, automated documentation and verification of these processes (automation of manual processes) - process re-engineering
    - NOTE: Rollout can be it's own presentation
- Deployment Scripts
- Hardened Images
- On-boarding Guides

### TASK LIST:
### Guiding principles
- It is not done until it's documented
- 3 stages for each task: working, automated & documented

### Infrastructure
- Add users/permissions to openshift
- Add users/permissions to jenkins
- reconfigure jenkins for HA
- Script deployments Jenkins and OS
- reconfigure jenkins & OS to run on hardened images
- Stand up UI test tools
- Stand up Elk Stack
- Security - Infrastructure scanning, machine level (Open VAS)
- Openshift Configuration
  - Configure Persistent Storage on Openshift
  - Configure pods to have health checks (liveness and readiness)
  - Configure DB access for local development (1. external to openshift, 2. external to aws)
  - Configure and standartize environment variable injection
  - Add a service account to openshift for jenkins jobs and configure openshift secret instead of token use
  - Increase buffer limit on git configuration if this error keeps showing up: `fatal: The remote end hung up unexpectedly`: http://stackoverflow.com/questions/6842687/the-remote-end-hung-up-unexpectedly-while-git-cloning

### Dev Support - unplanned
- Stand up – Kafka
- Write Kafka Spring Adapter Object
- Set up new services (repos/pipelines/deployments) – config, rules, data, submit
- Migrate services in legacy pipeline state into new dev environment
  - Redeploy Activiti service
  - Redeploy Application service
  - Redeploy UI
- Stand up databases in the test environent
- Script database population with test data

### Pipeline Development
- Configure pernament token for pipeline deployment
- Set up barebones Spring Service Pipeline template
- Set up barebones NodeJS/Angular 2 (UI) template
- Configure build trigger for openshift
- Configure pull request settings in openshift and jenkins, lock down branch permissions
- Configure deployment propagation to test environment
- Configure deployment propagation to pre-prod environment
- Configure pipeline to create new resources if they do not exist (oc new-app step)
- Pipeline as a Service - automated provisioning of the development environments
  - Script repository generation - Repository + Brach configuration
- Pipeline Stage Development
  - Security
    - Code scanning stage (sonarcube)
    - Application Scanning (OWASP), front-end and fuzzing
    - DB Scanning - SQL Injection/Fuzzing (SQL-MAP)
    - Docker Image Scanning
  - Service Tests
    - Lint
    - Unit
    - Integration
    - End-to-end
  - UI testing
- Figure out why we are getting `yaml: line 3: mapping values are not allowed in this context` when running oc new-app

### DevOps: Monitoring/Dashboard/Governance
- Come up with the feature plan for an Agency Demo
- Come up with the onboarding guide
- Configure elk stack for service performance monitoring
- Stand up a dashboard for microservice 'production readyness' status
  - Stability and Reliability
  - Scalability and Performance
  - Fault Tolerance and Catastrophe-Preparedness
  - Monitoring
  - Documentation
- Come up with a documentation template for microservices
- Come up with infrastructure diagram - VM perspective
- Decide and Configure centralized DevOps documentation location
  - Pipeline Architecture documentation
