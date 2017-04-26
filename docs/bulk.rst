Steps for uploading Metadata using Bulk upload
==============================================

1. prepare library (if necessary)
    a. Make sure you have Python3 installed. ()
    b. On terminal - pip3 install xlrd
    c. Download bulk upload script (submission.py) and Excel Template (TaRGET metadata template v2.0.xlsx) from https://github.com/xzhuo/TargetBulkUpload

2.  a. On your first login, you will need to register as a new user (“Create New Account”). After completing all fields, select “Create”, then “Login”.
    b. Click “Show API key” to get your token.

    .. image:: _static/tb01.png

    c. Replace 'tokenstring' in Line 9 to your real token string.

    .. image:: _static/tb02.png

    d. Fill in the excel template.

    https://www.youtube.com/watch?v=_MZUw_JEqK0

3.  Run the following command on terminal
    .. code-block:: python

       python3 submission.py -t V2 -x <path to excel file>

4.  Video tutorial to get started

    .. youtube:: https://www.youtube.com/watch?v=_MZUw_JEqK0
