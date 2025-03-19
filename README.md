<p align="center">
  <img src="https://github.com/user-attachments/assets/51e3a0a3-f9e2-4a33-b139-6291970581bb" width="150" height="auto">
  <h1 align="center">Securing Cloud Workloads with Microsoft Defender for Cloud</h1>
</p>

#### *In this tutorial, we will:*
*•	Assess and enhance your cloud security posture.*

*•	Configure compliance policies and workload protections to secure cloud environments.*

*•	Analyze and mitigate security threats effectively.*

#### Tasks:
 1. Activating Microsoft Defender for Cloud.
 2. Exploring the Microsoft Defender for Cloud Dashboard.
 3. Onboarding On-Premises Servers to Azure with Azure Arc.
 4. Improving Security Posture with Microsoft Defender Recommendations.
 5. Analyzing and Mitigating Threats Using Security Alerts.

## Task 1: Activating Microsoft Defender for Cloud

In this task, you'll enable and configure Microsoft Defender for Cloud.

1.	In the Search bar of the Microsoft Azure portal, type Defender, then select Microsoft Defender for Cloud.
2.	In the left navigation menu for Microsoft Defender for Cloud, expand the Management section , and select Environment settings.

<p align="center">
<img src="https://github.com/user-attachments/assets/64a24665-e201-49d5-ba66-aa9207ed051d">
</p>

3.	Select the "Expand all" button to view all subscriptions and resources, then select your Azure subscription.
4.	In the Cloud Security Posture Management (CSPM) section, select "On" for the Defender CSPM.
5.	In the Cloud Workload Protection (CWP) section, select "On" for the Servers Plan 2. Select the "Save" button at the top of the page.

<p align="center">
<img src="https://github.com/user-attachments/assets/e584b600-c496-404b-a5a6-0cd5a6f07ae5">
</p>

<p align="center">
<img src="https://github.com/user-attachments/assets/bce814f2-1a45-4677-994e-97a725464b28">
</p>

## Task 2: Exploring the Microsoft Defender for Cloud Dashboard.

This task explores the Microsoft Defender for Cloud dashboard, reviewing security posture, compliance, and recommendations. It covers navigating subscriptions, checking Secure Score, and accessing recent updates.

1.	In the Search bar of the Microsoft Azure portal, type Defender, then select "Microsoft Defender for Cloud".
2.	In the left navigation menu for Microsoft Defender for Cloud, under the General section, select "Overview".
3.	The Overview blade offers a unified security view with dedicated dashboards for posture, compliance, protections, inventory, and information security.

<p align="center">
<img src="https://github.com/user-attachments/assets/5dab813f-65ee-4f51-9b7c-a2e60e74d09a">
</p>

4.	Back to the Azure portal tab, from the top menu bar, select "Subscriptions". Return to the Overview page, and review the Security posture tile. You can see your current Secure score along with the number of completed controls and recommendations. The Secure Score and other information on the Security posture tile can take up to 24 hours to calculate.

<p align="center">
<img src="https://github.com/user-attachments/assets/d326527c-15ab-4e96-9438-051ec8958bfb">
</p>

5.  On the Regulatory compliance tile, you can get insights into your compliance posture based on continuous assessment of both Azure and hybrid cloud environments. This tile shows the following standards which are Microsoft Cloud Security benchmark, and Lowest compliance standard. To view the data we first need to add Security policies. Selecting this tile will redirect you to the Regulatory compliance page, where you can add additional standards or explore the current ones.

## Task 3: Onboarding On-Premises Servers to Azure with Azure Arc.

In this task, you install Azure Arc on an on-premises server to make onboarding easier.

1.	In the Search bar of the Azure portal, type Arc, then select "Azure Arc". In the navigation pane under Azure Arc resources select "Machines". Select "+ Add/Create", then select "Add a machine".

<p align="center">
<img src="https://github.com/user-attachments/assets/c267e4e9-87c3-40c3-831a-e92fcc5fafbd">
</p>

2.	Select "Generate script" from the "Add a single server" section.
3.	In the Add a server with Azure Arc page, select the Resource group you created earlier under Project details. Hint: RG-Defender. If you haven't already created a resource group, open another tab and create the resource group and start over.
4.	For Region, select (US) East Us from the drop-down list.

<p align="center">
<img src="https://github.com/user-attachments/assets/c8ef978d-824a-456c-b151-578174ee5200">
</p>

5.  Scroll down and select the "Download and run script" button. Save the file in Downloads folder.

<p align="center">
<img src="https://github.com/user-attachments/assets/9f46b5fc-deeb-4085-8e55-53a368548ac0">
</p>

6.  Go to Windows PowerShell (Admin) and enter: cd C:\Users\Administrator\Downloads.
7.  Type "Set-ExecutionPolicy -ExecutionPolicy Unrestricted" (allowing all scripts to run without restriction) and press enter. Enter "A" for "Yes to All" and press enter.
8.  Type ".\OnboardingScript.ps1" (this installs the Azure Arc agent, authenticates the machine, and connects it to the specified resource group and region) and press enter. Enter "R" to "Run once" and press enter (this may take a couple minutes).
9.  The setup process opens a new Microsoft Edge browser tab to authenticate the Azure Arc agent. Select or signin with your azure account, wait for the message Authentication completed and then go back to the Windows PowerShell window.

<p align="center">
<img src="https://github.com/user-attachments/assets/18dc16b5-59e4-4758-88b2-8bea9fb242d1">
</p>

<p align="center">
<img src="https://github.com/user-attachments/assets/9fc44689-5204-4555-a2f3-bb94165a53f2">
</p>

10.  Go back to the Azure Arc Machines page and select "Refresh" until WINServer server name appears and the Status is Connected. This could take a couple of minutes.

<p align="center">
<img src="https://github.com/user-attachments/assets/e443de54-43c7-4a21-a5f1-6f4d522adf6f">
</p>

## Task 4: Improving Security Posture with Microsoft Defender Recommendations.

In this task, you'll review cloud security posture management recommendations.

1.  In the General section, select "Recommendations" from the navigation menu.
2.	Select "Add filter" and then select "Resource type".
3.	Select the "Machines - Azure Arc" checkbox and then select the "Apply" button.

<p align="center">
<img src="https://github.com/user-attachments/assets/c6500b6f-5de0-4311-b084-2a144490e92b">
</p>

4.	In this case we'll select the recommendation that states "Machines should have a vulnerability assessment solution" where the status isn't Completed. You may need to scroll to the right to see the Status column.
5.	Review the recommendation and in the "Take action" tab scroll down to Delegate and select "Assign owner & set due date".

<p align="center">
<img src="https://github.com/user-attachments/assets/9699612a-4506-40e3-b2e1-0112b94179e0">
</p>

6.	In the Create assignment window, leave Type set to Defender for Cloud and expand the Assignment details.
7.	In the Email address box, type in your email.
8.	Explore the Set remediation timeframe and Set email notifications options and select "Create".

<p align="center">
<img src="https://github.com/user-attachments/assets/80d815b1-c5e7-489c-bdea-1aa5d6a39b93">
</p>

9.	Close the recommendation page by selecting the 'X' on the upper right of the window.

## Task 5: Analyzing and Mitigating Threats Using Security Alerts.

In this task, you'll load sample security alerts and review the alert details.

1.	Under General, select "Security alerts" in the portal menu.

<p align="center">
<img src="https://github.com/user-attachments/assets/cf1e2440-aafc-41a7-895c-943410e63ffc">
</p>

2.	Select Sample alerts from the command bar. Hint: you may need to select the ellipsis (...) button from the command bar.
3.	In the Create sample alerts (Preview) pane make sure your subscription is selected and that all sample alerts are selected in the Defender for Cloud plans area.
4.	Select Create sample alerts. This sample alert creation process may take a few minutes to complete, wait for the "Successfully created sample alerts" notification.

<p align="center">
<img src="https://github.com/user-attachments/assets/7b8529d7-60e8-4f2d-8eb1-184ea6fec31f">
</p>

5.	Once completed, select Refresh (if needed) to see the alerts appear under the Security alerts area.
6.	Choose an interesting alert with a Severity of High and perform the following actions:
•	Select the alert checkbox and the alert detail pane should appear. Select "View full details".
•	Review and read the Alert details tab.
•	Select the "Take action" tab or scroll down and select the "Next: Take Action" button at the end of the page.
•	Review the Take action information. Notice the sections available to take action depending on the type of alert: Inspect resource context, Mitigate the threat, Prevent future attacks, Trigger automated response and Suppress similar alerts.

<p align="center">
<img src="https://github.com/user-attachments/assets/27a3012a-4af7-4ab3-8f33-27f1851613b6">
</p>

<p align="center">
<img src="https://github.com/user-attachments/assets/cd11db36-7f14-4cad-9445-54bf5249fa21">
</p>
