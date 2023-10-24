# azure-functions-db
Contains Azure Functions for database operations.

## Pre-requisite:
- Postgres-13 ( give reader role for azure function in postgres )
- Resources for Azure Function

## Azure Function Setup:
1. After creating the Azure Function container, make sure to add the following additional environment variables if not available.

   ```json
   [
  {
    "name": "APPLICATIONINSIGHTS_CONNECTION_STRING",
    "value": GIVE THE VALUE,
    "slotSetting": false
  },
  {
    "name": "AzureWebJobsStorage",
    "value": GIVE THE VALUE,
    "slotSetting": false
  },
  {
    "name": "BUILD_FLAGS",
    "value": "UseExpressBuild",
    "slotSetting": false
  },
  {
    "name": "DOCKER_REGISTRY_SERVER_PASSWORD",
    "value": GIVE THE VALUE,
    "slotSetting": false
  },
  {
    "name": "DOCKER_REGISTRY_SERVER_URL",
    "value": GIVE THE VALUE,
    "slotSetting": false
  },
  {
    "name": "DOCKER_REGISTRY_SERVER_USERNAME",
    "value": GIVE THE VALUE,
    "slotSetting": false
  },
  {
    "name": "ENABLE_ORYX_BUILD",
    "value": "true",
    "slotSetting": false
  },
  {
    "name": "FUNCTIONS_EXTENSION_VERSION",
    "value": "~4",
    "slotSetting": false
  },
  {
    "name": "PGHOST",
    "value": GIVE THE VALUE,
    "slotSetting": false
  },
  {
    "name": "PGPASSWORD",
    "value": GIVE THE VALUE,
    "slotSetting": false
  },
  {
    "name": "PGUSER",
    "value": GIVE THE VALUE,
    "slotSetting": false
  },
  {
    "name": "SCM_DO_BUILD_DURING_DEPLOYMENT",
    "value": "1",
    "slotSetting": false
  },
  {
    "name": "STORAGE_CONNECTION_STRING",
    "value": GIVE THE VALUE,
    "slotSetting": false
  },
  {
    "name": "WEBSITES_ENABLE_APP_SERVICE_STORAGE",
    "value": "false",
    "slotSetting": false
  },
  {
    "name": "XDG_CACHE_HOME",
    "value": "/tmp/.cache",
    "slotSetting": false
  }
]

  
## building the image:
   ```bash
  docker build --tag <dockerid>/tag .  
  docker push <dockerid>/tag  
  ```
## To run locally:
   ```bash
  docker run -p 8080:80 -it <dockerid>/tag bash  
  ```
## Testing endpoint in azure:  
https://< appname >/api/databasebackup?code=< function code >/&database_name=< db name >&container_name=< container name >  

you could also skip giving the container name and just give the database name for the above endpoint
