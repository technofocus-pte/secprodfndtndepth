# **Lab 3 – Creating and Managing DLP Policies**

## Introduction

Data loss prevention is a security solution that identifies and helps prevent unsafe or inappropriate sharing, transfer, or use of sensitive data. It can help your organization monitor and protect sensitive information across on-premises systems, cloud-based locations, and endpoint devices. It also helps you achieve compliance with regulations such as the Health Insurance Portability and Accountability Act (HIPAA) and General Data Protection Regulation (GDPR).

You are Patti Fernandez, the newly hired Compliance Administrator for Contoso Ltd. tasked to configure the company's Microsoft 365 tenant for
data loss prevention. Contoso Ltd. is a company that offers driving instruction in the United States and you need to make sure that sensitive customer information does not leave the organization.

## Objectives

- Create a Data Loss Prevention (DLP) policy in test mode to safeguard sensitive data in Microsoft Purview.

- Modify an existing DLP policy to expand its scanning to include additional data locations.

- Activate a DLP policy to enforce its protective actions across the organization.

- Adjust policy priority settings to ensure higher-priority policies are enforced over others.

## Exercise 1 – Creating DLP Policies

### Task 1 – Creating a DLP policy in test mode

In this exercise, you will create a Data Loss Prevention policy in the
Microsoft Purview portal to protect sensitive data from being shared by
users. The DLP Policy that you create will inform your users if they
want to share content that contains Credit Card information and allow
them to provide a justification for sending this information. The policy
will be implemented in test mode because you do not want the block
action to affect your users yet.

1.  In **Microsoft Edge**, navigate
    to `https://purview.microsoft.com` and make sure you are
    logged into the **Microsoft Purview** portal as **Patti Fernandez**.

2.  In the **Microsoft Purview** portal, in the left navigation pane,
    select  **Solutions** \> **Data loss prevention**.

    ![](./media/image1.png)

3.  Under **Data loss prevention**, select **Policies**, and then
    select **+Create policy** to start the wizard for creating a new
    data loss prevention policy.

    ![](./media/image3.png)

4.  On the **Start with a template or create a custom policy** page,
    scroll down and select **Custom** under **Categories** and **Custom
    policy** under **Templates**. By default, both options should
    already be selected , select **Next**.

    ![](./media/image6.png)

5.  On the **Name your DLP policy** page,
    type `Credit Card DLP Policy` in the **Name** field
    and `Protect credit card numbers from being shared.` in
    the **Description** field. Select **Next**.

   ![](./media/image8.png)

6.  On the **Assign admin units** page, select **Next**.

7.  On the **Choose locations to apply the policy** page, make sure that
    the **Teams chat and channel messages** option is enabled and all of
    the other options are disabled and select **Next**.

   ![](./media/image10.png)

8.  On the **Define policy settings** page, select **Create or customize
    advanced DLP rules** and select **Next**.

   ![](./media/image12.png)

9.  On the **Customize advanced DLP rules** page, select **+ Create
    rule**.

   ![](./media/image14.png)

10. On the **Create rule** page, type `Credit card
    information` in the **Name** field.

   ![](./media/image16.png)

11. Under **Conditions** on the **Create rule** page, select **+ Add
    condition** and select **Content is shared from Microsoft 365** from
    the dropdown menu.

    ![](./media/image18.png)

12. In the new **Content is shared from Microsoft 365** section, select
    the **with people outside my organization** option.

   ![](./media/image19.png)

13. Select **+ Add Condition** and then select **Content contains** from
    the dropdown menu.

   ![](./media/image22.png)

14. In the new **Content contains** area, select **Add** and
    select **Sensitive info types** from the dropdown menu.

    ![](./media/image24.png)

15. On the **Sensitive info types** page, select **Credit Card
    Number** and select **Add**.

    ![](./media/nw30.png)

16. On the **Create rule** page, select **+ Add an action** and
    select **Restrict access or encrypt the content in Microsoft 365
    locations**.

    ![](./media/image28.png)

17. Ensure that the radio button in front of **Block users from receiving email, or accessing shared SharePoint, OneDrive, and Team files, and Power BI items** and **Block only people outside your organization** are selected.

   ![](./media/image29.png)

18. On the **Create rule** page, in the **User notifications** section,
    select the switch to put it in the **On** position.

   ![](./media/image32.png)

19. On the **Create rule** page, in the **User** **overrides** section,
    under the **Allow overrides from M365 services**, check the
    box **Allow overrides from M365 services. Allows users in
    Exchange,** **SharePoint, OneDrive and Teams to override policy
    restrictions.**

    ![](./media/image34.png)

**Note**: If you were not able to select the check box of **Allow
overrides from M365 services**, enable the check box of **Notify users
in Office 365 with a policy tip** which can be found on the **Create
rule** page under the **User notification \>\\ \>Microsoft 365
services** section from the previous step. Then select the check box
of **Allow overrides from M365 services. Allows users in Exchange,**
**SharePoint, OneDrive and Teams to override policy restrictions.**

20. Check the box **Require a business justification to override**.

    ![](./media/image35.png)

21. In the **Incident reports** section, in the **Use this severity
    level in admin alerts and reports** dropdown, select **Low**.

    ![](./media/image38.png)

22. Select **Save**, then select **Next**.

   ![](./media/image40.png)

23. On the **Policy mode** page select **Run the policy
    in simulation mode** and select **Show policy tips while in test**
    **mode**.


![](./media/image42.png)

24.  Select **Submit** to create the policy.

![](./media/image44.png)

26. Once the policy is created select **Done**.

![](./media/image47.png)

You have now created a DLP policy that scans for Credit Card numbers in
Microsoft Teams chats and channels and allows users to provide a
business justification to override the policy.

### Task 2 – Modifying a DLP policy

In this task, you will modify the existing DLP policy you created in the
previous step to also scan e-mails for Credit Card information and
inform users if they want to share this content in an e-mail.

1.  In the **Microsoft Purview** portal, in the left navigation pane,
    select **Solutions** \> **Data loss prevention**.

    ![](./media/image1.png)


2.  Under **Data loss prevention**, select **Policies**, and then select
    the policy named **Credit Card DLP Policy** and then select **Edit
    policy**(pencil icon) to open the policy wizard.

![](./media/image48.png)  

4.  On the **Name your DLP policy** and **Assign admin units** page,
    select **Next**.

5.  On the **Choose locations to apply the policy** page, enable
    the **Exchange email** option and then select **Next** until you
    reach the **Submit** page. Make sure that the rest of
    the locations are disabled.

    ![](./media/image51.png)

6. Select **Submit** to apply the change you made in the policy.

    ![](./media/image53.png)

7. Once the policy is updated select **Done**.

   ![](./media/image56.png)

You have now modified an existing DLP policy and changed the locations
it scans for content.

### Task 3 – Activating a policy in test mode

In this task, you will activate the credit card information DLP policy
you created in test mode so it enforces its protective actions.

1.  In the **Microsoft Purview** portal, in the left navigation pane,
    select **Solutions** \> **Data loss prevention**.

![](./media/image1.png)

3.  Under **Data loss prevention**, select **Policies**, and then select
    the policy named **Credit Card DLP Policy** and then select **Edit
    policy**(pencil icon) to open the policy wizard.

![](./media/image48.png)

4.  Select **Next** until you reach the **Policy mode** page and select **Turn** **the** **policy on immediately**.

   ![](./media/image63.png)

5.  Select **Next**, then select **Submit** to activate the policy.

![](./media/image66.png)

6. Once the policy is updated select **Done**.

   ![](./media/image68.png)

You have successfully activated the DLP Policy. If the policy detects an
attempt to share credit card information, it will now block the attempt
and allow the users to provide a business justification to override the
block action.

## Exercise 2 – Managing DLP Policies

### Task 1 – Modifying policy priority

After creating two DLP policies, you want to make sure that the more
restrictive policy is processed at a higher priority than the less
restrictive policy. For this reason, you want to move the EmployeeID DLP
Policy into the higher priority.

1.  In the **Microsoft Purview** portal, in the left navigation pane,
    select **Solutions** \> **Data loss prevention**.

    ![](./media/image1.png)

2.  Under **Data loss prevention**, select **Policies**, and then select
    the policy named **Credit Card DLP Policy**. Click on the vertical ellipsis, then select **Move to top**.

![](./media/image71.png)

3.  In the **Data loss prevention** window, select **Refresh** and
    review the priority in the **Order** column of the policy table.

![](./media/image73.png)

You successfully modified the priority of your DLP policies. If both
policies match the same content the action of the higher priority policy
will be enforced.

## Summary:

In this lab, you've configured and managed Data Loss Prevention (DLP) policies within Microsoft Purview to enhance data security. First, you've created a DLP policy in test mode designed to detect credit card information shared externally within Microsoft Teams, notifying users and allowing them to justify overrides. Then, you've modified this policy to scan email communications as well. Finally, you've activated the policy to enforce restrictions and adjust policy priorities to ensure the most restrictive policies are processed first. By completing these tasks, you've understood the essentials of configuring and managing DLP policies to protect sensitive data effectively.
