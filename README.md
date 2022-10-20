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
 
