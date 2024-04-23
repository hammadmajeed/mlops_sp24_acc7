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