Submitting data to the TaRGET DCC
=================================

1. Log in to the Submission Interface (https://submit.targetepigenomics.org)

    .. image:: _static/Login_edit.png
    
    a. On your first login, you will need to register as a new user (“Create New Account”). After completing all fields, select “Create”, then “Login”. If you have a consortium wiki account, you should use the same username and email for this account.

2. Go to your Submission Dashboard (https://submit.targetepigenomics.org/dashboard)

    a.	You can get to your Submission Dashboard by selecting the "View my Submission Dashboard" button on your homepage or selecting "My Dashboard" from the banner. 

    .. image:: _static/Homepage_edit.png

    b.	From here, you may choose to register metadata or data by selecting the appropriate button. 

3. Create a data submission 

    a. Select the "Data" button on your dashboard. You will be taken to a page (https://submit.targetepigenomics.org/submissions/list) that lists your previous data submissions (if any) and allows you to start a new submission.
    
    .. image:: _static/Dashboard_edit.png
    
    b. To create a new submission, select "Start new data file submission - SFTP". The Aspera upload option has been deprecated. 

    .. image:: _static/CreateNew_edit.png

    c. Follow the instructions to create a new file submission. To allow automated QC of your uploaded files, you may only include files from one assay (e.g., ATAC-seq, RNA-seq) in a single submission, and they must all be single-end or paired-end. Please also note the new file naming requirements. Submitted files must be in fastq format and unzipped or in .gz zipped format. You must generate an md5sum for each file before registering it, which will be used to ensure that the file was completely uploaded.
    
    .. image:: _static/DataInstructions.PNG   
    
    d. After filling in the form, select "Submit" at the bottom of the page. You will be taken to detailed instructions for uploading your data via command line SFTP. 

    .. image:: _static/Submit_edit.png

4. View previous data submissions

    a. Previously registered submissions are listed on your data Submission Dashboard. You may toggle between your submissions and your lab's submissions by selecting the buttons "Show all submissions by my lab"/"Show my submissions". Each submission is assigned a unique UUID and a DCC data wrangler. 

    .. image:: _static/SubmissionShowLab_edit.png
    
    .. image:: _static/SubmissionLab.PNG

    b. To view files that were uploaded as part of a submission, select the "View Files" button for that submission. Once files have been uploaded to the DCC server, they will be listed here along with their own UUID and upload date. The QC report is linked to each file.

    .. image:: _static/SubmissionFiles_edit.png

    c. Submissions are not considered complete until metadata has been registered for each file. To register metadata, select the "Upload Metadata" button, which will take you to instructions for bulk upload of metadata.

5. Register metadata for a submission 

    a.	To view your data on the Data Portal, you must fill out several pieces of information about how the files were generated (e.g., how the mouse was treated, how the assay was performed). You can register metadata one-by-one via the Accession Registry or in bulk (see https://submissionui.readthedocs.io/en/latest/bulk.html).
    b.	To register metadata one-by-one, click on “Metadata Registry” on the banner to go to the Accession Registry Portal (https://meta.targetepigenomics.org/).

    .. image:: _static/MetadataBanner_edit.png

    c. The metadata is organized into discrete categories (such as Mouse, Assay, Reagent) that are linked together. The entity relationship diagram on the home page displays the relationships between the metadata categories. Some categories will have only one or a few unique instances per lab (e.g., Bioproject), while others (e.g., Mouse) will have many. By storing metadata as unique objects, we can avoid entering redundant data (e.g., multiple mice may link to the same Diet and Treatment).

    .. image:: _static/ERDiagram_edit.png

    d. Fill out metadata for your files by clicking on “Files” and the metadata objects listed under “Other Metadata” (e.g., “Mouse” for individual mice, “Assays” for experimental assays performed on nucleic acid obtained from a mouse). 
    e. To create a new metadata object, fill out all of the required fields under the “Add new __” button. Some fields will include a description or a drop-down menu of available terms. After you submit the object (“Create”), a notification will appear that the object was successfully created, and its randomly generated, permanent accession number will become available in the list of current objects.
    
    .. image:: _static/Mice.PNG
    
    .. image:: _static/CreateMouse_edit.png

    f. To view the details of a metadata object, select the accession number for that object. If an object has already been registered, you do not need to register it again; however, you should check to make sure that all of the fields match your submission.
    g. To edit a metadata object, alter the relevant fields, and select "Save changes".
    
    .. image:: _static/SaveChanges_edit.png

    h. To link a metadata object to another metadata object (e.g., associate a Mouse with its Treatment or Diet), select the object from the drop down menu and select "Add". Links can also be deleted without deleting the object (“X”).
    
    .. image:: _static/Links_edit.png

    i. To delete a metadata object, select "Delete _". All links between the object and other objects must be deleted before the object can  be deleted.
    
    .. image:: _static/DeleteMouse_edit.png

Thank you for using the TaRGET DCC submission pipeline! Please contact us with any questions. 
