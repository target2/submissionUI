Submitting data and metadata to the TaRGET II DCC
=================================================

1. Log in to the Submission Interface (https://submit.targetepigenomics.org)

    .. image:: _static/Login_edit.png
    
    a. On your first login, you will need to register as a new user (“Create New Account”). After completing all fields, select “Create”, then “Login”. If you have a consortium wiki account, you should use the same username and email for this account.

2. Go to your Submission Dashboard (https://submit.targetepigenomics.org/dashboard)

    a.	You can get to your Submission Dashboard by selecting the "View my Submission Dashboard" button on your homepage or selecting "My Dashboard" from the banner. 

    .. image:: _static/Homepage_edit.png

    b.	From here, you may choose to register metadata or data by selecting the appropriate button. 

Data submission
---------------

1. Create a data submission 

    a. Select the "Data" button on your dashboard. You will be taken to a page (https://submit.targetepigenomics.org/submissions/list) that lists your previous data submissions (if any) and allows you to start a new submission.
    
    .. image:: _static/Dashboard_Data.png
    
    b. To create a new submission, select "Start new data file submission - SFTP". The Aspera upload option has been deprecated. 

    .. image:: _static/CreateNew_edit.png

    c. Follow the instructions to create a new file submission. To allow automated QC of your uploaded files, you may only include files from one assay (e.g., ATAC-seq, RNA-seq) in a single submission, and they must all be single-end or paired-end. Please also note the new file naming requirements. Submitted files must be in fastq format and unzipped or in .gz zipped format. You must generate an md5sum for each file before registering it, which will be used to ensure that the file was completely uploaded.
    
    .. image:: _static/DataInstructions.PNG   
    
    d. After filling in the form, select "Submit" at the bottom of the page. You will be taken to detailed instructions for uploading your data via command line SFTP. 

    .. image:: _static/SubmitSFTP_edit.png

2. View previous data submissions

    a. Previously registered submissions are listed on your data Submission Dashboard. You may toggle between your submissions and your lab's submissions by selecting the buttons "Show all submissions by my lab"/"Show my submissions". 

    .. image:: _static/CreateNew_bylab.png

    b. Each submission is assigned a unique UUID and a DCC data wrangler. 

    .. image:: _static/SubmissionLab_edit.png

    c. To view files that were uploaded as part of a submission, select the "View Files" button for that submission. Once files have been uploaded to the DCC server, they will be listed here along with their own UUID and upload date. The QC report is linked to each file.

    .. image:: _static/SubmissionFiles_edit.png

    d. Submissions are not considered complete until metadata has been registered for each file. Selecting the "Upload Metadata" button will take you to instructions for bulk upload of metadata (see below).

Metadata organization
---------------------
For a submission to be marked complete and to be available on the Data Portal, you must fill out several pieces of information about how the files were generated (e.g., how the mouse was treated, how the assay was performed).  

The metadata is organized into discrete categories (such as Mouse, Assay, Reagent) that are linked together. The entity relationship diagram on the Accession Registry Portal home page (https://meta.targetepigenomics.org/) displays the relationships between the metadata categories. Some categories will have only one or a few unique instances per lab (e.g., Bioproject), while others (e.g., Mouse) will have many. By storing metadata as unique objects, we can avoid entering redundant data (e.g., multiple mice may link to the same Diet and Treatment).

    .. image:: _static/ER.PNG

The following instructions can be used to register metadata in the TaRGET II DCC metadata database. You can use them to: 1. Upload new metadata to the database; 2. Update existing records in the database; 3. Establish relationships between metadata records. You can register metadata one-by-one via the Accession Registry or in bulk via the web UI. Bulk upload via the command line can be performed by request.

Metadata submission via the Accession Registry
----------------------------------------------
1. To register metadata one-by-one, go to the Accession Registry Portal (https://meta.targetepigenomics.org/).
   
    .. image:: _static/Dashboard_MR.png

    a. Fill out metadata for your files by clicking on “Files” and the metadata objects listed under “Other Metadata” (e.g., “Mouse” for individual mice, “Assays” for experimental assays performed on nucleic acid obtained from a mouse). 
   
    .. image:: _static/Mice_Add.png
    
    b. To create a new metadata object, fill out all of the required fields under the “Add new __” button. 
    c. Some fields will include a description or a drop-down menu of available terms. After you submit the object (“Create”), a notification will appear that the object was successfully created, and its randomly generated, permanent accession number will become available in the list of current objects.

    .. image:: _static/CreateMouse_edit.png

    d. To view the details of a metadata object, select the accession number for that object. If an object has already been registered, you do not need to register it again; however, you should check to make sure that all of the fields match your submission.
   
    .. image:: _static/Mice_View.png
    
    e. To edit a metadata object, alter the relevant fields, and select "Save changes".
    
    .. image:: _static/SaveChanges_edit.png

    f. To link a metadata object to another metadata object (e.g., associate a Mouse with its Treatment or Diet), select the object from the drop down menu and select "Add". Links can also be deleted without deleting the object (“X”).
    
    .. image:: _static/Links_edit.png

    g. To delete a metadata object, select "Delete _". All links between the object and other objects must be deleted before the object can  be deleted.
    
    .. image:: _static/DeleteMouse_edit.png

Metadata bulk submission via the web UI
---------------------------------------
1. To register metadata in bulk, on your Submission Dashboard (https://submit.targetepigenomics.org/dashboard), select "Metadata" to go to your metadata submission dashboard. This interface lists all of your previous bulk metadata submissions. 
    
    .. image:: _static/Dashboard_Metadata.png
    
2. Select "Create/Update bulk metadata submission" to access the web UI for bulk upload of metadata (https://submit.targetepigenomics.org/submission/upload). 
    
    .. image:: _static/MetadataSubmission_create.png
    
3. To upload new metadata, download a blank copy of the most recent metadata template (TaRGET_metadata_V<>.xlsx) by selecting "Download Bulk Upload Excel template". 

    a. You must use the TaRGET template for bulk upload. You should maintain the version number in the name.  

    .. image:: _static/BlankTemplate_edit.png

4. Fill out the Excel template.
    
    a. All required fields must be populated. 
    b. Enter dates as Excel-formatted dates or a string with format "YYYY-MM-DD".
    c. Link metadata entries together by entering User or System Accessions in the blue relationship columns. To establish relationships between records you are uploading at the same time, a user-provided User Accession can be used as a temporary placeholder. To eliminate potential record duplications, we now require the user to provide a unique User Accession for each record in the database (i.e., User Accessions must be unique across all submissions for a single user). Please fill in the User Accession according to the format for that tab. Metadata can be linked to other records already in the metadata database with their System or User Accession.
    d. If a System Accession is present in the row or the User Accession for a record already exists in the database, that record will be skipped and not uploaded.
    
5. To upload new metadata:

    a. Upload your Excel template from your computer ("Choose File") and select the "Validate Sheet" button. To see the results of validation, select "Click here for next step". 

    .. image:: _static/BulkUploadUI.png

    b. If validation is not successful ("Error validating the sheet"), the UI will print a log of errors that must be corrected before submission. Please correct all errors and re-validate the sheet. 
    c. If validation is successful ("Validated successfully"), the UI will print instructions and a log of validated metadata. Scroll to the bottom and select the "Submit sheet" button to submit your metadata. You will be asked to confirm this selection before submission. 
    
6. To update existing records in the metadata database:
    
    a. On your metadata submission dashboard, select "Download All of My Metadata". This will download the most recent metadata template populated with all of your submitted metadata, as well as the automatically generated System Accessions for each entry. Any changes made to an object between submission and re-download will be included.

    .. image:: _static/MetadataSubmission_edit.png

    b. Update the records as needed. Deleting individual fields for an entry will erase those fields in the database. Entries cannot be deleted by removing the row on the Excel sheet; they must be deleted through the UI. 
    c. Either the System or User Accession may be used to update an existing record. 
    d. On the bulk upload web UI (https://submit.targetepigenomics.org/submission/upload), upload the updated Excel template from your computer ("Choose File") and select the "Update Sheet" button. 
    e. Please correct all errors before submission. 
    
Thank you for using the TaRGET DCC submission pipeline! Please contact us with any questions. 
