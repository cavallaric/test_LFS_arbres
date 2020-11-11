# readme git LFS example

in my folder LFS_test/data I have the large .csv file

$git init #in LFS_test to initialise the git folder
$ git lsf track data/*.csv
Tracking "data/ESP_PUBLIC.IDENTITE_ARBRE.csv"

In LFS_test I have now .git and .gitattributes

$ git status
$ git add .gitattributes
$ git status
$ git commit -m "added .gitattributes"

$ git remote add originLFStest https://github.com/cavallaric/test_LFS_arbres.git
$ git remote -v
originLFStest	https://github.com/cavallaric/test_LFS_arbres.git (fetch)
originLFStest	https://github.com/cavallaric/test_LFS_arbres.git (push)

now add also the readme before pushing to the repository

$ git status
$ git add readme.txt
$ git status
$ git commit -m "added readme.txt"
