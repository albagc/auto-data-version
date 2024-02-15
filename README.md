# Code for FAIR--compliant data versioning service

This repository contains all the necessary source code to assign the "minor" term from the standard data versioning framework.

The main folder contains all the Python scripts and Jupyter notebooks to obtain the results submitted for publication.

To run the scripts, it is mandatory to have Python installed on your device. It is required specifically the Python 3.10.9 version ([link to download Python](https://www.python.org/downloads/release/python-3109/))

1.- Install the Python 3.10.9 version. Execute the following command to review the current version of Python installed on your machine:
```
python --version
```
It is also necessary to have .pip installed on your machine.
([link to download Pip](https://pypi.org/project/pip/))

2.- Install the pip and execute the following command to review the current version of pip installed on your machine:
```
pip show pip
```

## Clone the repository

3.- The first thing to do is to clone the content from this repository. 
    To do so, you can navigate to the folder where you want to store the repository locally and execute the following command to clone the repository:
```
git clone https://github.com/albagc/auto-data-version.git
```
or you can also download the auto-data-version.git project as a .zip file and extract the files in a selected folder. 

## Install Python dependencies

4.- To execute the scripts included in this repository, open a terminal window and run the following command:
```
pip install -r requirements.txt
```
5.- This will install all packages and their corresponding versions as they are included in the requirements.txt file.

## Run an experiment

Each experiment script obtains the Primary Source model and executes the Creation, Update and Deletion events on a particular dataset. 
Moreover, these scripts are both in jupyter notebook format (i.e., .ipynb extension) and also as Python scripts (i.e., .py extension):

6.- To run the jupyter notebook files, you can either:
      a) open the file in your IDE (e.g., VisualStudioCode), or
      b) navigate in your terminal to the folder containing the .ipnyb files, type ```jupyter notebook```, and execute the jupyter notebooks in your browser. 

7.- To run the Python scripts, you must navigate to the main folder and execute the script from your terminal as in:
    ```
    cd experiments
    python ds1_CUD.py
    ```
The complete experiments take hundreds of realisations and they can be quite time-consuming.
Hence, we included some demo files as well, which will perform the time series decomposition, the obtention of the Primary Source data model and finally will also simulate a single realisation of a Creation, Update and Deletion experiments. 
This allows the obtention of a single result, which is much more time efficient and also permits the direct comparison of the results for that single realisation across users, devices, etc. 

8.- To run those scripts, just navigate to the main folder and execute any of the ```<>_demo.py``` scripts from your terminal as in:
    ```
    cd demos
    python ds1_CUD_demo.py
    ```
The results should be all stored directly in the results/ folder, which contains a .txt file only as a placeholder. 
If you want to change the path where results should be stored, you can set the ```resultspath``` input argument from the ```do_exp``` function.

The results will be stored by default in the results folder, in a subfolder named by default as the date when the experiments are run.

## Plot figures as in the manuscript

9.- The scripts named as ```plot_paper_figures<>.py``` should be executed to obtain the pdfs with the figures included in the paper. 
The script ```ps_models_r2.py``` plots the Figure with the information regarding the goodness-of-fit and the time obtained when the Primary Source models are being fitted. 

10.- **WARNING**: By default, the scripts call to all the datasets. 
If users want to exclude any dataset, they should edit the scripts by removing the names of their corresponding files from the lists containing the names of all the experiments and datasets.
