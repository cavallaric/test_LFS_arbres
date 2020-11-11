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

$ git push originLFStest master

It uploads only .gitattributes and readme.txt

added a .gitignore to ignore .DS_Store

$ git status
$ git add .
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	new file:   .gitignore
	new file:   data/ESP_PUBLIC.IDENTITE_ARBRE.csv

$ git lfs ls-files
07edc74869 * data/ESP_PUBLIC.IDENTITE_ARBRE.csv

$ git commit -am "commit all the folder"
[master a065003] commit all the folder
 2 files changed, 5 insertions(+)
 create mode 100644 .gitignore
 create mode 100644 data/ESP_PUBLIC.IDENTITE_ARBRE.csv

 $ git push originLFStest master
 Uploading LFS objects --> very slow ?

 
