---
title: "Mobility Warnings | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.technology: 
  - "vs-ide-code-analysis"
ms.topic: "conceptual"
f1_keywords: 
  - "vs.codeanalysis.MobilityRules"
helpviewer_keywords: 
  - "managed code analysis warnings, mobility warnings"
  - "mobility warnings"
  - "warnings, mobility"
ms.assetid: 9808054c-593b-4fc3-92cc-1fc45f41569c
author: "gewarren"
ms.author: "gewarren"
manager: douge
ms.workload: 
  - "multiple"
---
# Mobility Warnings
Mobility warnings support efficient power usage.  
  
## In This Section  
  
|Rule|Description|  
|----------|-----------------|  
|[CA1600: Do not use idle process priority](../code-quality/ca1600-do-not-use-idle-process-priority.md)|Do not set process priority to Idle. Processes that have System.Diagnostics.ProcessPriorityClass.Idle will occupy the CPU when it would otherwise be idle, and will therefore block standby.|  
|[CA1601: Do not use timers that prevent power state changes](../code-quality/ca1601-do-not-use-timers-that-prevent-power-state-changes.md)|Higher-frequency periodic activity will keep the CPU busy and interfere with power-saving idle timers that turn off the display and hard disks.|