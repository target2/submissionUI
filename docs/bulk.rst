Bulk upload of metadata to the TaRGET II DCC
================

Description
-----------

The following instructions can be used to upload metadata to the TaRGET II DCC metadata database from an Excel template. You can use them to: 1. Upload new metadata to the database; 2. Update existing records in the database; 3. Establish relationships between metadata records. Instructions are provided for bulk upload via the web-based UI or the command line. 

Download and fill in the Excel template
---------------------------------------
1. Log on to the TaRGET Submission UI (http://submit.target.wustl.edu). 

    a. On your first login, you will need to register as a new user (“Create New Account”). After completing all fields, select “Create”, then “Login”.

2. A blank copy of the most recent template (TaRGET_metadata_V<>.xlsx) can be downloaded from the homepage or Bulk Upload page ("Download Bulk Upload Excel template"). You must use the TaRGET template for bulk upload. You should maintain the version number in the name.  

    .. image:: _static/TemplateDownload1.png
    
    .. image:: _static/TemplateDownload2.png

3. Fill out the Excel template.
    
    a. All required fields must be populated. 
    b. Enter dates as Excel-formatted dates or a string with format "YYYY-MM-DD".
    c. Group together technical replicates from a single mouse within an Experiment.
    d. Link metadata entries together by entering User or System Accessions in the blue relationship columns. To establish relationships between records you are uploading at the same time, a user-provided User Accession can be used as a temporary placeholder. To eliminate potential record duplications, we now require the user to provide a unique User Accession for each record in the database (i.e., User Accessions must be unique across all submissions for a single user). Please fill in the User Accession according to the format for that tab. Metadata can be linked to other records already in the metadata database with their System or User Accession.
    e. If a System Accession is present in the row or the User Accession for a record already exists in the database, that record will be skipped and not uploaded.
    
4. Redownload of Excel template from previous batch submissions. 

    a. On the Submission Dashboard (http://submit.target.wustl.edu/dashboard), go to "Show my Bulk Submissions" and click the "Download" button next to the submission. This will download the most recent metadata template populated with your submitted metadata, as well as the automatically generated System Accessions for each entry. 

    .. image:: _static/SubmissionDownload.png

    b. Only metadata submitted via bulk upload are currently available for download.
    c. Any changes made to an object between bulk submission and re-download will be included.
    d. Either the System or User Accession may be used to update an existing record. 
    e. Entries cannot be deleted by removing the row on the Excel sheet; they must be deleted through the UI. Deleting individual fields for an entry will erase those fields in the database. 

Bulk upload via the web UI
--------------------------
1. Log on to the Submission UI and go to "Bulk Upload" (http://submit.target.wustl.edu/submission/upload).

    .. image:: _static/BulkUploadUI.png

2. To upload new metadata:

    a. Upload your Excel template from your computer ("Choose File") and select the "Validate Sheet" button. To see the results of validation, select "Click here to view results". 
    b. If validation is not successful ("Error validating the sheet"), the UI will print a log of errors that must be corrected before submission. Please correct all errors and re-validate the sheet. 
    c. If validation is successful ("Validated successfully"), the UI will print instructions and a log of validated metadata. Scroll to the bottom and select the "Submit sheet" button to submit your metadata. You will be asked to confirm this selection before submission. 
    
3. To update existing records in the metadata database:
    
    a. Upload the updated Excel template from your computer ("Choose File") and select the "Update Sheet" button. 
    b. Please correct all errors before submission. 
    
Bulk upload via the command line
--------------------------------
1. Install the upload script.

    a. Python3 is required to run the bulk upload script. Please install python3 or use python3 from Anaconda (https://www.continuum.io/downloads). When you have python3 installed, run the following command to install the upload script and its dependencies:
    
    ::
        
        pip install --user submitTaRGET
    
    or
    
    ::

        pip3 install --user submitTaRGET

2. Obtain your API key.

    a. Log in to the Submission UI (http://submit.target.wustl.edu). 
    b. On the homepage, click “Show API key” to get your token.

    .. image:: _static/tb01.png

3. To upload new metadata: 
      
    a. To validate the sheet, run the following command on the command line. Contact the DCC if there are errors you cannot resolve.

    ::

        submitTaRGET -k <API key> -x <path to excel file>
   
    b. Once all errors have been addressed, run the following command to upload the metadata to the database.  

    ::

        submitTaRGET -k <API key> -x <path to excel file> --notest   
           
4. To update existing records in the metadata database:
 
    a. Validate and submit the modified Excel sheet using the following command. Contact the DCC if there are errors you cannot resolve.

    ::
   
        submitTaRGET -k <API key> -x <excel file> --update
   
See the github repo TargetBulkUpload for more scripts and information. 
