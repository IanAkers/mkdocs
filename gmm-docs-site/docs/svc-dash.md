# Service Dashboard

## Deployment

| Services                 | Declarative Pipeline | Dev      | Test     | Pre-Prod |
| ------------------------ | -------------------- | -------- | -------- | -------- |
| bahgmm-svc-activiti      | `legacy`             | `legacy` ||
| bahgmm-svc-application   | `legacy`             | `legacy` ||
| bahgmm-ui                | `legacy`             | `legacy` ||
| bahgmm-svc-config        | `yes`                | `yes`    ||
| bahgmm-svc-data          | `yes`                | `yes`    ||
| bahgmm-svc-submit        | `yes`                | `yes`    ||
| bahgmm-svc-rules         | `yes`                | `yes`    ||
| bahgmm-svc-taskdata      | `yes`                | `yes`    ||
| bahgmm-svc-utility       |                      |          ||
| **PIPELINE DEVELOPMENT** ||||
| bahgmm-spring-pipeline   | `yes`                | `yes`    ||
| bahgmm-node-pipeline     |                      |          ||

## Pipeline Test Stages

| Services                 | Unit | Lint | Coverage | Functional/UI | Integration | End-to-End | 508 |
| ------------------------ | ---- | -------- | -------- | -------- | -------- | -- | -- |
| bahgmm-svc-activiti      |      || ||
| bahgmm-svc-application   |             |  ||
| bahgmm-ui                |              |  ||
| bahgmm-svc-config        | `yes`|               ||
| bahgmm-svc-data          | `yes`|               ||
| bahgmm-svc-submit        | `yes`|               ||
| bahgmm-svc-rules         | `yes`|      ||
| bahgmm-svc-taskdata      | `yes`|    `yes`      |         ||
| bahgmm-svc-utility       |                  |               ||
| **PIPELINE DEVELOPMENT** |                  |               ||
| bahgmm-spring-pipeline   |    `yes`         | `yes`              ||
| bahgmm-node-pipeline     |                  |               ||

## Pipeline Security Stages

| Services                 | Code Scan | Container Image | Endpoint | DB | UI Crawler|
| ------------------------ | -------------- | -------- | -------- | -------- |---- |
| bahgmm-svc-activiti      |              |  |||
| bahgmm-svc-application   |              |  |||
| bahgmm-ui                |             |  |||
| bahgmm-svc-config        |                  |               ||
| bahgmm-svc-data          |                  |               ||
| bahgmm-svc-submit        |                  |               ||
| bahgmm-svc-rules         |             |               ||
| bahgmm-svc-taskdata      |                  |               ||
| bahgmm-svc-utility       |                  |               ||
| **PIPELINE DEVELOPMENT** |                  |               ||
| bahgmm-spring-pipeline   | `yes`            |               ||
| bahgmm-node-pipeline     |                  |               ||

Other repositories

bahgmm-bpmn -- ?  
bahgmm-kafka -- kafka demo services  
bahgmm-svc1-- ?   
bahgmm-templates -- repository holding service templates  
