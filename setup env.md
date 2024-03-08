## Step 1
# Download the VS Code IDE
https://code.visualstudio.com/ 

## Step 2
# Download Python 3.10.5 for Windows
https://www.python.org/ftp/python/3.10.5/python-3.10.5-amd64.exe

## Step 3
# Configure ENV path for Python on Windows
(This PC > C drive > Users > UserName > Enable Hidden Items from View > AppData > Local > Programs > Python > Python310) -> copy to clipboard

Start > environment variables for your account > Path > new/add > paste the copied path > ok/save

# to test if config is working as expected
Start > cmd > type 'python -V' 

## Step 4
# Integrate VS Code with Python
Open VS Code, install python extension

## Step 5
# Setup Python VENV using VS Code
VS Code > Terminal > New Terminal
Syntax: python -m venv <desired_venv_name>
Example: python -m venv degcp-venv
Ctrl+Shift+P > Python Select Interpreter > degcp-venv

## Step 6
# Install Google Cloud SDK on Windows
https://dl.google.com/dl/cloudsdk/channels/rapid/GoogleCloudSDKInstaller.exe
Start > Powershell > Run 'gsutil' to verify if its installed properly or not
gcloud init # To authenticate and configure with GCP

## Step 7
# Activate venv and install required gcp-python packages
Open New Terminal
# To activate venv using Terminal
degcp-venv\Scripts\Activate.ps1
# Once venv is activated, then run
pip install google-cloud-storage
