---
title: IIS Web App Deploy
description: Deploy a Website or Web Application using WebDeploy
ms.topic: reference
ms.prod: devops
ms.technology: devops-cicd
ms.assetid: 1B467810-6725-4B6D-ACCD-886174C09BBA
ms.manager: dastahel
ms.author: dastahel
ms.date: 05/04/2018
monikerRange: 'vsts'
---

# Deploy: IIS Web App Deploy

![](_img/iiswebappdeploymentonmachinegroup.png) Deploy a Website or Web Application using WebDeploy

::: moniker range="vsts"

[!INCLUDE [temp](../_shared/yaml/IISWebAppDeploymentOnMachineGroup.0.md)]

::: moniker-end

## Arguments

<table><thead><tr><th>Argument</th><th>Description</th></tr></thead>
<tr><td>Website Name</td><td>(Required) Provide the name of an existing website on the machine group machines</td></tr>
<tr><td>Virtual Application</td><td>(Optional) Specify the name of an already existing Virtual Application on the target Machines</td></tr>
<tr><td>Package or Folder</td><td>(Required) File path to the package or a folder generated by MSBuild or a compressed archive file.<br />Variables ( [Build](https://www.visualstudio.com/docs/build/define/variables) | [Release](https://www.visualstudio.com/docs/release/author-release-definition/understanding-tasks#predefvariables)), wild cards are supported. <br/> For example, $(System.DefaultWorkingDirectory)\\\*\*\\\*.zip.</td></tr>
<tr><td>SetParameters File</td><td>(Optional) Optional: location of the SetParameters.xml file to use.</td></tr>
<tr><td>Remove Additional Files at Destination</td><td>(Optional) Select the option to delete files on the Web App that have no matching files in the Web App zip package.</td></tr>
<tr><td>Exclude Files from the App_Data Folder</td><td>(Optional) Select the option to prevent files in the App_Data folder from being deployed to the Web App.</td></tr>
<tr><td>Take App Offline</td><td>(Optional) Select the option to take the Web App offline by placing an app_offline.htm file in the root directory of the Web App before the sync operation begins. The file will be removed after the sync operation completes successfully.</td></tr>
<tr><td>Additional Arguments</td><td>(Optional) Additional Web Deploy arguments that will be applied when deploying the Azure Web App like,-disableLink:AppPoolExtension -disableLink:ContentExtension.</td></tr>
<tr><td>XML transformation</td><td>(Optional) The config transforms will be run for `*.Release.config` and `*.<EnvironmentName>.config` on the `*.config file`.<br/> Config transforms will be run prior to the Variable Substitution.<br/>XML transformations are supported only for Windows platform.</td></tr>
<tr><td>XML variable substitution</td><td>(Optional) Variables defined in the Build or Release Definition will be matched against the 'key' or 'name' entries in the appSettings, applicationSettings, and connectionStrings sections of any config file and parameters.xml. Variable Substitution is run after config transforms. <br/><br/> Note: If same variables are defined in the Release Definition and in the Environment, then the Environment variables will supersede the Release Definition variables.<br/></td></tr>
<tr><td>JSON variable substitution</td><td>(Optional) Provide new line separated list of JSON files to substitute the variable values. Files names are to be provided relative to the root folder. <br/> To substitute JSON variables that are nested or hierarchical, specify them using JSONPath expressions. <br/> <br/> For example, to replace the value of ‘ConnectionString’ in the sample below, you need to define a variable as ‘Data.DefaultConnection.ConnectionString’ in the build/release definition (or release definition’s environment). <br/> {<br/>&nbsp;&nbsp;"Data": {<br/>&nbsp;&nbsp;&nbsp;&nbsp;"DefaultConnection": {<br/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"ConnectionString": "Server=(localdb)\SQLEXPRESS;Database=MyDB;Trusted_Connection=True"<br/>&nbsp;&nbsp;&nbsp;&nbsp;}<br/>&nbsp;&nbsp;}<br/> }<br/> Variable Substitution is run after configuration transforms. <br/><br/> Note: Build/Release’s system definition variables are excluded in substitution</td></tr>
[!INCLUDE [temp](../_shared/control-options-arguments.md)]
</table>

## Q&A

<!-- BEGINSECTION class="md-qanda" -->

<!-- ENDSECTION -->
