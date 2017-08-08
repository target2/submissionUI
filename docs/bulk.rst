Steps for uploading Metadata using Bulk upload
==============================================

1. prepare library (if necessary)
    a. Make sure you have Python3 installed. ()
    b. On terminal - pip3 install xlrd
    c. Download bulk upload script (submission.py) and Excel Template (TaRGET metadata template v2.0.xlsx) from https://github.com/xzhuo/TargetBulkUpload

2. a. On your first login, you will need to register as a new user (“Create New Account”). After completing all fields, select “Create”, then “Login”.
    b. Click “Show API key” to get your token.

    .. image:: _static/tb01.png

    c. Fill in the excel template.


3. Run the following command on terminal
    ::

       python3 submission.py -k <API key> -x <path to excel file>

4. Video tutorial to get started

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
