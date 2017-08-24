Bulk upload of metadata to the TaRGET II DCC
================

Description
-----------

The following instructions can be used to upload metadata to the TaRGET II DCC metadata database from an Excel template. You can use them to: 1. Upload new metadata to the database; 2. Update existing records in the database; 3. Establish relationships between metadata records. Instructions are provided for bulk upload via the command line or the web-based UI. 

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

    a. Log in to the Submission UI (submit.target.wustl.edu). On your first login, you will need to register as a new user (“Create New Account”). After completing all fields, select “Create”, then “Login”.
    b. On the homepage, click “Show API key” to get your token.

    .. image:: _static/tb01.png

3. Download and fill in the Excel template (TaRGET_metadata_V<2.0>.xlsx). 

    a. A blank copy of the most recent template can be downloaded from the TaRGET Submission UI homepage or Bulk Upload page ("Download Bulk Upload Excel template"). You must use our template for bulk upload. 

    .. image:: _static/TemplateDownload1.png
    
    .. image:: _static/TemplateDownload2.png

    b. If you rename the template, be sure to keep the version number intact in the name. 
    c. All required fields must be populated. 
    d. Link metadata entries together by entering User or System Accessions in the blue relationship columns (see below). 
    e. Enter dates as Excel-formatted dates or a string with format "YYYY-MM-DD".
    f. Group together technical replicates from a single mouse within an Experiment.

4. To upload new metadata: 
    
    a. To establish relationships between records you are uploading at the same time, a user-provided User Accession can be used as a temporary placeholder. To eliminate potential record duplications, we now require the user to provide a unique User Accession for each record in the database (i.e., User Accessions must be unique across all submissions for a single user). Please fill in the User Accession according to the format for that tab.  
    b. If a System Accession is present in the row or the User Accession for a record already exists in the database, that record will be skipped and not uploaded.
    c. Metadata can be linked to other records already in the metadata database with their System or User Accession.
    d. To validate the sheet, run the following command on the command line. Contact the DCC if there are errors you cannot resolve.

    ::

        submitTaRGET -k <API key> -x <path to excel file>
   
    e. Once all errors have been addressed, run the following command to upload the metadata to the database.  

    ::

        submitTaRGET -k <API key> -x <path to excel file> --notest   
           
5. To update existing records in the metadata database:
   
    a. On the Submission Dashboard, click the "Download" button next to the submission. This will download the most recent metadata template populated with your submitted metadata, as well as the automatically generated System Accessions for each entry. Only metadata submitted via bulk upload are currently available for batch download.

    .. image:: _static/SubmissionDownload.png

    b. Any changes made to an object between batch submission and re-download will be included.  
    c. Either the System or User Accession may be used to update an existing record. 
    d. Entries cannot be deleted by removing the row on the Excel sheet; they must be deleted through the UI. Deleting individual fields for an entry will erase those fields in the database. 
    e. After editing the Excel, validate and submit the modified sheet using the following command. Contact the DCC if there are errors you cannot resolve.

    ::
   
        submitTaRGET -k <API key> -x <excel file> --update

   .. rubric:: A summary flow chart
      :name: a-summary-flow-chart

   .. figure:: https://raw.githubusercontent.com/xzhuo/TargetBulkUpload/master/bulkupload_flow.20170714.png
      :alt: submit summary flow chart

      Flow chart

Bulk upload via the UI
----------------------
1. Download and fill in the Excel template as above.
2. Log on to the submission UI and go to "Bulk Upload" (http://submit.target.wustl.edu/submission/upload).

    .. image:: _static/BulkUploadUI.png

3. Upload your Excel template from your computer ("Choose File").
4. To upload data for the first time, select the "Validate Sheet" button. To see the results of validation, select "Click here to view results". 
    
    a. If validation is not successful ("Error validating the sheet"), the UI will print a log of warnings and errors that must be corrected before submission. Please correct all errors and re-validate the sheet. 
    b. If validation is successful ("Validated successfully"), the UI will print instructions and a log of validated metadata. Scroll to the bottom and select the "Submit sheet" button to submit your metadata. You will be asked to confirm this selection before submission. 
    
5. To update data, upload the updated Excel template from your computer ("Choose File") and select the "Update Sheet" button. Please correct all errors before submission. 
    
See the github repo TargetBulkUpload for more scripts and more information. 

Video tutorial to get started.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

    .. youtube:: https://www.youtube.com/watch?v=qDBxSGySTsI
    .. raw:: html

        <div style="position: relative; height: 0; overflow: hidden; max-width: 100%; height: auto;">
            <iframe width="640" height="400" src="https://www.youtube.com/embed/qDBxSGySTsI" frameborder="0" allowfullscreen></iframe>
        </div>
    
    .. youtube:: https://www.youtube.com/watch?v=233F6YpFfOQ
    .. raw:: html

        <div style="position: relative; height: 0; overflow: hidden; max-width: 100%; height: auto;">
            <iframe width="640" height="400" src="https://www.youtube.com/embed/233F6YpFfOQ" frameborder="0" allowfullscreen></iframe>
        </div>
