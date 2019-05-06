---
layout: doc
---
# Upload Site diagnostics to Citrix Technical Support

If you experience an issue with your Site, Citrix Technical Support might ask you to provide diagnostic data that they will use to help you resolve the issue. Smart Tools provides a simple way to securely upload your diagnostics data to Citrix Insight Services and share it with Citrix Support.

## Prerequisites

Before you can upload diagnostics, you need to create a diagnostics file. Typically, this is a ZIP file that you can generate with Citrix Scout.

For more information about creating a diagnostics file, see [CTX135408](https://support.citrix.com/article/CTX135408).

## To upload diagnostics

1.  From the command bar, click **Smart Check**.
1.  Click **Diagnostics > Upload Diagnostics**.
1.  Enter the following information:

    *  In **Diagnostic data file**, click **Select File** to locate and select the diagnostic ZIP file you generated earlier.
    *  In **Upload name**, enter a friendly name for your upload, if applicable. By default, the filename of your diagnostic data file is used.
    *  In **Case number**, enter your 8-digit case number, if applicable.
    *  In **Description**, enter any additional information about your Support case, if applicable.
    *  To be notified when Smart Tools has completed processing your file, select **Send me an email notification when file processing is complete**.

1.  Click **Upload**. Smart Tools uploads the file.
1.  Click **Done** to close the dialog.

As Smart Tools processes your file upload, the Diagnostic Uploads page displays its progress at the top of the page.

![Diagnostic Uploads page with file processing progress banner](/en-us/smart-tools/media/manual-upload-progress.png)

After processing is finished, Smart Tools adds your upload to the page and, if you selected the option, sends you an email notification. To view the details of your upload, click the upload entry displayed on the page. Each entry includes upload information such as upload date and time, name of the upload, Support case number (if included), the type of upload, and the user who initiated the upload.

If your Site is new to Smart Check, Smart Tools uses your diagnostics upload to discover and display your Site in Smart Check. You can then install the Smart Tools Agent to run health checks. To view your Site's health report, click **Back to All Sites** and then select your Site from the list.

> **Note**:
>
> If you remove your Site from Smart Check, uploaded diagnostics files associated with the Site are not deleted.

## To share diagnostics files with Citrix Technical Support

After you upload your diagnostics file, Smart Tools creates a URL that you can share with Citrix Technical Support. Citrix Technical Support can then locate your file using your Smart Tools user name, organization name, case number (if included) or upload ID.

1.  From the command bar, click **Smart Check**.
1.  Click **Diagnostics > View Uploads**. The Diagnostic Uploads page appears.
1.  Select the upload you want to share. The upload details page appears.
1.  Under **Share report with Citrix Support**, click **Copy** to copy the URL of your uploaded file. The report URL contains the upload ID for your diagnostics upload.

## Find and modify uploads

The Diagnostic Uploads page is where Smart Tools displays a list of all your previous uploads, including the following information:

*  **Case:** The case number associated with the upload.
*  **Source:** The mechanism by which the upload was generated. Examples: Scout or Call Home in Virtual Apps and Desktops, CDFControl.
*  **Upload Type:** Whether the upload was manually generated, scheduled, or triggered as the result of a product error or other event.
*  **Recommendations:** The number of notifications for issues that were detected in your diagnostic upload that you should address. Recommendations can include notifications for installing missing hotfixes, replacing obsolete hotfixes, or addressing issues that were detected.

![Diagnostic Uploads page with table of previous uploads](/en-us/smart-tools/media/diag-upload-page.png)

### Filter uploads

If you have a large list of uploads, Smart Tools makes it easier to navigate the list using the following features:

*  **Search as you type:** To search in a column, simply click the magnifying glass and begin typing. Smart Tools automatically displays uploads that contain your typed criteria.
*  **Filtering by Source or Upload Type:** When you click the magnifying glass in the Source and Upload Type columns, you can select search criteria from a list of options. Smart Tools automatically displays uploads that match your selections.
*  **Sorting:** You can sort any column in the list in ascending or descending order; simply click the column heading. If you filtered the list, clicking on a column heading sorts the filtered list.

You can also hide or display columns so the page displays only the information you want to see.

![Diagnostic Uploads page with search and filtering options](/en-us/smart-tools/media/diag-upload-page-search-2.png)

### Modify upload properties

When you click on an upload entry from the list, Smart Tools displays a Summary page that includes the case number and description that was entered when the upload was created. If you need to change this information later, simply click the pencil icon next to these fields.

### Delete uploads

1.  From the Diagnostic Uploads page, select an upload from the list.
1.  From the Summary page, click **Delete Upload**.
1.  Click **Delete**.

## View recommendations

When you upload a diagnostics file, the file is analyzed for potential issues such as missing hotfixes or known issues. If any issues are identified, Smart Tools displays a list of recommendations for addressing them. These recommendations also include links to Citrix resources to help you learn more about the issue and how to troubleshoot and resolve it.

![Recommendations list and details for existing upload](/en-us/smart-tools/media/diag-upload-recommendation-details.png)

> **Note**:
>
> Because recommendations are based on the contents of diagnostic uploads, they can provide more information about potential issues in your Virtual Apps and Desktops Sites, in addition to the issues that might be detected with health checks. Citrix recommends using diagnostic uploads alongside running health checks to ensure you address all important issues in your Site.

### To view recommendations

1.  From the Diagnostic Uploads page, select an upload from the list. The Summary page appears.
1.  Click the **Recommendations** tab. A list of recommendations appears.
1.  To view the recommendation details, click an entry in the list. Smart Tools displays a description of the recommendation and links to resources to help you fix the issue.