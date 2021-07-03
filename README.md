# dvc-stockmarket
### What is DVC?
Data versioning is enabled by replacing large files, dataset directories, machine learning models, etc. with small metafiles (easy to handle with Git). These placeholders point to the original data, which is decoupled from source code management.

### DVC remote supports?
DVC supports several types of remote storage: local file system, SSH, Amazon S3, Google Cloud Storage, HTTP, HDFS, among others.

Here, for this project i have used google drive as remote dvc to store data.

---
First lets create github repo and clone it to locally.</br>
We will add our code into this repo
```
git clone https://github.com/lit-infinity/dvc-stockmarket.git
```
###
Initialize dvc repo
```
dvc init
```
### 
Now we will add remote dvc path
```
dvc remote add google gdrive://xyz
```
###
Now we will push our changes to the repo.

We will add our data into dvc.

```
dvc remote list
google gdrive://xyz
dvc add Stocks\data1
```
###
Now you will see data dvc file inside repo.
```
dvc push -r google
```
###
It will ask for google drive authentication code
Enter verification code: google drive verification

Now you can see data dvc file inside google drive which will be used next time if someone wants to run model.
```
dvc add Stocks\data2
dvc push -r google
```
