**Secure Python Code Manager Script Documentation** 

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.14030325.svg)](https://doi.org/10.5281/zenodo.14030325)
[![License](https://img.shields.io/badge/license-Custom-blue.svg)](LICENSE.md)
[![Python Version](https://img.shields.io/badge/python-3.6%2B-blue)](https://www.python.org/downloads/)

*Version: 1.5\
Author: Alpha Beta Network Research Team\
© 2024 αβ.net (alphabetanet.com) - Alpha Beta Network. All Rights
Reserved.*

------------------------------------------------------------------------

## Table of Contents

- [1. Introduction](#1-introduction)
- [2. Installation](#2-installation)
- [3. Main Functions of the Script](#3-main-functions-of-the-script)
  - [3.1 Getting License Information (--license-info)](#31-getting-license-information---license-info)
  - [3.2 Getting Service Usage Information (--service-usage)](#32-getting-service-usage-information---service-usage)
  - [3.3 Uploading Code and Creating a License (--upload)](#33-uploading-code-and-creating-a-license---upload)
  - [3.4 Updating Previously Uploaded Code (--update)](#34-updating-previously-uploaded-code---update)
- [4. Detailed Description of Each Function](#4-detailed-description-of-each-function)
  - [4.1 Getting License Information (--license-info)](#41-getting-license-information---license-info)
  - [4.2 Getting Service Usage Information (--service-usage)](#42-getting-service-usage-information---service-usage)
  - [4.3 Uploading Code and Creating a License (--upload)](#43-uploading-code-and-creating-a-license---upload)
  - [4.4 Updating Previously Uploaded Code (--update)](#44-updating-previously-uploaded-code---update)
- [5. Additional Features](#5-additional-features)
  - [5.1 Extending the License Expiration Date (--extend)](#51-extending-the-license-expiration-date---extend)
  - [5.2 Setting the Maximum Number of Hardware IDs (--set_hwids)](#52-setting-the-maximum-number-of-hardware-ids---set_hwids)
  - [5.3 Deleting Licenses and Code](#53-deleting-licenses-and-code)
- [6. Working with Logs](#6-working-with-logs)
  - [6.1 Description of the license_cloud_info.log File](#61-description-of-the-license_cloud_infolog-file)
  - [6.2 How to Interpret Records in the Log](#62-how-to-interpret-records-in-the-log)
- [Appendix A: Installation of Required Packages](#appendix-a-installation-of-required-packages)
- [Appendix B: Contact Information](#appendix-b-contact-information)

# 1. Introduction

The **Secure Python Code Manager Script** is a command-line tool
designed to manage your code licenses with the Alpha Beta Network cloud
service. It provides functionalities to upload your Python scripts
securely to the cloud, create and manage licenses, retrieve license
information, and monitor service usage. With this script, you can:

-   **Upload your code** to the cloud and obtain a license.

-   **Update previously uploaded code** associated with a license.

-   **Retrieve detailed license information**, including status and
    usage data.

-   **Check your service usage statistics**, such as uploaded scripts
    and licenses.

-   **Manage licenses and code entries**, including deletion operations.

This tool is ideal for developers who need to protect their intellectual
property and want to distribute their Python scripts securely. By using
cloud-based licensing, you ensure that only authorized users can access
and execute your code.

# 2. Installation

Before using the Secure Python Code Manager Script, ensure that you
have **Python 3** installed on your system.

**2.1 Installing Required Packages**

The script requires the following Python packages:

-   requests

-   psutil

-   cryptography

You can install them using pip:

```bash

pip install requests psutil cryptography
```
If you are using a virtual environment, ensure it is activated before
installing the packages.

**2.2 Downloading the Script**

Download the secure_python_code_manager.py script to your local machine.

# 3. Main Functions of the Script

The Secure Python Code Manager Script provides the following main
functionalities:

## 3.1 Getting License Information (\--license-info)

## 3.2 Getting Service Usage Information (\--service-usage)

## 3.3 Uploading Code and Creating a License (\--upload)

## 3.4 Updating Previously Uploaded Code (\--update)

------------------------------------------------------------------------

# 4. Detailed Description of Each Function

## 4.1 Getting License Information (\--license-info)

This function retrieves detailed information about your licenses,
including their status, usage data, and associated limits.

**Command Syntax**

```bash

python secure_python_code_manager.py --license-info -l LICENSE_KEYS [OPTIONS]
```
**Description of Parameters**

-   \--license-info or -i: Specifies the action to retrieve license
    information.

-   -l LICENSE_KEYS or \--license LICENSE_KEYS: A required parameter
    specifying the license key(s) to retrieve information for. Multiple
    licenses should be separated by commas, or use all to retrieve
    information for all licenses.

-   \--extend or -e: *(Optional)* Extends the expiration date of the
    specified licenses by 24 hours.

-   \--set_hwids NUMBER or -d NUMBER: *(Optional)* Sets the maximum
    number of hardware IDs for the specified licenses to NUMBER.

**Examples of Use**

**Example 1:** Retrieve information for a specific license.

```bash

python secure_python_code_manager.py --license-info -l 1234567890
```
**Example 2:** Retrieve information for multiple licenses.

```bash

python secure_python_code_manager.py --license-info -l 1234567890,0987654321
```
**Example 3:** Retrieve information for all licenses.

```bash

python secure_python_code_manager.py --license-info -l all
```
**Example 4:** Extend the expiration date of a license by 24 hours.

```bash

python secure_python_code_manager.py --license-info -l 1234567890 --extend
```
**Example 5:** Set the maximum number of hardware IDs for a license.

```bash

python secure_python_code_manager.py --license-info -l 1234567890 --set_hwids 5
```
**Expected Output**

The script will display detailed information about the specified
licenses:

```javascript

License Information for License Key: 1234567890

Expiration date (UTC 0): 2024-01-01 00:00:00

Creation date: 2023-12-01 00:00:00

Is blocked: No

Is active: Yes

Limit alert: No

Upload limit alert: No

Update limit alert: No

IP limit alert: No

Hardware ID limit alert: No

Maximum total hardware IDs: 5

Maximum total downloads: 100

Maximum daily downloads: 10

Maximum downloads per minute: 2

Maximum total uploads: 50

Maximum daily uploads: 5

Maximum uploads per minute: 1

Maximum daily updates: 3

Maximum file size: 1024 bytes

Maximum total IPs: 3

Allowed IP address: 192.168.1.1

Allowed hardware ID: ABCDEF123456

Two-factor authentication: Enabled

Security level: High

Usage Data:

Total downloads: 10

Daily downloads: 2

Downloads per minute: 0

Total uploads: 5

Daily uploads: 1

Uploads per minute: 0

Daily updates: 0

Total IPs: 1

Total hardware IDs: 1

License information has been saved to license_cloud_info.log.

```

If the \--extend or \--set_hwids options are used, the output will also
reflect the changes made.

**Possible Errors and Their Solutions**

-   **Error:** *You must specify a license key or \'all\' with -l or
    \--license when using \--license-info* **Solution:** Provide the
    required license key(s) using -l or \--license.

-   **Error:** *Failed to retrieve license information from the server.\
    ***Solution:** Check your internet connection and ensure the server
    is reachable. If the problem persists, contact support.

-   **Error:** *No valid license keys provided.\
    ***Solution:** Verify that the license keys are correctly entered
    and try again.

------------------------------------------------------------------------

## 4.2 Getting Service Usage Information (\--service-usage)

This function retrieves information about your service usage, including
uploaded scripts and associated licenses.

**Command Syntax**

```bash

python secure_python_code_manager.py --service-usage [OPTIONS]
```
**Description of Parameters**

-   \--service-usage or -s: Specifies the action to retrieve service
    usage information.

-   \--license-removal LICENSE_KEYS or -r
    LICENSE_KEYS: *(Optional)* Removes the specified licenses.
    Use LICENSE_KEYS as a comma-separated list or all to remove all
    licenses.

-   \--code-removal CONTENT_HASHES or -c
    CONTENT_HASHES: *(Optional)* Removes the specified code entries.
    Use CONTENT_HASHES as a comma-separated list or all to remove all
    code entries.

**Examples of Use**

**Example 1:** Retrieve service usage information.

```bash

python secure_python_code_manager.py --service-usage
```
**Example 2:** Remove specific licenses.

```bash

python secure_python_code_manager.py --service-usage --license-removal
1234567890,0987654321
```
**Example 3:** Remove all licenses.

```bash

python secure_python_code_manager.py --service-usage --license-removal all
```
**Example 4:** Remove specific code entries.

```bash

python secure_python_code_manager.py --service-usage --code-removal 1122334455,5566778899
```
**Expected Output**

The script will display your service usage information:

```javascript

Service Usage Information:

Total Uploads (Licenses): 2

Max Total Uploads (Licenses): 5

Script #1:

Content Hash: 1122334455

Script Name: my_script.py

File Size: 2048 bytes

Creation Date: 2023-12-01 00:00:00

Update Count: 2

Associated License Keys:

License #1: 1234567890

Script #2:

Content Hash: 5566778899

Script Name: another_script.py

File Size: 1024 bytes

Creation Date: 2023-12-02 00:00:00

Update Count: 1

Associated License Keys:

License #1: 0987654321

Service usage information has been saved to license_cloud_info.log.
```

If removal options are used, the script will confirm the deletions.

**Possible Errors and Their Solutions**

-   **Error:** *Failed to retrieve service usage information from the
    server.\
    ***Solution:** Check your network connection and server
    availability.

-   **Message:** *No scripts found for the current hardware ID linked to
    the current license.\
    ***Solution:** You may not have any scripts uploaded.
    Use \--upload to upload code.

------------------------------------------------------------------------

## 4.3 Uploading Code and Creating a License (\--upload)

This function allows you to upload your Python script to the cloud and
create a new license for it.

**Command Syntax**

```bash

python secure_python_code_manager.py --upload -f FILE_PATH
```
**Description of Parameters**

-   \--upload or -u: Specifies the action to upload code.

-   \--file FILE_PATH or -f FILE_PATH: A required parameter specifying
    the path to the .py file to upload.

**Examples of Use**

**Example 1:** Upload a script and create a license.

```bash

python secure_python_code_manager.py --upload -f my_script.py
```
The script must be a valid .py file.

**Expected Output**

The script will confirm the successful upload:

```javascript

Upload successful. License key: 1234567890

License script saved as:
my_script_ExpDate2024-01-01_00-00-00_PSN1234567890.py
```

The uploaded script, now containing licensing code, will be saved with a
new filename including the expiration date and product serial number.

**Possible Errors and Their Solutions**

-   **Error:** *You must specify a file with -f or \--file when using
    --upload\
    ***Solution:** Provide the script file using -f or \--file.

-   **Error:** *File my_script.py does not exist\
    ***Solution:** Ensure the file path is correct and the file exists.

-   **Error:** *Only .py files are supported\
    ***Solution:** The script supports only Python .py files.

-   **Error:** *Failed to receive license information from the server.\
    ***Solution:** Check server connectivity and try again later.

## 4.4 Updating Previously Uploaded Code (\--update)

This function updates a previously uploaded script associated with a
specific license.

**Command Syntax**

```bash

python secure_python_code_manager.py --update -f FILE_PATH -l LICENSE_KEY
```
**Description of Parameters**

-   \--update or -p: Specifies the action to update code.

-   \--file FILE_PATH or -f FILE_PATH: A required parameter specifying
    the path to the .py file to update.

-   \--license LICENSE_KEY or -l LICENSE_KEY: A required parameter
    specifying the license key associated with the code to update.

**Examples of Use**

**Example 1:** Update a script.

```bash

python secure_python_code_manager.py --update -f my_script.py -l 1234567890
```
**Expected Output**

The script will confirm the successful update:

```javascript

Update successful.
```
**Possible Errors and Their Solutions**

-   **Error:** *You must specify both a file with -f or \--file and a
    license key with -l or \--license when using --update\
    ***Solution:** Provide both the file and the license key.

-   **Error:** *File my_script.py does not exist\
    ***Solution:** Verify the file path and ensure the file exists.

-   **Error:** *Only .py files are supported\
    ***Solution:** Ensure you are using a .py file.

-   **Error:** *Failed to update code on the server.\
    ***Solution:** Verify the license key and try again.

------------------------------------------------------------------------

# 5. Additional Features

## 5.1 Extending the License Expiration Date (\--extend)

Use the \--extend option with \--license-info to extend the expiration
date of specified licenses by 24 hours.

**Command Syntax**

```bash

python secure_python_code_manager.py --license-info -l LICENSE_KEYS --extend
```
**Example**

```bash

python secure_python_code_manager.py --license-info -l 1234567890 --extend
```
**Notes**

-   You must specify license keys with -l or \--license.

-   Cannot be used without \--license-info.

------------------------------------------------------------------------

## 5.2 Setting the Maximum Number of Hardware IDs (\--set_hwids)

Use the \--set_hwids option with \--license-info to set the maximum
number of hardware IDs for specified licenses.

**Command Syntax**

```bash

python secure_python_code_manager.py --license-info -l LICENSE_KEYS --set_hwids NUMBER
```
**Example**

```bash

python secure_python_code_manager.py --license-info -l 1234567890 --set_hwids 5
```
**Notes**

-   NUMBER should be 0 or greater.

-   Must be used with \--license-info and -l or \--license.

------------------------------------------------------------------------

## 5.3 Deleting Licenses and Code

Deleting Licenses and Code (\--license-removal, \--code-removal)

Use these options with \--service-usage to remove licenses or code
entries.

**Command Syntax**

```bash

python secure_python_code_manager.py --service-usage [--license-removal LICENSE_KEYS] [--code-removal CONTENT_HASHES]
```
**Examples**

**Delete specific licenses:**

```bash

python secure_python_code_manager.py --service-usage --license-removal 1234567890,0987654321
```
**Delete all licenses:**

```bash

python secure_python_code_manager.py --service-usage --license-removal all
```
**Delete specific code entries:**

```bash

python secure_python_code_manager.py --service-usage --code-removal 1122334455,5566778899
```
**Notes**

-   Use comma-separated values for multiple entries.

-   Use all to remove all licenses or code entries.

------------------------------------------------------------------------

# 6. Working with Logs

The script saves operation details to a log file
named license_cloud_info.log, which can be used for auditing and
troubleshooting.

## 6.1 Description of the license_cloud_info.log File

The license_cloud_info.log file records:

-   **Timestamps of operations.**

-   **Details of license information retrieved.**

-   **Service usage data.**

-   **Upload and update confirmations.**

-   **Any error messages encountered.**

## 6.2 How to Interpret Records in the Log

Each entry starts with a timestamp and includes the operation
performed.\
**Example Entry for License Information Retrieval:**

```javascript

2023-12-01 12:00:00.

License information for license 1234567890:

Expiration date (UTC 0): 2024-01-01 00:00:00

Creation date: 2023-12-01 00:00:00

Is blocked: No

Is active: Yes

\...

```

**Example Entry for Service Usage Information:**

```javascript

2023-12-01 12:05:00.

Service usage information:

Total Uploads (Licenses): 2

Max Total Uploads (Licenses): 5

\...

```

**Example Entry for Upload Confirmation:**

```javascript

2023-12-01 12:10:00.

The code from file my_script.py of 2048 bytes has been successfully
uploaded to the Alpha Beta Network (alphabetanet.com) cloud and a
license has been created for it with the following license number
1234567890 with an expiration date of 2024-01-01 00:00:00.

Content Hash: 1122334455

Product Serial Number (PSN): 1234567890

!!! Do not share this license key with anyone because it allows you to
update the uploaded code.

```

**Notes:**

-   **Content Hash**: A unique identifier for your code.

-   **PSN**: Product Serial Number; keep confidential.

-   **License Key**: Should be kept secure; required for updates.

------------------------------------------------------------------------

# Appendix A: Installation of Required Packages

The secure_python_code_manager.py script requires the following Python
packages:

-   **requests**: For making HTTP requests to interact with the cloud
    service API.

-   **psutil**: For accessing system and hardware information.

-   **cryptography**: For cryptographic functions and secure
    communications.

**Installing Packages with pip**

You can install these packages using the following command:

```bash

pip install requests psutil cryptography
```
Ensure that you are using Python 3 and that pip is installed. If you are
working within a virtual environment, make sure it is activated before
installing the packages.

------------------------------------------------------------------------

# Appendix B: Contact Information

If you experience issues or have questions not covered in this
documentation, please contact the Alpha Beta Network Research Team.

-   **Website**: https://alphabetanet.com \| https://αβ.net

-   **Official Telegram Channel**: https://t.me/alphabetanetcom
