<h1>Instructions for using github for github_instructions</h1>

<h2>Steps</h2>
1. Make an account at github.com and send me your github username by text or email.
2. Install git on your virtual machines

    **Ubuntu 10.04**

    ```bash
    sudo apt-get install python-software-properties
    sudo add-apt-repository ppa:git-core/ppa
    sudo apt-get update
    sudo apt-get install git
    ```

    **Ubuntu 12 and 14**

    ```bash
    sudo apt-get install git
    ```

    **Fedora 14**

    ```bash

    sudo yum install git
    ```

3. Configure your git global user using your real name and the email you used for github. Using your real name here will help us keep track of who did 
what.

    ```bash
    git config --global user.name "Dustin McManus"
    git config --global user.email dustin.mcmanus@hotmail.com
    ```

4. Set up git to save your password for 10 hours so you do not have to keep typing it when interacting with the remote github.com server.

    ```bash
    git config --global credential.helper 'cache --timeout=36000'
    ```

5. Verify configuration:

    ```bash
    git config --list
    ```

    **Output:**

    ```
    user.name=Dustin McManus
    user.email=dustin.mcmanus@hotmail.com
    credential.helper=cache --timeout=36000
    ```

6. Clone the remote repository to your current working directory so that you have a local copy to work with. This will create a github_instructions folder with 
everything in it.

    ```bash
    git clone https://github.com/dustinmcmanus/github_instructions.git
    cd github_instructions
    ```

7. Except for quick edits, we probably want create a local branch for each new feature and then merge it with the local master branch and push it to the 
server after it has been tested. From what I have read, this is the best way to use git. Here is how to do this:
8. Create local branch and switch to it.

    ```bash
    git checkout -b new_feature_name
    ```

10. Add new files to git project or completely destroy files.

    ```bash
    git add new_file_name
    git rm new_file_name
    ```

9. Make edits to files here. Whenever some progress is made that you would like to save, then commit the edits. You can use wildcards when adding files to be commited.

    ```bash
    git add edited_file_name
    git commit -a -m "message about what was accomplished"
    ```

11. Switch back to master branch when done with feature.

    ```bash
    git checkout master
    ```

12. Merge the new feature branch into the local master branch.

    ```bash
    git merge new_feature_name
    ```

13. Delete the feature branch when done merging and after testing that everything works well.

    ```bash
    git branch -d new_feature_name
    ```

14. Pull down any concurrent edits that other people have made to the online github repository in the mean time and merge them with your local 
repository so that you have the most up to date code along with the new feature you created.

    ```bash
    git pull
    ```

15. Push your local version of the repository along with the new feature you made to the online github repository

    ```bash
    git push
    ```
16. Repeat steps 7 through 15 until project is finished.

<h2>Extra git commands</h2>

```bash
git status
git log
git log --summary
git diff HEAD
git branch
git reset
git stash
```