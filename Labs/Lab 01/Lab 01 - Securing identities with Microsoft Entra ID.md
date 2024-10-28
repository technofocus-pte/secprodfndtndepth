# **Lab 01 - Securing identities with Microsoft Entra ID**

## Task 0: Sync Host environment time

1.  Login to the Lab Virtual Machine using the credentials provided on
    the Home tab of the Lab interface.

2.  In your VM, navigate and click in the **Search bar**, type
    `Settings` and then click on **Settings** under **Best match**.
    
    ![](./media/image1.png)

3.  On Settings window, navigate and click on **Time & language**.

    ![](./media/image2.png)

4.  On **Time & language** page, navigate and click on **Date & time**.

    ![](./media/image3.png)

5.  Scroll down and navigate to **Additional settings** section, then
    click on **Syn now** button.

    ![](./media/image4.png)

6.  Close the **Settings** window.

    ![](./media/image5.png)

## Task 1: Redeeming Azure pass and implementing Multifactor authentication

1.  In your lab VM, open Microsoft Edge and
    enter `http://www.microsoftazurepass.com`

     ![](./media/image6.png)

2.  On **Ready to get started?** page, click on the **Start** button.

    ![](./media/image7.jpeg)

> **Note**: Do not use your Company/Work Account to login to redeem the
Azure Pass, another Azure Pass will not be issued.

> **Note**: In case, you are directed to the page - The following Microsoft Account will be used for Azure Pass page, then ignore steps #3 to #5

3.  **Sign in** with the username given in the
**Home/Resources** tab of your Lab environment. and click on the **Next** button.

    ![](./media/image8.png)

4.  Enter **Office 365 Tenant Password** and click on the **Sign in**
    button.

    ![](./media/image9.png)

5.  On **Stayed signed in?** dialog box, click on **Yes** button.

    ![](./media/image10.png)

6.  On **The following Microsoft Account will be used for Azure pass**
    page, click on **Confirm Microsoft Account** button.

     ![](./media/image11.png)

7.  Enter the Promocode provided in the lab environment in the **Enter
    Promo code** field, then enter the characters under the **Enter the
    characters you see** field and click on the **Submit** button.

    ![](./media/image12.png)

8.  **We are processing your request** page will appear, it may take few
    seconds to process the redemption.

    ![](./media/image13.png)

9. Enter correct details in **Your Profile** page, tick all the check
    boxes, and then click on **Sign up** button.

     ![](./media/image14.png)

     ![](./media/image15.png)
 
     ![](./media/image16.png)
   
11. On **Protect your account** dialog box, click on the **Next**
    button.

    ![](./media/image17.png)

12. Then, on **More information required** dialog box, click on
    the **Next** button.

     ![](./media/image18.png)

13. If prompted, then enter the password and click on the **Sign in**
    button.

    ![](./media/image19.png)

14. In your mobile, install the **Microsoft Authenticator App**. Then,
    go back to Microsoft Azure port. In the Azure portal, **Microsoft
    Authenticator -** **Start by getting the app** window, navigate and
    click on the **Next** button.

    ![](./media/image20.png)

15. In **Microsoft Authenticator –** **Set up your account** window,
    click on the **Next** button.
    
    ![](./media/image21.png)

16. **Scan the QR code** using the **Authenticator app** installed in
    your mobile phone and click on the **Next** button.

    ![](./media/image22.png)

17. Enter the number in your mobile authenticator app and select
    **Yes**. In **testvm1**, click on the **Next** button.

    ![](./media/image23.png)

18. Click on the **Next** button.

![A screenshot of a computer Description automatically
    generated](./media/image24.png)

19. Click on the **Done** button.

    ![](./media/image25.png)

20. Enter the number again in your mobile authenticator app and select
    **Yes**..
  
    ![](./media/image26.png)

21. In the **Stay signed in?** window, click on the **Yes** button.
    
    ![A screenshot of a computer Description automatically
    generated](./media/image10.png)

## Task 2: Redeeming Azure pass and implementing Multifactor authentication

1. Navigate to Microsoft Azure Portal.

   ![](./media/new2.png)

2. In the Azure portal search bar, type `Microsoft Entra`, then navigate and click on **Microsoft Entra ID** under **Services**.

   ![](./media/new5.png)

3. In the **Create new user** page, in the **User principal name** field, enter **allan**. In the** Display name** field, enter **Allan DeYoung**, then uncheck Auto-generate password box. Enter the password of your choice (here, we've entered **Admin@5801**). Click on **Next: Properties >**

  ![](./media/new7.png)

4. Click on **Review + create** button.

   ![](./media/new8.png)

5. Click on **Create** button to successfully create the user.

   ![](./media/new9.png)

   ![](./media/new10.png)
   
## Exercise 2 – Set a conditional access policy to block a user from accessing Viva Engage

> **Note**: This feature is the part of Microsoft Entra P1 License.

### Task 1 – Confirm Allan Deyoung has access to Engage

1.  Launch a new InPrivate browser window in your lab VM.

    ![](./media/new3.png)

2.  Navigate to `https://www.office.com`.

    ![](./media/new3.png)

3. Click on **Sign in** button.

    ![](./media/new12.png)

4. Log in as **Allan Deyoung**:

   Username – `alland@`Paste the Tenant name from the **Home/Resources tab**

   Password – Paste the User Password (here, we entered **Admin@5801***)

 ![](./media/new13.png)

 ![](./media/new14.png)

5. On Update your password page, upgrade your password (here, we've updated the previous password to **Admin5801@***)

    ![](./media/new15.png)

6. On **Stay signed in?** dialog box, click on the **Yes** button.

    ![](./media/new16.png)

4. When prompted, log in as **Allan Deyoung**:

 
4. Click on **Explore App** and then click on the **Engage** icon to
    see that it loads correctly.

![](./media/image27.png)

5. Click on **Log in with Microsoft account**.

    ![](./media/image28.png)

6. The portal should load successfully.

    ![](./media/image29.png)

### Task 2 – Create a conditional access policy

Microsoft Entra conditional access is an advanced feature of Microsoft
Entra ID that allows you to specify detailed policies that control who
can access your resources. Using Conditional Access, you can protect
your applications by limiting users’ access based on things like groups,
device type, location, and role.

> **Note**: This Feature is the part of Microsoft Entra P1 License.

1.  Browse to `https://entra.microsoft.com/` and sign in using
    the **Office 365 tenant credentials**.


2. On the lefthand menu, under Identity, expand Protection, and then
    select **Conditional access**. On the **Overview (Preview)**,
    click **+ Create new policy**.

   ![](./media/image30.png)

3. On the **New Conditional Access Policy** page, provide the below
    details

    - Name – `Block Engage for Allan Deyoung`

    - Under **Users**, select **0 users and groups selected/Specific
      users included**. Then under **Include**, choose **Select users
      and groups**. Select the check box near **Users and groups**. Then
      under **Select**, choose **0 users and groups selected**.

   ![](./media/image31.png)

- Scroll down on the **Select users and groups** page, select **Allan
  Deyoung**. Choose **Select**.

   ![](./media/image32.png)

- Under **Target Resources**, select **No target resources selected**.
  Then under **Include**, choose **Select apps**. Under select, choose
  **None**. In the side pane, search for and select **Viva Engage** by
  selecting the check box near the app. Then choose **Select**.

   ![](./media/image33.png)

- Under **Access controls**, within the **Grant** section, select **0
  controls selected**. In the Grant pane, select **Block access** |
  **Required all the selected controls** and then choose **Select**.

    ![](./media/image34.png)

- Enable policy – **On**. Click on **Create**.

   ![](./media/image35.png)

    ![](./media/image36.png)

> **Note** - This policy is being configured for the exercise only and is
being used to quickly demonstrate a conditional access policy.


### Task 3 – Test the conditional access policy

You should test your conditional access policies to ensure they working
as expected.

1.  Close the InPrivate Window or Log out completely.


2.  Launch a new InPrivate browser window in your lab VM.


3. Navigate to `https://www.office.com`.

4. When prompted, log in as **Allan Deyoung**:

 Username – `alland@`Paste the Tenant name from the Resources
 tab**

 Password – Paste the User Password from the Resources tab.

5. Click on **Explore App** and then click on the **Engage** icon to
    see that it loads correctly.

6. Verify you are prevented from accessing **Viva Engage**.

    ![](./media/image37.png)

> **Note** - If you are signed in, close the tab, wait 1 minute, and then
retry. If you are auto-logged into Engage as Allan, then you will need
to manually log out. Your credentials / access were cached. Once you log
out and sign-in, your Engage session should deny access. To disable the
policy, follow the given steps.

7. Close the tab and return to the Conditional Access page, then select policies.

    ![](./media/image37a.png)

8. Select the **Block Engage for Allan Deyoung** policy.

9. Under **Enable policy**, select **Off** and then select **Save**.

### Task 4 – Use ‘What if’ to test conditional access policies

1.  Browse to `https://entra.microsoft.com/` and sign in using
    the **Office 365 tenant credentials**.

2.  On the lefthand menu, under Identity, expand Protection, and then
    select **Conditional access.** In the navigation pane,
    select **Policies**. Select **What If**.

   ![](./media/image38.png)

3. Under **User or Workload identity**, select **No user or service
    principal selected**. Under **Select identity type**, select
    **User**, and then choose **No user selected**.

    ![](./media/image39.png)

4. Choose **Allan Deyoung** as the user. Then choose **Select**.

   ![](./media/image40.png)

5. Under **Cloud apps, actions, or authentication context**,
    select **Any cloud app**. Under **Select what this policy applies
    to**, choose **Select apps** and then **None** under **Select**.

    ![](./media/image41.png)

6. In the select pane, choose **Viva Engage**. And then choose
    **Select**.

   ![](./media/image42.png)

7. Select **What if**.

   ![](./media/image43.png)

8. You will be provided with a report at the bottom of the tile
    for **Policies that will apply** and **Policies that will not
    apply**.

   ![](./media/image44.png)

This allows you to test the policies and their effectiveness before
enabling the policies.

### Task 5 – Configure sign in frequency controls using a conditional access policy

As part of your company’s larger security configuration, you must test a
conditional access policy that can be used to control sign in frequency.

1.  Browse to `https://entra.microsoft.com/` and sign in using
    the **Office 365 tenant credentials**.


2. On the lefthand menu, under Identity, expand Protection, and then
    select **Conditional access**. On the **Overview (Preview)**,
    click **+ Create new policy**.

   ![](./media/image30.png)

3. On the **New Conditional Access Policy** page, provide the below
    details.

    - Name – `Sign in frequency`

    - Under **Users**, select **0 users and groups selected/Specific
      users included**. Then under **Include**, choose **Select users
      and groups**. Select the check box near **Users and groups**. Then
      under **Select**, choose **0 users and groups selected**.

   ![](./media/image45.png)

- Scroll down on the **Select users and groups** page, select **Joni
  Sherman**. Choose **Select**.

   ![](./media/image46.png)

- Under **Target Resources**, select **No target resources selected**.
  Then under **Include**, choose **Select apps**. Under select, choose
  **None**. In the side pane, search for and select **Office 365** by
  selecting the check box near the app. Then choose **Select**.

   ![](./media/image47.png)

- Under **Access controls**, within the **Sessions** section, select **0
  controls selected**. In the **Grant** pane, select **Sign-in
  frequency,** in the value box, enter **14**. Select the units menu,
  select **Days**, and then choose **Select.**

  ![](./media/image48.png)

- Enable policy – **On**. Click on **Create**.

  ![](./media/image49.png)

  ![](./media/image50.png)

## Summary:

In this lab we enabled user risk policy, created a conditional access
policy to block a user from accessing a cloud app, and explored the
Identity Secure Score.
