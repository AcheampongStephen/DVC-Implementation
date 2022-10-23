1. Create a virtual environment and activate it
```
i. conda create -n winequality python=3.7 -y
ii. conda activate winequality
```
2. Create requirements.txt file and run it
```
i. touch requirements.txt
ii. In requirements.txt file, document the following packages:
    - dvc
    - dvc[gdrive]
    - sklearn
iii. pip install -r requirements.txt
```
3. Create a README.md file and document the above steps
```
touch README.md
``` 
4. Create a template to for the project
```
i. touch template.py
ii. In template.py, document the the packages, files and directories that will used forthe project.
iii. python template.py
```
5. Download the dataset into data_given directory. Link: https://bit.ly/3TmpoPC

6. Initiate GIT
```
git init
```
7. Initiate DVC
```
i. pip install dvc
ii. dvc init
```
8. Track the data using DVC
```
dvc add data_given/winequality.csv
```
9. Add and commit the files
```
i. git add .
11. git commit -m "first commit"
```
10. Create a GitHub repository to push your flies and codes
```
i. git remote add origin https://github.com/AcheampongStephen/DVC-Implementation.git
ii. git branch -M main
iii. git push origin main
```
11. Open params.yaml and document the stages of your project.
```
- base
    - project name
    - random state
    - target column
- data source
    - data source location
- loading the data
    - raw data localtion
split data
    - training path of the data
    - testing path of the data
    - size to split
- estimators
    - algorithm to be used
        -parameters of the algorithm
            - alpha value
            - l1_ratio value

- model directory : Path of the saved model
```

12. Create a 'src/get_data.py' in src directory to get the data.
```
- src/get_data.py: Read the params, process it, and return dataframe
    - pip install pandas
    - import os
    - import yaml
    - argparse
```
13. Create a 'src/load_data.py' in src directory to get the data.
```
- src/load_data.py: Read the datafrom the source and save it in the data/raw for further processing
    - import os
    - from get_data import read_params, get_data
    - import argparse
```
14. Documents the stages in dvc.yaml file then run it.
```
dvc repro
```
15. Create 'src/split_data' to split the loaded dataset from 'src/load_data'.
16. Document the splitting stages in dvc.yaml and then run it
```
dvc repro
```
17. Create 'src/train_and_evaluate.py' to train and evaluate the model.
18. Document the stages in dvc.yaml and run it
```
dvc repro
```
19. Create a report directory to save all your metrics and params. Within the directory, create params.json and scores.json to record all the metrics and parameters of the model.

20. Update the dvc.yaml file by documenting the stages for the report under train_and_evaluate params section

21. Update train_and_evaluate.py file to incorporate the metrics that needs to be parsed in the report directory. Do not forget to dump the metrics and and parameters to the their respective json files.

22. Update params.yaml to incorporate the paths of the reports.

23. Track the updates and update stages using dvc
```
dvc repro
```
24.
```
dvc metrics show
dvc metrics diff : differences between the metrics
```



********************************************************************

## TESTING
1. install pytest in requirements.txt
2. tox in requirements.txt
```
- pytest
- tox : create a virtual environment for your testing purposes
pip install -r requirements.txt

* push it to github
```
3. create tox.ini to initiate the file to document the desired environment for the testing
4. create a test directory to document your tests. Within the directory, create __init__.py, conftest.py, and test_config.py to test the configuration.
````
for example Inside test_config.py,
def tes_generic():
    a = 2
    b = 2
    assert a == b

    run: pytest -v
    The result will restun successful
```
4. Inside tox, document the virtual environment and run it.
```
[tox]
envlist = py37
skipsdist = True

[testenv]

deps = -rrequirements.txt
commands = pytest -v

on your cmd run to build your virtual env together with the packages: tox 

tox -r : rebuilding your virtual environment
```
5. create setup.py to find and install all your packages.
```
from setuptools import setup, find_packages

setup(
    name = "src",
    version = "0.0.1",
    description = "it's a wine quality packages",
    author = "Stephen Acheampong",
    packages = find_packages(),
    license = "MIT"
)

- pip install -e .
- pip freeze
```
6. MAke sure the range of each feature/columns has been determined. Under notebook directory, pip install jupyterlab.
```
- pip install jupyter lab
- jupyter-lab notebooks/
```
7. Paste the custom error into text_config.py to test the range


## PEP 8 GUIDELINES USING FLAKE
1. pip install flake
2. In tox.ini, document the processes under commands.
3. tox -r
3. run tox


    ### PREDICTION

1. create a directory called prediction_service. Inside the directory, create a directory called model.

2. In the root directory, create:
 - webapp directory
 - app.py

3. Inside the prediction directory, create the following:
    - __init__.py
    - prediction.py

4. In the webapp directory, create the following files and folders
    - create 'static folder'
    - inside static folder, create 'css folder'
    - inside static folder, create 'script folder'
    - In css folder, create main.css file
    - In script folder,  create index.js
    - in the webapp directory, create a 'template' folder
    - inside template folder, create index.html
    - inside template folder, create base.html