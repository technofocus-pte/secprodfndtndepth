# **Lab 2 - Validating Endpoint Onboarding: Conducting a PowerShell
Detection Test with Microsoft Defender for Endpoint**

**Introduction**

To verify that the device is properly onboarded and reporting to the
service, run the detection script on the newly onboarded device. If
successful, the new alert will appear in a few minutes.

**Objective**

- To verify the successful onboarding of Microsoft Defender for Endpoint
  on Windows 11 and Windows Server 2019 devices by conducting a
  PowerShell detection test.

## Exercise 1: Run a detection test on a newly onboarded Microsoft Defender for Endpoint devices

## Task 1: Verify Microsoft Defender for End point onboarding of a Windows 11 device using a PowerShell detection test

1. In Azure portal search bar, type virtual machines, then click on
Virtual machines under Services.

![](./media/image1.png)

2. In the **Virtual machines** page, navigate and click on **testvm2**.

![](./media/image2.png)

3. On the **testvm2** page, if your virtual machine is stopped, then
click on the **Start** button as shown in the below image.

![](./media/image3.png)

4. In **testvm2** virtual machine page, navigate and click on
**Connect** on the left side navigation menu, scroll down to **Native
RDP** tile, and click on the **Download RDP file**.

![](./media/image4.png)

5. In **testvm2.rdp could harm your device. Do you want to keep it
anyway?** dialog box, click on **Keep** button.

![A screenshot of a computer Description automatically
generated](./media/image5.png)

6.  On **The publisher of this remote connection can’t be identified. Do
    you want to connect anyway?** dialog box, click on **Connect**
    button.

 ![A screenshot of a computer Description automatically
 generated](./media/image6.png)

7.  On **Enter your credentials** dialog box, enter the password (here,
    **Administrator5801@***) and click on the **OK** button.

![A screenshot of a computer screen Description automatically
generated](./media/image7.png)

8.  On **The identity of the remote computer cannot be verified. Do you
    want to connect anyway?** dialog box, click on **Yes** button.

![A screenshot of a computer error message Description automatically
generated](./media/image8.png)

9.  Type **cmd** in the windows search bar, navigate to **Command
    Prompt**, select **Run as administrator**.

![](./media/image9.png)

10. In the command prompt, enter the following code and press the
    **Enter** button.

Copycode

powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden
$ErrorActionPreference= 'silentlycontinue';(New-Object
System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe',
'C:test-WDATP-testinvoice.exe');Start-Process
'C:test-WDATP-testinvoice.exe'

11. The Command Prompt window closes automatically. Wait for 5-10
    minutes. If successful, a new alert appears in the portal for the
    onboarded device.

![A screenshot of a computer Description automatically
generated](./media/image10.png)

12. Go back to **Microsoft Defender** portal and refresh the page.
    Navigate and click on **Incidents & alerts**, then click on
    **Alerts**. You’ll see the Alerts related to the execution of
    **Suspicious PowerShell Command**.

![](./media/image11.png)

## Task 2: Verify Microsoft Defender for Endpoint onboarding of a Windows Server 2019 server device using a PowerShell detection test

 1. In the Azure portal search bar, type virtual machine, then
 navigate and click on **Virtual machines** under **Services**.

 ![A screenshot of a computer Description automatically
 generated](./media/image12.png)

 2. In the **Virtual machines** page, navigate and click on
 **TESTSERVER1.**

![A screenshot of a computer Description automatically
generated](./media/image13.png)

3. Click on the **Start** button if the VM is stopped.

![A screenshot of a computer Description automatically
generated](./media/image14.png)

4. In **TESTSERVER1** virtual machine page, navigate and click on
**Connect** on the left side navigation menu, then click on **Select**
under **Native RDP** section.

![A screenshot of a computer Description automatically
generated](./media/image15.png)

5.  On **TESTSERVER1.rdp could harm your device. Do you want to keep it
    anyway?** dialog box, click on **Keep** button.

 ![A screenshot of a computer Description automatically
 generated](./media/image16.png)

6.  On **TESTSERVER1.rdp** file, click on **Open file** link.

 ![](./media/image17.png)

7.  On **The publisher of this remote connection can’t be identified. Do
    you want to connect anyway?** dialog box, click on **Connect**
    button.

 ![A screenshot of a computer Description automatically
 generated](./media/image18.png)

8.  On **Enter your credentials** dialog box, enter the password (here,
    **Administrator5801@***) and click on the **OK** button.

![](./media/image19.png)

9.  On **The identity of the remote computer cannot be verified. Do you
    want to connect anyway?** dialog box, click on **Yes** button.

![](./media/image20.png)

10. The TESTSERVER1 VM will be opened. Minimize the **Server Manager –
    Dashboard**.

![A screenshot of a computer Description automatically
generated](./media/image21.png)

11. Type **cmd** in the windows search bar, navigate to **Command
    Prompt** and right click on it, then select **Run as
    administrator**.

![](./media/image22.png)

12. In the command prompt, enter the following code and press the
    **Enter** button.

Copy code

**powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden
$ErrorActionPreference= 'silentlycontinue';(New-Object
System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe',
'C:test-WDATP-testinvoice.exe');Start-Process
'C:test-WDATP-testinvoice.exe'**

13. The Command Prompt window closes automatically. Wait for 5-10
    minutes. If successful, a new alert appears in the portal for the
    onboarded device.

![A screenshot of a computer Description automatically
generated](./media/image23.png)

14. Go back to **Microsoft Defender** portal and refresh the page.
    Navigate and click on **Incidents & alerts**, then click on
    **Alerts**. You’ll see the Alerts related to the execution of
    **Suspicious PowerShell Command**.

![](./media/image24.png)

**Summary**

In this lab, you’ve executed a PowerShell detection test on the
onboarded Windows 11 and Windows Server 2019 devices and checked the
generated alerts to validate endpoint onboarding.
