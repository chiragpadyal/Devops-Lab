# Perform various GIT operations on local and Remote repositories

### Make a local repository
```bash
mkdir myfirst
cd myfirst
```
### Initialize the local repository
```bash
git init
```
### To create a file in the local repository
```bash
touch filename
```
### Add some text to the file using cat command
```bash
cat > filename
```
### To check the status of repository
```bash
git status
```
### To add the file to the staging area
```bash
git add filename
```
### To commit the file to the local repository
```bash
git commit -m "message"
```
### To check the log of the repository
```bash
git log
```
### Use git show  to view expanded details on Git objects such as blobs, trees, tags, and commits
```bash
git show
```
### To check the difference between the files
```bash
git diff
```
### Lets push the code to the remote repository
```bash
git remote add origin git@github.com:User/UserRepo.git
```
```bash
git push -u origin master
```

### To pull the code from the remote repository
```bash
git pull origin master
```
