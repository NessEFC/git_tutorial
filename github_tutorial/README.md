# <a name="top"></a> Git and GitHub Tutorial for Beginners
This tutorial is intended for beginners to get you comfortable working with Git and GitHub in both individual and collaborative projects.

##Outline
  1. [Overview of Git and GitHub](#overview)
  2. [Cheat Sheet of Common Git Commands](#cheat_sheet)
  3. [Quick Reference for Common Actions](#common_actions)
  4. [Extra Tips](#extra_tips)
    - Atom GitHub Add-on

## <a name="overview"></a> Overview of Git and GitHub

###Git vs GitHub

  - **Git:** a folder that you store on your local computer inside each project folder. By typing git init in the command line while you’re in your project folder, you create a git folder that contains instructions and starts tracking changes that you make to your project.
  - **GitHub:** the online website that acts like a dropbox so that you can store your files in a secure place and share them with others. Git and GitHub integrate together so that you can use Git to push up and pull down files to and from GitHub.

###Working Directory, Staging Index, and the Repository
  - **Working Directory:** the place on your computer where you work and make changes
  - **Staging Index (also called Staging Area):** the place on your computer where you stage or prepare changes that are ready to officially save
  - **Local Repository:** the place on your computer where you store saved changes
  - **GitHub Branch:** the place on your online GitHub project where you save or push the changes from your computer
  - **GitHub Master Repository:** once you and everyone in your group agrees that the changes in your branch are good and should be added to the main project, you will merge the changes from you GitHub Branch into the GitHub Master Repository

###Git and GitHub Diagram
![alt text][diagram]

[diagram]: https://github.com/CPowell23/github_tutorial_untouched/blob/master/img/diagram.png "Git and GitHub Diagram"



## <a name="cheat_sheet"></a> Cheat Sheet of Common Git Commands
[Back to Top](#top)

| **Git Command**                    | **Action**                                                                             |
| :--------------------------------- |:---------------------------------------------------------------------------------------|
| git add .                          | Update the staging index with all changes made in your working directory               |
| git add file.txt                   | Only add changes made to a single file to the staging index                            |
| git commit –m “explain changes”    | Commit changes to local repository and briefly explain what the code does in imperative tense (e.g. “Fix bug #7")|
| git log                            | List the change sets that have been committed                                          |
| git log --oneline                  | Same as git log except that it only shows you a preview                                 |
| git status                         | Tells you what files have been modified or added and if they have been staged          |
| git rm file.txt                    | Deletes a file                                                                         |
| rm -r folder_name                  | Deletes a directory                                                                    |
| git mv first.txt primary.txt       | Renames first.txt to primary.txt                                                       |
| git mv file.txt directory/file.txt | Moves file to a different directory. You can also rename the file here if you want.    |
| git reset -hard SHA                | Revert to a previous repository version and discard your changes.                      |
| git branch                         | List all local branches. There will be an * next to the branch you’re on.               |
| git branch -r                      | List all remote branches                                                               |
| git branch -a                      | List all local and remote branches                                                     |
| git branch new_branch              | Create a new branch.                                                                   |
| git checkout branch_name           | Switch to a different branch. You must commit your changes before you can switch.      |
| git checkout -b new_branch         | Create branch and switch to that branch at the same time.                              |
| git branch -m old_branch new_branch| Rename old_branch to new_branch.                                                       |
| git branch -D delete_this_branch   | Deletes a branch                                                                        |
| git stash save "message"           | Stashes your changes, resets working directory and staging index to match HEAD.        |
| git stash list                     | Lists things in the stash.                                                             |
| git stash show -p stash@{0}        | Shows what changes are in the stash.                                                   |
| git stash pop                      | Applies the stashed changes to your working directory and deletes them from the stash. |
| git stash apply                    | Applies the stashed changes to your working directory and leaves a copy in the stash.  |
| git stash drop stash@{0}           | Deletes the specified stash.                                                           |
| git stash clear                    | Deletes everything in the stash.                                                       |
| git remote                         | See all the remote branches                                                            |
| git remote -v                      | See all the remotes branches and the URL                                               |
| git remote add origin URL          | Adds or changes the remote GitHub URL that your project is connected to                  |
| git clone GitHubURL.git            | Clones GitHub repository to your computer                                              |
| git push origin branch_name        | Pushes your branch to GitHub                                                           |
| git pull origin master             | Updates your local branch and repository to match the GitHub master                    |
| git pull origin branch_name        | Updates local branch and repository to match the remote branch                         |




## <a name="common_actions"></a> Quick Reference for Common Actions
[Back to Top](#top)

###How to clone a GitHub repository
1. Find the URL to the GitHub repo you want to clone (it should end in .git).
2. In your terminal, navigate to the place you want to store your new project folder.
2. Type this:
```
git clone https://github.com/Cpowell23/github_tutorial.git
```
###How to fork a GitHub repository
Coming soon...

###How to create a GitHub repository from an existing project on your computer
  1.	You have to have an existing project folder that contains at least one file for this to work.
  2.	Navigate to your project folder in the command line and type this:

  ```
  git init
  ```

  4.	Go to your online GitHub profile.
  5.	Click the plus icon and select new repository.
  6.	Name the repository the same thing as your project folder (This is not a must, just good convention).
  7.	Find the URL to your GitHub repo (it should end in .git).
  8.	Type this in your terminal:

  ```
  git remote add origin https://github.com/Cpowell23/github_tutorial.git
  git push -u origin master
  ```

  Now your local git project is connected to the online GitHub project. You can verify that by typing this:

  ```
  git remote -v
  ```

###How to invite others to collaborate on a GitHub repository
  1. Once you have your local git and online GitHub project set up, you can invite others to collaborate and contribute to your project.
  2. Go to your online GitHub repo.
  3. Click on Settings.
  4. Click on Collaborators, find the person you want to add, and add them.

###What to do when someone invites you to collaborate
  1. Go to your GitHub profile.
  2. You should see an invitation to collaborate on the project. Accept this invitation.
      **Note:** When someone invites you to collaborate, the project will live on their GitHub profile - not yours. But that’s okay.
  3. Create a project folder with the same name as the repo on your computer.
  4. Navigate to your project folder in your terminal and type this:
  ```
  git init
  ```
  6. Navigate to the online GitHub project that you were invited to. It will be on the invitor’s GitHub profile.
  7. Find the URL to the GitHub repo (it should end in .git).
  8. Type this in your terminal:
  ```
  git clone https://github.com/Cpowell23/github_tutorial.git
  ```
  9. Now you have a copy of the project on your local computer and it’s connected to the online GitHub repo on your pair partner’s GitHub profile.
      **Note:** If you ever wonder if your project is connected to a remote GitHub repo or if it’s connected to the correct one, type this:
      ```
      git remote -v
      ```
      If it turns out you are not connected to the repo you want, just type this:
      ```
      git remote add origin https://github.com/CPowell23/github_tutorial.git
      ```

###How to fix a merge conflict
The text below explains how to fix merge conflicts. Once you've skimmed it over, complete the "Practice Resolving Conflicts" section of [this tutorial](https://github.com/turingschool/backend-curriculum-site/blob/gh-pages/module2/lessons/git_workflows.markdown#practice-pushing-and-reviewing-code). **NOTE:** just skip the instructions that refer to waffle.

First off. You will get merge conflicts. They may seem daunting at first but they are easy to fix.  Here's how. These steps assume that you have already pushed to GutHub, are trying to merge to master, and have seen you have a merge conflict.

From your terminal and in the project root directory enter...
  1. `git checkout master`
  2. `git pull origin master`. This pulls the most recent version of master.
  3. `git checkout <branch name you were working on>`
  4. `git merge master`
  5. This is where you will see a print out that looks similar to [this](http://i.imgur.com/hQ0q66Y.png)
  6. Notice the lines that start with `CONFLICT`
  7. These are the files that you will have to fix along with the file path to each issue.
  8. Open up the first conflict and you will see something like [this](http://i.imgur.com/hXcpUGx.png)
  9. The important parts here is `<<<<<<< HEAD`, `=======`, and `>>>>>>> MASTER`.
  10. Everything between `<<<<<<< HEAD` and `=======` is your new code.
  11. Everything between `=======` and `>>>>>>> MASTER` is what is on Master branch.
  12. Look over the code and see what needs to be changed/moved around and change it. Make sure to delete `<<<<<<< HEAD`, `=======`, and `>>>>>>> MASTER`. once you are done.
  13. Now go through the normal `git add .`, `git commit -m "<Your message>"`, `git push origin <branch_name>` process.
  14. When you get to GitHub you should see that you can merge to master without a problem. 

###All About Git Ignore
When pushing to Github it will be necessary to have Git ignore certain files. There are to types of Git ignore files, Local and Global.

First we will talk about the local git ignore file.
  1. `touch .gitignore`
  2. Open the file with your text editor.
  3. Add any file you do not want to push to GitHub to this file.
  4. You must add the file path for any file you add. (eg. for anything in the root directory you would simply put `/<file_name>`)

Now for Global Git Ignore. This is useful to have if there will be files in every project that you do not want to push to GitHub.
  1. `git config --global core.excludesfile ~/.gitignore_global`
  2. This creates the `.gitignore_global` file in your machine's root directory.
  3. Open this file with your text editor.
  4. Same as the local `.gitignore` file so add any files (with the correct file path) that you do not want to add to GitHub.  

###How to find the SHA
  1. Type `git log` into your terminal in the directory for your project.
  2. You'll see a print out that looks similar to this
  ```
    commit 7047a0dd182981bb6a1748ec608c38a2d3c4a8c2
    Author: <Someone's name here>  <Their email>
    Date:   <Date in strftime>

    <Commit Message>
    ```
  3. the first line `commit` is your SHA.
  4. We'll talk about what to do with this in the next section


###How to revert to a previous version
Sometimes it may be necessary to revert your code to a previous version. This may happen because you have gotten way off base from your initial thoughts and the code is not save-able at this point. No worries this is super simple to fix.

  1. First find the SHA of the commit you want to reset to (See above)
  2. Once you have the SHA enter `git reset --hard [<SHA>]` in your terminal
  3. This will delete all code and files you have created since that SHA.

###How to view differences between versions
Coming soon...

###How to create a pull request
  1. Navigate to your online GitHub project.
  2. Click on branches.
  3. Next to the branch that you want to merge into master, click New pull request.
  4. Click Create pull request.
  5. Click Merge pull request. It is good git workflow for the person who created the pull request to NOT be the person who merges to the master. This ensures that the other person signs off on merging your changes to master.

###How to view the number of commits per person
  1. Navigate to the project on GitHub.
  2. Click on the “Pulse” tab.
  3. Hover over each partner down below to see how many commits they have.


## <a name="extra_tips"></a> Extra Tips
[Back to Top](#top)
  - **Atom GitHub Add-on:** Open Atom, go to preferences, go to install, search for **git-plus**, and install.
