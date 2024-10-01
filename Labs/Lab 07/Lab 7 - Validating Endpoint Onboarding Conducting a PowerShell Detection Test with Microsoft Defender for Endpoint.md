**Lab 2 - Validating Endpoint Onboarding: Conducting a PowerShell
Detection Test with Microsoft Defender for Endpoint**

**Introduction**

To verify that the device is properly onboarded and reporting to the
service, run the detection script on the newly onboarded device. If
successful, the new alert will appear in a few minutes.

**Objective**

- To verify the successful onboarding of Microsoft Defender for Endpoint
  on Windows 11 and Windows Server 2019 devices by conducting a
  PowerShell detection test.

# Exercise 1: Run a detection test on a newly onboarded Microsoft Defender for Endpoint devices

## Task 1: Verify Microsoft Defender for End point onboarding of a Windows 11 device using a PowerShell detection test

1\. In Azure portal search bar, type virtual machines, then click on
Virtual machines under Services.

<img src="./media/image1.png" style="width:6.5in;height:2.25278in" />

2\. In the **Virtual machines** page, navigate and click on **testvm2**.

<img src="./media/image2.png" style="width:6.5in;height:3.02431in" />

3\. On the **testvm2** page, if your virtual machine is stopped, then
click on the **Start** button as shown in the below image.

<img src="./media/image3.png" style="width:6.5in;height:3.62986in" />

4\. In **testvm2** virtual machine page, navigate and click on
**Connect** on the left side navigation menu, scroll down to **Native
RDP** tile, and click on the **Download RDP file**.

<img src="./media/image4.png" style="width:6.5in;height:4.75069in" />

5\. In **testvm2.rdp could harm your device. Do you want to keep it
anyway?** dialog box, click on **Keep** button.

<img src="./media/image5.png" style="width:6.5in;height:2.16319in"
alt="A screenshot of a computer Description automatically generated" />

6.  On **The publisher of this remote connection can’t be identified. Do
    you want to connect anyway?** dialog box, click on **Connect**
    button.

> <img src="./media/image6.png" style="width:5.71958in;height:2.99319in"
> alt="A screenshot of a computer Description automatically generated" />

7.  On **Enter your credentials** dialog box, enter the password (here,
    **Administrator5801@\***) and click on the **OK** button.

<img src="./media/image7.png" style="width:4.71074in;height:3.88531in"
alt="A screenshot of a computer screen Description automatically generated" />

8.  On **The identity of the remote computer cannot be verified. Do you
    want to connect anyway?** dialog box, click on **Yes** button.

<img src="./media/image8.png" style="width:4.06874in;height:4.18547in"
alt="A screenshot of a computer error message Description automatically generated" />

9.  Type **cmd** in the windows search bar, navigate to **Command
    Prompt**, select **Run as administrator**.

<img src="./media/image9.png" style="width:6.5in;height:4.21042in" />

10. In the command prompt, enter the following code and press the
    **Enter** button.

<span class="mark">Copycode</span>

powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden
\$ErrorActionPreference= 'silentlycontinue';(New-Object
System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe',
'C:\\test-WDATP-test\\invoice.exe');Start-Process
'C:\\test-WDATP-test\\invoice.exe'

11. The Command Prompt window closes automatically. Wait for 5-10
    minutes. If successful, a new alert appears in the portal for the
    onboarded device.

<img src="./media/image10.png" style="width:6.5in;height:2.36875in"
alt="A screenshot of a computer Description automatically generated" />

12. Go back to **Microsoft Defender** portal and refresh the page.
    Navigate and click on **Incidents & alerts**, then click on
    **Alerts**. You’ll see the Alerts related to the execution of
    **Suspicious PowerShell Command**.

<img src="./media/image11.png" style="width:6.5in;height:4.08681in" />

## Task 2: Verify Microsoft Defender for Endpoint onboarding of a Windows Server 2019 server device using a PowerShell detection test

> 1\. In the Azure portal search bar, type virtual machine, then
> navigate and click on **Virtual machines** under **Services**.
>
> <img src="./media/image12.png" style="width:6.5in;height:4.60417in"
> alt="A screenshot of a computer Description automatically generated" />
>
> 2\. In the **Virtual machines** page, navigate and click on
> **TESTSERVER1.**

<img src="./media/image13.png" style="width:6.5in;height:2.85069in"
alt="A screenshot of a computer Description automatically generated" />

3\. Click on the **Start** button if the VM is stopped.

<img src="./media/image14.png" style="width:6.5in;height:3.51389in"
alt="A screenshot of a computer Description automatically generated" />

4\. In **TESTSERVER1** virtual machine page, navigate and click on
**Connect** on the left side navigation menu, then click on **Select**
under **Native RDP** section.

<img src="./media/image15.png" style="width:6.5in;height:4.68194in"
alt="A screenshot of a computer Description automatically generated" />

5.  On **TESTSERVER1.rdp could harm your device. Do you want to keep it
    anyway?** dialog box, click on **Keep** button.

> <img src="./media/image16.png" style="width:3.95085in;height:1.48946in"
> alt="A screenshot of a computer Description automatically generated" />

6.  On **TESTSERVER1.rdp** file, click on **Open file** link.

> <img src="./media/image17.png" style="width:6.5in;height:4.04375in" />

7.  On **The publisher of this remote connection can’t be identified. Do
    you want to connect anyway?** dialog box, click on **Connect**
    button.

> <img src="./media/image18.png" style="width:5.1026in;height:2.69304in"
> alt="A screenshot of a computer Description automatically generated" />

8.  On **Enter your credentials** dialog box, enter the password (here,
    **Administrator5801@\***) and click on the **OK** button.

<img src="./media/image19.png"
style="width:4.42726in;height:3.87698in" />

9.  On **The identity of the remote computer cannot be verified. Do you
    want to connect anyway?** dialog box, click on **Yes** button.

<img src="./media/image20.png"
style="width:3.77693in;height:3.8603in" />

10. The TESTSERVER1 VM will be opened. Minimize the **Server Manager –
    Dashboard**.

<img src="./media/image21.png" style="width:6.5in;height:3.83681in"
alt="A screenshot of a computer Description automatically generated" />

11. Type **cmd** in the windows search bar, navigate to **Command
    Prompt** and right click on it, then select **Run as
    administrator**.

<img src="./media/image22.png" style="width:6.5in;height:5.2875in" />

12. In the command prompt, enter the following code and press the
    **Enter** button.

<span class="mark">Copy code</span>

**powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden
\$ErrorActionPreference= 'silentlycontinue';(New-Object
System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe',
'C:\\test-WDATP-test\\invoice.exe');Start-Process
'C:\\test-WDATP-test\\invoice.exe'**

13. The Command Prompt window closes automatically. Wait for 5-10
    minutes. If successful, a new alert appears in the portal for the
    onboarded device.

<img src="./media/image23.png" style="width:6.5in;height:1.675in"
alt="A screenshot of a computer Description automatically generated" />

14. Go back to **Microsoft Defender** portal and refresh the page.
    Navigate and click on **Incidents & alerts**, then click on
    **Alerts**. You’ll see the Alerts related to the execution of
    **Suspicious PowerShell Command**.

<img src="./media/image24.png" style="width:6.5in;height:3.03958in" />

**Summary**

In this lab, you’ve executed a PowerShell detection test on the
onboarded Windows 11 and Windows Server 2019 devices and checked the
generated alerts to validate endpoint onboarding.
