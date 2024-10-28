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

22. Navigate to Microsoft Azure Portal.

   ![](./media/new2.png)

## Exercise 2 – Set a conditional access policy to block a user from accessing Sway

Microsoft Entra conditional access is an advanced feature of Microsoft
Entra ID that allows you to specify detailed policies that control who
can access your resources. Using Conditional Access, you can protect
your applications by limiting users’ access based on things like groups,
device type, location, and role.

**Information**: Sway is a new app from Microsoft Office that makes it
easy to create and share interactive reports, personal stories,
presentations, and more.

**Note**: This feature is the part of Microsoft Entra P1 License.

1. Click on the following Microsoft Entra admin center link: `https://entra.microsoft.com/` and sign in using
    the **Office 365 tenant credentials**.
  
2. In the **Microsoft Entra admin center** page, navigate and click on
**Identity**, click on **Users**, then click on **All users**.

    ![](./media/a2.png)

3. Click on **Allan Deyoung**.

    ![](./media/a3.png)

4. Click on Reset password.

    ![A screenshot of a computer Description automatically
    generated](./media/a4.png)

5. Then, click on the Reset password button as shown in the below image.

    ![A screenshot of a computer Description automatically
    generated](./media/a5.png)

6. Note down the temporary password.

    ![](./media/a6.png)

7. Open a new browser and enter the following URL:
`https://sway.cloud.microsoft/`

    ![](./media/a7.png)

8. Sign in using Allan credentials as shown in the below images.

    ![A screenshot of a computer Description automatically
generated](./media/a8.png)

    ![](./media/a9.png)

9. In **Update your password** dialog box, update the password.

    ![](./media/a10.png)

10. You will be directed to **Sway** website.

    ![](./media/a11.png)

11. You have successfully logged in Sway website using Allan credentials,
now log out from the Sway website.

**Note**: Sign out from Sway website.

    ![](./media/a12.png)

12. Go back to **Microsoft Entra Admin Center**. Click on **Protection** and
then click on **Conditional Access**.

    ![A screenshot of a computer Description automatically
generated](./media/a13.png)

13. In the **Conditional Access** page, click on **+ Create new policy**.

    ![](./media/a14.png)

14. In the **Name** field, enter `Blocking Access to Sway`

    ![A screenshot of a computer Description automatically
generated](./media/a15.png)

15. Navigate and click on **Specific users included** link, then choose the
radio button of **Select users and groups**, tick on the **Users and
groups** checkbox.

    ![A screenshot of a computer Description automatically
generated](./media/a16.png)

16. In **Select users and groups** pane that appear on the right side, navigate
to the search field, then enter the name `Allan`  Select the checkbox
and click on the **Select** button.

    ![A screenshot of a computer Description automatically
generated](./media/a17.png)

17. Allan user is successfully selected. Now, under **Target resources**,
click on **No target resources selected** link.

    ![A screenshot of a computer Description automatically
generated](./media/a18.png)

18. Navigate and click on **Select resources** radio button, then click on
**None** link as shown in the below image.

    ![A screenshot of a computer Description automatically
generated](./media/a19.png)

19. In the **Select **pane that appears on the right side, type `Sway` and
then select it.

    ![A screenshot of a computer Description automatically
generated](./media/a20.png)

20. Navigate to **Conditions** section, click on **0 conditions selected**
link.

    ![A screenshot of a computer Description automatically
generated](./media/a21.png)

21. Navigate to **Insider risk** section and click on **Not configured**
link.

    ![](./media/a22.png)

22. In the **Insider risk** pane, under **Configure**, select **Yes**.
Select **Moderate** check box and then click on **Done** button.

    ![](./media/a23.png)

23. In the **Grant** section click on **0 controls selected** link. In the
**Grant** pane, navigate and select **Block access** radio button, then
click on the **Select** button.

    ![](./media/a24.png)

24. Navigate to **Enable policy** section and select **On** toggle button.
Then, click on **Create** button.

    ![](./media/a25.png)

25. You will see the message that the **Blocking Access to Sway**
Conditional Access policy is successfully created.

    ![A screenshot of a computer Description automatically
generated](./media/a26.png)

26. Wait for 5-10 minutes for the policy to be implemented. Then, open a new
browser and enter the following URL: `https://sway.cloud.microsoft/`

27. Login to the Sway website.

    ![](./media/a27.png)

28. Sign in using Allan credentials.

    ![A screenshot of a computer Description automatically
generated](./media/a28.png)

    ![A screenshot of a login page Description automatically
generated](./media/a29.png)

29. In the **Stay signed in?** dialog box, click on the **Yes** button.

    ![](./media/a30.png)

30. You will observe that the access to the website is blocked.

    ![](./media/a31.png)

## Summary:

In this lab we enabled user risk policy, created a conditional access
policy to block a user from accessing a cloud app, and explored the
Identity Secure Score.
