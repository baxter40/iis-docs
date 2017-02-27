---
title: "Using Configuration Editor: Generate Scripts | Microsoft Docs"
author: rick-anderson
description: "This walkthrough is aimed to demonstrate how to use Configuration Editor's Generate Script functionality through the example of Application Pool generation...."
ms.author: aspnetcontent
manager: wpickett
ms.date: 03/20/2008
ms.topic: article
ms.assetid: 
ms.technology: dotnet-webforms
ms.prod: .net-framework
msc.legacyurl: /learn/manage/managing-your-configuration-settings/using-configuration-editor-generate-scripts
msc.type: authoredcontent
---
Using Configuration Editor: Generate Scripts
====================
by Crystal Hoyer

## Walkthrough Goal

This walkthrough is aimed to demonstrate how to use Configuration Editor's Generate Script functionality through the example of Application Pool generation.

## Prerequisites

This walkthrough requires the following prerequisites:

- [Administration Pack V1 for IIS](https://www.iis.net/downloads/microsoft/administration-pack "Install Administration Pack")

## Part 1 – Create an application pool using the configuration editor

1. Launch the Configuration Editor in the IIS Manager by double clicking the "Configuration Editor" feature from a server connection.
2. Under the *Section:* dropdown menu click on system.applicationHost -&gt; applicationPools
3. In the property grid displayed below, click on the ellipse "…" on the first row, which corresponds to the *(Collection)* item.
4. In the *Collection Editor*, you will see a list of the application pools that already exists.
5. On the action pane, click *"Add"*
6. Fill in the property grid displayed in the *Properties* section. 

    1. Notice the *"name"* property has a key in symbol. This indicates a required field. Enter "applicationPool1" as your name to create a new application pool.
    2. Select processModel to expand.
    3. Set userName to "PoolId1"
    4. Set password to "PoolId1Pwd"
    5. Change identityType to "SpecificUser"
    6. You can optionally change other settings here
7. [optional] To commit the changes to the configuration system, click *Apply*on the *Actions* pane. However, for the purpose of our walkthrough, please do not do so.

## Part 2 – Generate script

After closing the properties dialog, click on the *Generate Script* link on the *Actions* pane. The 3 tabs of the Script Dialog displays 3 types of scripts to accomplish the actions we did on this section.

### Managed Code: C# code snippet to create ‘applicationPool1'

[!code-csharp[Main](using-configuration-editor-generate-scripts/samples/sample1.cs)]

### Scripting: Jscript code to create ‘applicationPool1'

### 

[!code-csharp[Main](using-configuration-editor-generate-scripts/samples/sample2.cs)]

### Command Line: Appcmd commands to create ‘applicationPool1' and specify an identiy.

[!code-console[Main](using-configuration-editor-generate-scripts/samples/sample3.cmd)]

## Part 3 – Create a C# program that creates 10 application pools

Based on the code generated by the Configuration Editor, we will refactor the code to create one application pool to the method "CreateApplicationPool". The final code looks like this:

[!code-csharp[Main](using-configuration-editor-generate-scripts/samples/sample4.cs)]

## Summary

You have now created code to create 10 application pools with aid from the Configuration Editor.
  
  
[Discuss in IIS Forums](https://forums.iis.net/1149.aspx)