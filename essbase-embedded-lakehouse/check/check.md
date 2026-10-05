# Check the Existing Lakehouse and Prepare Access

## Introduction

In this lab, you will locate your existing Oracle Autonomous AI Lakehouse, open Database Actions as the database ADMIN user, and create a workshop database user. You will then sign in as that user to confirm access to Database Actions and Data Studio. You will also download / upload the Sporting Goods data for the optional drill-through exercise.

Estimated Time: 35 minutes

### About Database Actions

Database Actions is a browser-based interface for working with your Autonomous AI Database. Access from the OCI Console and access to database tools are controlled separately. In this lab, you will use the OCI Console to find the Lakehouse, then use database credentials to sign in to Database Actions.

### Objectives

In this lab, you will:

- Locate an existing Autonomous AI Lakehouse in your tenancy.
- Open Database Actions using the database ADMIN credentials.
- Create a workshop user with Web Access and the Data Studio role.
- Verify that the workshop user can sign in.
- Load the Sporting Goods source data used for drill-through.

### Prerequisites

This lab assumes you have:

- An existing Autonomous AI Lakehouse with embedded Essbase.
- An OCI ADMIN account that can view the Lakehouse in the Console.
- Access to Database Actions in AI Lakehouse.

## Task 1: Locate the Existing Autonomous AI Lakehouse

1. Sign in to the Oracle Cloud Infrastructure Console.

2. Open the hamburger menu in the top left corner and select **Oracle AI Database**, then **Autonomous AI Database**.
![OCI navigation menu with Autonomous AI Database highlighted](images/ailh_step1.png)

3. Select the region and compartment that contain your AI Lakehouse.
![OCI navigation menu with Autonomous AI Database highlighted](images/ailh_2.png)

4. Find your AI Lakehouse in the database list. Confirm that it is the correct database and the lifecycle state is **Available**.
![OCI navigation menu with Autonomous AI Database highlighted](images/ailh_2b.png)

5. Click on the AI Lakehouse to access the database details page.
![OCI navigation menu with Autonomous AI Database highlighted](images/ailh_2a.png)

## Task 2: Open Database Actions

1. On the AI Lakehouse details page, open the **Database actions** menu and select **View all database actions**.
![OCI navigation menu with Autonomous AI Database highlighted](images/ailh_3.png)

2. When prompted, sign in as the database **ADMIN** user.
![OCI navigation menu with Autonomous AI Database highlighted](images/ailh_4.png)

3. Confirm that the Database Actions launchpad opens. Locate the **Data Studio** area and its available tools. This will be used later in the workshop.

    > **Note:** The tools shown can vary with the signed-in database user's permissions. You will verify the workshop user's view in Task 4.

## Task 3: Create and Enable the Workshop Database User

1. In Database Actions, open the hamburger menu in the top left corner. Under **Administration**, select **Database Users**.
![OCI navigation menu with Autonomous AI Database highlighted](images/ailh_6.png)

2. Select **Create User**.
![OCI navigation menu with Autonomous AI Database highlighted](images/ailh_7.png)

3. Enter a username for the workshop user and create a password that meets the displayed requirements. Keep the credentials saved for future use.
![OCI navigation menu with Autonomous AI Database highlighted](images/ailh_8a.png)

4. Set the  **Quota on tablespace DATA** to the amount approved for your workshop environment.
![OCI navigation menu with Autonomous AI Database highlighted](images/ailh_8b.png)

5. Enable **REST, GraphQL, MongoDB API, and Web Access** for the new user.
![OCI navigation menu with Autonomous AI Database highlighted](images/ailh_8c.png)

6. Open **Granted Roles**. Grant **DWROLE** and **ESSBASE DEVELOPER** so the user can access the Data Studio tools used in this workshop. Confirm that **DWROLE** is set by default and **CONNECT** is enabled.
![OCI navigation menu with Autonomous AI Database highlighted](images/hold.png)

7. Select **Create User** and confirm that Database Actions reports that the user was created.

8. Find the new user's card on the **Database Users** page. Confirm that the account is open and shows **REST Enabled**.
![OCI navigation menu with Autonomous AI Database highlighted](images/aidp_10.png)


<!-- Author TODO: Add the specialist-confirmed Essbase application import permission step here. Database roles alone do not establish that permission. -->

## Task 4: Sign In as the Workshop User and Verify Access

1. Sign out of the **ADMIN** session, or open a separate private browser window.
![OCI navigation menu with Autonomous AI Database highlighted](images/ailh_11.png)

2. Sign in with the workshop user's credentials from Task 3.
![OCI navigation menu with Autonomous AI Database highlighted](images/ailh_12.png)

3. Keep the credentials saved and Database Actions URL available for the next lab.

## Task 5: Prepare PeakGear Source Data

1. Download and extract the [PeakGear Sporting Goods Data](files/peakgear.zip) on your computer. This will be uploaded to embedded Essbase in the next portion of the Lab.

2. In Database Actions, open **Data Studio**.
![OCI navigation menu with Autonomous AI Database highlighted](images/dataload.png)

3. Select **Data Load**, then **Load Data**.
![OCI navigation menu with Autonomous AI Database highlighted](images/dl.png)

4. Confirm data is being loaded from **Local Files** then click **Select Files**
![OCI navigation menu with Autonomous AI Database highlighted](images/dl2.png)

5. Select `store_sales_transactions.csv`, `products.csv`, and `store_locations.csv` from the extracted package.
![OCI navigation menu with Autonomous AI Database highlighted](images/data.png)

6. Review the detected columns and target table names, then **Start** and **Run** the load.
![OCI navigation menu with Autonomous AI Database highlighted](images/data2.png)

7. When the load completes, preview each table and confirm that it contains rows. Record the table names for the drill-through exercise in Lab 4.

    > **Note:** The prepared Essbase workbook in the same package contains cube data. These source tables provide the underlying transaction detail for the optional drill-through exercise.

You have prepared and verified the database user. In the next lab, you will use this account to launch embedded Essbase.

## Learn More

- [Connect with Built-In Oracle Database Actions](https://docs.oracle.com/en/cloud/paas/autonomous-database/serverless/adbsb/connect-database-actions.html)
- [Create and Manage Users on Autonomous AI Database](https://docs.oracle.com/en/cloud/paas/autonomous-database/serverless/adbsb/manage-users-create.html)
- [Manage User Roles and Privileges on Autonomous AI Database](https://docs.oracle.com/en/cloud/paas/autonomous-database/serverless/adbsb/manage-users-privileges.html)

## Acknowledgements

* **Author** - Ty Wolber, Cloud Engineer
* **Last Updated By/Date** - Ty Wolber, October 2026