##Git Basic Commands

Initializes the repository

     git init
Adds the files into the initialized repository

     git add -A
finally git commit to commit the files and add it to the master repository.

     git commit -m "message goes here"
Checking the status of the repository

     git status
If you need to see the different changes that have occurred in the repository

     git diff
To see all of your commits in your git repository

     git log
Working from a topic branch

     git checkout master
     git checkout -b topic-branch-name
To merge changes into the master branch

     git checkout master
     git merge topic-branch-name
Navigating through folders using git bash

     cd filename
Go back a previous location

     cd -
Moving up a file directory

     cd ..

