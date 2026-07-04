# Exercise 1: Publish and Share Your Work

### Estimated Duration: 60 Minutes

## 📘 Scenario

The **Item Sales Report** — a pre-built `.pbix` file provided in your lab environment — currently lives only in Power BI Desktop on your lab machine. Contoso Retail's leadership team wants this report available in the cloud — viewable from any device, summarized in a single executive dashboard, shared with the right people at the right permission level, and refreshed automatically every day.

In this exercise, you will move your report to the Power BI Service and make it available to your audience: you will publish the report and its semantic model, build a dashboard from its key visuals, review the three primary sharing methods, and configure scheduled refresh.

## 🎯 Objectives

In this exercise, you will complete the following tasks:

- Task 1: Launch the environment and open your working report
- Task 2: Power BI Service – Creating a Workspace
- Task 3: Publish from Power BI Desktop to the Power BI Service
- Task 4: Build a dashboard from report tiles
- Task 5: Configure sharing (workspace roles, apps, links)
- Task 6: Set up scheduled refresh

## 🧩 Architecture Diagram

   ![](./Images/arch-exercise-01.png)

## Task 1: Launch the environment and open your working report

In this task, you will open Power BI Desktop on the lab virtual machine and load the pre-built Item Sales Report provided for this lab. Verifying the report opens cleanly is an important checkpoint before publishing — any broken visuals or data errors will be carried into the Power BI Service.

1. On the lab VM, from the desktop or Start menu, open **Power BI Desktop**.

   ![](./Images/images/exercise-1/L2E1T1S1.png)

1. Click on the **Sign-in icon** located in the top-right corner.

    ![](./Images/images/exercise-1/L2E1T1S2.png)

1. Once the "Enter your email address" dialog appears, copy the **Username** and paste it into the **Email** field of the dialog and select **Continue**.

   * **Email/Username**: <inject key="AzureAdUserEmail"></inject>

     ![](./Images/images/exercise-1/L2E1T1S3.png) 

1. After clicking Continue, you will be prompted to sign in again. Use the credentials provided below to sign in, and then click **Next (2)** to proceed.

   * **Email/Username**: <inject key="AzureAdUserEmail"></inject> **(1)**

     ![](./Images/images/exercise-1/L2E1T1S4.png)

1. Enter the temporary access pass and click on **Sign in (2)**

   - **Temporary Access Pass:** <inject key="AzureAdUserPassword"></inject> **(1)**

     ![02](./Images/images/exercise-1/L2E1T1S5.png)

1. For the pop-up **Automatically sign in to all desktop apps and websites on this device?** window, select **No,this app only**

   ![02](./Images/images/exercise-1/L2E1T1S6.png)

1. On the **Power BI free license assigned** window, click on **Ok**.

   ![](./Images/images/exercise-1/L2E1T1S7.png)

1. On the **Home** ribbon, click **open (1)** and click **Browse this device (2)**.

   ![](./Images/images/exercise-1/L2E1T1S8.png)

1. In the **Open** dialog, navigate to the path **C:\LabFiles (1)** and select the **Item Sales Report.pbix (2)** file, then click **Open (3)**.

   ![](./Images/images/exercise-1/L2E1T1S9.png)

   > **Note**: If the file is not found at this path, check the **Resources/Files** section of your lab environment for the provided **Item Sales Report.pbix**.

1. Wait for the report to load completely.

1. Review each report page and confirm that all visuals render correctly without error icons.

   ![](./Images/images/exercise-1/L2E1T1S10.png)

1. Click the **Save** icon from the top-left corner to save your workbook with all the changes you've made.

   ![](./Images/images/exercise-1/L2E1T1S11.png)

## Task 2: Power BI Service – Creating a Workspace

In this task, you will create a workspace in the Power BI Service.

1. In the left-hand navigation pane of the Power BI interface, select **Workspaces** to view and manage your available workspaces.
   
    ![](./Images/images/exercise-1/L2E1T2S1.png)

1. Click on **+ New workspace** at the bottom of the Workspaces pane. This will open the **Create a workspace** dialog box.

    ![](./Images/images/exercise-1/L2E1T2S2.png)

1. On the **Create a workspace** page, provide the following details.

    - In the **Name** field, enter **DIAD_<inject key="DeploymentID" enableCopy="false"/> (1)**.

    - In the **Description** field, type **This is DIAD workspace (2)**.

    - Click **Upload (3)** to upload an image that will serve as the workspace logo and help identify your workspace visually.

      ![](./Images/images/exercise-1/L2E1T2S3.png)

1. A file browser dialog box will open. Browse to the **DIAD** folder, then navigate to the **Data** folder at `C:\DIAD\DIADL4\Data`. Select the **VanArsdel\_WSLogo** **(1)** file and click **Open** **(2)**.

      ![](./Images/images/exercise-1/L2E1T2S4.png)

1. Click **Apply** to finalize and create the workspace with your configured settings.

    ![](./Images/images/exercise-1/L2E1T2S5.png)

    > 📌 **Note:** If prompted Introducing task flows, Click on **Got it** to proceed.

    ![](./Images/images/exercise-1/NOTE.png)

1. Once the **DIAD_<inject key="DeploymentID" enableCopy="false"/>** workspace is created, navigate to **Manage Access (1)** to configure user permissions and access levels.

    ![](./Images/images/exercise-1/L2E1T2S6.png)

1. On the **Manage Access** window, click on **+Add people or groups (1)** to add new users or service principals to your workspace.

    ![](./Images/images/exercise-1/L2E1T2S9.png)

1. On the **+Add people or groups** window, search for the service principal using `https://cloudlabs-v2.ai/` and select it from the search results.

1. In the Add people pane, after selecting the service principle **(1)**, select the appropriate role from the drop down. Choose **Admin (2)** to grant administrative permissions, and then click **Add (3)** to confirm. Make sure that is listed on the **Manage access** window.

     ![](./Images/images/exercise-1/L2E1T2S7.png)

1. On the **Manage Access** page, you should see that your account and service principle is listed as an **Admin**.

    ![](./Images/images/exercise-1/L2E1T2S8.png)

## Task 3: Publish from Power BI Desktop to the Power BI Service

In this task, you will publish your report — and the semantic model behind it — from Power BI Desktop into a workspace in the Power BI Service. Publishing is the moment your report stops being a local file and becomes a shared cloud asset.

1. In Power BI Desktop, verify from the top-right corner of the window that you are signed in with your organizational account:

   - **Account:** <inject key="AzureAdUserEmail"></inject>

     ![](./Images/images/exercise-1/L2E1T3S1.png)

1. From the **Home (1)** tab in the top ribbon, click on **Publish (2)** to publish your report to the Power BI Service.

   ![](./Images/images/exercise-1/L2E1T3S2.png)

1. If prompted to save your changes first, click **Save**.

   ![](./Images/images/exercise-1/L2E1T3S3.png)

1. In the **Publish to Power BI** dialog box, select the destination workspace **Workspace-<inject key="DeploymentID" enableCopy="false"/> (1)** and click **Select (2)**.

   ![](./Images/images/exercise-1/L2E1T3S4.png)

1. Wait for the publishing process to complete. A success message appears when it is done.

   ![](./Images/images/exercise-1/L2E1T3S5.png)

1. On the success message, click **Open 'Item Sales Report.pbix' in Power BI** to open the published report in the browser.

   ![](./Images/images/exercise-1/L2E1T3S6.png)

1. In the left navigation pane, select **Workspaces (1)** and open **Workspace-<inject key="DeploymentID" enableCopy="false"/> (2)**.

   ![](./Images/images/exercise-1/L2E1T3S7.png)

1. Verify that the workspace now contains **both** of the following items:

   - The **Item Sales Report** (type: Report)
   - The **Item Sales Report** semantic model (type: Semantic model)

      ![](./Images/images/exercise-1/L2E1T3S8.png)

   > **Note**: The semantic model is published automatically alongside the report. It holds the data, relationships, and measures, and is the object you will configure for scheduled refresh in Task 6.

## Task 4: Build a dashboard from report tiles

In this task, you will create a consolidated executive view by pinning key report visuals to a new dashboard. Unlike a report, a dashboard is a single-page canvas that can combine tiles from multiple reports — ideal for at-a-glance monitoring by leadership.

1. In the Power BI Service, from the workspace, open the **Item Sales Report**.

   ![](./Images/images/exercise-1/L2E1T4S1.png)

1. Navigate to the first report page and identify a visual that represents a key business metric, such as the item-wise sales bar chart.

1. Hover over the visual and select the **Pin visual** icon from the visual header.

   ![](./Images/images/exercise-1/L2E1T4S2.png)

1. In the **Pin to dashboard** window, select **New dashboard (1)** and enter the following name **(2)**, then click **Pin (3)**:

   ```
   Executive Dashboard
   ```

   ![](./Images/images/exercise-1/L2E1T4S3.png)

1. When the **Pinned to dashboard** confirmation appears, close it and remain on the report.

   ![](./Images/images/exercise-1/L2E1T4S3.png)

1. Repeat the pinning process for additional visuals — this time, in the **Pin to dashboard** window, select **Existing dashboard (1)**, ensure **Executive Dashboard (2)** is selected, and click **Pin (3)**.

   ![](./Images/images/exercise-1/L2E1T4S5.png)

1. Pin **at least four visuals** in total, from this page or other report pages, so that together they provide a meaningful executive summary (for example: total revenue, top items by quantity, a trend over time, and a KPI or card visual).

1. In the left navigation pane, select your workspace and open the **Executive Dashboard**.

   ![](./Images/images/exercise-1/L2E1T4S6.png)

1. Rearrange and resize the tiles by dragging them, so the layout reads cleanly — place the single most important metric at the top-left, where the eye lands first.

   ![](./Images/images/exercise-1/L2E1T4S7.png)

## Task 5: Configure sharing (workspace roles, apps, links)

In this task, you will review the three primary ways to share content in the Power BI Service — **workspace access** (roles for collaborators), **direct item sharing** (links and invitations for specific reports or dashboards), and **apps** (a packaged, read-only experience for broad audiences) — and understand when to use each.

1. In the Power BI Service, return to **Workspace-<inject key="DeploymentID" enableCopy="false"/>** and review its contents.

   ![](./Images/images/exercise-1/L2E1T5S1.png)

1. From the upper-right corner of the workspace, click **Manage access**.

   ![](./Images/images/exercise-1/L2E1T5S2.png)

1. In the **Manage access** pane, review the four available workspace roles:

   - **Admin** — full control, including managing workspace access and settings
   - **Member** — can edit, publish, and share content
   - **Contributor** — can create and edit content, but cannot manage access
   - **Viewer** — can only view and interact with content.

1. Click **+ Add people or groups (1)**, enter a test user or group provided in your lab instructions, set the permission to **Viewer (2)** using the dropdown, and click **Add (3)**.

   ![](./Images/images/exercise-1/L2E1T5S4.png)

   ![](./Images/images/exercise-1/L2E1T5S5.png)

1. Open the **Item Sales Report (1)** and, from the top menu, click **Share (2)**.

   ![](./Images/images/exercise-1/L2E1T5S6.png)

1. In the **Send link** dialog, review the available direct sharing options:

   - **Sharing with specific people** — enter a name or email to send an invitation
   - **Copy link** — generate a shareable link with configurable permissions
   - **Link settings** — control whether recipients can share further or build content on the underlying data

     ![](./Images/images/exercise-1/L2E1T5S7.png)

1. Click the **link settings (gear/pencil) icon**, review the audience options — **People in your organization**, **People with existing access**, and **Specific people** — and the additional permissions checkboxes, then click **Apply**.

   ![](./Images/images/exercise-1/L2E1T5S8.png)

1. Close the sharing dialog and return to the workspace.

1. From the workspace toolbar, click **Create app**.

   ![](./Images/images/exercise-1/L2E1T5S9.png)

1. On the **Setup** tab, review and configure the following:

   - **App name (1)**: `Contoso Executive Insights`
   - **Description (2)**: `Board-ready sales insights for the Contoso executive team.`
   - Click **Next: Add content (3)**

     ![](./Images/images/exercise-1/L2E1T5S10.png)

1. On the **Content** tab, click **+ Add content (1)**, select the **Item Sales Report** and the **Executive Dashboard (2)**, click **Add (3)**, and review the navigation order, then click **Next: Add audience (4)**.

   ![](./Images/images/exercise-1/L2E1T5S11.png)

1. On the **Audience** tab, review how audiences control who sees which content, and review the audience access options.

   ![](./Images/images/exercise-1/L2E1T5S12.png)

1. If your environment allows app publishing, click **Publish app** and confirm.

   ![](./Images/images/exercise-1/L2E1T5S13.png)

## Task 6: Set up scheduled refresh

In this task, you will configure the published semantic model to refresh on a schedule so that the report and dashboard always reflect current data without any manual steps.

1. In the workspace, locate the **Item Sales Report** semantic model.

   ![](./Images/images/exercise-1/L2E1T6S1.png)

1. Hover over the semantic model, click the **More options (…) (1)** menu, and select **Settings (2)**.

   ![](./Images/images/exercise-1/L2E1T6S2.png)

1. On the settings page, review the available sections:

   - **Gateway and cloud connections**
   - **Data source credentials**
   - **Refresh** (scheduled refresh)
   - **Refresh history** (accessible from the Refresh section or the semantic model's Refresh menu)

     ![](./Images/images/exercise-1/L2E1T6S3.png)

1. Expand **Data source credentials** and verify whether authentication is required for the data source.

1. If a credentials warning is displayed, click **Edit credentials (1)**, provide the appropriate **Authentication method (2)** for the lab data source, set the **Privacy level (3)** if prompted, and click **Sign in / Save (4)**.

   ![](./Images/L2E1T5S3.png)

   > **Note**: If your data source is an on-premises file, a data gateway is required for refresh. In this lab environment, review the **Gateway and cloud connections** section and note whether a gateway is configured.

1. Expand the **Refresh** section.

1. Toggle **Configure a refresh schedule** (Keep your data up to date) to **On (2)**.

1. Configure the schedule as follows:

   - **Refresh frequency (3)**: Daily
   - **Time zone (1)**: Select your local time zone
   - Click **Add another time (4)** and set a refresh time, such as **8:00 AM**

     ![](./Images/images/exercise-1/L2E1T6S4.png)

1. Enable the **Send refresh failure notifications** option so the dataset owner is notified when a refresh fails.

   ![](./Images/images/exercise-1/L2E1T6S5.png)

1. Click **Apply** to save the configuration.

   ![](./Images/images/exercise-1/L2E1T6S6.png)

1. Return to the workspace, hover over the semantic model, and click the **Refresh now (circular arrow)** icon to trigger an on-demand refresh and test your configuration.

   ![](./Images/images/exercise-1/L2E1T6S7.png)

1. click the **More options (…) (1)** menu and open the **Refresh history (2)** for the semantic model and verify that the refresh completed successfully.

   ![](./Images/images/exercise-1/L2E1T6S8.png)

## 📝 Summary

In this exercise, you have accomplished the following:

- Opened and reviewed the existing report in Power BI Desktop
- created workspace in the powerbi service
- Published the report and its semantic model to the Power BI Service
- Created an Executive Dashboard by pinning key report visuals
- Reviewed workspace roles, direct sharing, and app publishing
- Configured and tested scheduled refresh for the semantic model

### You have successfully completed the exercise. Click on **Next >>** to continue to the next exercise.

![](./Images/gs-next.png)
