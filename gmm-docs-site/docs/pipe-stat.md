# Services Dashboard


## Deployment

| Services                 | Declarative Pipeline | Dev      | Test     | Pre-Prod |
| ------------------------ | -------------------- | -------- | -------- | -------- |
| bahgmm-svc-activiti      | `legacy`             | `legacy` ||
| bahgmm-svc-application   | `legacy`             | `legacy` ||
| bahgmm-ui                | `legacy`             | `legacy` ||
| bahgmm-svc-data          | `yes`                | `yes`    ||
| bahgmm-svc-rules         | `yes`                | `yes`    ||
| bahgmm-svc-submit        | `yes`                | `yes`    ||
| bahgmm-svc-config        | `yes`                | `yes`    ||
| bahgmm-svc-utility       |                      |          ||
| bahgmm-svc-taskdata      | `yes`                | `yes`    ||
| **PIPELINE DEVELOPMENT** ||||
| bahgmm-spring-pipeline   | `yes`                | `yes`    ||
| bahgmm-node-pipeline     |                      |          ||

## Pipeline Test Stages

| Services                 | Lint | Unit      | Functional |Integration    | End-to-End |
| ------------------------ | -------------- | -------- | -------- | -------- | -------- |
| bahgmm-svc-activiti      | ``             | `legacy` ||
| bahgmm-svc-application   | ``             | `legacy` ||
| bahgmm-ui                | ``             | `legacy` ||
| bahgmm-svc-config        |                  |               ||
| bahgmm-svc-data          |                  |               ||
| bahgmm-svc-submit        |                  |               ||
| bahgmm-svc-taskdata      |                  |               ||
| bahgmm-svc-utility       |                  |               ||
| bahgmm-svc-rules         | `yes`           |               ||
| **PIPELINE DEVELOPMENT** |                  |               ||
| bahgmm-spring-pipeline   | `yes`            |               ||
| bahgmm-node-pipeline     |                  |               ||

## Pipeline Security Stages


Other repositories

bahgmm-bpmn -- ?  
bahgmm-kafka -- kafka demo services  
bahgmm-svc1-- ?   
bahgmm-templates -- repository holding service templates  
