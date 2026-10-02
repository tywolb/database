# Import the Prepared PeakGear Application

## Introduction

In this lab, you will download the prepared PeakGear application package, extract its application workbook, and import the workbook into Essbase. You will then check the import job, cube outline, and a known sales value.

Estimated Time: 20 minutes

### About Application Workbooks

An Essbase application workbook is an Excel file that defines an application, cube, dimensions, and optional data. Importing the prepared PeakGear workbook creates the cube and loads its data without requiring you to build the outline manually.

### Objectives

In this lab, you will:

- Download and extract the PeakGear application package.
- Import the application workbook and load its data.
- Verify the import job, cube outline, and a known sales value.

### Prerequisites

This lab assumes you have:

- Access to embedded Essbase with permission to import a new application.
- The approved PeakGear application package download link.
- A web browser that can download and extract a ZIP file.

## Task 1: Download the Prepared Application Workbook

<!-- Author TODO: Replace the URL below with the tested, object-specific download URL before publishing. -->

1. If you did not download the package in Lab 1, download the [PeakGear application package](https://example.invalid/peakgear-lab3.zip).

2. Extract the ZIP file on your computer if you have not already done so.

3. Locate `peakgear_sales.xlsx` in the extracted folder. This is the file you will select in Essbase.

    > **Note:** The ZIP file is the download package. Import the extracted Excel application workbook, not the ZIP file. The package also includes the CSV source files used for optional drill-through.

## Task 2: Import the Application and Load Data

1. Return to the Essbase home page and select **Import**.

2. In the Import dialog, select **File Browser** and open `peakgear_sales.xlsx`.

3. Confirm that the application and cube names are populated from the workbook.

4. Open the build options. Select **Create Database** and **Load Data**.

5. Select **OK** to start the import.

    > **Note:** If an application with the same name already exists, choose a unique application or cube name before continuing.

## Task 3: Review the Import Job

1. Open **Jobs** in Essbase and find the most recent import job for the PeakGear application.

2. Open the job details and confirm that the job completed successfully.

3. If the job reports an error, review its details before continuing.

## Task 4: Inspect the Cube Outline

1. On the Essbase home page, open the imported PeakGear application and its cube.

2. Select **Launch Outline**.

3. Expand the dimensions and confirm that the product, store, and time members defined in the prepared workbook are present.

## Task 5: Verify a Known Sales Value

1. Open the PeakGear cube and select **Analyze Data**.

2. Navigate to the member intersection listed below.

    <!-- Author TODO: Replace the member names and value after the workbook has been built and tested. -->

    | Time | Product | Store | Measure | Expected value |
    | --- | --- | --- | --- | --- |
    | [INSERT PERIOD] | [INSERT PRODUCT MEMBER] | [INSERT STORE MEMBER] | [INSERT SALES MEASURE] | [INSERT VALUE] |

3. Confirm that the displayed value matches the expected value.

You have imported the prepared PeakGear application and verified that its cube and data are available.

## Learn More

- [About Application Workbooks](https://docs.oracle.com/en/database/other-databases/essbase/21/esscd/application-workbooks.html)
- [Create a Cube from an Application Workbook](https://docs.oracle.com/en/database/other-databases/essbase/21/esscd/create-cube-application-workbook.html)
- [Analyze Data in the Web Interface](https://docs.oracle.com/en/database/other-databases/essbase/26/ugess/analyze-data-web-interface.html)

## Acknowledgements

* **Author** - Ty Wolber, Cloud Engineer
* **Last Updated By/Date** - Ty Wolber, October 2026