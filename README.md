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

