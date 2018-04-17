---
title: "Bind a Test Controller or Test Agent to a Network Adapter in Visual Studio | Microsoft Docs"
ms.date: "10/19/2016"
ms.topic: "conceptual"
helpviewer_keywords:
  - "controllers, netwrok adapter"
  - "agents, configuring"
  - "agents, network adapter"
  - "controllers, configuring"
ms.assetid: 7eb9290a-f9f6-4e41-9caa-796fcfaf0610
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-ide-test
---
# How to: Bind a test controller or test agent to a network adapter

If a computer that has the test controller or the test agent software installed has multiple network adapters, then you must specify the IP address instead of the name of the computer to identify that test controller or test agent.

> [!WARNING]
> When you try to set up a test agent, you might receive the following error:
>
> **Error 8110. Can not connect to the specified controller computer or access the controller object**
>
> This error can be caused by installing the test controller on a computer that has more than one network adapter. It is also possible to install agents successfully, and not see this problem until you try to run a test.

## Binding a Test Controller to a Specific Network Adapter

### To obtain the IP addresses of the network adapters

1.  From Microsoft Windows, choose **Start**, choose in the **Start Search** box, type **cmd**, and then choose **Enter**.

2.  Type **ipconfig /all**.

     The IP addresses for your network adapters are displayed. Record the IP address of the network adapter that you want to bind your controller to.

### To Bind a Network Adapter to a Test Controller

1.  From Microsoft Windows, choose **Start**, choose in the **Start Search** box, type **services.msc**, and then choose **Enter**.

     The **Services** dialog box is displayed.

2.  In the results pane, under the **Name** column, right-click the **Visual Studio Test Controller** service and then choose **Stop**.

     -or-

     Open an elevated command prompt and run the following command at a command:

     `net stop vsttcontroller`

3.  Open the *QTCcontroller.exe.config* XML configuration file located in *%ProgramFiles(x86)%\Microsoft Visual Studio\2017\\<edition>\Common7\IDE*.

4.  locate `<appSettings>` tag.

    ```xml
    <appSettings>
      <add key="LogSizeLimitInMegs" value="20"/>
      <add key="AgentConnectionTimeoutInSeconds" value="120"/>
      <add key="AgentSyncTimeoutInSeconds" value="300"/>
      <add key="ControllerServicePort" value="6901"/>
      <add key="ControllerUsersGroup" value="TeamTestControllerUsers"/>
      <add key="ControllerAdminsGroup" value="TeamTestControllerAdmins"/>
      <add key="CreateTraceListener" value="no"/>
    </appSettings>
    ```

5.  Add the `BindTo` key to specify which network adapter to use in the `<appSettings>` section.

    ```xml
            <add key="BindTo" value="<YOUR IP ADDRESS>"/>
    </appSettings>
    ```

6.  Start the test controller service. To do this, run the following command at a command prompt:

    `net start vsttcontroller`

    > [!WARNING]
    > You must run the test agent installation again to connect the test agent to the controller. This time, specify the IP address for the controller instead of the controller name.

     This applies to the controller, the agent service, and the agent process. The `BindTo` property must be set for each process that is running on a computer that has more than one network adapter. The procedure to set the `BindTo` property is the same for all three processes, as specified earlier in this topic for the test controller.

### To Bind a Network Interface Card to a Test Agent

1.  From Microsoft Windows, choose **Start**, choose in the **Start Search** box, type **services.msc**, and then choose **Enter**.

    The **Services** dialog box is displayed.

2.  In the results pane, under the **Name** column, right-click the **Visual Studio Test Agent** service and then choose **Stop**.

     -or-

     Open an elevated command prompt and run the following command at a command:

     **net stop vsttagent**

3.  Open the *QTAgentService.exe.config* XML configuration file located in *%ProgramFiles(x86)%\Microsoft Visual Studio\2017\\<edition>\Common7\IDE*.

4.  locate `<appSettings>` tag.

    ```xml
    <appSettings>
      <appSettings>
      <add key="LogSizeLimitInMegs" value="20"/>
      <add key="AgentServicePort" value="6910"/>
      <add key="ControllerConnectionPeriodInSeconds" value="30"/>
      <add key="StopTestRunCallTimeoutInSeconds" value="120"/>
      <add key="CreateTraceListener" value="no"/>
      <add key="GetCollectorDataTimeout" value="300"/>
    </appSettings>  </appSettings>
    ```

5.  Add the `BindTo` key to specify which network adapter to use in the `<appSettings>` section.

    ```xml
            <add key="BindTo" value="<YOUR IP ADDRESS>"/>
    </appSettings>
    ```

6.  Start the test agent service. To do this, run the following command at a command prompt:

    `net start vsttagent`

## See also

- [Install and configure test agents](../test/lab-management/install-configure-test-agents.md)
- [Modifying Load Test Logging Settings](../test/modify-load-test-logging-settings.md)
- [Configuring Ports for Test Controllers and Test Agents](../test/configure-ports-for-test-controllers-and-test-agents.md)
- [How to: Specify the Maximum Size for the Log File](../test/how-to-specify-the-maximum-size-for-the-log-file.md)
- [How to: Specify Timeout Periods for Test Controllers and Test Agents](../test/how-to-specify-timeout-periods-for-test-controllers-and-test-agents.md)