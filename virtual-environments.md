# Index

Workflow:
* defina a versão do python a ser usada
* Use pyenv para instalar a versão do python escolhida
* Crie o diretório do projeto e nele crie um ambiente virtual com venv, virtualenv ou pyenv na versão do python escolhida
* Instale o poetry

# Table of Contents

1. [pip](#pip)
2. [venv](#venv)
3. [pyenv + venv](#pyenv+venv)
4. [poetry](#poetry)
5. [Tools](#tools)
6. [Reads](#reads)


## pip

Install requirements
```
pip install -r requirements.txt
```

 Output all installed packages in your environment
```
pip freeze > requirements.txt
```

pip in makefile:
```
venv:
    python3 -m venv venv
    source venv/bin/activate && \
    python3 -m pip install pip setuptools wheel && \
    python3 -m pip install -e .
```

## venv
```
python -m venv .venv
. .venv/bin/activate
```
## pyenv + venv

for different python versions:

List all avaibe versions
```
pyenv install --list
```
Install python 3.9.0
```
pyenv install 3.9.0
```

Set the python version for current shell session
```
pyenv shell 3.9.0
```
Deactivate current shell
```
pyenv shell --unset
```

or automatically select whenever you are in the current directory
```
pyenv local 3.9.0
```
or select globally for your user account

```
pyenv global 3.9.0
```
Create new environment with venv for some project
```
python -m venv /home/user/python_venvs/new_project_env
```

Activate environment
```
source /home/user/python_venvs/new_project_env/bin/activate
```
Install all dependencies
```
python -m pip install -r requirements.txt
```
## Conda

Install a fresh conda environment
```
conda create -n env_name python=3.7
```

```
conda env create -f environment.yaml
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

If you want to see a list of all installed packages
```
poetry show
```
with a tree
```
poetry show --tree
```
If nothing works just use:
```
pip install -r requirements.txt
```
## Tools
to help identify which packages are required by others. https://pypi.org/project/pipdeptree/

## Reads
https://chriswarrick.com/blog/2023/01/15/how-to-improve-python-packaging/
