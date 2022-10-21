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

23. Track the updates and stages using dvc
```
dvc repro
```




 

