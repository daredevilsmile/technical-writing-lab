Exercise C — Technical Report Section



Python Development Environment Setup



Overview



A Python development environment was configured to support isolated package management and reproducible development. A dedicated project directory was created, followed by the creation of a Python virtual environment named `venv`.



Implementation



The virtual environment was activated before installing external dependencies. The `requests` package was installed using Python's package manager with the following command:



```powershell

python -m pip install requests

