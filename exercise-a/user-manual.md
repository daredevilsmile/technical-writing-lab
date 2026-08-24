Exercise A — User Manual Procedure

EXERCISE A

Creating and Using a Python Virtual Environment

Prerequisites

Before starting, make sure you have:

A Windows computer.

Python installed on the computer.

Windows PowerShell.

An internet connection.

Basic knowledge of opening and using a command-line terminal.

Procedure

Step 1 — Open PowerShell

Action: Open Windows PowerShell.

Expected result: A PowerShell window opens and displays a command prompt.

Step 2 — Create the project folder

Action: Enter the following command:

mkdir python\_project



Expected result: A folder named python\_project is created in the current location.

Step 3 — Open the project folder

Action: Enter the following command:

cd python\_project



Expected result: The PowerShell prompt shows that you are inside the python\_project folder.

Step 4 — Create the virtual environment

Action: Enter the following command:

python -m venv venv



Expected result: A folder named venv is created inside the project folder.

Step 5 — Activate the virtual environment

Action: Enter the following command:

.\\venv\\Scripts\\Activate.ps1



Expected result: (venv) appears at the beginning of the PowerShell prompt, showing that the virtual environment is active.

Step 6 — Install the requests package

Action: Enter the following command:

python -m pip install requests



Expected result: PowerShell reports that the requests package and its dependencies have been successfully installed.

Step 7 — Verify the installation

Action: Enter the following command:

python -c "import requests; print(requests.\_\_version\_\_)"



Expected result: PowerShell displays the installed version number of the requests package.

Step 8 — Deactivate the virtual environment

Action: Enter the following command:

deactivate



Expected result: The (venv) label disappears from the PowerShell prompt.



Screenshot Description

The screenshot shows a Windows PowerShell terminal documenting the successful creation and use of a Python virtual environment.

The screenshot shows the following:

The python\_project folder being created.

The terminal entering the python\_project folder.

The venv virtual environment being created using python -m venv venv.

The virtual environment being activated, shown by (venv) appearing in the PowerShell prompt.

The requests package being installed successfully using python -m pip install requests.

The message Successfully installed confirms that requests and its required dependencies were installed.

The installed requests version is verified as 2.34.2.

The virtual environment is deactivated, shown by (venv) disappearing from the PowerShell prompt.

This screenshot demonstrates that the procedure was completed successfully from creating the project environment through installing and verifying the package.

Troubleshooting

PowerShell says that running scripts is disabled

If PowerShell displays an error stating that Activate.ps1 cannot be loaded because running scripts is disabled, temporarily allow scripts for the current PowerShell session.

Action: Enter:

Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass



Expected result: PowerShell allows scripts to run for the current session.

Action: Enter:

.\\venv\\Scripts\\Activate.ps1



Expected result: (venv) appears at the beginning of the PowerShell prompt, indicating that the virtual environment is active.

