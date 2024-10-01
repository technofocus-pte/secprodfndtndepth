# Day 2 – Lab 2 – Implementing Microsoft Entra Identity Protection​

## Objective:

In this lab we will explore how to configure and enable user risk
policy. We will also explore how to block a user or a group of users
from using any cloud app using a conditional policy.

We will also see how to monitor and manage security posture using
Identity Secure Score.

## Exercise 1 – Enable User risk policy.

### Task 1 – Configure a user risk policy

1.  Sign in to the +++https://entra.microsoft.com/+++ using your
    **Office 365 tenant credentials**.

<!-- -->

1.  On the lefthand menu, under **Identity**, expand **Protection**, and
    then select **Identity protection**.

<img src="./media/image1.png" style="width:6.5in;height:3.67431in" />

2.  In the **Identity protection** page, in the left navigation,
    select **User risk policy**.

<img src="./media/image2.png" style="width:6.5in;height:3.67431in" />

3.  Under **Assignments**, select **All users** and review the available
    options. Then choose **Select individuals and groups**. We will
    limit our policy rollout to **Sales101** team.

<img src="./media/image3.png" style="width:6.5in;height:3.67431in" />

4.  In the **Select Users** pane, select the group **Sales101**. Then
    choose **Select**.

<img src="./media/image4.png" style="width:6.5in;height:3.67431in" />

5.  Under **User risk**, select **Low and above**. In the User risk
    pane, select **High** and then select **Done**.

<img src="./media/image5.png" style="width:6.5in;height:3.67431in" />

6.  Under **Controls** \> **Access**, select **Allow access** and
    **Require password change**, then select **Done**.

<img src="./media/image6.png" style="width:6.5in;height:3.67431in" />

7.  Under **Policy enforcement**, select **Enabled** and then
    select **Save**.

<img src="./media/image7.png" style="width:6.5in;height:3.67014in" />

<img src="./media/image8.png" style="width:6.5in;height:3.67014in" />

### Task 2 – Enable Sign-in risk policy

1.  On the **Identity Protection** page, in the left navigation,
    select **Sign-in risk policy**.

<img src="./media/image9.png" style="width:6.5in;height:3.67014in" />

8.  Under **Assignments**, select **All users** and review the available
    options. Then choose **Select individuals and groups**. We will
    limit our policy rollout to **Sales** team.

<img src="./media/image10.png" style="width:6.5in;height:3.67014in"
alt="A screenshot of a computer Description automatically generated" />

9.  In the **Select Users** pane, select the group **Sales101**. Then
    choose **Select**.

<img src="./media/image11.png"
style="width:6.45966in;height:3.67014in" />

10. Under **User risk**, select **Low and above**. In the User risk
    pane, select **High** and then select **Done**.

<img src="./media/image12.png" style="width:6.5in;height:3.67014in" />

11. Under **Controls** \> **Access**, select **Block access**. Select
    the **Require multi-factor authentication** check box and then
    select **Done**.

<img src="./media/image13.png" style="width:6.5in;height:3.67014in"
alt="A screenshot of a computer screen Description automatically generated" />

12. Under **Policy enforcement**, select **Enabled** and then
    select **Save**.

<img src="./media/image14.png" style="width:6.5in;height:3.67014in"
alt="A screenshot of a computer Description automatically generated" />

<img src="./media/image15.png" style="width:6.5in;height:3.67014in" />

Your organization needs to be able to limit user access to its internal
applications. You must deploy a Conditional access policy.

## Exercise 2 – Set a conditional access policy to block a user from accessing Viva Engage

### Task 1 – Confirm Allan Deyoung has access to Engage

1.  Launch a new InPrivate browser window in your lab VM.

<!-- -->

13. Navigate to +++**https://www.office.com+++**.

14. When prompted, log in as **Allan Deyoung**:

> Username – +++**alland@+++Paste the Tenant name from the Resources
> tab**
>
> Password – Paste the User Password from the Resources tab.

15. Click on **Explore App** and then click on the **Engage** icon to
    see that it loads correctly.

<img src="./media/image16.png" style="width:6.5in;height:3.67431in" />

16. Click on **Log in with Microsoft account**.

    <img src="./media/image17.png" style="width:6.5in;height:3.25556in" />

17. The portal should load successfully.

    <img src="./media/image18.png" style="width:6.5in;height:3.67431in" />

### Task 2 – Create a conditional access policy

Microsoft Entra conditional access is an advanced feature of Microsoft
Entra ID that allows you to specify detailed policies that control who
can access your resources. Using Conditional Access, you can protect
your applications by limiting users’ access based on things like groups,
device type, location, and role.

1.  Browse to **+++https://entra.microsoft.com/+++** and sign in using
    the **Office 365 tenant credentials**.

<!-- -->

18. On the lefthand menu, under Identity, expand Protection, and then
    select **Conditional access**. On the **Overview (Preview)**,
    click **+ Create new policy**.

<img src="./media/image19.png" style="width:6.5in;height:3.67431in"
alt="A screenshot of a computer Description automatically generated" />

19. On the **New Conditional Access Policy** page, provide the below
    details

    - Name – +++**Block Engage for Allan Deyoung+++**

    - Under **Users**, select **0 users and groups selected/Specific
      users included**. Then under **Include**, choose **Select users
      and groups**. Select the check box near **Users and groups**. Then
      under **Select**, choose **0 users and groups selected**.

<img src="./media/image20.png" style="width:6.5in;height:3.67431in"
alt="A screenshot of a computer Description automatically generated" />

- Scroll down on the **Select users and groups** page, select **Allan
  Deyoung**. Choose **Select**.

<img src="./media/image21.png" style="width:6.5in;height:3.67431in"
alt="A screenshot of a computer Description automatically generated" />

- Under **Target Resources**, select **No target resources selected**.
  Then under **Include**, choose **Select apps**. Under select, choose
  **None**. In the side pane, search for and select **Viva Engage** by
  selecting the check box near the app. Then choose **Select**.

<img src="./media/image22.png" style="width:6.5in;height:3.67431in"
alt="A screenshot of a computer Description automatically generated" />

- Under **Access controls**, within the **Grant** section, select **0
  controls selected**. In the Grant pane, select **Block access** \|
  **Required all the selected controls** and then choose **Select**.

<img src="./media/image23.png" style="width:6.5in;height:3.67431in" />

- Enable policy – **On**. Click on **Create**.

<img src="./media/image24.png" style="width:6.5in;height:3.67431in"
alt="A screenshot of a computer Description automatically generated" />

<img src="./media/image25.png" style="width:6.5in;height:3.67431in" />

**Note** - This policy is being configured for the exercise only and is
being used to quickly demonstrate a conditional access policy.

20. Keep the page open we will return to this page in **Task 4**.

### Task 3 – Test the conditional access policy

You should test your conditional access policies to ensure they working
as expected.

1.  Close the InPrivate Window or Log out completely.

<!-- -->

2.  Launch a new InPrivate browser window in your lab VM.

<!-- -->

21. Navigate to +++**https://www.office.com+++**.

22. When prompted, log in as **Allan Deyoung**:

> Username – +++**alland@+++Paste the Tenant name from the Resources
> tab**
>
> Password – Paste the User Password from the Resources tab.

23. Click on **Explore App** and then click on the **Engage** icon to
    see that it loads correctly.

24. Verify you are prevented from accessing **Viva Engage**.

<img src="./media/image26.png" style="width:6.5in;height:3.67431in" />

**Note** - If you are signed in, close the tab, wait 1 minute, and then
retry. If you are auto-logged into Engage as Allan, then you will need
to manually log out. Your credentials / access were cached. Once you log
out and sign-in, your Engage session should deny access. To disable the
policy, follow the given steps.

25. Close the tab and return to the Conditional Access page.

26. Select the **Block Engage for Allan Deyoung** policy.

27. Under **Enable policy**, select **Off** and then select **Save**.

### Task 4 – Use ‘What if’ to test conditional access policies

1.  Browse to **+++https://entra.microsoft.com/+++** and sign in using
    the **Office 365 tenant credentials**.

2.  On the lefthand menu, under Identity, expand Protection, and then
    select **Conditional access.** In the navigation pane,
    select **Policies**. Select **What If**.

<img src="./media/image27.png" style="width:6.5in;height:3.67431in"
alt="A screenshot of a computer Description automatically generated" />

28. Under **User or Workload identity**, select **No user or service
    principal selected**. Under **Select identity type**, select
    **User**, and then choose **No user selected**.

<img src="./media/image28.png" style="width:6.5in;height:3.67431in" />

29. Choose **Allan Deyoung** as the user. Then choose **Select**.

<img src="./media/image29.png" style="width:6.5in;height:3.67431in"
alt="A screenshot of a computer Description automatically generated" />

30. Under **Cloud apps, actions, or authentication context**,
    select **Any cloud app**. Under **Select what this policy applies
    to**, choose **Select apps** and then **None** under **Select**.

<img src="./media/image30.png" style="width:6.5in;height:3.67431in" />

31. In the select pane, choose **Viva Engage**. And then choose
    **Select**.

<img src="./media/image31.png" style="width:6.5in;height:3.67431in"
alt="A screenshot of a computer Description automatically generated" />

32. Select **What if**.

<img src="./media/image32.png" style="width:6.5in;height:3.67431in"
alt="A screenshot of a computer Description automatically generated" />

33. You will be provided with a report at the bottom of the tile
    for **Policies that will apply** and **Policies that will not
    apply**.

<img src="./media/image33.png" style="width:6.5in;height:3.67431in"
alt="A screenshot of a computer Description automatically generated" />

This allows you to test the policies and their effectiveness before
enabling the policies.

### Task 5 – Configure sign in frequency controls using a conditional access policy

As part of your company’s larger security configuration, you must test a
conditional access policy that can be used to control sign in frequency.

1.  Browse to **+++https://entra.microsoft.com/+++** and sign in using
    the **Office 365 tenant credentials**.

<!-- -->

34. On the lefthand menu, under Identity, expand Protection, and then
    select **Conditional access**. On the **Overview (Preview)**,
    click **+ Create new policy**.

<img src="./media/image19.png" style="width:6.5in;height:3.67431in"
alt="A screenshot of a computer Description automatically generated" />

35. On the **New Conditional Access Policy** page, provide the below
    details.

    - Name – +++**Sign in frequency+++**

    - Under **Users**, select **0 users and groups selected/Specific
      users included**. Then under **Include**, choose **Select users
      and groups**. Select the check box near **Users and groups**. Then
      under **Select**, choose **0 users and groups selected**.

<img src="./media/image34.png" style="width:6.5in;height:3.67431in"
alt="A screenshot of a computer Description automatically generated" />

- Scroll down on the **Select users and groups** page, select **Joni
  Sherman**. Choose **Select**.

<img src="./media/image35.png" style="width:6.5in;height:3.67431in"
alt="A screenshot of a computer Description automatically generated" />

- Under **Target Resources**, select **No target resources selected**.
  Then under **Include**, choose **Select apps**. Under select, choose
  **None**. In the side pane, search for and select **Office 365** by
  selecting the check box near the app. Then choose **Select**.

<img src="./media/image36.png" style="width:6.5in;height:3.67431in"
alt="A screenshot of a computer Description automatically generated" />

- Under **Access controls**, within the **Sessions** section, select **0
  controls selected**. In the **Grant** pane, select **Sign-in
  frequency,** in the value box, enter **14**. Select the units menu,
  select **Days**, and then choose **Select.**

<img src="./media/image37.png" style="width:6.5in;height:3.59236in" />

- Enable policy – **On**. Click on **Create**.

<img src="./media/image38.png"
style="width:4.2587in;height:5.73383in" />

<img src="./media/image39.png" style="width:6.5in;height:3.67431in"
alt="A screenshot of a computer Description automatically generated" />

## Exercise 3 – Monitor and managed security posture with Identity Secure Score

1.  Browse to **+++https://entra.microsoft.com/+++** and sign in using
    the **Office 365 tenant credentials**.

<!-- -->

36. On the lefthand menu, under **Protection,** click on**… Show more**,
    select **Identity Secure Score.** Select **Identity Secure Score
    from the sub-menu.** This will take you to the Identity Secure Score
    dashboard.

<img src="./media/image40.png" style="width:6.5in;height:3.66528in"
alt="A screenshot of a computer Description automatically generated" />

37. You may not see many recommendations but in a production environment
    you can view the **Improvement actions**. Sort the recommendations
    by **User impact**.

<img src="./media/image41.png" style="width:6.5in;height:3.66528in"
alt="A screenshot of a computer Description automatically generated" />

38. Select the first Improvement action. Review the recommendations
    under **WHAT AM I ABOUT TO CHANGE?** section and then you can select
    the status of the action from the dropdown. Change it to **Planned**
    and then select **Save**.

<img src="./media/image42.png" style="width:6.5in;height:3.53889in" />

In contrast to the improvement actions in Microsoft Defender for Cloud
and Microsoft 365 Defender, these improvement actions are specific to
identity. This provides a more focused list of potential actions to your
security posture management. Any improvement actions initiated from this
list will also provide an impact to your overall tenant security
posture.

## Summary:

In this lab we enabled user risk policy, created a conditional access
policy to block a user from accessing a cloud app, and explored the
Identity Secure Score.
