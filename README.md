# PythonDataScience with venv and pip
(The fork for using pipenv is here: https://github.com/DrOzturk/PythonDataScience. Bevare: If you are using PyCharm, pipenv may cause some difficulties.)

Starter data science project using Python with common dependencies included...  
Pull requests welcome...
```bash
# clone this repo to local
git clone git@github.com:DrOzturk/PythonDataScience.git
```
# Create a Virtual Environment and activate it:
```bash
python -m venv myenv
```
On Windows, run:
```bash
myenv\Scripts\activate
```
On Unix or MacOS, run:
```bash
source myenv/bin/activate
```
More: https://docs.python.org/3/tutorial/venv.html

If you need to exit the virtual environment, command:
```
deactivate
```

# To connect from Jupyter to this kernel in the virtual env,
After above virtual environment activation
```bash
# install ipykernel, which consists of IPython as well
pip install ipykernel
# create a kernel that can be used to run notebook commands inside the virtual environment
python -m ipykernel install --user --name=myenv
# you can now find this myenv as an available kernel in your Jupyter if it is already running
# else you can launch JupyterLab from virtual environment:
jupyter lab
```
More: https://medium.com/@royce963/setting-up-jupyterlab-and-a-virtual-environment-c79002e0e5f7

# Installing the dependencies
```bash
pip install -r requirements.txt
```

# Adding new dependencies
If you add a new dependency to the project using pip
like:
```bash
pip install pandas
```
You will also need to update the requirements.txt
```bash
pip freeze > requirements.txt
```
before checking into the repository.

# Developer Tools
## Linting
- pycodestyle <filename>: use to check if code complies with code style guide
ex: 
```bash
pycodestyle example_package/example.py
```

## Setuptools
- Command to Create the package to distribute in dist folder <ProjectName>-<version>.tar.gz (like dist/example_package-0.0.1.tar.gz)
```bash
python setup.py sdist
```
- For More info type:
```bash
python setup.py --help-commands
```

- helps in module discovery using find_packages(), so we can refer to all modules without relative import

## Unit Test Running
- Running all unit tests in the command line:
```bash
python -m unittest -v example_package/tests/test_example.py
```
- Running a specific test in a TestExample class in test_example test module:
```bash
python -m unittest example_package.tests.test_example.TestExample.test_greater_than
```

## Clean Compiled
find . -type f -name "*.py[co]" -delete -or -type d -name "__pycache__" -delete

.gitignore 
