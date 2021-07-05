# NestJS

What are the steps?

Scaffold a NestJS app

Generate something that adds a module to the NestJS app

- Install Nest.js CLI
- Generate an app
- Add Azure module



## Install CLI

To install the Nest.js CLI type

```
npm i -g @nestjs/cli
```

## Generate an app

To generate an app we just type

```
nest new hello-world
cd hello-world
```



Turns Nest.js app into Azure Function app

```
nest add @nestjs/azure-func-http
```

This should give you an output like the following:

```
✔ Installation in progress... ☕
CREATE /.funcignore (66 bytes)
CREATE /host.json (23 bytes)
CREATE /local.settings.json (116 bytes)
CREATE /proxies.json (72 bytes)
CREATE /main/function.json (294 bytes)
CREATE /main/index.ts (287 bytes)
CREATE /main/sample.dat (23 bytes)
CREATE /src/main.azure.ts (321 bytes)
UPDATE /package.json (1827 bytes)
```

Your project has now turned into a Azure functions app



Ensure you have the following installed:

- Azure Core Tools, <https://github.com/Azure/azure-functions-core-tools#installing>
- Azure Functions extension for VS Code, <vscode:extension/ms-azuretools.vscode-azurefunctions>

Now in VS Code locate the Azure tool icon to the left, and sign in to Azure

![](https://code.visualstudio.com/assets/tutorials/functions-extension/sign-in.png?WT.mc_id=academic-0000-chnoring)

 Next click the blue arrow icon to deploy

![](https://code.visualstudio.com/assets/tutorials/functions-extension/function-app-publish-project.png?WT.mc_id=academic-0000-chnoring)

From here follow the prompts. Choose the directory that you currently have open, select your Azure subscription, and then choose **Create New Function App**.

1. Type a globally unique name for your Function App and press Enter. Valid characters for a function app name are 'a-z', '0-9', and '-'.
2. Choose **Create New Resource Group**, type a Resource Group name, like 'myResourceGroup' and press Enter.
3. Choose a location in a [region](https://azure.microsoft.com/regions/?WT.mc_id=academic-0000-chnoring) near you or near other services you may need to access.
4. Choose **Create New Storage Account**, type a globally unique name of the new storage account used by your function app and press Enter. Storage account names must be between 3 and 24 characters in length and may contain numbers and lowercase letters only.



It should look something like this when it's done deploying

![](https://code.visualstudio.com/assets/tutorials/functions-extension/function-create-output.png?WT.mc_id=academic-0000-chnoring)

# Deploy an Angular app

Scaffold an app

```
ng new MyApp
cd Myapp
```

`MyApp` can be whatever name you choose

Upgrade to Angular 8+ if needed

```
ng update @angular/cli @angular/core
```



## Ng-deploy

There are two steps here

1. **Generate** config file
2. **Deploy** to Azure



### Generate config file

Pre step, run the following command

```
ng add @azure/ng-deploy
```

This will install `@azure/ng-deploy` from NPM

1. it will prompt you to log in (unless you are already logged in to Azure via the terminal)
2. t will bring up a dialog where you are asked to *select* a subscription (if you have more than one).

Then it will create the needed resources at Azure and ends with creating an `azure.json` file that contains all the needed config



### Deploy to Azure

Just type the following command:

```
ng deploy
```

This will do the following:

1. **Compile** the Angular project if `dist` folder is empty
2. **Upload** files to Azure using the config found in `azure.json`

The step will finish with the *public URL* being displayed




