To initialize the DVC in the current directory. Assuming DVC is installed

`dvc init`

Make data directory for data storage

`mkdir data`

Get data from the remote hosted site using dvc get

`dvc get url -o local path`

Add the file to dvc tracking

`dvc add data/data.csv`

Look at the contetnts of data/data.csv.dvc

`cat data/data.csv.dvc`

Now use some remote location to store your large data file. We are not pushing data to github as it is not a data repository management, rather is a code version system.

`git remote add -d storage gdrive://1h-XbbzW41KEpzCVp8x_h69fO-yUDjWuv`

Lets try to remove the local copy of the data and try to restore it using the dvc

`rm -f data/data.csv`

Clear DVC Cache as well 

`rm -rf .dvc/cache`

Get the data from the remote drive

`dvc pull`

Now we shall try to update the update the data set and restore the old version after pushing the new version to the remote folder

`python get_data.py`

Push the data to the remote site 

`dvc add data/data.csv`

`dvc push`

Checkout the old version of the data set

`git log --oneline`

`git checkout HEAD^1 data/data.csv.dvc`

`dvc checkout`

Commit to git

`git commit data/data.csv.dvc -m 'reverted to the old dataset`


