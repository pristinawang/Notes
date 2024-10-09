# Git

[https://www.freecodecamp.org/news/practical-git-and-git-workflows/](https://www.freecodecamp.org/news/practical-git-and-git-workflows/)

[https://kbroman.org/github_tutorial/pages/first_time.html](https://kbroman.org/github_tutorial/pages/first_time.html)

# Setting None Default Key

## Set up None Default Key

```python
$ ssh-keygen -t rsa -C "github"
#The algorithm is selected using the -t option
#-C is for comment
```

## Give the public/private key pair a none default file name

```python
Enter file in which to save the key (/home/cs601-pwang71/.ssh/id_rsa): /home/cs601-pwang71/.ssh/id_rsa_github
```

## Checkout the comment this way

```python
[cs601-pwang71@login01 .ssh]$ cat id_rsa_github.pub 
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABgQDExGkcDaHYT9SpX+4UQqi66H95WkeYVHENvGXICWLX0fxmx4JzFgBuWKwV2J12CKQ+QWXiGcDgWIWlF9ij2ZAeVeqy7H6DFhnV1nmenJIRuenTFDNf8gNpy6/YYK4PeMQOQiM/ctvFCeVyP/6uPHSASbyYDyBScZ+GtWEMnOWnoU04sja9fG1kDC9VjkLFt1fWJuAvfAxahUAGZiKnmJhUwd8CtgKr58vuH2DrpRD5HY+MWe69634ZxgN846ecBN+oUmit75pC9KqJQSAepwMxhV137jfjMa8PRNbZCw5i7QnaR1x2A27hZQ9XLjz6NOn3UiXVD5gt1xewV8cu/8V1aVQtL3P4fS1CsLAiTJuCEuRhcEMdHk5XqWKahFndZlSXRcYQdlx6tW1J2h5Ht8esoIECXYCXqtZggDu0VgluCXOVizjKcO3xHc+1QduJA9/+tTAWYXpFN6wWHhY5sws72kfwQW7PEA8Oc1JWhVj9+Qy1Y6u8r1F0UTla0i4TiU0= github
```

## Full Process

```python
[cs601-pwang71@login01 .ssh]$ ssh-keygen -t rsa -C "github"
Generating public/private rsa key pair.
Enter file in which to save the key (/home/cs601-pwang71/.ssh/id_rsa): /home/cs601-pwang71/.ssh/id_rsa_github
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in /home/cs601-pwang71/.ssh/id_rsa_github.
Your public key has been saved in /home/cs601-pwang71/.ssh/id_rsa_github.pub.
The key fingerprint is:
SHA256:BclZSJHrua3I61UfMNTtOzebcPN1rt2iXqrQ0BAeq+0 github
The key's randomart image is:
+---[RSA 3072]----+
|       o*Bo. .   |
|       .**  . .  |
|        +.+  .   |
|       o.+ o  .  |
|      ..S.o .  . |
|       .o+ . oo++|
|        Eo. . ++O|
|     . o...  o.++|
|     .=....o+..oo|
+----[SHA256]-----+
[cs601-pwang71@login01 .ssh]$ ls
authorized_keys  id_ecdsa  id_ecdsa.pub  id_rsa_github  id_rsa_github.pub
[cs601-pwang71@login01 .ssh]$ cat id_rsa_github.pub 
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABgQDExGkcDaHYT9SpX+4UQqi66H95WkeYVHENvGXICWLX0fxmx4JzFgBuWKwV2J12CKQ+QWXiGcDgWIWlF9ij2ZAeVeqy7H6DFhnV1nmenJIRuenTFDNf8gNpy6/YYK4PeMQOQiM/ctvFCeVyP/6uPHSASbyYDyBScZ+GtWEMnOWnoU04sja9fG1kDC9VjkLFt1fWJuAvfAxahUAGZiKnmJhUwd8CtgKr58vuH2DrpRD5HY+MWe69634ZxgN846ecBN+oUmit75pC9KqJQSAepwMxhV137jfjMa8PRNbZCw5i7QnaR1x2A27hZQ9XLjz6NOn3UiXVD5gt1xewV8cu/8V1aVQtL3P4fS1CsLAiTJuCEuRhcEMdHk5XqWKahFndZlSXRcYQdlx6tW1J2h5Ht8esoIECXYCXqtZggDu0VgluCXOVizjKcO3xHc+1QduJA9/+tTAWYXpFN6wWHhY5sws72kfwQW7PEA8Oc1JWhVj9+Qy1Y6u8r1F0UTla0i4TiU0= github
```

Must change config file

[https://stackoverflow.com/questions/41412964/using-a-non-default-key-name-other-than-id-rsa](https://stackoverflow.com/questions/41412964/using-a-non-default-key-name-other-than-id-rsa)

[https://superuser.com/questions/232373/how-to-tell-git-which-private-key-to-use](https://superuser.com/questions/232373/how-to-tell-git-which-private-key-to-use)

# Cloning Repository with SSH

[https://phoenixnap.com/kb/git-clone-ssh](https://phoenixnap.com/kb/git-clone-ssh)

# Test if ssh is setup for Github correctly

```jsx
ssh -T git@github.com
```

![image.png](Git%20b8b8b3750b42432dbda974472722a56a/image.png)

# Local Repo is up to date with Git repo or not

## Check if local is up to date with Git repo or not

```python
git remote update
git status
```

## It is behind Git repo and you’d like to bring local repo up to date with Git repo

```python
git pull
```

# Git commits history

```java
git log
```

# Squash

To squash the last 3 commits and then edit the commit message use this following command.

```java
git reset --soft HEAD~3 && 
git commit --edit -m"$(git log --format=%B --reverse HEAD..HEAD@{1})"
```

### To not include certain files in git commit

specify the files that you don’t want to include in .gitignore file

```java
touch .gitignore //create .gitignore file first
vim .gitignore //edit this text file and specify files you don't want
```

This is the .gitignore file and this file shows to not include all .log and .json files

```java
*.log
*.json
```

Now we want to clear all cache before committing because if you don’t clear cache, git might still be tracking the files that you just specified to ignore in .gitignore and these files will also get included in new commits. We want to clear the cache so that git is not tracking these files(in our case, .log and .json) anymore.

```java
git rm -r --cached .
```

To check files included in a particular file

```java
git ls-tree --name-only -r <commit-ish>
```

# How to push non-git directory to github

*Source: https://stackoverflow.com/questions/3311774/how-to-convert-existing-non-empty-directory-into-a-git-working-directory-and-pus*

This is how I do. I have added an explanation to understand what the heck is going on.

**Initialize Local Repository**

- first, initialize Git with
    
    > git init
    > 
- Add all Files for version control with
    
    > git add .
    > 
- Create a commit with a message of your choice

> git commit -m 'AddingBaseCode'
> 

**Initialize Remote Repository**

- Create a project on GitHub and copy the SSH URL of your project. as shown below:

![image.png](Git%20b8b8b3750b42432dbda974472722a56a/image%201.png)

**Link Remote repo with Local repo**

**Use SSH url so that the ssh key you setup can be used to authenticate. Otherwise, it might prompt you to enter github username, password and it’s really clumsy and possibly not work**

- Now use copied URL to link your local repo with the remote GitHub repo. When you clone a repository with git clone, it automatically creates a remote connection called **origin**pointing back to the cloned repository. The command remote is used to manage a set of tracked repositories.
    
    > git remote add origin [git@github.com](mailto:git@github.com):pristinawang/temp-test.git
    > 

If you added the wrong url at first, use this to update to the right url

```jsx
git remote set-url origin git@github.com:ppreyer/first_app.git
```

Add branch

- No branch, must add main branch
    
    > git branch -M main
    > 

**Commit your code**

- Finally, push all changes on GitHub
    
    > git push -u origin main
    >