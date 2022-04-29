# Python Package Starter

## Bootstrap

```sh
# Provide your package name
PACKAGE_NAME=YOUR-PACKAGE-NAME
echo Constructing $PACKAGE_NAME
mkdir $PACKAGE_NAME && cd $PACKAGE_NAME
python3 -m venv ./venv
source venv/bin/activate
pip install --upgrade pip
# Setup dirs and empty files
mkdir src && mkdir tests && touch src/__init__.py
# Download files
STARTER_PROJECT_PATH=https://www.github.com/brendenvogt/python-package-starter/
curl -K $STARTER_PROJECT_PATH/.gitignore -o .gitignore
curl -K $STARTER_PROJECT_PATH/README.md -o README.md
curl -K $STARTER_PROJECT_PATH/setup.cfg -o setup.cfg
curl -K $STARTER_PROJECT_PATH/pyproject.toml -o pyproject.toml
# Add your dependencies
pip install # YOUR-DEPENDENCIES-HERE (separated by spaces)
# save dependencies to requirements
pip freeze > requirements.txt
```

## Build

- prerequisites: `python3 -m pip install --upgrade build`
- build: `python3 -m build`

## Publish

- prerequisites: `python3 -m pip install --upgrade twine`
- publish: `python3 -m twine upload --repository testpypi dist/*`
