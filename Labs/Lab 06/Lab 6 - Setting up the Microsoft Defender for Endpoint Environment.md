## **Lab 6 - Setting up the Microsoft Defender for Endpoint Environment**

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

- To create a Windows Server virtual machine (**testserver1**) and
  onboard it to Microsoft Defender for Endpoints for security
  monitoring.

- To create a Windows 11 Pro virtual machine (**testVM1**) and onboard
  it to Microsoft Defender for Endpoints for security monitoring.

- To create another Windows 11 Pro virtual machine (**testVM2**) and
  onboard it to Microsoft Defender for Endpoints for security
  monitoring.

- To create a new user account (**Robert Frost**) with Office 365
  license for testing purposes.

- To prepare the testvm1 virtual machine for upcoming tasks, including
  installing Microsoft 365 apps.

## **Task 0: Sync Host environment time**

1.  Login to the Lab Virtual Machine using the credentials provided on
    the Home tab of the Lab interface.

2.  In your VM, navigate and click in the **Search icon**, in the search
    bar type **Settings** and then click on **Settings** under **Best
    match**.

> <img src="./media/image1.png" style="width:6.5in;height:6.05in" />

2.  On Settings window, navigate and click on **Time & language**.

<img src="./media/image2.png" style="width:6.5in;height:5.72222in" />

3.  On **Time & language** page, navigate and click on **Date & time**.

<img src="./media/image3.png" style="width:6.5in;height:5.27639in" />

4.  Scroll down and navigate to **Additional settings** section, then
    click on **Syn now** button.

<img src="./media/image4.png" style="width:6.5in;height:5.04861in" />

5.  Close the **Settings** window.

<img src="./media/image5.png" style="width:6.5in;height:5.12222in" />

## **Task 1: Redeem Azure pass**

1.  In your lab VM, open Microsoft Edge browser and enter the following
    URL:
    [**http://www.microsoftazurepass.com**](http://www.microsoftazurepass.com)

> <img src="./media/image6.png" style="width:6.5in;height:3.86181in" />

2.  On **Ready to get started?** page, click on the **Start** button.

<img src="./media/image7.jpeg" style="width:5.34464in;height:4.56693in"
alt="Graphical user interface, website Description automatically generated" />

**Note**: Do not use your Company/Work Account to login to redeem the
Azure Pass, another Azure Pass will not be issued.

4.  In the **Sign in** window, enter the **Office 365 Tenant ID** -
    <admin@WWLxxxx.onmicrosoft.com> and click on the **Next** button.

<img src="./media/image8.png"
style="width:4.10694in;height:3.22639in" />

5.  Enter **Office 365 Tenant Password** and click on the **Sign in**
    button.

<img src="./media/image9.png"
style="width:4.11875in;height:3.20208in" />

6.  On **The following Microsoft Account will be used for Azure pass**
    page, click on **Confirm Microsoft Account** button.

> <img src="./media/image10.png" style="width:5.1524in;height:3.2841in" />

7.  Enter the Promocode provided in the lab environment in the **Enter
    Promo code** field, then enter the characters under the **Enter the
    characters you see** field and click on the **Submit** button.

<img src="./media/image11.png"
style="width:5.03428in;height:3.40087in" />

8.  **We are processing your request** page will appear, it may take few
    seconds to process the redemption.

<img src="./media/image12.png" style="width:5.09449in;height:1.51509in"
alt="Screenshot" />

9.  Enter correct details in **Your Profile** page, tick all the check
    boxes, and then click on **Sign up** button.

<img src="./media/image13.jpeg" style="width:4.1209in;height:2.696in"
alt="A screenshot of a computer Description automatically generated with medium confidence" />

> <img src="./media/image14.png" style="width:3.78902in;height:4.5671in"
> alt="Graphical user interface, text, application Description automatically generated" />

In case you are asked to set up your account using Microsoft
Authenticator App, then perform the following steps:

10. In your mobile, install the **Microsoft Authenticator App**. Then,
    go back to Microsoft Azure port. In the Azure portal, **Microsoft
    Authenticator -** **Start by getting the app** window, navigate and
    click on the **Next** button.

<img src="./media/image15.png" style="width:6.5in;height:3.45278in" />

11. In **Microsoft Authenticator –** **Set up your account** window,
    click on the **Next** button.

<img src="./media/image16.png" style="width:6.5in;height:3.55972in"
alt="A screenshot of a computer Description automatically generated" />

12. **Scan the QR code** using the **Authenticator app** installed in
    your mobile phone and click on the **Next** button.

<img src="./media/image17.png" style="width:6.5in;height:4.29375in"
alt="A screenshot of a computer Description automatically generated" />

13. Enter the number in your mobile authenticator app and select
    **Yes**.

<img src="./media/image18.png" style="width:6.5in;height:3.91042in"
alt="A screenshot of a computer error Description automatically generated" />

14. Click on the **Next** button.

<img src="./media/image19.png" style="width:6.5in;height:3.72083in"
alt="A screenshot of a computer Description automatically generated" />

15. Click on the **Done** button.

<img src="./media/image20.png" style="width:6.5in;height:3.11597in" />

16. If prompted, then enter the number again in your mobile
    authenticator app and select **Yes**..

<img src="./media/image21.png"
style="width:4.72741in;height:6.01974in" />

17. In the **Stay signed in?** window, click on the **Yes** button.

<img src="./media/image22.png"
style="width:5.6779in;height:4.85247in" />

18. On **Are you satisfied with your signup experience** window, enter
    your feedback and click on the **Submit** button.

<img src="./media/image23.png"
style="width:3.72271in;height:3.63271in" />

19. In **Welcome to Microsoft Azure** page, click on **Get started**.

<img src="./media/image24.png" style="width:6.5in;height:4.06528in"
alt="A screenshot of a computer Description automatically generated" />

20. On **How do you plan to use Azure?** page, click on the **Skip**
    button.

<img src="./media/image25.png" style="width:6.5in;height:4.14306in"
alt="A screenshot of a computer Description automatically generated" />

21. On **Now, let’s show you around Azure** page, click on the **Skip**
    button.

<img src="./media/image26.png" style="width:6.5in;height:4.23125in"
alt="A screenshot of a computer Description automatically generated" />

22. You’ll be directed to Azure portal page.

<img src="./media/image27.png" style="width:6.5in;height:4.08264in"
alt="A screenshot of a computer Description automatically generated" />

## **Task 2: Add Owner role to subscription**

1.  In the Azure portal search box, type **subscription**, navigate and
    click on **Subscriptions** under **Services**.

<img src="./media/image28.png" style="width:6.76222in;height:3.76262in"
alt="A screenshot of a computer Description automatically generated" />

2.  Click on your **Azure Pass – Sponsorship** subscription name.

<img src="./media/image29.png" style="width:7.06622in;height:3.93177in"
alt="A screenshot of a computer Description automatically generated" />

3.  On **Azure Pass – Sponsorship** page, navigate and click on **Access
    control (IAM)**, click on **+Add** button, navigate and click on
    **Add role assignment** as shown in the below image**.**

> <img src="./media/image30.png" style="width:6.26806in;height:4.36111in"
> alt="A screenshot of a computer Description automatically generated" />

4.  On **Add role assignment** page, click on **Privileged administrator
    roles** tab, navigate and select **Owner** role, then click on the
    **Next** button**.**

> <img src="./media/image31.png" style="width:6.26806in;height:4.36111in"
> alt="A screenshot of a computer Description automatically generated" />

5.  Navigate and click on **+Select members** hyperlink. On **Select
    members** pane that appear on the right side, type and select your
    Office 365 tenant ID, then click on the **Select** button as shown
    in the below images.

> <img src="./media/image32.png" style="width:6.5in;height:4.125in" />
>
> <img src="./media/image33.png" style="width:6.5in;height:4.10208in" />

6.  Click on the **Next** button.

> <img src="./media/image34.png" style="width:6.26806in;height:4.36111in"
> alt="A screenshot of a computer Description automatically generated" />

7.  Click again on **Review + assign** button.

> <img src="./media/image35.png" style="width:6.5in;height:5.29514in" />

8.  In the **Add role assignment** – **Conditions** tab, navigate to
    **What user can do** row and select the radio button **Allow user to
    assign all roles (highly privileged)**. Then, click on **Review +
    assign** button.

> <img src="./media/image36.png" style="width:6.5in;height:3.98603in" />

9.  Click again on **Review + assign** button.

> <img src="./media/image37.png" style="width:6.5in;height:5.29514in" />

10. You’ll receive a notification confirming the Owner role is
    successfully assigned to the subscription.

> <img src="./media/image38.png" style="width:5.33606in;height:0.98384in"
> alt="A white background with black text Description automatically generated" />

**Note**: Microsoft 365 E5 license is assigned to your O365 tenant ID,
which included Microsoft Defender for Endpoint feature.

## **Task 3: Onboarding testserver1 in Microsoft Defender for Endpoints**

> 1\. In the Azure portal search bar, type **virtual machine**, then
> navigate and click on **Virtual machines** under **Services**.
>
> <img src="./media/image39.png" style="width:6.5in;height:3.68056in" />

3.  In the **Virtual machines** page, navigate and click on **Create**,
    then click on **Azure virtual machine**.

> <img src="./media/image40.png" style="width:6.5in;height:3.92986in"
> alt="A screenshot of a computer Description automatically generated" />

4.  In the **Create a virtual machine** page, navigate to **Resource
    group** row and click on **Create new**. Enter the name of the
    resource group (here, we entered **RG-DOE** as resource group name),
    then click on the **OK** button.

> <img src="./media/image41.png" style="width:6.5in;height:5.25903in"
> alt="A screenshot of a computer Description automatically generated" />

5\. Navigate to **Instance details** section, in the **virtual machine
name** field, enter the name of the virtual machine (here, we entered
**TESTSERVER1**). In the **Security type** field, click on the dropdown
and select **Standard**. In the **Image** field, select **Windows Server
2019 Datacenter -x64 Gen2** from the dropdown.

> <img src="./media/image42.png" style="width:6.5in;height:3.47986in" />

5.  Scroll down to **Administrator account** section, enter the
    following details:

| Username         | +++**Admin5801**+++            |
|------------------|--------------------------------|
| Password         | +++**Administrator5801@\***+++ |
| Confirm password | +++**Administrator5801@\***+++ |

> <img src="./media/image43.png" style="width:6.5in;height:4.42917in" />

6.  Scroll down and select the checkbox, then click on **Review +
    create** button as shown in the below image.

<img src="./media/image44.png" style="width:6.5in;height:5.38194in" />

7.  In the **Create a virtual machine** page, navigate and click on the
    **Create** button.

> <img src="./media/image45.png" style="width:6.5in;height:5.42153in"
> alt="A screenshot of a computer Description automatically generated" />
>
> <img src="./media/image46.png" style="width:6.5in;height:3.78333in" />

8.  After the TESTSERVER1 virtual machine is successfully created, click
    on the **Go to resource** button.

> <img src="./media/image47.png" style="width:6.5in;height:3.82083in"
> alt="A screenshot of a computer Description automatically generated" />

9.  You will be directed to the TESTSERVER1 virtual machine page.

> <img src="./media/image48.png" style="width:6.5in;height:3.44236in"
> alt="A screenshot of a computer Description automatically generated" />
>
> **Note**: If you see testserver1 virtual machine status is not ready.
> Troubleshoot the issue… then wait for 10-15 minutes and reload the
> page.

10. In **TESTSERVER1** virtual machine page, navigate and click on
    **Connect** on the left side navigation menu, then click on
    **Select** under **Native RDP** section.

<img src="./media/image49.png" style="width:6.5in;height:5.24722in" />

11. In the **Native RDP** pane that appears on the right side, after
    fulfilling all the requirements, scroll down and click on **Download
    RDP file** button.

<img src="./media/image50.png" style="width:6.5in;height:4.07778in" />

12. On **TESTSERVER1.rdp could harm your device. Do you want to keep it
    anyway?** dialog box, click on **Keep** button.

> <img src="./media/image51.png" style="width:6.5in;height:4.02639in"
> alt="A screenshot of a computer Description automatically generated" />

13. On **TESTSERVER1.rdp** file, click on **Open file** link.

> <img src="./media/image52.png" style="width:6.5in;height:3.08194in" />

14. On **The publisher of this remote connection can’t be identified. Do
    you want to connect anyway?** dialog box, click on **Connect**
    button.

> <img src="./media/image53.png" style="width:5.1026in;height:2.69304in"
> alt="A screenshot of a computer Description automatically generated" />

15. On **Enter your credentials** dialog box, enter the password (here,
    **Administrator5801@\***) and click on the **OK** button.

<img src="./media/image54.png"
style="width:4.42726in;height:3.87698in" />

16. On **The identity of the remote computer cannot be verified. Do you
    want to connect anyway?** dialog box, click on **Yes** button.

<img src="./media/image55.png"
style="width:3.77693in;height:3.8603in" />

17. The TESTSERVER1 VM will be opened. Minimize the Server Manager –
    Dashboard then then minimize the virtual machine.

<img src="./media/image56.png" style="width:6.5in;height:3.83681in" />

18. In the Edge browser, open a new tab and enter the following link:
    **<https://security.microsoft.com>** to open the Microsoft Defender
    Portal

<img src="./media/image57.png" style="width:6.5in;height:2.87639in" />

19. Close **Meet your improved security center** dialog box. Wait for 10
    minutes and refresh the page before proceeding to the next step.

<img src="./media/image58.png" style="width:6.5in;height:4.18056in"
alt="A screenshot of a computer Description automatically generated" />

19\. In **Microsoft Defender** portal, navigate and click on **System**,
then click on **Settings**. In the Settings page, you’ll see **Defender
for** **Endpoints** as shown in the below images.

<img src="./media/image59.png" style="width:6.5in;height:4.01944in" />

<img src="./media/image60.png" style="width:6.5in;height:3.86528in" />

**Note**:

> In case, you did not see **Defender for Endpoint**, then close all the
> tabs in the browser. Open a new Edge browser and login to Azure
> portal. Then, open a new tab in Edge browser and enter the following
> URL and wait for the configuration to be completed:
> <https://security.microsoft.com/securitysettings/endpoints/integration?tid=>

20\. In the **Endpoints** page, navigate to **Device management**
section and then click on **Onboarding**.

<img src="./media/image61.png" style="width:6.5in;height:4.09931in" />

21. Click on the dropdown under **Select operating system to start
    onboarding process** and select **Windows Server 2019 and 2022**.

<img src="./media/image62.png" style="width:6.5in;height:3.25694in"
alt="A screenshot of a computer Description automatically generated" />

22. Scroll down and click on **Download onboarding package** button.

<img src="./media/image63.png" style="width:6.5in;height:3.44792in"
alt="A screenshot of a computer Description automatically generated" />

23. After onboarding package is successfully downloaded, click on **Open
    file** link.

<img src="./media/image64.png" style="width:3.07644in;height:1.47718in"
alt="A search box with words Description automatically generated" />

24. Copy the Windows Command script

<img src="./media/image65.png" style="width:6.5in;height:4.23542in" />

25. Go back to your server VM and paste the copied Windows Command
    Script on the desktop as shown in the below image.

<img src="./media/image66.png" style="width:6.5in;height:4.95833in" />

26. Right click on the script and select **Run as administrator**.

<img src="./media/image67.png" style="width:6.5in;height:4.57708in" />

27. Type **Y** and press the **Enter** button to continue the onboarding
    process.

<img src="./media/image68.png" style="width:6.5in;height:2.62847in" />

28. After onboarding the machine successfully on Defender for Endpoint,
    click on any key to continue the onboarding process.

<img src="./media/image69.png" style="width:6.5in;height:3.14792in" />

29. The onboarding of the **testserver1 VM** usually takes **15-30
    minutes**; therefore, continue with the next task.

30. After 15-30 minutes, close the **testserver1 VM**, go back to
    Microsoft Defender portal and refresh the page, navigate and click
    on **Devices**, you'll see the **testserver1** was successfully
    onboarded in Microsoft Defender for Endpoint.

<img src="./media/image70.png" style="width:6.5in;height:3.09861in" />

## **Task 4: Onboarding testVM1 in Microsoft Defender for Endpoints**

> 1\. In the Azure portal search bar, type virtual machine, then
> navigate and click on **Virtual machines** under **Services**.

<img src="./media/image71.png" style="width:6.5in;height:3.63194in" />

2\. In the Virtual machines page, navigate and click on **Create**, then
click on **Azure virtual machine**.

<img src="./media/image72.png" style="width:6.5in;height:3.50139in" />

3\. In **Create a virtual machine**, under the **Resource group** field,
select **MCS-RG** resource group. Then, navigate to **Instance details**
section, in the **Virtual machine name** field, enter +++**testvm1**+++.
In the **Region** field, ensure **EAST US** region is selected.

<img src="./media/image73.png" style="width:6.5in;height:5.17292in"
alt="A screenshot of a computer Description automatically generated" />

5\. In the **Security type** field, click on the dropdown and select
**Standard**. In the **Image** field, select **Windows 11 Pro, version
22H2 -x64 Gen2** from the dropdown.

<img src="./media/image74.png" style="width:6.5in;height:5.14931in"
alt="A screenshot of a computer Description automatically generated" />

6.  Navigate to **Administrator account** section, enter the following
    details and leave all the field in the default state:

| Username         | +++**Admin5802**+++            |
|------------------|--------------------------------|
| Password         | +++**Administrator5801@\***+++ |
| Confirm password | +++**Administrator5801@\***+++ |

<img src="./media/image75.png" style="width:6.5in;height:4.66458in" />

7.  Under **Licensing** section, select the checkbox **I confirm I have
    an eligible Windows 10/11 license with multi-tenant hosting
    rights**. Then, click on **Review + create** button.

<img src="./media/image76.png" style="width:6.5in;height:5.42639in" />

8.  Click on the **Create** button.

<img src="./media/image77.png" style="width:6.5in;height:5.18542in"
alt="A screenshot of a computer Description automatically generated" />

<img src="./media/image78.png" style="width:6.5in;height:3.04722in"
alt="A screenshot of a computer Description automatically generated" />

9.  The virtual machine is successfully created, click on the **Go to
    resource** button.

<img src="./media/image79.png" style="width:6.5in;height:3.16736in" />

10. You will be directed to the **vmtest1** virtual machine page.

<img src="./media/image80.png" style="width:6.5in;height:3.91736in"
alt="A screenshot of a computer Description automatically generated" />

**Note**: If you see **testvm1** virtual machine status is not ready.
Troubleshoot the issue… then wait for 10-15 minutes and reload the page.

11. In **testvm1** virtual machine page, navigate and click on
    **Connect** on the left side navigation menu, scroll down to
    **Native RDP** tile, and click on the **Download RDP file**.

<img src="./media/image81.png" style="width:6.5in;height:5.16181in" />

12. On **testvm1.rdp could harm your device. Do you want to keep it
    anyway?** dialog box, click on **Keep** button.

> <img src="./media/image82.png" style="width:6.5in;height:3.44722in"
> alt="A screenshot of a computer Description automatically generated" />

13. On **testvm1.rdp** file, click on **Open file** link.

> <img src="./media/image83.png" style="width:6.5in;height:2.81042in"
> alt="A screenshot of a computer Description automatically generated" />

14. On **The publisher of this remote connection can’t be identified. Do
    you want to connect anyway?** dialog box, click on **Connect**
    button.

> <img src="./media/image84.png" style="width:5.62787in;height:2.97652in"
> alt="A screenshot of a computer Description automatically generated" />

15. On **Enter your credentials** dialog box, enter the password (here,
    +++**Administrator5801@\***+++) and click on the **OK** button.

<img src="./media/image85.png" style="width:4.63989in;height:4.01872in"
alt="A screenshot of a computer Description automatically generated" />

16. On **The identity of the remote computer cannot be verified. Do you
    want to connect anyway?** dialog box, click on **Yes** button.

<img src="./media/image86.png" style="width:3.70189in;height:3.76859in"
alt="A screenshot of a computer error Description automatically generated" />

17. On the **Choose privacy settings for your device** page, click on
    **Next** couple of times and then click on **Accept** button as
    shown in the below images.

<img src="./media/image87.png" style="width:6.5in;height:4.59931in"
alt="A screenshot of a computer Description automatically generated" />

<img src="./media/image88.png" style="width:6.5in;height:4.58056in"
alt="A screenshot of a computer Description automatically generated" />

<img src="./media/image89.png" style="width:6.5in;height:4.61181in"
alt="A screenshot of a computer Description automatically generated" />

18. Go back to Microsoft Defender portal. In **Microsoft Defender**
    portal, navigate and click on **Settings**. In the **Settings**
    page, click on **Endpoints**.

<img src="./media/image90.png" style="width:6.5in;height:4.09167in"
alt="A screenshot of a computer Description automatically generated" />

19. In the **Endpoints** page, navigate to **Device management** section
    and then click on **Onboarding**.

20. Click on the dropdown under **Select operating system to start
    onboarding process** and select **Windows 10 and 11**.

<img src="./media/image91.png" style="width:6.5in;height:4.14306in"
alt="A screenshot of a computer Description automatically generated" />

21. Scroll down and click on the **Download onboarding package** button.

<img src="./media/image92.png" style="width:6.5in;height:4.15486in"
alt="A screenshot of a computer Description automatically generated" />

22. After the onboarding package is successfully downloaded, click on
    **Open file** link.

<img src="./media/image64.png" style="width:3.07644in;height:1.47718in"
alt="A search box with words Description automatically generated" />

23. Copy the Windows Command script

<img src="./media/image65.png" style="width:6.5in;height:4.23542in"
alt="A screenshot of a computer Description automatically generated" />

24. Go back to **testvm1** and paste the copied Windows Command Script
    on the desktop as shown in the below image.

<img src="./media/image93.png" style="width:6.5in;height:4.14722in" />

25. Right click on the script and select **Run as administrator**.

<img src="./media/image94.png" style="width:6.5in;height:4.625in" />

26. Type **Y** and press the **Enter** button to continue the onboarding
    process.

<img src="./media/image95.png" style="width:6.5in;height:4.27917in"
alt="A screenshot of a computer Description automatically generated" />

27. After onboarding the machine successfully on Defender for Endpoint,
    click on any key to continue the onboarding process.

<img src="./media/image96.png" style="width:6.5in;height:3.85694in" />

28. The onboarding of the **testvm1** usually takes **15-30 minutes**;
    therefore, continue with the next task.

29. After 15-30 minutes, close the **testvm1**, go back to Microsoft
    Defender portal and refresh the page, navigate and click
    on **Devices**, you'll see the **testvm1** was successfully
    onboarded in Microsoft Defender for Endpoint.

<img src="./media/image97.png" style="width:6.5in;height:4.11597in" />

## **Task 5: Onboarding testVM2 in Microsoft Defender for Endpoints**

> 1\. In the Azure portal search bar, type virtual machine, then
> navigate and click on **Virtual machines** under **Services**.

<img src="./media/image98.png" style="width:6.5in;height:4.04306in" />

2\. In the Virtual machines page, navigate and click on **Create**, then
click on **Azure virtual machine**.

<img src="./media/image99.png" style="width:6.5in;height:2.77361in"
alt="A screenshot of a computer Description automatically generated" />

3\. In **Create a virtual machine**, under the **Resource group** field,
select **RG-DOE** resource group. Then, navigate to **Instance details**
section, in the **Virtual machine name** field, enter +++**testvm2**+++.
In the **Region** field, ensure **EAST US** region is selected.

<img src="./media/image100.png" style="width:6.5in;height:5.31389in" />

5.  In the **Security type** field, click on the dropdown and select
    **Standard**. In the **Image** field, select **Windows 11 Pro,
    version 22H2 -x64 Gen2** from the dropdown.

<img src="./media/image101.png" style="width:6.5in;height:5.00972in" />

6.  Navigate to **Administrator account** section, enter the following
    details and leave all the field in the default state:

| Username         | +++**Admin5803**+++            |
|------------------|--------------------------------|
| Password         | +++**Administrator5801@\***+++ |
| Confirm password | +++**Administrator5801@\***+++ |

<img src="./media/image102.png" style="width:6.5in;height:4.45417in" />

7.  Under **Licensing** section, select the checkbox **I confirm I have
    an eligible Windows 10/11 license with multi-tenant hosting
    rights**. Then, click on **Review + create** button.

<img src="./media/image76.png" style="width:6.5in;height:5.42639in" />

8.  Click on the **Create** button.

<img src="./media/image103.png" style="width:6.5in;height:4.78194in"
alt="A screenshot of a computer Description automatically generated" />

<img src="./media/image104.png" style="width:6.5in;height:3.00833in"
alt="A screenshot of a computer Description automatically generated" />

9.  The virtual machine is successfully created, click on the **Go to
    resource** button.

<img src="./media/image105.png" style="width:6.5in;height:2.97014in"
alt="A screenshot of a computer Description automatically generated" />

**Note:** If you see **testvm2 virtual machine status is not ready.
Troubleshoot the issue**… then wait for 10-15 minutes and reload the
page.

10. In **testvm2** virtual machine page, navigate and click on
    **Connect** on the left side navigation menu, scroll down to
    **Native RDP** tile, and click on the **Download RDP file**.

<img src="./media/image106.png" style="width:6.5in;height:4.75069in" />

11. In **testvm2.rdp could harm your device. Do you want to keep it
    anyway?** dialog box, click on **Keep** button.

<img src="./media/image107.png" style="width:6.5in;height:2.16319in"
alt="A screenshot of a computer Description automatically generated" />

12. On **testvm2.rdp** file, click on **Open file** link.

> <img src="./media/image108.png" style="width:6.5in;height:1.93681in"
> alt="A screenshot of a computer Description automatically generated" />

13. On **The publisher of this remote connection can’t be identified. Do
    you want to connect anyway?** dialog box, click on **Connect**
    button.

> <img src="./media/image109.png" style="width:5.71958in;height:2.99319in"
> alt="A screenshot of a computer Description automatically generated" />

14. On **Enter your credentials** dialog box, enter the password (here,
    +++**Administrator5801@\***+++) and click on the **OK** button.

<img src="./media/image110.png" style="width:4.71074in;height:3.88531in"
alt="A screenshot of a computer screen Description automatically generated" />

15. On **The identity of the remote computer cannot be verified. Do you
    want to connect anyway?** dialog box, click on **Yes** button.

<img src="./media/image111.png" style="width:4.06874in;height:4.18547in"
alt="A screenshot of a computer error message Description automatically generated" />

16. On **Choose privacy settings for your device** page, click on
    **Next** couple of times and then click on **Accept** button as
    shown in the below images.

<img src="./media/image87.png" style="width:6.5in;height:4.31597in"
alt="A screenshot of a computer Description automatically generated" />

<img src="./media/image88.png" style="width:6.5in;height:4.28889in"
alt="A screenshot of a computer Description automatically generated" />

<img src="./media/image89.png" style="width:6.5in;height:4.34514in"
alt="A screenshot of a computer Description automatically generated" />

17. Go back to your VM and open the WindowsDefenderATPOnboardingPackage
    that you have downloaded in **Task 4, Step \#22**.

<img src="./media/image64.png" style="width:3.07644in;height:1.47718in"
alt="A search box with words Description automatically generated" />

18. Copy the Windows Command script.

<img src="./media/image65.png" style="width:6.5in;height:4.23542in"
alt="A screenshot of a computer Description automatically generated" />

19. Go back to **testvm2** and paste the copied Windows Command Script
    on the desktop as shown in the below image.

<img src="./media/image112.png" style="width:6.5in;height:4.18403in" />

20. Right click on the script and select **Run as administrator**.

<img src="./media/image113.png" style="width:6.5in;height:5.20278in"
alt="A screenshot of a computer Description automatically generated" />

21. Type **Y** and press the **Enter** button to continue the onboarding
    process.

<img src="./media/image114.png" style="width:6.5in;height:3.86736in"
alt="A screenshot of a computer Description automatically generated" />

22. After onboarding the machine successfully on Defender for Endpoint,
    click on any key to continue the onboarding process.

<img src="./media/image115.png" style="width:6.5in;height:3.18542in"
alt="A screenshot of a computer Description automatically generated" />

23. **Refresh** Microsoft Defender portal.

<img src="./media/image116.png" style="width:6.5in;height:4.21597in" />

30. The onboarding of the **testvm2** usually takes **15-30 minutes**;
    therefore, continue with the next task.

31. After 15-30 minutes, close the **testvm2**, go back to Microsoft
    Defender portal and refresh the page, navigate and click
    on **Devices**, you'll see the **testvm2** was successfully
    onboarded in Microsoft Defender for Endpoint.

<img src="./media/image117.png" style="width:6.5in;height:3.13472in"
alt="A screenshot of a computer Description automatically generated" />

32. Close all the VMs.

## Task 6: Create test account using Microsoft Entra ID

1.  Open a new tab and enter the following link:
    **https://admin.microsoft.com/AdminPortal/#/homepage**

<img src="./media/image118.png" style="width:6.5in;height:5.70208in" />

2.  Click on the Navigation menu represented by three horizontal bars,
    navigate and click on **Users**, then click on **Active users** as
    shown in the below image.

> <img src="./media/image119.png" style="width:6.5in;height:3.16528in" />

3.  In the **Active users** page, click on **Add a user**.

> <img src="./media/image120.png" style="width:6.5in;height:2.60417in"
> alt="A screenshot of a computer Description automatically generated" />

4.  Under **Set up the basics** pane, in the **First name** field, enter
    +++**Robert**+++, and in the **Last name** field, enter
    +++**Frost**+++. Navigate to **Username** field, and enter
    +++**bob**+++ as shown in the below image.

5.  Uncheck all the boxes, in the **Password** field, enter the
    following password: +++**Xof37931@**+++

| Username | **[bob@](mailto:bob@WWLx956024.onmicrosoft.com)** |
|----------|---------------------------------------------------|
| Password | +++**Xof37931@**+++                               |

6.  Click on the **Next** button.

**Note**: You can use the **Username** and **Password** of your choice,
kindly note them on a notepad as these are required in the upcoming
tasks.

> <img src="./media/image121.png" style="width:6.5in;height:4.25in"
> alt="A screenshot of a computer Description automatically generated" />
>
> <img src="./media/image122.png" style="width:6.5in;height:4.35764in"
> alt="A screenshot of a computer Description automatically generated" />

7.  In the **Product licenses** pane, navigate and select **Office 365
    E3** license checkbox and click on the **Next** button.

<img src="./media/image123.png" style="width:6.5in;height:4.90139in"
alt="A screenshot of a computer Description automatically generated" />

8.  In the **Optional settings** pane, enter the following details and
    click on the **Next** button. You can mentioned your address
    details.

| Job title          | +++Financial Analyst+++ |
|--------------------|-------------------------|
| Department         | +++Finance+++           |
| Office             | Alpine                  |
| Mobile phone       | XXX-XXX-XXXX            |
| Street Address     | Suite 215               |
| City               | Alpine                  |
| State or province  | Alabama                 |
| Zip or postal code | 35014                   |
| Country or region  | United States           |

<img src="./media/image124.png" style="width:6.5in;height:4.63889in"
alt="A screenshot of a computer Description automatically generated" />

<img src="./media/image125.png" style="width:6.5in;height:4.13056in"
alt="A screenshot of a computer Description automatically generated" />

9.  Review the details and click on the **Finish adding** button.

<img src="./media/image126.png" style="width:6.5in;height:5.21806in"
alt="A screenshot of a computer Description automatically generated" />

10. On **Robert Frost added to active users** pane, navigate and click
    on the **Close** button.

<img src="./media/image127.png" style="width:6.5in;height:4.81528in"
alt="A screenshot of a computer Description automatically generated" />

11. You’ll see that Robert Frost is added to the **Active users** page.

<img src="./media/image128.png" style="width:6.5in;height:2.84514in" />

## Task 7: Preparing the prerequisite on the testvm1 virtual machine

1\. Go back to Azure portal. In the Azure portal search bar, type
**virtual machines**, then navigate and click on **Virtual machines**
under **Services**.

<img src="./media/image129.png" style="width:6.5in;height:4.47083in"
alt="A screenshot of a computer Description automatically generated" />

2\. In the **Virtual machines** page, click on **testvm1**.

<img src="./media/image130.png" style="width:6.5in;height:3.1875in"
alt="A screenshot of a computer Description automatically generated" />

23. **vmtest1** virtual machine page will be opened.

<img src="./media/image80.png" style="width:6.5in;height:3.91736in"
alt="A screenshot of a computer Description automatically generated" />

24. In **testvm1** virtual machine page, navigate and click on
    **Connect** on the left side navigation menu, scroll down to
    **Native RDP** tile, and click on the **Download RDP file**.

<img src="./media/image81.png" style="width:6.5in;height:5.16181in" />

25. On the **testvm1.rdp could harm your device. Do you want to keep it
    anyway?** dialog box, click on **Keep** button.

> <img src="./media/image82.png" style="width:6.5in;height:3.44722in"
> alt="A screenshot of a computer Description automatically generated" />

26. On **testvm1.rdp** file, click on **Open file** link.

> <img src="./media/image83.png" style="width:6.5in;height:2.81042in"
> alt="A screenshot of a computer Description automatically generated" />

27. On **The publisher of this remote connection can’t be identified. Do
    you want to connect anyway?** dialog box, click on **Connect**
    button.

> <img src="./media/image84.png" style="width:5.62787in;height:2.97652in"
> alt="A screenshot of a computer Description automatically generated" />

28. On **Enter your credentials** dialog box, enter the password (here,
    +++**Administrator5801@\***+++) and click on the **OK** button.

<img src="./media/image85.png" style="width:4.59822in;height:4.01872in"
alt="A screenshot of a computer Description automatically generated" />

29. On **The identity of the remote computer cannot be verified. Do you
    want to connect anyway?** dialog box, click on **Yes** button.

<img src="./media/image86.png" style="width:3.70189in;height:3.76859in"
alt="A screenshot of a computer error Description automatically generated" />

30. After logging in to testvm1 virtual machine, open the Edge browser,
    then select **Start without your data** button \> **Confirm and
    Continue** button \> **Continue without this data** button \>
    **Confirm and start browsing** button \> **Finish** button as shown
    in the below
    images.<img src="./media/image131.png" style="width:6.5in;height:4.49028in" />

<img src="./media/image132.png" style="width:6.5in;height:4.70556in" />

<img src="./media/image133.png" style="width:6.5in;height:4.35347in" />

<img src="./media/image134.png" style="width:6.5in;height:4.37431in"
alt="A screenshot of a computer Description automatically generated" />

<img src="./media/image135.png" style="width:6.5in;height:4.67014in" />

31. Then, enter the following URL in the address bar:
    [**https://portal.office.com**](https://portal.office.com)

<img src="./media/image136.png" style="width:6.5in;height:4.67292in"
alt="A screenshot of a computer Description automatically generated" />

32. Sign in to the Microsoft 365 portal using the following details:

| Username | **bob@**            |
|----------|---------------------|
| Password | +++**Xof37931@**+++ |

<img src="./media/image137.png" style="width:6.5in;height:5.24792in"
alt="A screenshot of a computer Description automatically generated" />

<img src="./media/image138.png" style="width:5.61397in;height:4.48697in"
alt="A screenshot of a login box Description automatically generated" />

Note: If you see a dialog box **Sign in to Microsoft Edge**, then click
on **No, thanks** button.

33. Click on the **Next** button.

<img src="./media/image139.png"
style="width:5.47779in;height:5.21933in" />

34. In case, you see **Microsoft Authenticator -** **Start by getting
    the app** window, navigate and click on the **Next** button, else
    skip the steps from **\#34 to \#41**.

<img src="./media/image15.png" style="width:6.5in;height:3.45278in"
alt="A screenshot of a computer Description automatically generated" />

35. In **Microsoft Authenticator –** **Set up your account** window,
    click on the **Next** button.

<img src="./media/image16.png" style="width:6.5in;height:3.55972in"
alt="A screenshot of a computer Description automatically generated" />

36. **Scan the QR code** using the **Authenticator app** installed in
    your mobile phone and click on the **Next** button.

<img src="./media/image17.png" style="width:6.5in;height:4.29375in"
alt="A screenshot of a computer Description automatically generated" />

37. Enter the number in your mobile authenticator app and select
    **Yes**. In **testvm1**, click on the **Next** button.

<img src="./media/image18.png" style="width:6.5in;height:3.91042in"
alt="A screenshot of a computer error Description automatically generated" />

38. Click on the **Next** button.

<img src="./media/image19.png" style="width:6.5in;height:3.72083in"
alt="A screenshot of a computer Description automatically generated" />

39. Click on the **Done** button.

<img src="./media/image20.png" style="width:6.5in;height:3.11597in"
alt="A screenshot of a computer screen Description automatically generated" />

40. Enter the number again in your mobile authenticator app and select
    **Yes**..

<img src="./media/image21.png"
style="width:4.72741in;height:6.01974in" />

41. In the **Stay signed in?** window, click on the **Yes** button.

<img src="./media/image22.png"
style="width:5.6779in;height:4.85247in" />

42. In **Microsoft 365** page, navigate and click on **Install and
    more** dropdown, then click on **Install Microsoft 365 apps**.

<img src="./media/image140.png" style="width:6.5in;height:3.96111in" />

43. Click on **Install Office**.

<img src="./media/image141.png" style="width:6.5in;height:5.03056in" />

44. **OfficeSetup.exe** file will be downloaded, click on **Open file**
    link.

<img src="./media/image142.png" style="width:6.5in;height:3.70972in"
alt="A screenshot of a computer Description automatically generated" />

45. Wait for few minutes while Microsoft 365 and Office downloads.

<img src="./media/image143.png" style="width:6.5in;height:4.275in"
alt="A screenshot of a computer Description automatically generated" />

<img src="./media/image144.png" style="width:6.5in;height:3.62569in" />

**Note**: The installation will take around 10-20 minutes to complete.

46. On **You’re all set!** dialog box, click on the **Close** button.

<img src="./media/image145.png" style="width:6.5in;height:3.97361in" />

47. Click on the **Start menu** and then click on **Word** as shown in
    the below image.

<img src="./media/image146.png" style="width:6.5in;height:5.52569in" />

48. Click on **Sign in or create account** button.

<img src="./media/image147.png" style="width:6.5in;height:4.15972in" />

49. Login using the following details:

| Username | **bob@**            |
|----------|---------------------|
| Password | +++**Xof37931@**+++ |

<img src="./media/image148.png" style="width:6.5in;height:4.66528in"
alt="A screenshot of a computer Description automatically generated" />

<img src="./media/image149.png" style="width:6.5in;height:4.3625in" />

50. In case, you’re prompted to Approve sign in request, then enter the
    number in your mobile authenticator app and select **Yes**..

<img src="./media/image150.png"
style="width:6.25451in;height:6.03769in" />

51. On **Stay signed in to all your apps** dialog box, click on **OK**
    button.

<img src="./media/image151.png" style="width:6.5in;height:5.14653in" />

52. On **You’re all set** dialog box, click on **Done** button.

<img src="./media/image152.png" style="width:6.5in;height:5.50139in"
alt="A screenshot of a computer Description automatically generated" />

53. On the **Accept the license agreement** dialog box, click on
    **Accept** button.

<img src="./media/image153.png" style="width:6.5in;height:4.26944in"
alt="A screenshot of a computer Description automatically generated" />

54. On Your privacy matters dialog box, click on the **Close** button.

<img src="./media/image154.png" style="width:6.5in;height:4.14861in" />

## Task 8: Stop all the Virtual Machines

1\. In the Azure portal search box, type +++**virtual machines**+++,
then navigate and click on **Virtual machines** under **Services**.

<img src="./media/image155.png" style="width:6.5in;height:5.09861in"
alt="A screenshot of a computer Description automatically generated" />

2\. Click on **testvm1** virtual machine.

<img src="./media/image156.png" style="width:5.29212in;height:3.38286in"
alt="A screenshot of a computer Description automatically generated" />

3\. In the **testvm1** virtual machine page, navigate and click on the
**Stop** button.

<img src="./media/image157.png" style="width:6.5in;height:3.87986in"
alt="A screenshot of a computer Description automatically generated" />

3.  In **Stop this virtual machine** dialog box, click on the **Yes**
    button. Similarly, stop **TESTSERVER** and **testvm2** virtual
    machines.

<img src="./media/image158.png" style="width:6.5in;height:3.31875in"
alt="A screenshot of a computer Description automatically generated" />

**Summary**

In this lab, you’ve assigned the Owner role to the Azure subscription,
then you’ve created and onboarded Windows Server and Windows 11 Pro
virtual machines (testserver1, testVM1, and testVM2) to Microsoft
Defender for Endpoints, bolstering security with real-time monitoring
and threat response capabilities across different VM types. Then, you’ve
created a test user account (Robert Frost) with an Office 365 license.
Finally, you’ve installed Microsoft 365 apps and configured necessary
settings.
