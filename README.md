## Code for the paper: The Bathy-Drone: An autonomous uncrewed drone-tethered sonar system 
The code performs an analysis to determine the precision of our sonar bathymetry

All with the help of https://github.com/andrespulido8/side_scan_sonar_jupyter_notebook

To run the jupyter notebook is recommended to have docker installed on your machine to follow the instructions.
Also make sure that you have the sample-data submodule cloned.

```shell
git submodule update --init --recursive
```

# Echogram (sonar image)
Using the `precision.ipynb` file, one can visualize and process sonar data to perform the precision analysis 

![example echogram][output1]

[output1]: paper_figures/error_hist.png "Histogram of precision"

# Usage with Makefiles
```shell
make build
# now wait while the image is being built

make run
# follow the instructions that and browse to the link provided by 
# jupyter in the end
```

# Usage from PowerShell
Could be from you linux terminal as well but you will have to make some adjustments.
## Build new docker image
```powershell
docker build -t sllib-scipy-notebook -f containers/Dockerfile containers/
```
## Running
```powershell
# this works in powershell on windows, adapt to your environment
docker run --rm -p 8888:8888 -e JUPYTER_ENABLE_LAB=yes `
    -v "${PWD}:/home/jovyan/work" `
    sllib-scipy-notebook
```

# Data
The sl2 files and the csv files are stored in the [APRILab Google Drive](https://drive.google.com/drive/folders/1K57onShdPBO5McJBp5whlUoWPsp_cfui)
