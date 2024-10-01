# Lab 4 – Configuring and Implementing Sensitivity Labels for Information Protection

# Objective:

In this lab you will assume the role of <span class="mark">Patti
Fernandez</span>, a System Administrator for Contoso Ltd. Your
organization is based in Rednitzhembach, Germany and is currently
implementing a sensitivity plan to ensure that all employee documents in
the HR department have been marked with a sensitivity label as part of
your organizations information protection policies.

## Exercise 1 – Enabling support for sensitivity labels

In this task, you will install the MSOnline module and the SharePoint
Online PowerShell module and enable support for sensitivity labels on
your tenant.

1.  Select the windows symbol in the taskbar with the right mouse button
    and select **Windows PowerShell (Admin)** and run as administrator.

<img src="./media/image1.png" style="width:6.26806in;height:3.90417in"
alt="A screenshot of a computer Description automatically generated" />

2.  Confirm the **User Account Control** window with **Yes** and press
    Enter.

3.  Enter the following cmdlet to install the latest Microsoft Online
    PowerShell module version:

**+++Install-Module -Name MSOnline+++**

<img src="./media/image2.png" style="width:6.26806in;height:3.28958in"
alt="A screenshot of a computer Description automatically generated" />

4.  Confirm the NuGet security dialog and the Untrusted repository
    security dialog with Y for Yes and press Enter. This may take a
    while to complete processing.

<img src="./media/image3.png" style="width:6.26806in;height:3.28958in"
alt="BrokenImage" />

5.  Enter the following cmdlet to install the latest SharePoint Online
    PowerShell module version:

**+++Install-Module -NameMicrosoft.Online.SharePoint.PowerShell+++**

<img src="./media/image4.png" style="width:6.26806in;height:3.28958in"
alt="A screenshot of a computer Description automatically generated" />

6.  Confirm the Untrusted repository security dialog with **Y** for Yes
    and press Enter.

<img src="./media/image5.png" style="width:6.26806in;height:3.28958in"
alt="A screenshot of a computer screen Description automatically generated" />

7.  Enter the following cmdlet to connect to the Microsoft Online
    service:

**+++Connect-MsolService+++**

<img src="./media/image6.png" style="width:6.26806in;height:3.28958in"
alt="BrokenImage" />

8.  In the **Sign in to your account** form, log in as **Patti
    Fernandez** using the username **PattiF@WWLxXXXXXX.onmicrosoft.com**
    and the User Password given on your resources tab.

<img src="./media/image7.png" style="width:6.26806in;height:4.41389in"
alt="A screenshot of a computer screen Description automatically generated" />

9.  After signing in, go the **PowerShell window**.

10. Enter the following cmdlet to get the domain:

**+++\\domain = get-msoldomain+++**

<img src="./media/image8.png" style="width:6.26806in;height:3.29583in"
alt="BrokenImage" />

11. Enter the following cmdlet to create the SharePoint admin url:

**+++\\adminurl = "https://" +\\domain.Name.split('.')\[0\] +"-admin.sharepoint.com"+++**

<img src="./media/image9.png" style="width:6.26806in;height:3.29583in"
alt="A screenshot of a computer screen Description automatically generated" />

12. Enter the following cmdlet to sign in to the SharePoint Online admin
    center:

**+++Connect-SPOService -url \\adminurl+++**

<img src="./media/image10.png" style="width:6.26806in;height:3.29583in"
alt="A screenshot of a computer screen Description automatically generated" />

13. In the **Sign in to your account** form, log in as **MOD
    Administrator** using the credentials provided in the resources tab
    of your lab environment.

14. After signing in, select the PowerShell window.

15. Enter the following cmdlet to enable support for sensitivity labels:

**+++Set-SPOTenant -EnableAIPIntegration \$true+++**

<img src="./media/image11.png" style="width:6.26806in;height:3.29583in"
alt="BrokenImage" />

16. Confirm the changes with **Y** for Yes and press Enter.

<img src="./media/image12.png" style="width:6.26806in;height:3.29583in"
alt="BrokenImage" />

17. Close the **PowerShell** window.

You have successfully enabled support for sensitivity labels with Teams
and SharePoint sites.

## Exercise 2 – Creating Sensitivity Labels

In this task, your HR department has requested a sensitivity label to
apply to HR employee documents. You will create a sensitivity label for
Internal documents and a sublabel for the HR department.

1.  In **Microsoft Edge** navigate to
    **+++**https://purview.microsoft.com**+++** and log in as **Patti
    Fernandez** using the username **PattiF@WWLxXXXXXX.onmicrosoft.com**
    and the User Password given on your resources tab.

2.  

3.  In the Microsoft Purview portal, on the left navigation pane, select
    **Solutions** \> **Information Protection**.

<img src="./media/image13.png"
style="width:6.26806in;height:3.53472in" />

4.  From the sub-navigation select **Sensitivity** **Labels** \>
    **Create Labels**.

<img src="./media/image15.png"
style="width:6.26806in;height:3.53472in" />

5.  The **New sensitivity label** wizard will start. On the **Label**
    **details** page for the **Name**, **Description for
    admins** and **Description for users**, enter the following
    information:

    - Name: **+++Internal+++**

    - Display name: **+++Internal+++**

    - Description for users: **+++Internal sensitivity label+++**

    - Description for admins: **+++Internal sensitivity
      label for Contoso.+++**

<img src="./media/image16.png" style="width:6.26719in;height:3.19149in"
alt="Graphical user interface, text, application, email Description automatically generated" />

6.  Select **Next**.

<img src="./media/image17.png" style="width:6.26736in;height:3.18572in"
alt="Graphical user interface, text, application Description automatically generated" />

7.  On the **Define the scope for this label** page, select the
    option **Items** which protects emails, files, and Power BI items.
    Uncheck the box near **Meetings**.

<img src="./media/image18.png" style="width:6.26678in;height:3.11779in"
alt="A screenshot of a computer Description automatically generated" />

8.  Select **Next**.

<img src="./media/image19.png" style="width:6.26806in;height:3.34187in"
alt="A screenshot of a computer Description automatically generated" />

9.  On the **Choose protection settings for labeled items** page,
    select **Next**.

<img src="./media/image20.png" style="width:6.26806in;height:3.33957in"
alt="A screenshot of a computer Description automatically generated" />

10. On the **Auto-labeling** for files and emails page, select **Next**.

<img src="./media/image21.png" style="width:6.26719in;height:3.20213in"
alt="A screenshot of a computer Description automatically generated" />

11. On the **Define protection settings for groups and sites** page,
    select **Next**.

<img src="./media/image22.png" style="width:6.26712in;height:3.17021in"
alt="A screenshot of a computer Description automatically generated" />

12. On the **Auto-labeling for schematized data** **assets
    (preview)** page, select **Next**.

<img src="./media/image23.png" style="width:6.268in;height:3.17021in"
alt="Graphical user interface, text, application Description automatically generated" />

13. On the **Review your settings and finish** page, select **Create
    label**.

<img src="./media/image24.png" style="width:6.26759in;height:3.19149in"
alt="A screenshot of a computer Description automatically generated" />

14. The label will be created and when complete a message will
    display: **Your sensitivity label was created**

15. Select **Don’t create a policy yet** and then select **Done**.

<img src="./media/image25.png" style="width:6.26759in;height:3.18085in"
alt="A screenshot of a computer screen Description automatically generated" />

16. On the **Information protection** page, highlight (without
    selecting) the newly created **Internal** label and select the
    vertical **…**.

17. Select the **+ Add sub label** from the drop-down menu.

<img src="./media/image26.png" style="width:4.99146in;height:3.3206in"
alt="A screenshot of a computer Description automatically generated" />

18. The **New sensitivity label** wizard will start. On the **Label
    details** page, enter the following information:

    - Name: **+++Employee data (HR)** **+++**

    - Display name: **+++Employee data (HR)** **+++**

    - Description for users: **+++This HR
      label is the default label for all specified documents in the
      HR Department.** **+++**

    - Description for admins: **+++This label is created in**
      **consultation with Ms.Jones (Head of HR
      department). Contact her,** **when you want to change
      settings of the label.** **+++**

<img src="./media/image28.png"
style="width:6.26806in;height:3.32986in" />

19. Select **Next**.

<img src="./media/image30.png"
style="width:6.26806in;height:3.32153in" />

20. On the **Define the scope for this label** page, select the
    option **Items** which protects emails, files, and Meetings.
    Select **Next**.

<img src="./media/image32.png"
style="width:6.26806in;height:3.32986in" />

21. On the **Choose protection settings for labeled items** page, select
    the **Control Access** option. Select **Next**.

<img src="./media/image34.png"
style="width:6.26806in;height:3.32986in" />

22. On **Encryption Page**, select **Configure
    encryption** **settings**.

<img src="./media/image36.png"
style="width:6.26806in;height:3.32986in" />

23. Enter the following information into the encryption settings:

    - Assign permissions now or let users decide?: **Assign permissions
      now**

    - User access to content expires: **Never**

    - Allow offline access: **Only for a number of days**

    - Users have offline access to the content for this many
      days: **15**

<img src="./media/image37.png" style="width:6.34043in;height:4.31852in"
alt="A screenshot of a computer Description automatically generated" />

24. Select the **Assign permissions** link.

<img src="./media/image38.png" style="width:6.74468in;height:4.78121in"
alt="A screenshot of a computer Description automatically generated" />

25. On the **Assign permissions** pane, select the **+ Add any
    authenticated users**.

<img src="./media/image39.png" style="width:5.47872in;height:6.1616in"
alt="BrokenImage" />

26. Select **Save**.

<img src="./media/image40.png" style="width:5.43617in;height:6.05692in"
alt="BrokenImage" />

27. On the **Encryption** page, select **Next**.

<img src="./media/image41.png" style="width:5.98079in;height:4.34043in"
alt="A screenshot of a computer Description automatically generated" />

28. On the **Auto-labeling for files and emails** page, select **Next**.

<img src="./media/image42.png" style="width:6.10638in;height:4.22728in"
alt="A screenshot of a computer Description automatically generated" />

29. On the **Define protection settings for groups and sites** page,
    select **Next**.

<img src="./media/image43.png" style="width:5.88298in;height:4.23499in"
alt="A screenshot of a computer Description automatically generated" />

30. On the **Auto-labeling for schematized data assests
    (preview)** page, select **Next**.

<img src="./media/image44.png" style="width:5.98936in;height:4.36362in"
alt="A screenshot of a computer Description automatically generated" />

31. On the **Review your settings and finish** page, select **Create
    label**.

<img src="./media/image45.png" style="width:6.30826in;height:4.5in"
alt="A screenshot of a computer Description automatically generated" />

32. The label will be created and when complete a message will
    display **Your sensitivity label was created**.

33. Select **Don’t create a policy yet** and then select **Done**.

<img src="./media/image46.png" style="width:5.89362in;height:4.14329in"
alt="A screenshot of a computer screen Description automatically generated" />

34. Keep the tab open to continue to the next task.

You have successfully created a sensitivity label for your organizations
internal policies and a sensitivity sublabel for the Human Resources
(HR) department.

## Exercise 3 – Publishing Sensitivity Labels

You will now publish the Internal and HR sensitivity label so that the
published sensitivity labels will be available for the HR users to apply
to their HR documents.

1.  In **Microsoft Edge** navigate to
    **+++https://purview.microsoft.com+++** and log in as **Patti
    Fernandez** using the username **PattiF@WWLxXXXXXX.onmicrosoft.com**
    and the User Password given on your resources tab.

2.  In the Microsoft Purview portal, on the left navigation pane, select
    **Solutions** \> **Information Protection**.

<img src="./media/image13.png"
style="width:6.26806in;height:3.53472in" />

3.  

4.  

5.  From the sub-navigation select **Sensitivity Labels** \> **Publish**
    **Labels**.

<img src="./media/image48.png"
style="width:6.26806in;height:3.32986in" />

6.  The publish sensitivity labels wizard will start.

7.  On the **Choose sensitivity labels to publish** page, select
    the **Choose sensitivity labels to publish** link.

<img src="./media/image49.png" style="width:6.26806in;height:3.11616in"
alt="A screenshot of a computer Description automatically generated" />

8.  A side bar called **Sensitivity labels to publish** will appear on
    the right.

9.  Select the **Internal** and **Internal/Employee Data
    (HR)** checkboxes.

<img src="./media/image50.png" style="width:5.92553in;height:7.26682in"
alt="A screenshot of a computer Description automatically generated" />

10. Select **Add**.

<img src="./media/image51.png" style="width:4.29787in;height:5.45007in"
alt="A screenshot of a computer Description automatically generated" />

11. On the **Choose sensitivity labels to publish** page,
    select **Next**.

<img src="./media/image52.png" style="width:4.4163in;height:2.94649in"
alt="A screenshot of a computer Description automatically generated" />

12. On the **Publish to users and groups page**, select **Next**.

<img src="./media/image54.png" style="width:4.49118in;height:3.05327in"
alt="A screenshot of a computer Description automatically generated" />

13. On the **Policy settings** page, select **Next**.

<img src="./media/image55.png" style="width:4.46879in;height:2.93598in"
alt="BrokenImage" />

14. On the **Apply a default label to documents** page, select **Next**.

<img src="./media/image56.png" style="width:4.44821in;height:2.9465in"
alt="A screenshot of a computer Description automatically generated" />

15. 

16. On the **Apply a default label to emails** page, select **Next**.

17. On the **Default settings for meetings and calendar events**,
    select **Next**.

18. 

19. On the **Default settings for Fabric and Power BI content page**,
    select **Next**.

20. On the **Name your policy** page, enter the following information:

    - Name: **+++Internal HR employee data+++**

    - Enter a description for your sensitivity label
      policy: **+++This HR label is to be applied to internal HR
      employee data.** **+++**

<img src="./media/image59.png" style="width:6.06383in;height:4.03676in"
alt="Graphical user interface, text, application, email Description automatically generated" />

21. Select **Next**.

<img src="./media/image60.png" style="width:6.45745in;height:4.29963in"
alt="Graphical user interface, text, application Description automatically generated" />

22. On the **Review and finish** page, select **Submit**.

<img src="./media/image61.png" style="width:4.45903in;height:2.89362in"
alt="Graphical user interface, text, application Description automatically generated" />

23. The policy will be created and when complete a message will
    display **New policy created**.

24. Select **Done and proceed to next task without closing the window**.

<img src="./media/image62.png" style="width:4.37431in;height:2.93617in"
alt="A screenshot of a computer Description automatically generated" />

You have successfully published the Internal and HR sensitivity labels.
Note that it can take up to 24 hours for changes to replicate to all
users and services.

## Exercise 4 – Working with Sensitivity Labels

In this task, you will create sensitivity labels in Word and Outlook
emails. The document created will be stored in OneDrive and sent to an
HR employee via email.

1.  

2.  Navigate to **+++https://portal.office.com+++** and log in as
    **Patti Fernandez**.

3.  If a **Get your work done with Office 365** message is shown, close
    it.

<img src="./media/image63.png" style="width:6.32979in;height:3.3617in"
alt="Graphical user interface Description automatically generated" />

4.  Select the **Microsoft Word** symbol from the left side pane to open
    Word Online.

<img src="./media/image64.png" style="width:6.26806in;height:3.39362in"
alt="Graphical user interface, website Description automatically generated" />

5.  Select **New blank document** to create a new document.

<img src="./media/image65.png" style="width:6.32083in;height:3.41489in"
alt="Graphical user interface, website Description automatically generated" />

6.  If a **Your privacy options** message is shown, close it with
    selecting **Close**.

<img src="./media/image66.png" style="width:6.26736in;height:3.15957in"
alt="BrokenImage" />

7.  Enter the following contents into the word document:

**+++Important HR employee document.+++**

<img src="./media/image67.png" style="width:6.32078in;height:3.06383in"
alt="Graphical user interface, application, Word Description automatically generated" />

8.  Select **Sensitivity** from the top pane to open the dropdown menu.

<img src="./media/image68.png" style="width:6.26759in;height:3.07447in"
alt="Graphical user interface, application, Word Description automatically generated" />

9.  Select **Internal** \>**Employee data (HR)** to apply the label.

**Note**: Be aware, the script you ran in task 1 of this exercise
activated sensitivity labels in Word for your tenant. It can sometimes
take an hour for that activation to be realized in Microsoft Word
online. If you don't see the Sensitivity label menu in Word, you may
need to return to this lab later or make sure you properly completed
task 1 of this exercise.

<img src="./media/image69.png" style="width:6.268in;height:3.09574in"
alt="BrokenImage" />

10. Select the **Document – Saved** in the upper left of the window,
    enter **HR Document** as the File Name and press **Enter** key.

<img src="./media/image70.png" style="width:6.04236in;height:3.31915in"
alt="Graphical user interface, application, Word Description automatically generated" />

11. Close the word tab to return to the **Office 365** tab. Select
    the **Outlook** symbol from the left side pane to
    open **Outlook** on the web.

<img src="./media/image71.png" style="width:6.26716in;height:3.39362in"
alt="Graphical user interface, text, application Description automatically generated" />

12. If a welcome message is shown, close it with selecting the **X**.

13. In Outlook on the web, select **New message** from the upper left of
    the window.

<img src="./media/image72.png" style="width:6.26806in;height:3.53472in"
alt="A screenshot of a computer Description automatically generated" />

14. In the **To** field enter the name: **Adele** and select **Adele
    Vance** from the drop-down list.

<img src="./media/image74.png" style="width:6.26806in;height:3.213in" />

15. In the subject field, enter: **+++Employee data for HR+++**.

16. Within the email message (the large content panel at the bottom of
    the page), insert the following message:

> **+++Dear** **Ms. Adele,**
>
> **Please find attached the important HR employee document.**
>
> **Kind regards,**
>
> **Patti Fernandez+++**

<img src="./media/image76.png" style="width:6.26806in;height:3.53472in"
alt="A screenshot of a computer Description automatically generated" />

17. Select the **paperclip symbol** from the bottom menu.

<img src="./media/image78.png"
style="width:6.26806in;height:3.53472in" />

18. 

19. Select the **HR Document.docx** below **Suggested attachments** to
    attach the document.

20. 

21. Select **Send** to send out the email message with attached
    document.

22. Leave the browser window open.

You have successfully created an HR Word document with a sensitivity
label, which was saved onto your OneDrive. You then emailed to document
to an HR staff member where the email was also set with a sensitivity
label.

In the trial account, note that you will be able to send the mail but it
will bounce back and will not be able to reach the receiver from your
current tenant.

## Exercise 5 – Configuring Auto Labelling

n this task, you will create a **Sensitivity Label** that will auto
label documents and emails found to contain information related to
the **European General Data Protection Regulation (GPDR)**.

1.  In **Microsoft Edge**, the Microsoft Purview portal tab should still
    be open.

2.  You should be logged into the portal as **Patti** **Fernandez**.

3.  Under the **Information protection**, select **Label**, highlight
    (without selecting) the existing **Internal** label, and select the
    three dots. Select the **+ Create sublabel** menu item.

<img src="./media/image81.png" style="width:5.03401in;height:3.24348in"
alt="A screenshot of a computer Description automatically generated" />

4.  The **New sensitivity label** wizard will start. On the **label
    details** page, enter the following information:

    - Name: **+++GDPR Germany+++**

    - Display name: **+++GDPR Germany+++**

    - Description for users: **+++This document or email contains data
      related to the European General Data
      Protection Regulation(GPDR) for the region Germany.** **+++**

    - Description for admins: **+++This label is auto applied
      to German GDPR documents.** **+++**

5.  Select **Next**.

<img src="./media/image82.png" style="width:6.26806in;height:4.51302in"
alt="BrokenImage" />

6.  On the **Define the scope for this label** page, select the
    option **Items** which protects Files, Emails, and Meetings items.
    Then select **Next**.

<img src="./media/image83.png" style="width:6.26806in;height:4.46052in"
alt="BrokenImage" />

7.  On the **Choose protection settings for labeled items** page,
    select **Next**.

<img src="./media/image84.png" style="width:6.26806in;height:4.49244in"
alt="BrokenImage" />

8.  On the **Auto-labeling for files and emails** page, set
    the **Auto-labeling for files and emails** to enabled.

<img src="./media/image85.png" style="width:4.49095in;height:3.15956in"
alt="Graphical user interface, text, application Description automatically generated" />

9.  In the **Detect content that matches these conditions** section,
    select **+Add condition** and then select **Content contains**.

<img src="./media/image86.png" style="width:5.90426in;height:4.1145in"
alt="BrokenImage" />

10. In **Content contains** section select the **Add** text and then
    select **Sensitive info types**.

<img src="./media/image87.png" style="width:6.64894in;height:4.76058in"
alt="A screenshot of a computer Description automatically generated" />

11. A **Sensitive info types** panel will be displayed on the right.

12. In the **Search for sensitive info types** search panel, enter the
    following information:

**German**

13. Press the enter button, the results will display sensitivity info
    types related to Germany. Press the **Select all** check box.

<img src="./media/image88.png" style="width:6.06383in;height:4.41164in"
alt="BrokenImage" />

14. Select **Add**.

<img src="./media/image89.png" style="width:4.60833in;height:3.17021in"
alt="BrokenImage" />

15. Select **Next**.

<img src="./media/image90.png" style="width:4.53333in;height:3.08511in"
alt="A screenshot of a computer Description automatically generated" />

16. On the **Define protection settings for groups and sites** page,
    select **Next**.

<img src="./media/image91.png" style="width:4.56528in;height:3.19149in"
alt="A screenshot of a computer Description automatically generated" />

17. 

18. On the **Auto-labeling for schematized data** **assets
    (preview)** page, select **Next**.

19. On the **Auto-labeling for schematized data assets (preview)** page,
    select **Next**.

20. On the **Review your settings and finish** page, select **Create
    label**.

21. The label will be created and when complete a message will
    display: **Your sensitivity label was created**. Then
    select **Done**.

<img src="./media/image93.png" style="width:6.40426in;height:4.56602in"
alt="Graphical user interface, text, application, Word Description automatically generated" />

22. From the sub-navigation select **Sensitivity Labels** \> **Publish
    Labels**.

23. 

<img src="./media/image48.png"
style="width:6.26806in;height:3.32986in" />

24. The **Publish sensitivity labels wizard** will start.

<img src="./media/image94.png" style="width:4.50208in;height:3.14894in"
alt="Graphical user interface, text, application, Word Description automatically generated" />

25. On the Choose sensitivity labels to publish page, select the Choose
    sensitivity labels to publish link.

<img src="./media/image95.png" style="width:4.59722in;height:3.19149in"
alt="A screenshot of a computer Description automatically generated" />

26. A side bar called **Sensitivity labels to publish** will appear on
    the right.

<img src="./media/image96.png" style="width:4.59722in;height:3.17021in"
alt="Graphical user interface, application, Word Description automatically generated" />

27. Select the **Internal** and **Internal/GDPR Germany** checkbox and
    select **Add**.

<img src="./media/image97.png" style="width:4.42708in;height:3.20213in"
alt="Graphical user interface, application, Word Description automatically generated" />

28. On the **Choose sensitivity labels to publish** page,
    select **Next**.

<img src="./media/image98.png" style="width:4.61875in;height:3.18085in"
alt="Graphical user interface, text, application, Word Description automatically generated" />

29. On the **Publish to users and groups** page, select **Next**.

<img src="./media/image99.png" style="width:4.47014in;height:3.17021in"
alt="Graphical user interface, text, application Description automatically generated" />

30. On the **Policy settings** page, select **Next**.

<img src="./media/image100.png" style="width:4.43819in;height:3.12766in"
alt="Graphical user interface, text, application, Word Description automatically generated" />

31. On the **Apply a default label to documents** page, select **Next**.

<img src="./media/image101.png" style="width:4.43819in;height:3.18085in"
alt="Graphical user interface, text, application Description automatically generated" />

32. On the **Apply a default label to emails** page, select **Next**.

33. On the **Default settings for meetings and calendar events**,
    select **Next**.

34. 

35. 

36. 

37. On the **Default settings for Fabric and Power BI content page**,
    select **Next**.

38. On the **Name your policy** page, enter the following information:

    - Name: **+++GDPR Germany policy+++**

    - Enter a description for your sensitivity label
      policy: **+++This auto apply sensitivity labels policy is for the
      GDPR region of** **Germany.** **+++**

39. Select **Next**.

<img src="./media/image104.png" style="width:4.42708in;height:3.1383in"
alt="Graphical user interface, text, application Description automatically generated" />

40. On the **Review and finish** page, select **Submit**.

<img src="./media/image105.png" style="width:4.55319in;height:3.17021in"
alt="Graphical user interface, application Description automatically generated" />

41. The policy will be created and when complete a message will
    display, **New policy created**.

42. Select **Done**.

<img src="./media/image106.png" style="width:4.54444in;height:3.18085in"
alt="Graphical user interface, text, application, Word Description automatically generated" />

## Summary:

You have successfully created and published an auto apply sensitivity
label for GDPR documents in the region Germany.

Be aware that it can take up to 24 hours for auto applied sensitivity
labels to be applied, this duration will be longer when applied to more
than 25,000 documents (that is, the daily limit).​
