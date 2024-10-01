# Lab 8 - Manage Device Enrollment into Microsoft Intune

**Summary**

In this lab, you prepare for device management using Microsoft Intune by
reviewing and assigning licenses, configuring Windows automatic
enrollment, and configuring enrollment restrictions.

**Prerequisites**

To following lab(s) must be completed before this lab:

- Lab \#1-Managing Identities in Microsoft Entra ID

- Lab \#2-Synchronizing Identities by using Microsoft Entra Connect

**Note**: You will also need a mobile phone that can receive text
messages used to secure Windows Hello sign in authentication to Entra
ID.

**Scenario**

You need to prepare for device management using Microsoft Intune. First
of all, you need to ensure that users are assigned appropriate licenses
for device management. As a verification test, you will assign Aaron
Nicholls the required licenses. You also need to ensure that any Windows
device that is joined or registered to Microsoft Entra ID will
automatically be enrolled into Intune. You have also been asked to
ensure that members of the Sales group are restricted from enrolling
personal Android and iOS devices into Intune and that the Enrollment
Device Limit is increased to 10 devices. Finally, you need to configure
Allan Deyoung as a Device enrollment manager to allow him to enroll 1000
devices.

**Task 1: Review and assign licenses for device management**

1.  On [<u>SEA-SVR1</u>](https://labclient.labondemand.com/Instructions/e7cc4ae1-e3d9-4c55-accc-696f537e1e17?rc=10),
    navigate to **Microsoft Entra admin center** window, navigate and
    click on **Identity**.

<img src="./media/image1.png" style="width:6.26806in;height:3.72986in"
alt="A screenshot of a computer Description automatically generated" />

2.  Navigate and select **Billing**, then click on **Licenses**.

<img src="./media/image2.png"
style="width:6.26806in;height:4.30278in" />

3.  In the **Licenses \| Overview** page, navigate and click on **All
    products**. Take note of the licenses that are available in the
    tenant.

<img src="./media/image3.png"
style="width:6.26806in;height:3.91389in" />

<img src="./media/image4.png" style="width:6.26806in;height:2.99653in"
alt="A screenshot of a computer Description automatically generated" />

4.  Select and click on **Enterprise Mobility + Security E5**. Notice
    all the users that have been assigned this license. You can assign
    and remove licenses from this location.

<img src="./media/image5.png"
style="width:6.26806in;height:3.48611in" />

<img src="./media/image6.png"
style="width:6.26806in;height:3.65903in" />

5.  Under **General**, select **Service plan details**. Take note of the
    services included in the Enterprise Mobility + Security E5 license.
    Microsoft Intune is one of the supported services for this license.

<img src="./media/image7.png"
style="width:6.26806in;height:5.42431in" />

6.  In the **Microsoft Entra admin center** navigation pane,
    select **Users**.

<img src="./media/image8.png" style="width:6.26806in;height:3.64722in"
alt="A screenshot of a computer Description automatically generated" />

7.  Search and select !!**Cindy White**!!

<img src="./media/image9.png" style="width:6.26806in;height:3.80347in"
alt="A screenshot of a computer Description automatically generated" />

8.  On **Cindy White user** page, click on **Edit properties**.

<img src="./media/image10.png" style="width:6.26806in;height:3.98056in"
alt="A screenshot of a computer Description automatically generated" />

9.  Click on **Settings** tab.
    <img src="./media/image11.png" style="width:6.26806in;height:4.48681in"
    alt="A screenshot of a computer Description automatically generated" />

10. Under **Settings**, in the **Usage location** field, select **United
    States** and then select **Save**.

<img src="./media/image12.png"
style="width:6.26806in;height:5.31875in" />

*<span class="mark">**Note**: Before you can assign a license to a user,
the user must have a usage location set.</span>*

11. In the Cindy White user navigation pane, select **Licenses**, then
    click on **+Assignments.**

<img src="./media/image13.png"
style="width:6.26806in;height:4.46389in" />

12. In the **Update license assignments** page, select both **Enterprise
    Mobility + Security E5** and **Office 365 E5**, and then
    select **Save**.

<img src="./media/image14.png"
style="width:6.26806in;height:5.58958in" />

**Task 2: Setting Password of the user utilizing PowerShell**

1.  In [**<u>SEA-SVR1</u>**](urn:gd:lg:a:select-vm), right-click on
    **Start button**, and then select **Windows PowerShell (Admin)**.

<img src="./media/image15.png"
style="width:3.10234in;height:5.71183in" />

2.  On **User Account Control** dialog box, select **Yes**.

<img src="./media/image16.png"
style="width:4.30219in;height:3.5268in" />

3.  In the **Windows PowerShell** window, type the following command,
    and then press **Enter**:

!!**Connect-MsolService**!!

<img src="./media/image17.png" style="width:6.26806in;height:1.42222in"
alt="A computer screen with white text Description automatically generated" />

4.  In the **Sign in to your account** dialog box, sign in using the
    Office 365 Tenant credentials from the Home tab.

**<span class="mark">Note – If you had been prompted to change the
Tenant admin credentials password, ensure to provide the updated
password</span>.**

<img src="./media/image18.png" style="width:3.82292in;height:3.07292in"
alt="A screenshot of a computer Description automatically generated" />

<img src="./media/image19.png" style="width:3.99749in;height:2.36579in"
alt="A screenshot of a computer screen Description automatically generated" />

5.  In the **Windows PowerShell** window, type the following command to
    reset the passwords of the **Cindy White**

!!**Get-MsolUser \| Where-Object DisplayName -EQ "Cindy White" \|
Set-MsolUserPassword -NewPassword P@55w.rd1234 -ForceChangePassword
\$false**!!

<img src="./media/image20.png" style="width:6.26806in;height:1.44653in"
alt="A computer screen shot of a program Description automatically generated" />

**Task 3: Enable Windows Automatic Enrollment into Microsoft Intune**

1.  In **SEA-SVR1**, open a new tab in **Microsoft Edge**, and then in
    the address bar type !!**https://Endpoint.microsoft.com**!! and then
    press **Enter**. If prompted to sign in, provide the Credential of
    the **Office 365 Tenant Admin**.

2.  In the Microsoft Intune admin center, select **Devices**.

<img src="./media/image21.png" style="width:6.26806in;height:4.59653in"
alt="A screenshot of a computer Description automatically generated" />

3.  Navigate and click on **Enrollment**. Ensure that **Windows** tab is
    select, then navigate to **Enrollment options** section and click on
    **Automatic Enrollment**.

<img src="./media/image22.png"
style="width:6.26806in;height:4.15278in" />

4.  On the **MDM user scope** row, select **All** radio button and then
    select **Save**.

<img src="./media/image23.png"
style="width:5.79462in;height:6.06976in" />

5.  Click on **Devices \| Enrollment** link as shown in the below image.

<img src="./media/image24.png"
style="width:4.80245in;height:6.0781in" />

<span class="mark">**Note**: By performing this step, you enabled
automatic enrollment into Intune for any User that performs an Azure AD
join with a Windows device.</span>

**Task 4: Configure Enrollment Restrictions**

1.  Navigate to **Devices onboarding** section and click on
    **Enrollment**. Then, click on **Android** tab as shown in the below
    image.

<img src="./media/image25.png"
style="width:6.26806in;height:3.95833in" />

2.  Scroll down to **Enrollment options** section and click on **Device
    platform restriction**.

<img src="./media/image26.png"
style="width:6.26806in;height:3.99931in" />

3.  Select **Android restrictions** tab, then select +**Create
    restriction**.

<img src="./media/image27.png"
style="width:6.26806in;height:3.66528in" />

<img src="./media/image28.png"
style="width:6.26806in;height:3.46319in" />

4.  On the **Create restriction** page, in the **Name** box,
    enter !!**Android Personal Device Restriction**!! Select **Next**.

<img src="./media/image29.png"
style="width:6.26806in;height:4.8875in" />

5.  On the Platform settings page, under **Personally owned**,
    select **Block** for the following device types and click on the
    **Next** button:

    - Android Enterprise (work profile)

    - Android device administrator

<img src="./media/image30.png"
style="width:6.26806in;height:3.95417in" />

6.  On the **Scope tags** page, select **Next**.

<img src="./media/image31.png" style="width:6.26806in;height:5.46944in"
alt="A screenshot of a computer Description automatically generated" />

7.  On the **Assignments** page, under **Included groups**, select **Add
    groups**.

<img src="./media/image32.png" style="width:6.26806in;height:5.42917in"
alt="A screenshot of a computer Description automatically generated" />

8.  In **Select groups to include** pane **Search bar**, type and select
    **Sales**, then click on the **Select** button.

<img src="./media/image33.png" style="width:6.26806in;height:5.70972in"
alt="A screenshot of a computer Description automatically generated" />

9.  In the **Assignments** tab, click on the **Next** button.

<img src="./media/image34.png" style="width:6.26806in;height:5.35486in"
alt="A screenshot of a computer Description automatically generated" />

10. On the **Review + create** page, select **Create**.

<img src="./media/image35.png" style="width:6.26806in;height:4.96736in"
alt="A screenshot of a computer Description automatically generated" />

<span class="mark">Notice the Android Personal Device Restriction
assigned with a priority of 1.</span>

<img src="./media/image36.png" style="width:6.26806in;height:3.57847in"
alt="A screenshot of a computer Description automatically generated" />

11. In the **Devices \| Enrollment** page, in the **Windows** tab,
    navigate to **Enrollment options** section and click on the **Device
    limit restriction**.

<img src="./media/image37.png" style="width:6.26806in;height:4.12917in"
alt="A screenshot of a computer Description automatically generated" />

<span class="mark">Notice that there is a Default device limit
restriction that is assigned to All Users. This default restriction sets
a device enrollment limit to 5 devices per user.</span>

12. In the **Enrollment device limit restrictions**, select + **Create
    restriction**.

<img src="./media/image38.png" style="width:6.26806in;height:3.57847in"
alt="A screenshot of a computer Description automatically generated" />

13. On the Create restriction page, in the **Name** box, enter !!**Sales
    Device Enrollment Limit**!! Select **Next**.

<img src="./media/image39.png" style="width:6.26806in;height:5.41042in"
alt="A screenshot of a computer Description automatically generated" />

14. On the **Device limit** page, select **10**, and then
    select **Next**.

<img src="./media/image40.png" style="width:6.26806in;height:5.42014in"
alt="A screenshot of a computer Description automatically generated" />

15. On the **Scope tags** page, select **Next**.

<img src="./media/image41.png" style="width:6.26806in;height:5.44028in"
alt="A screenshot of a computer Description automatically generated" />

16. On the **Assignments** page, under **Included groups**, select **Add
    groups**.

<img src="./media/image42.png" style="width:6.26806in;height:5.42153in"
alt="A screenshot of a computer Description automatically generated" />

17. In the **Select groups to include** page search box type and select
    **Sales** and then click on **Select** button.

<img src="./media/image43.png"
style="width:6.26806in;height:5.66875in" />

18. Click on the **Next** button.

<img src="./media/image44.png" style="width:6.26806in;height:5.47083in"
alt="A screenshot of a computer Description automatically generated" />

19. On the **Review + create** page, select **Create**.

<img src="./media/image45.png" style="width:6.26806in;height:5.46319in"
alt="A screenshot of a computer Description automatically generated" />

20. Reload the page. Notice the Sales Device Enrollment Limit,
    configured with a Device limit of 10 and assigned with a priority of
    1.

<img src="./media/image46.png" style="width:6.26806in;height:3.51528in"
alt="A screenshot of a computer Description automatically generated" />

**Task 5: Configure a Device enrollment manager**

1.  In the **Microsoft Intune admin center**, select **Devices**.

<img src="./media/image47.png"
style="width:6.26806in;height:4.51528in" />

2.  Navigate to **Device onboarding** section and click on
    **Enrollment**, then click on **Device enrolment managers** tab.

<img src="./media/image48.png"
style="width:6.26806in;height:3.64583in" />

3.  On the **Enroll devices** pane, select **Device enrollment
    managers**.

<span class="mark">Notice that, by default, there are no Device
enrollment managers configured.</span>

4.  On the **Enroll devices\|Device enrollment managers** page,
    select **Add**.

<img src="./media/image49.png" style="width:6.26806in;height:3.64028in"
alt="A screenshot of a computer Description automatically generated" />

5.  In the **Add user** page, under User name, enter the email address
    of Allan [DeYoung
     !!**AllanD@M365xXXXXXXX.onmicrosoft.com**](mailto:DeYoung !!AllanD@M365xXXXXXXX.onmicrosoft.com)!!
     (substitute **XXXXXX** with your tenant name) and then
    select **Add**.

<img src="./media/image50.png" style="width:6.26806in;height:3.64653in"
alt="A screenshot of a computer Description automatically generated" />

**<span class="mark">Allan is now allowed to enroll up to 1000
devices.</span>**

6.  In the Microsoft Intune admin center, in the navigation pane,
    select **Home**.

<img src="./media/image51.png" style="width:6.26806in;height:3.14514in"
alt="A screenshot of a computer Description automatically generated" />

7.  Close Microsoft Edge.

**Results**: After completing this exercise, you will have successfully
reviewed and assigned licenses, configured Windows automatic enrollment,
enabled and assigned enrollment restrictions, and configured a Device
enrollment manager.
