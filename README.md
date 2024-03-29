Sample azure-functions.gradle:
~~~
azurefunctions {
    resourceGroup = 'java-functions-group'
    appName = 'azure-functions-sample-demo'
    pricingTier = 'Consumption'
    region = 'westus'
    runtime {
      os = 'windows'
    }
    localDebug = "transport=dt_socket,server=y,suspend=n,address=5005"
}
~~~

Sample local.settings.json:
~~~
{
  "IsEncrypted": false,
  "Values": {
    "FUNCTIONS_WORKER_RUNTIME": "java",
    "AzureWebJobsStorage": "",
    "AzureWebJobsDashboard": "",
    "MyBindingConnection": "",
    "AzureWebJobs.HttpExample.Disabled": "true",
  },
  "ConnectionStrings": {
    "SQLConnectionString": ""
  },
  "Host": {
    "LocalHttpPort": 7071,
    "CORS": "*"
  }
}
~~~

Sample host.json (generated by task installFunctionsExtensions):
~~~
{
  "version": "2.0",
  "extensionBundle": {
    "id": "Microsoft.Azure.Functions.ExtensionBundle",
    "version": "[2.*, 3.0.0)"
  }
}
~~~

Tasks:

~~~
    ./gradlew installFunctionsExtensions
~~~

~~~
    ./gradlew azureAccountSet
~~~

~~~
    ./gradlew azureFunctionsDeploy
~~~

~~~
    ./gradlew fetchAppSettings
~~~