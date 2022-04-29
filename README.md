# Python Package Starter

## Bootstrap

```sh
# Provide your package name
PACKAGE_NAME=YOUR-PACKAGE-NAME
echo Constructing $PACKAGE_NAME
mkdir $PACKAGE_NAME && cd $PACKAGE_NAME
git init
python3 -m venv ./venv
source venv/bin/activate
pip install --upgrade pip # alternatively `python3 -m pip install --upgrade pip`
# Setup dirs and empty files
mkdir $PACKAGE_NAME && mkdir tests && touch $PACKAGE_NAME/__init__.py && touch tests/__init__.py
# Download files
STARTER_PROJECT_PATH=https://raw.githubusercontent.com/brendenvogt/python-package-starter/master
curl "$STARTER_PROJECT_PATH/.gitignore" > .gitignore
curl "$STARTER_PROJECT_PATH/README.md" > README.md
curl "$STARTER_PROJECT_PATH/setup.cfg" > setup.cfg
curl "$STARTER_PROJECT_PATH/pyproject.toml" > pyproject.toml
# Add your dependencies
pip install # YOUR-DEPENDENCIES-HERE (separated by spaces) # e.g. click colorama shellingham typer
# save dependencies to requirements
pip freeze > requirements.txt
```

## Build

- prerequisites: `python3 -m pip install --upgrade build`
- build: `python3 -m build`

## Publish

- prerequisites: `python3 -m pip install --upgrade twine`
- publish: `python3 -m twine upload --repository testpypi dist/*`

## Download

- `python3 -m pip install --index-url https://test.pypi.org/simple/ --no-deps example-package-YOUR-USERNAME-HERE`
