Steps for uploading metadata using bulk upload
==============================================

1. Download the bulk upload script and install required dependencies. 
    a. The script requires python3 to be installed. 
    b. Install the python module xlrd ("pip3 install xlrd").
    c. Download the bulk upload script (submission.py) from https://github.com/xzhuo/TargetBulkUpload .
    d. Alternatively, install the script and dependencies as a pip package ("pip install --user submitTaRGET") and replace "python3 submission.py" with "submitTaRGET".

2. Obtain your API key. 
    a. Log in to the Submission UI (submit.target.wustl.edu). On your first login, you will need to register as a new user (“Create New Account”). After completing all fields, select “Create”, then “Login”.
    b. On the homepage, click “Show API key” to get your token.

    .. image:: _static/tb01.png

3. Download and fill in the Excel template (TaRGET_metadata_V2.0.xlsx). 
    a. A blank copy of the most recent template can be downloaded from the TaRGET Submission UI homepage or Bulk Upload page ("Download Bulk Upload Excel template").
    b. All required fields must be populated. Link metadata entries together using User or System Accessions. 
    c. Group together technical replicates from a single mouse within an Experiment.

4. Submit the Excel template via the command line. 
    a. To validate the sheet, run the following command on the terminal.
    ::

       python3 submission.py -k <API key> -x <path to excel file>
    b. Once all errors have been addressed, run the following command to upload the data to the database. 
    ::

       python3 submission.py -k <API key> -x <path to excel file> --notest

5. Update previously submitted data. 
    a. Click the "Download" button next to the submission on the submission dashboard. This will return the most recent metadata template populated with the submitted metadata, as well as the automatically generated System Accessions for each entry. Note that any changes made to an object between batch submission and re-download will be included. Only metadata submitted via bulk upload are available for batch download.  
    b. After editing, validate and submit the modified sheet using the following command. Note that entries must be deleted through the UI, not by deleting the entry on the template. 
    ::
        python3 submission.py -k <API key> -x <excel file> --update

7. Video tutorial to get started

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
