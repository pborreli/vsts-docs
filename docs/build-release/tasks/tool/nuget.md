---
title: NuGet Tool Installer | VSTS or Team Foundation Server
description: Learn how to use the NuGet Tool Installer for VSTS and TFS to find, download, and cache the specified version of NuGet.
ms.prod: devops
ms.technology: devops-cicd
ms.assetid: 740DA69C-E173-46AD-BA6F-0F138285AC39
ms.manager: douge
ms.author: amullans
ms.date: 7/05/2017
monikerRange: 'vsts'
---

# Tool: NuGet Tool Installer

**VSTS**

**Build**

![icon](_img/nuget.png) Finds or downloads and caches the specified version of [NuGet](https://nuget.org/) and adds it to the PATH

## Demands

None

::: moniker range="vsts"

[!INCLUDE [temp](../_shared/yaml/NuGetToolInstallerV0.0.md)]

::: moniker-end

## Arguments

| Argument | Description |
|----------|-------------|
| Version Spec | Specify which [NuGet version](https://dist.nuget.org/tools.json) you want to use. Examples: `4.1.0`, `3.x`, `>2.x`, `>=3.5` |
| Check for Latest Version | Select if you want the agent to check for the latest available version that satisfies the version spec. For example, you select this option because you run this build on your [private agent](../../concepts/agents/agents.md#install) and you want to always use the latest `3.x` version. <div class="tip"><h5>TIP</h5><p>If you're using [our hosted agents](../../concepts/agents/hosted.md), you should leave this check box cleared. We update the hosted agents on a regular basis, but they're often slightly behind the latest version. So selecting this box will result in your build spending a lot of time updating to a newer minor version.</p></div>|
| Control options | See [Control options](../../concepts/process/tasks.md#controloptions). |

## Q&A
<!-- BEGINSECTION class="md-qanda" -->

### Where can I learn more about tool installers?

For an explanation of tool installers and examples, see [Tool installers](../../concepts/process/tasks.md#tool-installers).

[!INCLUDE [temp](../../_shared/qa-agents.md)]

<!-- ENDSECTION -->
