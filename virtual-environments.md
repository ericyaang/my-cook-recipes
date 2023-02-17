# Index

# Table of Contents
1. [venv](#venv)
2. [pyenv + venv](#pyenv+venv)
3. [poetry](#poetry)
4. [Tools](#tools)
5. [Reads](#reads)


## venv

```
python -m venv .venv
. .venv/bin/activate
```
## pyenv + venv
for different python versions:

Install python 3.9.0
```
pyenv install 3.9.0
```

Set the python version
```
venv shell 3.9.0
```

Create new environment with venv for some project
```
python -m venv /home/user/python_venvs/new_project_env
```

Activate environment
```
source /home/user/python_venvs/new_project_env/bin/activate
```
```
python -m pip install -r requirements.txt
```
## poetry

issues: 
*  longer build time
*  can't install packages with conflicting dependencies

### Basic workflow
```
Install poetry

pip install poetry
```

Generate pyproject.toml interactively and create venv
```
poetry init 
```
Add dependency
```
poetry add requests # Add --dev for development dependencies
```
Install dependencies into venv
```
poetry install
```
Activate venv
```
poetry shell
```
Exit venv

```
exit
```
### Other commands

Install package with a specific version
```
poetry add package-i-want@^1.2.3
```
For development dependencies
```
poetry add --dev <package>
```

If nothing works just use:
```
pip install -r requirements.txt
```
## Tools
to help identify which packages are required by others. https://pypi.org/project/pipdeptree/

## Reads
https://chriswarrick.com/blog/2023/01/15/how-to-improve-python-packaging/
