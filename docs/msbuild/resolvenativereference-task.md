---
title: "ResolveNativeReference Task | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.technology: msbuild
ms.topic: "conceptual"
f1_keywords: 
  - "http://schemas.microsoft.com/developer/msbuild/2003#ResolveNativeReference"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "MSBuild, ResolveNativeReference task"
  - "ResolveNativeReference task [MSBuild]"
ms.assetid: 56acd101-de77-4eec-92c6-f5c6d2187579
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload: 
  - "multiple"
---
# ResolveNativeReference Task
Resolves native references. Implements the <xref:Microsoft.Build.Tasks.ResolveNativeReference> class. This class supports the .NET Framework infrastructure which is not intended to be used directly from your code.  
  
## Task Parameters  
 The following table describes the parameters of the `ResolveNativeReference` task.  
  
|Parameter|Description|  
|---------------|-----------------|  
|`AdditionalSearchPaths`|Required <xref:System.String?displayProperty=fullName>`[]` parameter.<br /><br /> Gets or sets the search paths for resolving assembly identities of native references.|  
|`ContainedComComponents`|Optional <xref:Microsoft.Build.Framework.ITaskItem>`[]` output parameter.<br /><br /> Gets or sets the COM components of the native assembly.|  
|`ContainedLooseEtcFiles`|Optional <xref:Microsoft.Build.Framework.ITaskItem>`[]` output parameter.<br /><br /> Gets or sets the loose Etc files listed in the native manifest.|  
|`ContainedLooseTlbFiles`|Optional <xref:Microsoft.Build.Framework.ITaskItem>`[]` output parameter.<br /><br /> Gets or sets the loose .tlb files of the native assembly.|  
|`ContainedPrerequisiteAssemblies`|Optional <xref:Microsoft.Build.Framework.ITaskItem>`[]` output parameter.<br /><br /> Gets or sets the assemblies that must be present before the manifest can be used.|  
|`ContainedTypeLibraries`|Optional <xref:Microsoft.Build.Framework.ITaskItem>`[]` output parameter.<br /><br /> Gets or sets the type libraries of the native assembly.|  
|`ContainingReferenceFiles`|Optional <xref:Microsoft.Build.Framework.ITaskItem>`[]` output parameter.<br /><br /> Gets or sets the reference files.|  
|`NativeReferences`|Required <xref:Microsoft.Build.Framework.ITaskItem>`[]` parameter.<br /><br /> Gets or sets the Win32 native assembly references.|  
  
## Remarks  
 In addition to the parameters listed above, this task inherits parameters from the <xref:Microsoft.Build.Tasks.TaskExtension> class, which itself inherits from the <xref:Microsoft.Build.Utilities.Task> class. For a list of these additional parameters and their descriptions, see [TaskExtension Base Class](../msbuild/taskextension-base-class.md).  
  
## See Also  
 [Tasks](../msbuild/msbuild-tasks.md)   
 [Task Reference](../msbuild/msbuild-task-reference.md)