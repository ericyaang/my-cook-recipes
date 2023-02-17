# Project setup workflow

## Defina qual versão do python usar
- python 3.8.0

## Instale a versão escolhida com o pyenv

Instalando a versão escolhida
```
pyenv install 3.8.0

```
Verifique se deu certo

```
pyenv versions
```

## Crie o diretório do seu projeto

```
mkdir meu-projeto
cd meu-projeto
```

## Verifique a versão do python 
Faça a versão escolhida ser a nativa dentro do seu diretório
```
pyenv local 3.8.0
```

Verifique a versão do python associada ao seu diretório atual
```
python -V
```

## Configurando o ambiente virtual

Crie o ambiente virtual
```
	python -m venv .venv
  
 ```
 
 Ative o novo ambiente virtual
 ```
 .venv\Scripts\Activate.ps1
 ```

Atualizando as packages necessárias e baixando a versão atualizada do wheels
```
python -m pip install --upgrade pip setuptools wheel
```

## Poetry

```
python -m pip install poetry
```

Iniciando o poetry, gerando o pyproject.toml

```
poetry init
```

Divirta-se!
