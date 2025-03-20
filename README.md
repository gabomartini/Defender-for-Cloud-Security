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

Enable and configure Microsoft Defender for Cloud to secure your Azure environment.

1.	In the Search bar of the Microsoft Azure portal, type "Defender" and select "Microsoft Defender for Cloud".
2.	In the left navigation menu, expand the "Management" section and select "Environment settings".

<p align="center">
<img src="https://github.com/user-attachments/assets/64a24665-e201-49d5-ba66-aa9207ed051d">
</p>

3.	Click the "Expand all" button to view all subscriptions and resources, then select your Azure subscription.
4.	In the Cloud Security Posture Management (CSPM) section, turn "On" the Defender CSPM option. (CSPM helps assess and improve your cloud security posture.)
5.	In the Cloud Workload Protection (CWP) section, turn "On" the Server Plan 2 option. (CWP provides advanced threat protection for workloads like servers.)
6.	Click the "Save" button at the top of the page.

<p align="center">
<img src="https://github.com/user-attachments/assets/e584b600-c496-404b-a5a6-0cd5a6f07ae5">
</p>

<p align="center">
<img src="https://github.com/user-attachments/assets/bce814f2-1a45-4677-994e-97a725464b28">
</p>

## Task 2: Exploring the Microsoft Defender for Cloud Dashboard.

Explore the Microsoft Defender for Cloud dashboard to review your security posture, compliance, and recommendations. This task covers navigating subscriptions, checking your Secure Score, and accessing recent updates.

1.	In the Search bar of the Microsoft Azure portal, type "Defender" and select "Microsoft Defender for Cloud".
2.	In the left navigation menu, under the "General" section, select "Overview".
3.	Review the Overview blade, which provides a unified security view with dashboards for posture, compliance, protections, inventory, and information security.

<p align="center">
<img src="https://github.com/user-attachments/assets/5dab813f-65ee-4f51-9b7c-a2e60e74d09a">
</p>

4.	From the top menu bar in the Azure portal, select "Subscriptions". Return to the Overview page and review the "Security posture" tile. This displays your current Secure Score (a metric reflecting your security status), along with the number of completed controls and recommendations. Note: This data may take up to 24 hours to calculate.

<p align="center">
<img src="https://github.com/user-attachments/assets/d326527c-15ab-4e96-9438-051ec8958bfb">
</p>

5.	On the "Regulatory compliance" tile, view insights into your compliance posture based on continuous assessments of Azure and hybrid cloud environments. This tile displays standards such as the Microsoft Cloud Security Benchmark. To view data, add security policies by selecting the tile and following the prompts on the Regulatory compliance page.

## Task 3: Onboarding On-Premises Servers to Azure with Azure Arc.

Install Azure Arc (a service that extends Azure management to on-premises servers) on an on-premises server to simplify onboarding to Microsoft Defender for Cloud.

1.	In the Search bar of the Azure portal, type "Arc" and select "Azure Arc".
2.	In the navigation pane under "Azure Arc resources", select "Machines".
3.	Click "+ Add/Create", then select "Add a machine".

<p align="center">
<img src="https://github.com/user-attachments/assets/c267e4e9-87c3-40c3-831a-e92fcc5fafbd">
</p>

4.	In the "Add a single server" section, click "Generate script".
5.	On the "Add a server with Azure Arc" page, under "Project details", select the resource group you created earlier (e.g., "RG-Defender"). If you haven’t created a resource group, open another tab, create one, and return to this step.
6.	For "Region", select "(US) East US" from the drop-down list.

<p align="center">
<img src="https://github.com/user-attachments/assets/c8ef978d-824a-456c-b151-578174ee5200">
</p>

7.	Scroll down and click the "Download and run script" button. Save the file to the Downloads folder.

<p align="center">
<img src="https://github.com/user-attachments/assets/9f46b5fc-deeb-4085-8e55-53a368548ac0">
</p>

8.	Open Windows PowerShell as Administrator and enter: cd C:\Users\Administrator\Downloads.
9.	Type Set-ExecutionPolicy -ExecutionPolicy Unrestricted, press Enter, then type "A" for "Yes to All" and press Enter. (This allows scripts to run without restrictions.)
10.	Type .\OnboardingScript.ps1, then press Enter. (This installs the Azure Arc agent, authenticates the machine, and connects it to the specified resource group and region.) Type "R" for "Run once" and press Enter. (This may take a few minutes.)
11.	When a Microsoft Edge browser tab opens to authenticate the Azure Arc agent, select or sign in with your Azure account. Wait for the "Authentication completed" message, then return to the PowerShell window.

<p align="center">
<img src="https://github.com/user-attachments/assets/18dc16b5-59e4-4758-88b2-8bea9fb242d1">
</p>

<p align="center">
<img src="https://github.com/user-attachments/assets/9fc44689-5204-4555-a2f3-bb94165a53f2">
</p>

12.	Return to the Azure Arc "Machines" page and click "Refresh" until your server (e.g., "WINServer") appears with a "Connected" status. This may take a few minutes.

<p align="center">
<img src="https://github.com/user-attachments/assets/e443de54-43c7-4a21-a5f1-6f4d522adf6f">
</p>

## Task 4: Improving Security Posture with Microsoft Defender Recommendations.

Review and act on Microsoft Defender for Cloud recommendations to enhance your cloud security posture.

1.	In the "General" section of the Microsoft Defender for Cloud navigation menu, select "Recommendations".
2.	Click "Add filter", select "Resource type", check the "Machines - Azure Arc" box, and click "Apply".

<p align="center">
<img src="https://github.com/user-attachments/assets/c6500b6f-5de0-4311-b084-2a144490e92b">
</p>

3.	Locate the recommendation "Machines should have a vulnerability assessment solution" where the status is not "Completed". (You may need to scroll right to see the Status column.)
4.	Review the recommendation, then in the "Take action" tab, scroll down to "Delegate" and select "Assign owner & set due date".

<p align="center">
<img src="https://github.com/user-attachments/assets/9699612a-4506-40e3-b2e1-0112b94179e0">
</p>

5.	In the "Create assignment" window, leave "Type" set to "Defender for Cloud" and expand "Assignment details".
6.	In the "Email address" box, enter your email address.
7.	Explore the "Set remediation timeframe" and "Set email notifications" options, then click "Create".

<p align="center">
<img src="https://github.com/user-attachments/assets/80d815b1-c5e7-489c-bdea-1aa5d6a39b93">
</p>

8.	Close the recommendation page by clicking the "X" in the upper-right corner.

## Task 5: Analyzing and Mitigating Threats Using Security Alerts.

Load and review sample security alerts to practice analyzing and mitigating threats in Microsoft Defender for Cloud.

1.	In the "General" section of the Microsoft Defender for Cloud navigation menu, select "Security alerts".

<p align="center">
<img src="https://github.com/user-attachments/assets/cf1e2440-aafc-41a7-895c-943410e63ffc">
</p>

2.	Click "Sample alerts" from the command bar. (You may need to click the ellipsis (...) button to find it.)
3.	In the "Create sample alerts (Preview)" pane, ensure your subscription is selected and all sample alerts are checked in the "Defender for Cloud plans" area.
4.	Click "Create sample alerts". Wait for the "Successfully created sample alerts" notification. (This may take a few minutes.)

<p align="center">
<img src="https://github.com/user-attachments/assets/7b8529d7-60e8-4f2d-8eb1-184ea6fec31f">
</p>

5.	Click "Refresh" (if needed) to view the alerts in the "Security alerts" area.
6.	Select an alert with a "Severity" of "High" by checking its box. When the alert detail pane appears, click "View full details".
7.	Review the "Alert details" tab.
8.	Select the "Take action" tab (or scroll down and click "Next: Take Action" at the bottom of the page).
9.	Review the "Take action" information, noting options such as "Inspect resource context", "Mitigate the threat", "Prevent future attacks", "Trigger automated response", and "Suppress similar alerts", depending on the alert type.

<p align="center">
<img src="https://github.com/user-attachments/assets/27a3012a-4af7-4ab3-8f33-27f1851613b6">
</p>

<p align="center">
<img src="https://github.com/user-attachments/assets/cd11db36-7f14-4cad-9445-54bf5249fa21">
</p>
