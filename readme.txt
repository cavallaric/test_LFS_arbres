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

 #################

 now added fr.csv to data
 $ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   readme.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)

	data/fr.csv

no changes added to commit (use "git add" and/or "git commit -a")

$ git add -u
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	modified:   readme.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)

	data/fr.csv

$ git add data/fr.csv
git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	new file:   data/fr.csv
	modified:   readme.txt

$ git commit -m "added a new .csv file and update readme.txt"
$ git push originLFStest master

it did not store it!!! it as LSF

remove the file from the folder,
$ git add data/fr.csv
$ git commit - m "removed fr.csv as not stored as LFS"
$ git push originLFStest master
Ok it is not there anymore

AGAIN
add fr.csv to data
$ git lfs track data/fr.csv

$ git add .gitattributes data/fr.csv readme.txt
$ git commit -m "added new fr.csv, .gitattributes and readme.txt - git lfs tracks fr.csv too"

$ git push originLFStest master
