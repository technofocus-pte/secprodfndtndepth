## **Lab 5 - Setting up the Microsoft Defender for Endpoint Environment**

**Introduction**

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

**Objectives**

- To assign the Owner role to the Azure subscription.

- To create a Windows 11 Pro virtual machine (**testVM1**) and onboard
  it to Microsoft Defender for Endpoints for security monitoring.

- To prepare the testvm1 virtual machine for upcoming tasks, including
  installing Microsoft 365 apps.

## **Task 1: Add Owner role to subscription**

1.  In the Azure portal `https://portal.azure.com` search box, type **subscription**, navigate and
    click on **Subscriptions** under **Services**.

![A  of a computer Description automatically
generated](./media/image28.png)

2.  Click on your **Azure Pass – Sponsorship** subscription name.

![A  of a computer Description automatically
generated](./media/image29.png)

3.  On **Azure Pass – Sponsorship** page, navigate and click on **Access
    control (IAM)**, click on **+Add** button, navigate and click on
    **Add role assignment** as shown in the below image.

  ![A  of a computer Description automatically
  generated](./media/image30.png)

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

8.  In the **Add role assignment** – **Conditions** tab, navigate to
    **What user can do** row and select the radio button **Allow user to
    assign all roles (highly privileged)**. Then, click on **Review +
    assign** button.

  ![](./media/image36.png)

9.  Click again on **Review + assign** button.

  ![](./media/image37.png)

10. You’ll receive a notification confirming the Owner role is
    successfully assigned to the subscription.

  ![A white background with black text Description automatically
  generated](./media/image38.png)

**Note**: If the owner role is already assigned, then you would get an error in the notification. Ignore it and move on to the next task.

## **Task 2: Onboarding testserver1 in Microsoft Defender for Endpoints**

1. In the Azure portal search bar, type `virtual machine`, then
 navigate and click on **Virtual machines** under **Services**.

 ![](./media/a38.png)

3.  In the **Virtual machines** page, navigate and click on **Create**,
    then click on **Azure virtual machine**.

 ![A screenshot of a computer Description automatically
 generated](./media/a39.png)

4.  In the **Create a virtual machine** page, navigate to **Resource
    group** row and click on **Create new**. Enter the name of the
    resource group (here, we entered `MCS-RG` as resource group name),
    then click on the **OK** button.

 ![](./media/a40.png)

5. Navigate to **Instance details** section, in the **virtual machine
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

5.  Scroll down to **Administrator account** section, enter the
    following details:

|Name|Credentials|
|:------|:------|
|Username	|`Admin5801`	|
|Password	|`Administrator5801@#`	|
|Confirm password	|`Administrator5801@#`|
 
 ![A screenshot of a computer Description automatically
 generated](./media/a46.png)

6.  Scroll down and select the checkboxes, then click on **Review +
    create** button as shown in the below image.

![A screenshot of a computer Description automatically
generated](./media/a47.png)

7.  In the **Create a virtual machine** page, navigate and click on the
    **Create** button.

 ![A screenshot of a computer Description automatically
 generated](./media/image48.png)

 ![](./media/a49.png)

8.  After the TESTSERVER1 virtual machine is successfully created, click
    on the **Go to resource** button.

 ![A screenshot of a computer Description automatically
 generated](./media/a50.png)

9.  You will be directed to the TESTSERVER1 virtual machine page.

 ![A screenshot of a computer Description automatically
 generated](./media/a51.png)

 **Note**: If you see testserver1 virtual machine status is not ready.
 Troubleshoot the issue… then wait for 10-15 minutes and reload the
 page.

10. In **TESTSERVER1** virtual machine page, navigate and click on
    **Connect** on the left side navigation menu, then click on
    **Select** under **Native RDP** section.

![](./media/a52.png)

11. In the **Native RDP** pane that appears on the right side, after
    fulfilling all the requirements, scroll down and click on **Download
    RDP file** button.

![](./media/a53.png)

12. On **TESTSERVER1.rdp could harm your device. Do you want to keep it
    anyway?** dialog box, click on **Keep** button.

 ![A screenshot of a computer Description automatically
 generated](./media/a54.png)

13. On **TESTSERVER1.rdp** file, click on **Open file** link.

 ![](./media/a55.png)

14. On **The publisher of this remote connection can’t be identified. Do
    you want to connect anyway?** dialog box, click on **Connect**
    button.

 ![A screenshot of a computer Description automatically
 generated](./media/a56.png)

15. On **Enter your credentials** dialog box, enter the password (here,
    `Administrator5801#`) and click on the **OK** button.

![](./media/a57.png)

16. On **The identity of the remote computer cannot be verified. Do you
    want to connect anyway?** dialog box, click on **Yes** button.

![](./media/a58.png)

17. The TESTSERVER1 VM will be opened. Minimize the Server Manager –
    Dashboard then minimize the virtual machine.

![](./media/a59.png)

18. In the Edge browser, open a new address bar and enter the following
    link: `https://security.microsoft.com` to open the Microsoft
    Defender Portal

![](./media/a60.png)

19. Close **Meet your improved security center** dialog box.

![A screenshot of a computer Description automatically
generated](./media/a61.png)

19. In **Microsoft Defender** portal, navigate and click on **System**,
then click on **Settings**. In the Settings page, you’ll see **Defender
for** **Endpoints** as shown in the below image.

**Note**:

In case, you did not see **Defender for Endpoint**, ensure that you are
logged into Azure portal, then open a new address bar and enter the
following URL and wait for the configuration to be completed:
`https://security.microsoft.com/securitysettings/endpoints/integration?tid=`

![](./media/a62.png)

![](./media/a63.png)

20. In the **Endpoints** page, navigate to **Device management**
section and then click on **Onboarding**.

![](./media/a64.png)

21. Click on the dropdown under **Select operating system to start
    onboarding process** and select **Windows Server 2019 and 2022**.

![A screenshot of a computer Description automatically
generated](./media/a65.png)

22. Scroll down and click on **Download onboarding package** button.

![A screenshot of a computer Description automatically
generated](./media/a66.png)

23. After onboarding package is successfully downloaded, click on **Open
    file** link.

![A screenshot of a computer Description automatically
generated](./media/a67.png)

24. Copy the Windows Command script

![](./media/a68.png)

25. Go back to your server VM and paste the copied Windows Command
    Script on the desktop as shown in the below image.

![](./media/a69.png)

26. Right click on the script and select **Run as administrator**.

![](./media/a70.png)

27. Type **Y** and press the **Enter** button to continue the onboarding
    process.

![](./media/a71.png)

28. After onboarding the machine successfully on Defender for Endpoint,
    click on any key to continue the onboarding process.

![](./media/a72.png)

29. The onboarding of the **testserver1 VM** usually takes **15-30
    minutes**; therefore, continue with the next task.

30. After 15-30 minutes, close the **testserver1 VM**, go back to
    Microsoft Defender portal and refresh the page, navigate and click
    on **Devices**, you'll see the **testserver1** was successfully
    onboarded in Microsoft Defender for Endpoint.

![](./media/a73.png)


## **Task 3: Onboarding testVM1 in Microsoft Defender for Endpoints**

1. In the Azure portal search bar, type virtual machine, then
  navigate and click on **Virtual machines** under **Services**.

![](./media/image71.png)

2. In the Virtual machines page, navigate and click on **Create**, then
click on **Azure virtual machine**.

![](./media/image72.png)

3. In **Create a virtual machine**, under the **Resource group** field,
select **MCS-RG** resource group. Then, navigate to **Instance details**
section, in the **Virtual machine name** field, enter `testvm1`.
In the **Region** field, ensure **EAST US** region is selected.

![A  of a computer Description automatically
generated](./media/image73.png)

5. In the **Security type** field, click on the dropdown and select
**Standard**. In the **Image** field, select **Windows 11 Pro, version
22H2 -x64 Gen2** from the dropdown.

![A  of a computer Description automatically
generated](./media/image74.png)

6.  Navigate to **Administrator account** section, enter the following
    details and leave all the field in the default state:

[TABLE]

![](./media/image75.png)

7.  Under **Licensing** section, select the checkbox **I confirm I have
    an eligible Windows 10/11 license with multi-tenant hosting
    rights**. Then, click on **Review + create** button.

![](./media/image76.png)

8.  Click on the **Create** button.

![A  of a computer Description automatically
generated](./media/image77.png)

![A  of a computer Description automatically
generated](./media/image78.png)

9.  The virtual machine is successfully created, click on the **Go to
    resource** button.

![](./media/image79.png)

10. You will be directed to the **vmtest1** virtual machine page.

![A  of a computer Description automatically
generated](./media/image80.png)

**Note**: If you see **testvm1** virtual machine status is not ready.
Troubleshoot the issue… then wait for 10-15 minutes and reload the page.

11. In **testvm1** virtual machine page, navigate and click on
    **Connect** on the left side navigation menu, scroll down to
    **Native RDP** tile, and click on the **Download RDP file**.

![](./media/image81.png)

12. On **testvm1.rdp could harm your device. Do you want to keep it
    anyway?** dialog box, click on **Keep** button.

  ![A  of a computer Description automatically
  generated](./media/image82.png)

13. On **testvm1.rdp** file, click on **Open file** link.

  ![A  of a computer Description automatically
  generated](./media/image83.png)

14. On **The publisher of this remote connection can’t be identified. Do
    you want to connect anyway?** dialog box, click on **Connect**
    button.

  ![A  of a computer Description automatically
  generated](./media/image84.png)

15. On **Enter your credentials** dialog box, enter the password (here,
    `Administrator5801@`) and click on the **OK** button.

![A  of a computer Description automatically
generated](./media/image85.png)

16. On **The identity of the remote computer cannot be verified. Do you
    want to connect anyway?** dialog box, click on **Yes** button.

![A  of a computer error Description automatically
generated](./media/image86.png)

17. On the **Choose privacy settings for your device** page, click on
    **Next** couple of times and then click on **Accept** button as
    shown in the below images.

![A  of a computer Description automatically
generated](./media/image87.png)

![A  of a computer Description automatically
generated](./media/image88.png)

![A  of a computer Description automatically
generated](./media/image89.png)

18. Go back to Microsoft Defender portal. In **Microsoft Defender**
    portal, navigate and click on **Settings**. In the **Settings**
    page, click on **Endpoints**.

![A  of a computer Description automatically
generated](./media/image90.png)

19. In the **Endpoints** page, navigate to **Device management** section
    and then click on **Onboarding**.

20. Click on the dropdown under **Select operating system to start
    onboarding process** and select **Windows 10 and 11**.

![A  of a computer Description automatically
generated](./media/image91.png)

21. Scroll down and click on the **Download onboarding package** button.

![A  of a computer Description automatically
generated](./media/image92.png)

22. After the onboarding package is successfully downloaded, click on
    **Open file** link.

![A search box with words Description automatically
generated](./media/image64.png)

23. Copy the Windows Command script

![A  of a computer Description automatically
generated](./media/image65.png)

24. Go back to **testvm1** and paste the copied Windows Command Script
    on the desktop as shown in the below image.

![](./media/image93.png)

25. Right click on the script and select **Run as administrator**.

![](./media/image94.png)

26. Type **Y** and press the **Enter** button to continue the onboarding
    process.

![A  of a computer Description automatically
generated](./media/image95.png)

27. After onboarding the machine successfully on Defender for Endpoint,
    click on any key to continue the onboarding process.

![](./media/image96.png)

28. The onboarding of the **testvm1** usually takes **15-30 minutes**;
    therefore, continue with the next task.

29. After 15-30 minutes, close the **testvm1**, go back to Microsoft
    Defender portal and refresh the page, navigate and click
    on **Devices**, you'll see the **testvm1** was successfully
    onboarded in Microsoft Defender for Endpoint.

![](./media/image97.png)

32. Close the VM.

## Task 6: Preparing the prerequisite on the testvm1 virtual machine

30. After logging in to testvm1 virtual machine, open the Edge browser,
    then select **Start without your data** button   **Confirm and
    Continue** button   **Continue without this data** button  
    **Confirm and start browsing** button   **Finish** button as shown
    in the below images.![](./media/image131.png)

![](./media/image132.png)

![](./media/image133.png)

![A  of a computer Description automatically
generated](./media/image134.png)

![](./media/image135.png)

31. Then, enter the following URL in the address bar:
    [**https://portal.office.com**](https://portal.office.com)

![A  of a computer Description automatically
generated](./media/image136.png)

32. Sign in to the Microsoft 365 portal using the following details:

[TABLE]

![A  of a computer Description automatically
generated](./media/image137.png)

![A  of a login box Description automatically
generated](./media/image138.png)

Note: If you see a dialog box **Sign in to Microsoft Edge**, then click
on **No, thanks** button.

33. Click on the **Next** button.

![](./media/image139.png)

34. In case, you see **Microsoft Authenticator -** **Start by getting
    the app** window, navigate and click on the **Next** button, else
    skip the steps from **#34 to #41**.

![A  of a computer Description automatically
generated](./media/image15.png)

35. In **Microsoft Authenticator –** **Set up your account** window,
    click on the **Next** button.

![A  of a computer Description automatically
generated](./media/image16.png)

36. **Scan the QR code** using the **Authenticator app** installed in
    your mobile phone and click on the **Next** button.

![A  of a computer Description automatically
generated](./media/image17.png)

37. Enter the number in your mobile authenticator app and select
    **Yes**. In **testvm1**, click on the **Next** button.

![A  of a computer error Description automatically
generated](./media/image18.png)

38. Click on the **Next** button.

![A  of a computer Description automatically
generated](./media/image19.png)

39. Click on the **Done** button.

![A  of a computer screen Description automatically
generated](./media/image20.png)

40. Enter the number again in your mobile authenticator app and select
    **Yes**..

![](./media/image21.png)

41. In the **Stay signed in?** window, click on the **Yes** button.

![](./media/image22.png)

42. In **Microsoft 365** page, navigate and click on **Install and
    more** dropdown, then click on **Install Microsoft 365 apps**.

![](./media/image140.png)

43. Click on **Install Office**.

![](./media/image141.png)

44. **OfficeSetup.exe** file will be downloaded, click on **Open file**
    link.

![A  of a computer Description automatically
generated](./media/image142.png)

45. Wait for few minutes while Microsoft 365 and Office downloads.

![A  of a computer Description automatically
generated](./media/image143.png)

![](./media/image144.png)

**Note**: The installation will take around 10-20 minutes to complete.

46. On **You’re all set!** dialog box, click on the **Close** button.

![](./media/image145.png)

47. Click on the **Start menu** and then click on **Word** as shown in
    the below image.

![](./media/image146.png)

48. Click on **Sign in or create account** button.

![](./media/image147.png)

49. Login using the following details:

[TABLE]

![A  of a computer Description automatically
generated](./media/image148.png)

![](./media/image149.png)

50. In case, you’re prompted to Approve sign in request, then enter the
    number in your mobile authenticator app and select **Yes**..

![](./media/image150.png)

51. On **Stay signed in to all your apps** dialog box, click on **OK**
    button.

![](./media/image151.png)

52. On **You’re all set** dialog box, click on **Done** button.

![A  of a computer Description automatically
generated](./media/image152.png)

53. On the **Accept the license agreement** dialog box, click on
    **Accept** button.

![A  of a computer Description automatically
generated](./media/image153.png)

54. On Your privacy matters dialog box, click on the **Close** button.

![](./media/image154.png)


**Summary**

In this lab, you’ve assigned the Owner role to the Azure subscription,
then you’ve created and onboarded Windows Server and Windows 11 Pro
virtual machines (testserver1, testVM1, and testVM2) to Microsoft
Defender for Endpoints, bolstering security with real-time monitoring
and threat response capabilities across different VM types. Then, you’ve
created a test user account (Robert Frost) with an Office 365 license.
Finally, you’ve installed Microsoft 365 apps and configured necessary
settings.
