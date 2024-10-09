# Git Habits

## 1: What is Git?
Git is a version control software. 

### 1.1: What is version control?
When you make PowerPoint slides for a school presentation, you will update them multiple times. Sometimes you make changes but don't like them, so you revert (恢復) the changes and go back to a previous version. It's the same when you code.

When coding, you constantly update your code, creating multiple versions, and sometimes you might want to revert to a previous version. Git is software that helps you track code changes to "control versions." You can revert (上一步), commit (存擋), merge (兩個版本合併), etc., using Git. 

> **Note**: Translation here is just a simple explanation. It should not be taken literally.

### 1.2: What is GitHub?
GitHub is a platform (or we can say a website) that uses the Git software to host code repositories (倉庫). GitHub uses Git to host its users' code.

## 2: How do I use Git?

### 2.1: Follow good Git habits.
Git can be confusing, but it is necessary, and having good Git habits will pay off in the long run. Trust me. Just follow the habits listed here. You will start to see the benefits of Git once you begin using it regularly.



## 3: Git Tutorial

### 3.1: Setup
To use Git on your local machine, you need to set it up first.

#### 3.1.1: Make sure you have Git on your local machine.
What is the local machine that I should set up Git on? 

The local machine is the one where you do your coding, because you will use Git to push code to GitHub (or elsewhere). "To push code to GitHub" means "to push code that you wrote on your local machine to GitHub."

- If you SSH into a server and code on the server, set up Git on the server.
- If you code on your laptop, set up Git on your laptop.

Check if Git is installed on local machine with the following command.
```
git --version
```
If not, install Git.
#### 3.1.2 Setup ssh key
What is ssh key? 
High level explanation: ssh key helps Github know that this local machine that's trying to git push, git commit, or do anything to this github account is you and not someone else. Essentially, ssh key is the key to your Github account. ssh key comes in pairs and you generate the key pairs(one private, one public) on your local machine. You add the public key to your Github account so that Github knows that when you are using ssh key to authenticate, it is indeed you(because you added the public key of the pair of keys to your account).
How to setup? Follow this guide: https://www.freecodecamp.org/news/git-ssh-how-to/
After you setup, you should be able to test the connection using the following command:
```
ssh -T git@github.com
```
> **Note**: As time goes on, you might have more ssh key pairs and you might want to name them differently(some names other than id_rsa). If that's the case, follow the section "Setting Non Default Key" in notionnotes in this repository.
### 3.2: Git workflow
#### 3.2.1: Step1-Git Repository

When coding, we should always start by creating a new repository and then cloning it to our local directory. With the above action, we have established a working git repository on our local machine. The cloned repository is a full-fledged Git repository on your local machine, allowing you to code in your local directory and push code to Github.

To do this:

- Go to Github and manually create a new repository.
- Use the green code button and copy the SSH url.
- cd to your local work directory and use the following command to clone to local machine
```
git clone <repository-url>
```
However, sometimes we might start coding and forgot to do the above steps, now we want to push existing code to Github.

-Follow the "How to push non-git directory to github" in notionnotes in this repository.
#### 3.2.2: Step2-(Simple)Daily Git Workflow
For simplicity, we are not using branches here yet.

- Code in local directory
- git add .
- git commit -m "Your commit message"
- git push origin main

"git add ." this is telling git what are the files that you are committing. "." means all files in this directory
"git commit" this is telling git to commit(存擋)the added files in previous step with a commit message "Your commit message"
"git push origin main" this is pushing this commit(this checkpoint) to main branch on Github. We haven't created any branch so we only have one branch which is "main".

After git add or git commit, you can always use the following command to check the status of this git repository.
```
git status
```
