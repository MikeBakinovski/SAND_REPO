# 02. GIT Local Home Work 

## BASH Script steps

Create an empty Git repository
```bash
git init

git config user.name "MikeBakinovski"
git config user.email mike.bakinovski@gmail.com
```
Create an text file with home task for first commit
```bash
touch 02.Home_Task.txt
printf "Home task text" > 02.Home_Task.txt
```


# First commit to 'master' with 02.Home_Task.txt file.

git add 02.Home_Task.txt
git commit -m "First commit to master with 02.Home_Task.txt file."

# Second commit to 'master' with masterlog.txt file.

git log > masterlog.txt
git add masterlog.txt
git commit -m "Second commit to master with masterlog.txt file."

# Create brach 'dev'

git checkout -b dev

# First commit to dev with devlog.txt file.

git log > devlog.txt
git add devlog.txt
git commit -m "First commit to dev with devlog.txt file."

# Second commit to dev with devlog.txt file.

git log > devlog.txt
git add devlog.txt
git commit -m "Second commit to dev with devlog.txt file."

# Create brach 'features/do_one'

git checkout -b features/do_one

# One commit to features/do_one with do_onelog.txt file.

git log > do_onelog.txt
git add do_onelog.txt
git commit -m "One commit to features/do_one with do_onelog.txt file."

# Switch to branch 'master'

git checkout master

# Create brach 'hotfix/we_gonna_die'

git checkout -b hotfix/we_gonna_die

# One commit to hotfix/we_gonna_die with gonna_dielog.txt file.

git log > gonna_dielog.txt
git add gonna_dielog.txt
git commit -m "One commit to hotfix/we_gonna_die with gonna_dielog.txt file."

# RELEASE PHASE

# Switch to branch 'master'

git checkout master

#All commits inside master except commits which is presented in branch hotfix.

git merge dev
git merge features/do_one

# HOTFIX DEPLOY

git merge --no-commit hotfix/we_gonna_die
git add --all
git commit -m "HOTFIX DEPLOY TO 'master' BRANCH"

git checkout dev
git merge --no-commit hotfix/we_gonna_die
git add --all
git commit -m "HOTFIX DEPLOY TO 'dev' BRANCH"

git checkout features/do_one
git merge --no-commit hotfix/we_gonna_die
git add --all
git commit -m "HOTFIX DEPLOY TO 'features/do_one' BRANCH"

git log --graph --all > finallog.txt

