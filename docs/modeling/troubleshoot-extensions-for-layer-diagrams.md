---
title: "Troubleshoot extensions for dependency diagrams | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.topic: "conceptual"
helpviewer_keywords: 
  - "dependency diagrams, extension errors"
  - "dependency diagrams, troubleshooting extensions"
author: gewarren
ms.author: gewarren
manager: douge
ms.workload: 
  - "multiple"
ms.technology: vs-ide-modeling
---
# Troubleshoot extensions for dependency diagrams
This topic addresses some problems that you might encounter when you create layer model extensions.  
  
#### When I press F5 to debug my extension, my commands, gesture handlers, validation extensions, or custom properties do not appear on dependency diagrams in the Experimental instance of [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]  
  
1.  Open your extension solution in the Experimental instance of [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], and on the **Build** menu, click **Rebuild Solution**.  
  
2.  Press **F5** or **CTRL+F5** to start the experimental instance of [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Open a dependency diagram and test your extension.  
  
 Continue with the next procedure if necessary.  
  
#### An old version of my extension runs.  
  
1.  Make sure that no experimental instance of [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] is running.  
  
2.  Delete the following folder:  %LocalAppData%\Microsoft\VisualStudio\\[version]\ComponentModelCache  
  
    > [!NOTE]
    >  %LocalAppData% is typically *DriveName*:\Users\\*UserName*\AppData\Local.  
  
 Continue with the next procedure if necessary.  
  
#### An old version of my validation results appears, or my validation method is not called.  
  
1.  In the experimental instance of [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], on the **Build** menu, click **Clean Solution**. This clears the cached results of the previous validation analysis.  
  
2.  Make sure that the layers in your model are associated with code elements, and that there is at least one dependency link in the model. Validation is not invoked if there is nothing to validate.  
  
3.  Regular breakpoints might not work in a validation method, because it runs in a separate process. You must insert a call to `System.Diagnostics.Debugger.Launch()` if you want to step through your method.  
  
4.  In **source.extension.vsixmanifest** in your layer validation project, make sure that you have added both a **MEF Component** item and a **Custom Extension Type** item under **Content**.  
  
## See Also  
 [Extend dependency diagrams](../modeling/extend-layer-diagrams.md)
