# Lab 5 - Setting up the Microsoft Defender for Endpoint Environment

## Introduction

Unprotected or misconfigured devices can pose a risk to your
organization. Attackers can take advantage and do damage to your devices
or data. Many organizations have suffered reputational and financial
loss at the hands of attackers. To protect your organization, you need
to protect your devices.

Microsoft Defender for Endpoint is an endpoint security solution that
offers vulnerability management, endpoint protection, endpoint detection
and response, mobile threat defense, and managed services in a single,
unified platform. It enables you to prevent, detect, investigate, and
respond to security threats and risks across Windows, Windows Server,
macOS, Linux, Android, and iOS devices.

## Objectives

- To assign the Owner role to the Azure subscription

- To create a TESTSERVER1 and Windows 11 Pro virtual machine (**testVM1**) and onboard
  it to Microsoft Defender for Endpoints for security monitoring

- To prepare the testvm1 virtual machine for upcoming tasks, including
  installing Microsoft 365 apps

## Task 1: Add Owner role to subscription

1.  In the Azure portal `https://portal.azure.com` search box, type **subscription**, navigate and
    click on **Subscriptions** under **Services**.

    ![A  of a computer Description automatically generated](./media/image28.png)

2. Click on your **Azure Pass – Sponsorship** subscription name.

  ![A  of a computer Description automatically
  generated](./media/image29.png)

3.  On **Azure Pass – Sponsorship** page, navigate and click on **Access
    control (IAM)**, click on **+Add** button, navigate and click on
    **Add role assignment** as shown in the below image.

    ![A  of a computer Description automatically generated](./media/image30.png)

4.  On **Add role assignment** page, click on **Privileged administrator
    roles** tab, navigate and select **Owner** role, then click on the
    **Next** button.

  ![A  of a computer Description automatically
  generated](./media/image31.png)

5.  Navigate and click on **+Select members** hyperlink. On **Select
    members** pane that appear on the right side, type and select your
    Office 365 tenant ID, then click on the **Select** button as shown
    in the below images.

  ![](./media/image32.png)
 
  ![](./media/image33.png)

6.  Click on the **Next** button.

  ![A  of a computer Description automatically
  generated](./media/image34.png)

7.  In the **Add role assignment** – **Conditions** tab, navigate to
    **What user can do** row and select the radio button **Allow user to
    assign all roles (highly privileged)**. Then, click on **Review +
    assign** button.

  ![](./media/image36.png)

8.  Click again on **Review + assign** button.

  ![](./media/image37.png)

9. You’ll receive a notification confirming the Owner role is
    successfully assigned to the subscription.

  ![A white background with black text Description automatically
  generated](./media/image38.png)

**Note**: If the owner role is already assigned, then you would get an error in the notification. Ignore it and move on to the next task.

## Task 2: Onboarding testserver1 in Microsoft Defender for Endpoints

1. In the Azure portal search bar, type `virtual machine`, then
 navigate and click on **Virtual machines** under **Services**.

 ![](./media/a38.png)

2.  In the **Virtual machines** page, navigate and click on **Create**,
    then click on **Azure virtual machine**.

 ![A screenshot of a computer Description automatically
 generated](./media/a39.png)

3.  In the **Create a virtual machine** page, navigate to **Resource
    group** row and click on **Create new**. Enter the name of the
    resource group (here, we entered `MCS-RG` as resource group name),
    then click on the **OK** button.

 ![](./media/a40.png)

4. Navigate to **Instance details** section, in the **virtual machine
name** field, enter the name of the virtual machine (here, we
entered `TESTSERVER1`. In
the **Region** field, select **Central Canada**. In the **Availability
zone** field, ensure that **Zone 1** is selected. In the **Security
type** field, click on the dropdown and select **Standard**. In
the **Image** field, select **Windows Server 2019 Datacenter -x64
Gen2** from the dropdown.

 ![](./media/nw51.png)

 ![](./media/a42.png)

**Note**: If you encounter the following error - **This size is not
available in zone 1 . Zones ‘2,3’ are supported”**, then scroll up and
uncheck Zone 1, check Zone 2 or 3 box.

5.  Navigate to **Size** field and click on **See all sizes**.
    In **Select a VM size** page, navigate and select **B2ms**, then
    click on the **Select** button.

 ![A screenshot of a computer Description automatically
 generated](./media/a43.png)

 ![A screenshot of a computer Description automatically
 generated](./media/a44.png)

 ![A screenshot of a computer Description automatically
 generated](./media/a45.png)

6.  Scroll down to **Administrator account** section, enter the
    following details:

|Name|Credentials|
|:------|:------|
|Username	|`Admin5801`	|
|Password	|`Administrator5801@#`	|
|Confirm password	|`Administrator5801@#`|
 
 ![A screenshot of a computer Description automatically
 generated](./media/a46.png)

7.  Scroll down and select the checkboxes, then click on **Review +
    create** button as shown in the below image.

![A screenshot of a computer Description automatically
generated](./media/a47.png)

8.  In the **Create a virtual machine** page, navigate and click on the
    **Create** button.

 ![A screenshot of a computer Description automatically
 generated](./media/image48.png)

 ![](./media/a49.png)

9.  After the TESTSERVER1 virtual machine is successfully created, click
    on the **Go to resource** button.

 ![A screenshot of a computer Description automatically
 generated](./media/a50.png)

10.  You will be directed to the TESTSERVER1 virtual machine page.

 ![A screenshot of a computer Description automatically
 generated](./media/a51.png)

 **Note**: If you see testserver1 virtual machine status is not ready.
 Troubleshoot the issue… then wait for 10-15 minutes and reload the
 page.

11. In **TESTSERVER1** virtual machine page, navigate and click on
    **Connect** on the left side navigation menu, then click on
    **Select** under **Native RDP** section.

![](./media/a52.png)

12. In the **Native RDP** pane that appears on the right side, after
    fulfilling all the requirements, scroll down and click on **Download
    RDP file** button.

![](./media/a53.png)

13. On **TESTSERVER1.rdp could harm your device. Do you want to keep it
    anyway?** dialog box, click on **Keep** button.

 ![A screenshot of a computer Description automatically
 generated](./media/a54.png)

14. On **TESTSERVER1.rdp** file, click on **Open file** link.

 ![](./media/a55.png)

15. On **The publisher of this remote connection can’t be identified. Do
    you want to connect anyway?** dialog box, click on **Connect**
    button.

 ![A screenshot of a computer Description automatically
 generated](./media/a56.png)

16. On **Enter your credentials** dialog box, enter the password (here,
    `Administrator5801@#`) and click on the **OK** button.

![](./media/a57.png)

17. On **The identity of the remote computer cannot be verified. Do you
    want to connect anyway?** dialog box, click on **Yes** button.

![](./media/a58.png)

18. The TESTSERVER1 VM will be opened. Minimize the Server Manager –
    Dashboard then minimize the virtual machine.

![](./media/a59.png)

19. In the Edge browser, open a new address bar and enter the following
    link: `https://security.microsoft.com` to open the Microsoft
    Defender Portal

![](./media/a60.png)

20. Close **Meet your improved security center** dialog box.

![A screenshot of a computer Description automatically
generated](./media/a61.png)

21. In **Microsoft Defender** portal, navigate and click on **System**,
then click on **Settings**. In the Settings page, you’ll see **Defender
for** **Endpoints** as shown in the below image.

**Note**:

In case, you did not see **Defender for Endpoint**, ensure that you are
logged into Azure portal, then open a new address bar and enter the
following URL and wait for the configuration to be completed:
`https://security.microsoft.com/securitysettings/endpoints/integration?tid=`

![](./media/a62.png)

![](./media/a63.png)

22. In the **Endpoints** page, navigate to **Device management**
section and then click on **Onboarding**.

![](./media/a64.png)

23. Click on the dropdown under **Select operating system to start
    onboarding process** and select **Windows Server 2019 and 2022**.

![A screenshot of a computer Description automatically
generated](./media/a65.png)

24. Scroll down and click on **Download onboarding package** button.

![A screenshot of a computer Description automatically
generated](./media/a66.png)

25. After onboarding package is successfully downloaded, click on **Open
    file** link.

![A screenshot of a computer Description automatically
generated](./media/a67.png)

26. Copy the Windows Command script

![](./media/a68.png)

27. Go back to your server VM and paste the copied Windows Command
    Script on the desktop as shown in the below image.

![](./media/a69.png)

28. Right click on the script and select **Run as administrator**.

![](./media/a70.png)

29. Type **Y** and press the **Enter** button to continue the onboarding
    process.

![](./media/a71.png)

30. After onboarding the machine successfully on Defender for Endpoint,
    click on any key to continue the onboarding process.

![](./media/a72.png)

31. The onboarding of the **testserver1 VM** usually takes **15-30
    minutes**; therefore, continue with the next task.

32. After 15-30 minutes, close the **testserver1 VM**, go back to
    Microsoft Defender portal and refresh the page, navigate and click
    on **Devices**, you'll see the **testserver1** was successfully
    onboarded in Microsoft Defender for Endpoint.

![](./media/a73.png)


## Task 3: Onboarding testVM1 in Microsoft Defender for Endpoints

1. In the Azure portal search bar, type virtual machine, then
 navigate and click on `Virtual machines` under **Services**.

![](./media/a74.png)

2. In the Virtual machines page, navigate and click on **Create**, then
click on **Azure virtual machine**.

![](./media/a75.png)

3.  In **Create a virtual machine**, under the **Resource group** field,
    select **RG-DOE** resource group. Then, navigate to **Instance
    details** section, in the **Virtual machine name** field,
    enter `testvm1`. In
    the **Region** field, ensure **Canada Central** region is selected.

 ![](./media/nw55.png)

4.  In the **Security type** field, click on the dropdown and
    select **Standard**. In the **Image** field, select **Windows 11
    Pro, version 22H2 -x64 Gen2** from the dropdown.

    **Note**: If you did not find **Windows 11 Pro, version 22H2 -x64 Gen2** then select **Windows 10
    Pro, version 22H2 -x64 Gen2**

 ![](./media/a77.png)

5. Navigate to **Administrator account** section, enter the following
    details and leave all the field in the default state:


|Name|Credentials|
|:------|:------|
|Username	|`Admin5802`	|
|Password	|`Administrator5801@#`	|
|Confirm password	|`Administrator5801@#`|

![](./media/a78.png)

6. Under **Licensing** section, select the checkbox **I confirm I have
    an eligible Windows 10/11 license with multi-tenant hosting
    rights**. Then, click on **Review + create** button.

![](./media/a79.png)

7. Click on the **Create** button.

![A screenshot of a computer Description automatically
generated](./media/a80.png)

![A screenshot of a computer Description automatically
generated](./media/a81.png)

8. The virtual machine is successfully created, click on the **Go to
    resource** button.

![](./media/a82.png)

9. You will be directed to the **vmtest1** virtual machine page.

![A screenshot of a computer Description automatically
generated](./media/a83.png)

**Note**: If you see testvm1 virtual machine status is not ready.
Troubleshoot the issue... then wait for 10-15 minutes and reload the
page.

10. In **testvm1** virtual machine page, navigate and click on
    **Connect** on the left side navigation menu, scroll down to
    **Native RDP** tile, and click on the **Download RDP file**.

![](./media/a84.png)

11. On **testvm1.rdp could harm your device. Do you want to keep it
    anyway?** dialog box, click on **Keep** button.

 ![A screenshot of a computer Description automatically
 generated](./media/a85.png)

12. On **testvm1.rdp** file, click on **Open file** link.

 ![A screenshot of a computer Description automatically
 generated](./media/a86.png)

13. On **The publisher of this remote connection can’t be identified. Do
    you want to connect anyway?** dialog box, click on **Connect**
    button.

 ![A screenshot of a computer Description automatically
 generated](./media/a87.png)

14. On **Enter your credentials** dialog box, enter the password (here,
    `Administrator5801@#`) and click on the **OK** button.

![A screenshot of a computer Description automatically
generated](./media/a88.png)

15. On **The identity of the remote computer cannot be verified. Do you
    want to connect anyway?** dialog box, click on **Yes** button.

![A screenshot of a computer error Description automatically
generated](./media/a89.png)

16. On the **Choose privacy settings for your device** page, click on
    **Next** couple of times and then click on **Accept** button as
    shown in the below images.

![A screenshot of a computer Description automatically
generated](./media/a90.png)

![A screenshot of a computer Description automatically
generated](./media/a91.png)

![A screenshot of a computer Description automatically
generated](./media/a92.png)

17. Go back to Microsoft Defender portal. In **Microsoft Defender**
    portal, navigate and click on **Settings**. In the **Settings**
    page, click on **Endpoints**.

![A screenshot of a computer Description automatically
generated](./media/a93.png)

18. In the **Endpoints** page, navigate to **Device management** section
    and then click on **Onboarding**.

19. Click on the dropdown under **Select operating system to start
    onboarding process** and select **Windows 10 and 11**.

![](./media/a94.png)

20. Scroll down and click on the **Download onboarding package** button.

![](./media/a95.png)

21. After the onboarding package is successfully downloaded, click on
    **Open file** link.

![A screenshot of a phone Description automatically
generated](./media/a96.png)

22. Copy the Windows Command script

![A screenshot of a computer Description automatically
generated](./media/a68.png)

23. Go back to **testvm1** and paste the copied Windows Command Script
    on the desktop as shown in the below image.

![](./media/a97.png)

24. Right click on the script and select **Run as administrator**.

![](./media/a98.png)

25. Type **Y** and press the **Enter** button to continue the onboarding
    process.

![A screenshot of a computer Description automatically
generated](./media/a99.png)

26. After onboarding the machine successfully on Defender for Endpoint,
    click on any key to continue the onboarding process.

![](./media/a100.png)

27. The onboarding of the **testvm1** usually takes **15-30 minutes**;
    therefore, continue with the next task.

28. After 15-30 minutes, close the **testvm1**, go back to Microsoft
    Defender portal and refresh the page, navigate and click
    on **Devices**, you'll see the **testvm1** was successfully
    onboarded in Microsoft Defender for Endpoint.

![](./media/a101.png)

## Task 4: Preparing the prerequisite on the testvm1 virtual machine

1. In testvm1 virtual machine, open the Edge browser,
    then select **Start without your data** button   **Confirm and
    Continue** button   **Continue without this data** button  
    **Confirm and start browsing** button   **Finish** button as shown
    in the below images.

    ![](./media/image131.png)

    ![](./media/image132.png)

    ![](./media/image133.png)

    ![A  of a computer Description automatically generated](./media/image134.png)

    ![](./media/image135.png)

2. Then, enter the following URL in the address bar:
    ``https://portal.office.com``

![A  of a computer Description automatically
generated](./media/image136.png)

3. Sign in to the Microsoft 365 portal using the admin credentials:

4. In **Microsoft 365** page, navigate and click on **Install and
    more** dropdown, then click on **Install Microsoft 365 apps**.

![](./media/image140.png)

5. Click on **Install Office**.

![](./media/image141.png)

6. **OfficeSetup.exe** file will be downloaded, click on **Open file**
    link.

![A  of a computer Description automatically
generated](./media/image142.png)

7. Wait for few minutes while Microsoft 365 and Office downloads.

![A  of a computer Description automatically
generated](./media/image143.png)

![](./media/image144.png)

**Note**: The installation will take around 10-20 minutes to complete.

8. On **You’re all set!** dialog box, click on the **Close** button.

![](./media/image145.png)

9. Click on the **Start menu** and then click on **Word** as shown in
    the below image.

![](./media/image146.png)

10. Click on **Sign in or create account** button.

![](./media/image147.png)

11. Login using the admin credentials.

12. In case, you’re prompted to Approve sign in request, then enter the
    number in your mobile authenticator app and select **Yes**..

![](./media/image150.png)

13. On **Stay signed in to all your apps** dialog box, click on **OK**
    button.

![](./media/image151.png)

14. On **You’re all set** dialog box, click on **Done** button.

![A  of a computer Description automatically
generated](./media/image152.png)

15. On the **Accept the license agreement** dialog box, click on
    **Accept** button.

![A  of a computer Description automatically
generated](./media/image153.png)

16. On Your privacy matters dialog box, click on the **Close** button.

![](./media/image154.png)


**Summary**

In this lab, you’ve assigned the Owner role to the Azure subscription,
then you’ve created and onboarded Windows Server and Windows 11 Pro
virtual machines (testserver1, testVM1) to Microsoft
Defender for Endpoints, bolstering security with real-time monitoring
and threat response capabilities across different VM types. Then, you’ve installed Microsoft 365 apps and configured necessary
settings.
