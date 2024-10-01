# Lab 1 - Configuring Hybrid Identity with Microsoft Entra ID, Password Hash Sync, and Multi-Factor Authentication

## Objective:

In this lab we will first redeem a pass for an Azure subscription.

When Entra ID tenants are created, they receive a onmicrosoft.com tenant
domain. In the real suppose you have just purchased a new domain that
resides in Microsoft Azure but not in Adatum's on-premises environment.
In this lab we will manually create the necessary DNS records required
by this new custom domain and then integrate a single AD forest using
Password Hash Sync (PHS). We will also enable MFS and add basic
conditional access policy.

## Exercise 1 – Prerequisites

### Task 1 – Redeem the Azure Pass

1.  Log into the **LON-CL1** with the credentials provided in the
    Resources tab of your lab.

<img src="./media/image1.png"
style="width:2.83423in;height:5.78907in" />

2.  **Note the Tenant Credentials** and the **PromoCode** provided on
    the resources tab of your lab environment.

<img src="./media/image2.png" style="width:2.91671in;height:5.958in" />
<img src="./media/image3.png"
style="width:2.90017in;height:5.92423in" />

3.  Open a browser on the Lab VM in **incognito/InPrivate** mode and
    navigate to: **+++http://www.microsoftazurepass.com/+++**. Click
    the **Start** button.

<img src="./media/image4.png" style="width:6.26806in;height:3.54722in"
alt="A person sitting on a couch using a computer Description automatically generated" />

> <span class="mark">**Note**: Do not use your Company/Work Account to
> login to redeem the Azure Pass, another Azure Pass will not be
> issued.</span>

4.  Enter the **Office 365 tenant credentials** given on the Resources
    page of your lab environment and select "**Sign In**".

5.  Click "**Confirm Microsoft Account**" if the email address is
    correct.

<img src="./media/image5.png" style="width:6.26806in;height:3.54722in"
alt="A screenshot of a computer Description automatically generated" />

6.  Paste the promo code given on the **Resources** page of your lab
    environment in the **Enter Promo code box,** enter the captcha and
    select **Submit** button.

<img src="./media/image6.png" style="width:6.26806in;height:3.54722in"
alt="A screenshot of a computer Description automatically generated" />

7.  If asked login with your tenant credentials again. It may take few
    seconds to process the redemption.

8.  Enter the mandatory profile information. Select the check box – **I
    agree to the subscription agreement, offer details.**, and then
    select **Sign up**.

<img src="./media/image7.png" style="width:6.26806in;height:3.54722in"
alt="A screenshot of a computer Description automatically generated" />

9.  On the feedback page, click on **Submit**.

<img src="./media/image8.png" style="width:6.26806in;height:3.57361in"
alt="A screenshot of a computer Description automatically generated" />

10. It would automatically redirect you to the **Azure Portal** and now
    you are ready to use Azure services.

11. Click on **Subscriptions** to verify that your new subscription is
    listed in the list of active subscriptions.

<img src="./media/image9.png" style="width:6.26806in;height:3.54722in"
alt="A screenshot of a computer Description automatically generated" />

## Exercise 2 – Integrate a single AD forest using Password Hash Sync (PHS)

### Task 1 – Install Azure AD Connect 

**Password Hash Sync (PHS) **

Password hash synchronization is one of the sign-in methods used to
accomplish hybrid identity. Azure AD Connect synchronizes a hash, of the
hash, of a user's password from an on-premises Active Directory instance
to a cloud-based Microsoft Entra instance. 

Password hash synchronization is an extension to the directory
synchronization feature implemented by Azure AD Connect sync. You can
use this feature to sign in to Azure AD services like Microsoft 365. You
sign in to the service by using the same password you use to sign in to
your on-premises Active Directory instance. 

Password hash synchronization helps by reducing the number of passwords,
your users need to maintain to just one. Password hash synchronization
can: 

- Improve the productivity of your users.

- Reduce your helpdesk costs.

1.  Switch to the **LON-DC1** machine in the lab environment.

2.  Sign in with the username and the password given in the resources
    tab of your environment.

<!-- -->

12. Open a browser and navigate to
    **+++https://entra.microsoft.com/+++** and login using the admin
    tenant credentials.

13. In the **Microsoft Entra admin center** navigate to **Identity**
    then expand **Users**, click **All Users** then click on **New
    User** then click on **Create new user**.

<img src="./media/image10.png" style="width:6.5in;height:3.67917in" />

14. Enter the following information under **Basics**: 

- **User principal name**: **+++meconnect+++**

- **Display name**: **+++MEConnect+++**

- **First name**: Blank 

- **Last name**: Blank 

- **Password**: uncheck Auto-generate password and provide
  **+++Pa\$\$.w0rd@MS01+++**

<img src="./media/image11.png" style="width:6.5in;height:3.66528in"
alt="A screenshot of a computer Description automatically generated" />

15. Under **Properties**, scroll down and select **United States** as
    **Usage location**.

<img src="./media/image12.png" style="width:6.5in;height:3.67917in" />

16. Under the **Assignment** tab, select **Add role**.

<img src="./media/image13.png" style="width:6.5in;height:3.67917in"
alt="A screenshot of a computer Description automatically generated" />

17. Select **Global Administrator** and click **Select**.

<img src="./media/image14.png" style="width:6.5in;height:3.67917in"
alt="A screenshot of a computer Description automatically generated" />

18. Then select **Review + Create**.

<img src="./media/image15.png" style="width:6.5in;height:3.67917in" />

19. Note the **User principal name** and **Password**, and then select
    **Create**.

<img src="./media/image16.png" style="width:6.5in;height:3.67917in"
alt="A screenshot of a computer Description automatically generated" />

20. Open an In Private / Incognito session in your browser and login to
    **+++https://entra.microsoft.com/+++** as the user you created i.e.
    **meconnect** with the password **+++Pa\$\$.w0rd@MS01+++** that you
    noted down in the previous step.

21. When prompted, update the password to **+++Pa\$\$.w0rd@123+++**.
    Then select **Sign in**.

<img src="./media/image17.png" style="width:3.38889in;height:3.58333in"
alt="A screenshot of a login page Description automatically generated" />

22. Open a browser and navigate to the URL —
    **+++https://www.microsoft.com/en-us/download/details.aspx?id=47594+++**

23. Click **Download** and then select **Open file**.

<img src="./media/image18.png" style="width:6.5in;height:4.50625in"
alt="A screenshot of a computer Description automatically generated" />

24. Once installed, the **Microsoft Azure AD Connect** configuration
    will start. select the **Terms & Conditions** check box and click
    **Continue**.

<img src="./media/image19.png"
style="width:5.87127in;height:3.92077in" /> 

25. On the **Express Settings** page click **Customize**. 

<img src="./media/image20.png" style="width:5.90098in;height:3.94058in"
alt="A screenshot of a computer Description automatically generated" />

26. On the Install required components page click **Install**. 

<img src="./media/image21.png" style="width:5.89164in;height:3.95048in"
alt="A screenshot of a computer Description automatically generated" />

27. At the **User sign-in** page, choose **Password Hash
    Synchronization** as the **Sign On method** and click **Next**. We
    will use the MEConnect user we had created in the **Azure portal**
    to continue the installation process of **ADConnect**.

<img src="./media/image22.png" style="width:5.88202in;height:3.93125in"
alt="A screenshot of a computer Description automatically generated" />

28. In the Username enter **+++meconnect@+++** and paste Tenant name and
    for the password enter **+++Pa\$\$.w0rd@123+++**. Then select
    **Next**.

<img src="./media/image23.png" style="width:6.5in;height:4.33681in" />

29. If you get a prompt that the content is blocked by Internet Explorer
    Enhanced Security Configuration, select **Add**.

<img src="./media/image24.png"
style="width:5.45833in;height:5.01389in" />

30. On the Trusted sites prompt, again select **Add** and then
    **Close**. Do these for all the required sites.

<img src="./media/image25.png"
style="width:4.98398in;height:4.48512in" />

31. If asked, provide the tenant credentials again.

    <img src="./media/image26.png" style="width:3.6054in;height:2.96812in"
    alt="A screenshot of a computer Description automatically generated" />

32. On the connect your directories page click **Add directory**. 

<img src="./media/image27.png" style="width:6.5in;height:4.15486in"
alt="Graphical user interface, text, application Description automatically generated" />

33.  On the **AD Forest account** window click **Create new account**
    and enter the login credentials of your VM, i.e. the domain name and
    the password and select **Next**.

    <img src="./media/image28.png" style="width:6.5in;height:4.63542in" />

34. Back on the **Connect your directories** page click on **Next.**

    <img src="./media/image29.png" style="width:6.5in;height:4.50486in" />

35. On the Azure AD sign in configuration page select the check box for
    **Continue without matching all UPN suffixes to verified domains**
    check box and click **Next**. 

  <img src="./media/image30.png" style="width:6.5in;height:4.51916in" />

36. On the **Domain and OU filtering** page select the Sync **selected
    domains and OUs** radio button and only select the **IT** OU and
    then click on **Next**

    <img src="./media/image31.png" style="width:6.5in;height:4.55486in" />

37. On the **Uniquely identify your users**, leave the default values
    and click on **Next**.

38. On the **Filter users and devices**, leave the default values and
    click on **Next**.

39. On the **Optional features**, leave the default values and click on
    **Next**.

40. On the **Ready to configure** page, click on the **Install** button.

<img src="./media/image32.png" style="width:6.5in;height:4.53885in" />

41. Once the installation is complete, select **Exit**. 

<img src="./media/image33.png" style="width:6.5in;height:4.51528in" />

### Task 2 – Verify users are created and synchronization is occurring with Microsoft Entra ID

We will now verify that the users that we had in our on-premises
directory have been synchronized and now exist in Microsoft Entra ID
tenant. To verify users are synchronized do the following. 

1.  Switch back to the browser with the **Microsoft Entra admin center**
    opened, then select **Identity**, expand **Users**, select **All
    users**.

<img src="./media/image34.png" style="width:6.5in;height:3.20278in" />

2.  If required click on the Refresh button and verify that you see the
    new users in our tenant, the **On-premises synced** enabled. 

    <img src="./media/image35.png" style="width:6.5in;height:4.56181in" />

<img src="./media/image36.png" style="width:6.5in;height:3.34306in" />

3.  From the list of users, select the user **Abbi Skinner**, then click
    on **Edit properties**

    <img src="./media/image37.png" style="width:6.5in;height:4.43403in" />

4.  Select the **Settings** tab, then from the drop-down choose **United
    states** for Usage location and then click on the **Save** button.

    <img src="./media/image38.png" style="width:6.5in;height:5.22917in" />

    <img src="./media/image39.png"
    style="width:5.00877in;height:0.56672in" />

5.  Repeat the same steps to verify the Usage location for the below
    users.

    - Beth Burke

    - Huong Tang

    - Logan Boyle

<span class="mark">**Note** - Usage location is necessary while
assigning a License, the License assignment will fail for a user who
does not have a Usage location.</span>

## Exercise 3 – Create Groups and assign Licenses from Microsoft Entra admin center- <span class="mark">Full Exercise replaced</span>

### Task 1 - Create Groups and assign Licenses

1.  Open the Edge browser and login to the **Microsoft Entra admin
    center +++https://entra.microsoft.com+++**.

<!-- -->

42. If prompted for credentials enter your **Office365 Tenant
    Credentials** provided on the **resources** tab of the lab Interface
    as show in the Image.

43. Select **Identity** expand the **Groups**, select **All groups**
    then click on **New group**.

<img src="./media/image40.png" style="width:6.5in;height:3.67917in" />

44. The **New Group** pane will appear, provide the below details.

    - Group type – **Microsoft 365**

    - Group name – **+++Sales101+++**

    - Group email address – **+++Sales+++**

    - Group Description – **+++Group for users in Sales department+++**

    - Microsoft Entra roles can be assigned to the group – **Yes**

    - Scroll down and click on link – **No members selected**

> <img src="./media/image41.png" style="width:6.5in;height:3.67917in" />

- On the Add members tab, add **Abbi Skinner** and **Huong Tang** and
  click on **Select**.

> <img src="./media/image42.png" style="width:6.5in;height:3.67917in"
> alt="A screenshot of a computer Description automatically generated" />

- Click on **Create**.

<img src="./media/image43.png" style="width:6.5in;height:3.67917in" />

45. You will get a prompt as shown in below image, click **Yes**.

<img src="./media/image44.png" style="width:6.5in;height:3.67917in"
alt="A screenshot of a computer Description automatically generated" />

46. Your group is created, and you will get a successful notification.

<img src="./media/image45.png" style="width:6.5in;height:3.67917in"
alt="A screenshot of a computer Description automatically generated" />

47. Repeat the steps 3-5 to create another group with below details

- Group type – **Microsoft 365**

- Group name – **+++Research101+++**

- Group email address – **+++Research101+++**

- Group Description – **+++Group for users in Research department+++**

- Microsoft Entra roles can be assigned to the group – **Yes**

- Members – **Beth Burke** and **Logan Boyle**

<img src="./media/image46.png" style="width:6.5in;height:3.67917in"
alt="A screenshot of a computer Description automatically generated" />

<img src="./media/image47.png" style="width:6.5in;height:3.67917in"
alt="A screenshot of a computer Description automatically generated" />

48. Once both the **Groups** have been created, click on the **Refresh**
    button and the Group list should appear as shown in the below image.

<img src="./media/image48.png" style="width:6.5in;height:3.67917in" />

49. While in the **Microsoft Entra admin center**, click on **… Show
    more**.

<img src="./media/image49.png" style="width:6.5in;height:3.67917in" />

50. Expand **Billing** then click on **Licenses**, then select **All
    Products**.

<img src="./media/image50.png" style="width:6.5in;height:3.67917in" />

51. Click on the **Microsoft 365 E5** license, you will notice that
    **20/20** licenses have been assigned, we will release few licenses
    to be used for the upcoming steps.

    <img src="./media/image51.png" style="width:6.5in;height:3.30278in" />

52. From the list of users select the below users and then click on
    Remove license

    1.  Lee Gu

    2.  Nestor Wilke

    3.  Patti Fernandez

    4.  Pradeep Gupta

        <img src="./media/image52.png" style="width:6.5in;height:4.3625in" />

53. When prompted to Remove license click on the **Yes** button.

    <img src="./media/image53.png" style="width:6.5in;height:1.71528in" />

    <img src="./media/image54.png"
    style="width:2.81691in;height:0.55838in" />

54. Close the **Microsoft 365 E5** blade and then refresh the page, now
    the available number should be **4.**

    <img src="./media/image55.png" style="width:6.5in;height:3.0875in" />

55. Select **Microsoft 365 E5** and **Office 365 E5** licenses and then
    click on **+ Assign**.

<img src="./media/image56.png" style="width:6.5in;height:2.59306in" />

56. On the **Assign license** window, on the **Users and groups** tab,
    select on **Add users and groups**.

<img src="./media/image57.png" style="width:6.5in;height:3.67917in"
alt="A screenshot of a computer Description automatically generated" />

57. Under Groups tab, select the groups **Sales101** and
    **Research101**, then click on **Select**.

<img src="./media/image58.png" style="width:6.5in;height:3.67917in"
alt="A screenshot of a computer Description automatically generated" />

58. Click on **Review + assign**.

<img src="./media/image59.png" style="width:6.5in;height:3.67917in" />

59. Click on **Assign**.

<img src="./media/image60.png" style="width:6.5in;height:4.32917in" />

60. You should get the notification as shown in below image.

<img src="./media/image61.png"
style="width:3.51697in;height:0.71673in" />

61. Both the Groups have the license assigned.

<img src="./media/image62.png" style="width:6.5in;height:3.67917in" />

### Task 2 – Add a Guest account and create an External Collaborators group.

1.  Open the Edge browser and login to the **Microsoft Entra admin
    center +++https://entra.microsoft.com+++**.

<!-- -->

62. If prompted for credentials enter your **Office365 Tenant
    Credentials** provided on the **resources** tab of the lab Interface
    as show in the Image.

63. Select **Identity** expand **Users**, select **All Users**, the from
    the **New user** drop-down menu select **Invite external user**.

    <img src="./media/image63.png" style="width:6.5in;height:2.62153in" />

64. On the Invite external user page, provide the below details

    - Email – your personal outlook email address or create a new
      outlook email for testing.

    - Display name – **+++External User+++**

    - Message – **+++Invite to my Org+++**

65. Click on **Next: Properties \>**

    <img src="./media/image64.png"
    style="width:6.49922in;height:3.85139in" />

66. On the **Properties** tab, set the Usage location to **United
    States** and then click on **Review + invite** button.

    <img src="./media/image65.png" style="width:6.5in;height:4.88056in" />

67. On the **Review + invite** tab, click on the **Invite** button.

    <img src="./media/image66.png"
    style="width:5.60049in;height:5.4338in" />

    <img src="./media/image67.png"
    style="width:2.56689in;height:0.50004in" />

68. Open an InPrivate window and open the Outlook for the external
    account on which the invite was sent.

    <img src="./media/image68.png"
    style="width:6.02552in;height:5.0171in" />

69. Click on the **Accept invitation** link.

70. Click on the **Accept** button to grant permission.

    <img src="./media/image69.png"
    style="width:4.43372in;height:5.47547in" />

71. You should successfully be logged into My Apps portal for the
    Microsoft Entra Tenant.

    <img src="./media/image70.png" style="width:6.5in;height:3.04931in" />

72. Switch back to the tab with **Microsoft Entra admin center** portal
    logged with Tenant admin.

73. Select **Identity** expand the **Groups**, select **All groups**
    then click on **New group**.

<img src="./media/image40.png" style="width:6.5in;height:3.67917in" />

74. Create the group with below details.

- Group type – **Security**

- Group name – **+++External Collaborators+++**

- Group Description – **+++Group of External Users+++**

- Microsoft Entra roles can be assigned to the group – **Yes**

  <img src="./media/image71.png" style="width:6.5in;height:3.75208in" />

- Scroll down and add the Invited user account – External User and then
  click on **Select** button.

  <img src="./media/image72.png"
  style="width:6.49945in;height:3.93403in" />

75. Click on **Create** button

    <img src="./media/image73.png" style="width:6.5in;height:3.50679in" />

76. Click on the Yes button when prompted.

    <img src="./media/image74.png" style="width:6.5in;height:1.0625in" />

    <img src="./media/image75.png"
    style="width:2.87525in;height:0.48337in" />

## Exercise 4 – Enabling Microsoft Entra ID per-user Multifactor Authentication

To secure user sign-in events in **Microsoft Entra ID**, you can require
multi-factor authentication (MFA). We can enable each account for
per-user Multi-Factor Authentication. When users are enabled
individually, they perform multi-factor authentication each time they
sign in (with some exceptions, such as when they sign in from trusted IP
addresses or when the remember MFA on trusted devices feature is turned
on).

1.  Open the Edge browser and login to the Microsoft Entra admin center
    **+++https://entra.microsoft.com+++**.

<!-- -->

77. If prompted for credentials enter your **Office365 Tenant
    Credentials** provided on the **resources** tab of the lab Interface
    as show in the Image.

78. In the **Microsoft Entra admin center** navigate
    to **Identity** then expand Users, click **All** **Users** then
    click on the ellipses **…** then select **Per-user MFA**.

<img src="./media/image76.png" style="width:6.5in;height:3.67917in" />

79. Select the users **Abbi Skinner** and **Beth Burke** and click
    on **Enable**.

<img src="./media/image77.png" style="width:6.5in;height:3.67917in" />

80. On the Message About enabling multi-factor auth, click on **enable
    multi-factor auth**.

<img src="./media/image78.png" style="width:6.5in;height:3.67917in" />

81. Click on the **Close** button on the confirmation message.

<img src="./media/image79.png" style="width:6.5in;height:3.67917in" />

82. Open a browser in InPrivate/incognito mode and login to **My Apps
    portal** **+++https://myapps.microsoft.com+++**.

83. Enter the credentials for **Beth Burke** account

- Username – **+++Beth@+++** paste the **Tenant name** from the
  Resources tab.

- Password – **+++Pa55w.rd+++**

84. You will be prompted to More information is required, click
    on **Next**

    <img src="./media/image80.png"
    style="width:3.62771in;height:3.1871in" />.

85. On the **Start by getting the app** page, click on **Next**

<img src="./media/image81.png" style="width:6.5in;height:3.67917in" />

86. Install the **Microsoft Authenticator App** on your phone from the
    play store or app store as appropriate.

87. On the **Set up your account page**, select **Next.**

<img src="./media/image82.png" style="width:6.5in;height:3.67917in" />

88. On the **Scan the QR code** page, scan the QR image to add the
    account on your Microsoft Authenticator App on your phone.

<img src="./media/image83.png" style="width:6.5in;height:3.67917in"
alt="A screenshot of a computer Description automatically generated" />

89. Now, select **Next**.

<img src="./media/image84.png" style="width:6.5in;height:3.67917in"
alt="A screenshot of a computer Description automatically generated" />

90. When prompted, approve the notification on your phone. Once you see
    that the notification is approved, select **Next**.

<img src="./media/image85.png" style="width:4.76088in;height:2.11646in"
alt="Graphical user interface, text, application Description automatically generated" />

91. Click on **Done**

<img src="./media/image86.png" style="width:6.5in;height:2.70833in" />

92. You should be logged in to the **My Apps Portal**

<img src="./media/image87.png" style="width:6.5in;height:3.27014in" />

93. You have completed this task, please proceed ahead with the next
    task.

## Exercise 5 – Enabling Conditional Access for the Research Group

Conditional Access policies at their simplest are if-then statements, if
a user wants to access a resource, then they must complete an action.

<img src="./media/image88.png" style="width:6.53789in;height:2.65509in"
alt="Timeline Description automatically generated" />

We will set a Conditional Access policy to require MFA for Research
Group only when the Access **Microsoft Forms**

1.  Open the Edge browser and login to the **Microsoft Entra admin
    center +++https://entra.microsoft.com+++**.

<!-- -->

94. In the **Microsoft Entra admin center**, expand **Protection** and
    select **Conditional Access**. Click on **Create new policy**.

<img src="./media/image89.png" style="width:6.5in;height:3.67917in" />

95. On the **New Conditional Access Policy** page, provide the below
    details

    - Name – **+++CA for Microsoft Forms+++**

    - Under **Users**, select **Specific users included**. Then under
      **Include**, choose **Select users and groups**. Select the check
      box near **Users and groups**. Then under **Select**, choose **0
      users and groups selected**.

<img src="./media/image90.png" style="width:6.5in;height:3.67917in"
alt="A screenshot of a computer Description automatically generated" />

- Scroll down on the **Select users and groups** page, select
  **Research101**. Choose **Select**.

<img src="./media/image91.png" style="width:6.5in;height:3.67917in" />

- Under **Target Resources**, select **No target resources selected**.
  Then under **Include**, choose **Select apps**. Under select, choose
  **None**. In the side pane, search for and select **Microsoft Forms**
  by selecting the check box near the app. Then choose **Select**.

<img src="./media/image92.png" style="width:6.5in;height:3.67917in"
alt="A screenshot of a computer Description automatically generated" />

- Similarly select **Access Controls** \> **Grant** \> **0 controls
  selected** \> **Grant access** \> **Require multi-factor
  authentication** \> **Select**.

<img src="./media/image93.png" style="width:6.5in;height:3.67917in"
alt="A screenshot of a computer Description automatically generated" />

- Enable policy – **Report-only**

- Click on **Create**

<img src="./media/image94.png" style="width:6.5in;height:3.67917in"
alt="A screenshot of a computer Description automatically generated" />

96. You should get the notification as shown in below image.

<img src="./media/image95.png" style="width:6.5in;height:3.67917in"
alt="A screenshot of a computer Description automatically generated" />

**NOTE** - Report-only mode is a new Conditional Access policy state
that allows administrators to evaluate the impact of Conditional Access
policies before enabling them in their environment. With the release of
report-only mode:

- Conditional Access policies can be enabled in report-only mode.

- During sign-in, policies in report-only mode are evaluated but not
  enforced.

- Results are logged in the Conditional Access and Report-only tabs of
  the Sign-in log details.

- Customers with an Azure Monitor subscription can monitor the impact of
  their Conditional Access policies using the Conditional Access
  insights workbook.​

97. Now open a browser in InPrivate/incognito mode and login to **MyApps
    portal** – **+++https://myapps.microsoft.com+++**.

98. Login using **Logan Boyle’s** credentials you will be signed in
    without any additional information required prompt

- Username – **+++Logan@+++** paste the **Tenant name** from the
  Resources tab.

- Password – **+++Pa55w.rd+++**

99. Click on Forms to access **Microsoft Forms**.

<img src="./media/image96.png" style="width:6.5in;height:3.14653in" />

100. Select **Create new**.

<img src="./media/image97.png" style="width:6.5in;height:3.325in" />

101. Switch back to the **Microsoft Entra admin center** and set the
     Conditional access policy to **On** and **Save** it.

     <img src="./media/image98.png"
     style="width:3.93367in;height:5.85051in" />

102. Now log off on the InPrivate tab and login to **MyApps portal**
     – **+++https://myapps.microsoft.com+++**.

103. Login using **Logan Boyle’s** credentials you will be signed in
     without any additional information required prompt

- Username – **+++Logan@+++** paste the **Tenant name** from the
  Resources tab.

- Password – **+++Pa55w.rd+++**

104. Click on Forms to access **Microsoft Forms**.

<img src="./media/image96.png" style="width:6.5in;height:3.14653in" />

105. You will notice that the Conditional Access policy requires you to
     perform MFA in order to access Forms.

<img src="./media/image99.png"
style="width:4.16703in;height:4.19203in" />

106. Click on **Next** and complete the MFA process to gain access to
     Forms.

107. You would be required to go through the Microsoft Authenticator
     process, once completed you will be logged in Microsoft Forms
     successfully as shown in below images

<img src="./media/image86.png" style="width:6.5in;height:2.70833in" />

108. You should be able to login successfully

     <img src="./media/image100.png" style="width:6.5in;height:3.12083in" />

     <img src="./media/image101.png" style="width:6.5in;height:3.05278in" />

## Summary:

In this lab we assigned the required licenses and created the required
records using the provided public domain. We enabled MFA for our users
and assigned a basic conditional access policy to a group of users in
our organization.
