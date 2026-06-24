## Hey there! Here are some quick actions for common issues :)
Fun fact: Each instruction starts from the bottom to the top of the file in order to not mix up the line location making it easier to find.

### Don't like the preinstalled formatter?
Remove the following from **.devcontainer/devcontainer.json**
```
        "editor.formatOnSave": true,
        "editor.defaultFormatter": "esbenp.prettier-vscode",
        "python.analysis.languageServer": "Pylance",
        "[python]": {
          "editor.defaultFormatter": "charliermarsh.ruff",
          "editor.codeActionsOnSave": {
            "source.organizeImports": "always",
            "source.fixAll": "always"
```
Find it at lines 11-18 (from the original template).
These are the extensions that format your code.

and from **.vscode/settings.json**
```
  "editor.formatOnPaste": true
  "editor.formatOnSave": true
```
Find it at lines 10-11 (from the original template).
These are the ones that automatically format code the moment you save or paste code in.


### Don't like the installation before the installation of requirements.txt?
Remove the following from **.devcontainer/devcontainer.json**
```
  "postCreateCommand": "python -m venv .venv && .venv/bin/python -m pip install -r requirements.txt"
```
Find it at line 6 (from the original template).

### Want to update the default Python to a newer version?
Update at **.devcontainer/devcontainer.json**
```
  "image": "mcr.microsoft.com/devcontainers/python:3.13",
```
Find it at line 3 (from the original template).
This is the 3.13.x Python (the latest Python) is being installed by default.

With your desired Python image from:
https://mcr.microsoft.com/en-us/artifact/mar/devcontainers/python/about (recommended as it installs git zsh and curl by default)
https://hub.docker.com/_/python
Or any other site!
