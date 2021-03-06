---
title: "How to: Set Breakpoints in Workflows (Legacy) | Microsoft Docs"
ms.date: "11/04/2016"
ms.topic: "reference"
helpviewer_keywords: 
  - "breakpoints, setting in workflows"
  - "debugging, setting breakpoints in workflows"
  - "debugging workflows, setting breakpoints"
  - "workflows, setting breakpoints"
ms.assetid: 78e0be39-3e99-487c-bfef-19db0daf6f42
author: gewarren
ms.author: gewarren
manager: douge
ms.workload: 
  - "multiple"
---
# How to: Set Breakpoints in Workflows (Legacy)
This topic describes how to set breakpoints in [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] applications build using the legacy Windows Workflow Designer. Use the legacy [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] when your [!INCLUDE[wf2](../workflow-designer/includes/wf2_md.md)] application needs to target either the [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] or the [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)].

 When you use the legacy [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] in [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] to build a [!INCLUDE[wf2](../workflow-designer/includes/wf2_md.md)] application, you can set breakpoints in C# and Visual Basic code as you do in Visual Studio. As expected, workflow execution stops at each breakpoint that you set.

 A breakpoint has three states: *Pending*, *Bound*, and *Error*. When you set a breakpoint, it is Pending, and it is represented by a hollow red icon. When the runtime has loaded the workflow type, it becomes Bound and is represented by a solid red icon. If you specify an incorrect format for the breakpoint, as with an activity name that is not valid, an error window appears. The breakpoint is still added to the breakpoint window, but it is marked with a small "x".

 You can set breakpoints on an activity on the workflow design surface in the following ways:

-   Right-click the activity and select **Breakpoint \ Insert Breakpoint**.

-   Select the activity and press F9.

-   Select **New Breakpoint** from the **Debug** menu.

     You can also use this option to set a new breakpoint while debugging, when the debugger stops at a breakpoint.

    > [!NOTE]
    > Setting breakpoints on invoked workflows is not supported.

### To set a breakpoint using the New Breakpoint option on the Debug menu

1.  On the **Debug** menu, select **New Breakpoint**.

2.  Click **Break at Function**.

     The **New Breakpoint** dialog box opens.

3.  Specify the name of an activity in the **Function** text box using this syntax: `QualifiedActivityId[:[FullClassName][:InstanceId]]`.

    > [!NOTE]
    > Optionally, instead of using the activity name in the **Function** text box, you can set a breakpoint by specifying the absolute path of the workflow activity. For example, suppose you have a workflow solution named **WorkflowConsoleApplication1** and a workflow in the solution named **Workflow1** that uses an activity called **Delay1**. You can use the activity name **Delay1** or specify the path as **Delay1:WorkflowConsoleApplication1.Workflow1** or **Delay1:WorkflowConsoleApplication1.Workflow1:{6614886A-608E-412B-BF98-99FF1559DDDF}**.

4.  Select the **Use IntelliSense** check box to verify the function name.

     If this check box is not selected, no breakpoint name verification is performed.

5.  Select **Workflow** from the **Language** list.

6.  Click **OK**.

## See also

- [Debugging Legacy Workflows](../workflow-designer/debugging-legacy-workflows.md)
- [Invoking the Visual Studio Debugger for Windows Workflow Foundation (Legacy)](../workflow-designer/invoking-the-visual-studio-debugger-for-windows-workflow-foundation-legacy.md)