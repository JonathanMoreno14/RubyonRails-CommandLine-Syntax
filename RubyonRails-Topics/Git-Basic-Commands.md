##Git Basic Commands

#####Initializes the repository

     git init
#####Adds the files into the initialized repository

     git add -A
#####Finally git commit to commit the files and add it to the master repository.

     git commit -m "message goes here"
#####Checking the status of the repository

     git status
#####If you need to see the different changes that have occurred in the repository

     git diff
#####To see all of your commits in your git repository

     git log
#####Working from a topic branch

     git checkout master
     git checkout -b topic-branch-name
#####To merge changes into the master branch

     git checkout master
     git merge topic-branch-name
     
#####Adding a local repository to a remote repository

     git remote add origin remote repository_URL
     git push origin master
     
     //the -f origin master is only used if you cannot push the origin master
     //the -f origin master forces the push to the remote repository
     git push -f origin master     
     
#####Navigating through folders using git bash

     cd filename
#####Go back a previous location

     cd -
#####Moving up a file directory

     cd ..

#####Clearing the git bash terminal

     clear
