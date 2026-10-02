# Check the Existing Lakehouse and Prepare Access

## Introduction

In this lab, you will locate your existing Oracle Autonomous AI Lakehouse, open Database Actions as the database ADMIN user, and create a workshop database user. You will then sign in as that user to confirm access to Database Actions and Data Studio. If you plan to complete the optional drill-through exercise, you will also prepare the PeakGear source data.

Estimated Time: 20 minutes, plus 15 minutes for the optional PeakGear data load

### About Database Actions

Database Actions is a browser-based interface for working with your Autonomous AI Database. Access from the OCI Console and access to database tools are controlled separately. In this lab, you will use the OCI Console to find the Lakehouse, then use database credentials to sign in to Database Actions.

### Objectives

In this lab, you will:

- Locate an existing Autonomous AI Lakehouse in your tenancy.
- Open Database Actions using the database ADMIN credentials.
- Create a workshop user with Web Access and the Data Studio role.
- Verify that the workshop user can sign in.
- Optionally, load the PeakGear source data used for drill-through.

### Prerequisites

This lab assumes you have:

- An existing Autonomous AI Lakehouse with embedded Essbase enabled.
- An OCI account that can view the Lakehouse in the Console.
- The database ADMIN username and password for that Lakehouse.
- Network access to Database Actions. If your Lakehouse uses a private endpoint, your browser must be able to reach its virtual cloud network.
- For the optional data load, the approved PeakGear application package download link.

## Task 1: Locate the Existing Autonomous AI Lakehouse

1. Sign in to the Oracle Cloud Infrastructure Console.

2. Open the navigation menu and select **Oracle AI Database**, then **Autonomous AI Database**.

3. Select the region and compartment that contain your workshop Lakehouse.

4. Find your Autonomous AI Lakehouse in the database list and select its display name.

5. On the database details page, confirm that you have opened the intended Lakehouse and that its lifecycle state is **Available**.

## Task 2: Open Database Actions

1. On the Lakehouse details page, open the **Database actions** menu and select **View all database actions**.

2. When prompted, sign in as the database **ADMIN** user.

3. Confirm that the Database Actions launchpad opens. Locate the **Data Studio** area and its available tools.

    > **Note:** The tools shown can vary with the signed-in database user's permissions. You will verify the workshop user's view in Task 4.

## Task 3: Create and Enable the Workshop Database User

1. In Database Actions, open the navigation menu. Under **Administration**, select **Database Users**.

2. Select **Create User**.

3. Enter a username for the workshop user and create a password that meets the displayed requirements. Keep the username for use in the remaining labs.

4. Select **Web Access** for the new user.

5. Set the quota on the **DATA** tablespace to the amount approved for your workshop environment.

6. Open **Granted Roles**. Grant **DWROLE** so the user can access the Data Studio tools used in this workshop. Confirm that the user also has **CONNECT**.

7. Select **Create User** and confirm that Database Actions reports that the user was created.

8. Find the new user's card on the **Database Users** page. Confirm that the account is open and shows **REST Enabled**. Copy the Database Actions URL shown on the card.

<!-- Author TODO: Add the specialist-confirmed Essbase application import permission step here. Database roles alone do not establish that permission. -->

## Task 4: Sign In as the Workshop User and Verify Access

1. Sign out of the ADMIN session, or open a separate private browser window.

2. Open the Database Actions URL that you copied from the workshop user's card.

3. Sign in with the workshop user's username and password.

4. Confirm that Database Actions opens under the workshop user's account and that the Data Studio tools needed for the workshop are visible.

5. Keep the workshop username and Database Actions URL available for the next lab.

## Task 5: Prepare PeakGear Source Data for Optional Drill-Through

If you plan to complete Lab 4, load the PeakGear source files into your Lakehouse. If the prepared PeakGear tables are already available in your tenancy, confirm that you can view their data and continue to the next lab.

<!-- Author TODO: Replace the URL below with the same tested package URL used in Lab 3. Confirm that the package includes the three CSV files named here. -->

1. Download the [PeakGear application package](https://example.invalid/peakgear-lab3.zip) and extract it on your computer.

2. In Database Actions, open **Data Studio**, then **Data Load**.

3. Select **Load Data**, then **Local File**.

4. Select `store_sales_transactions.csv`, `products.csv`, and `store_locations.csv` from the extracted package.

5. Review the detected columns and target table names, then start the load.

6. When the load completes, preview each table and confirm that it contains rows. Record the table names for the drill-through exercise in Lab 4.

    > **Note:** The prepared Essbase workbook in the same package contains cube data. These source tables provide the underlying transaction detail for the optional drill-through exercise.

You have prepared and verified the database user. In the next lab, you will use this account to launch embedded Essbase.

## Learn More

- [Connect with Built-In Oracle Database Actions](https://docs.oracle.com/en/cloud/paas/autonomous-database/serverless/adbsb/connect-database-actions.html)
- [Create and Manage Users on Autonomous AI Database](https://docs.oracle.com/en/cloud/paas/autonomous-database/serverless/adbsb/manage-users-create.html)
- [Manage User Roles and Privileges on Autonomous AI Database](https://docs.oracle.com/en/cloud/paas/autonomous-database/serverless/adbsb/manage-users-privileges.html)

## Acknowledgements

* **Author** - Ty Wolber, Cloud Engineer
* **Last Updated By/Date** - Ty Wolber, October 2026
