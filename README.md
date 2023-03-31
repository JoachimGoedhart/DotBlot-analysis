![https://colab.research.google.com/github/JoachimGoedhart/DotBlot-analysis/blob/main/DotBlot_analysis.ipynb](https://colab.research.google.com/assets/colab-badge.svg)

# DotBlot-analysis

Repository with Python code in a Jupyter Notebookto to perform automated (image) analysis on dotblot data.

## Introduction 
Levels of chemokines are measured through an array that produces a dotblot as result (https://www.rndsystems.com/products/proteome-profiler-human-cytokine-array-kit_ary005b). Every dot is linked to different antibodies, and we must quantify it in order to get informative data on levels.

![](https://raw.githubusercontent.com/JoachimGoedhart/DotBlot-analysis/main/Dotblot_Example-data.png)

Previously, dot blot quantification has tipically been done manually. Thus, the goal is to automate this process by creating a pipeline of code in ‘Python’. 

Therefore, the aim of this Jupyter Notebook is to automatize the process of registering each single dotblots to the mask, to get the grey value from each dot, and finally to arrange the values in a tidy table to allow for a faster and easier analysis.

## How to use this Notebook 
Before you run the Notebook, make sure that you are logged into your Google account and have the data to process in your Google Drive. 
## Before Starting 
For the code to work, Images must be 700x300 and in .tif format. This is best done in ImageJ before starting the analysis. 
## Load Packages 
GoogleCoLab provides pre-installed packages that need to be imported by running the code. These include: 
-	Os
-	Matplotlib
-	Numpy
- Pandas
-	Skimage

Other libraries, such as pystackreg, must be installed as an extra. 
## Mount Drive 
The most important step to make this Notebook work is to mount the personal Drive to the GoogleCoLab. To do that, “Run” the code and accept to access your Drive. 
If you click on the left, on the folder icon, your Drive folder should appear with all your personal organized Drive that you are able to access freely. 
## Directories 
Once you are connected to your personal Drive you can access the data. To make the workspace clear and neat I divided the data in folders (“directories”): 
-	In_dir = folder with the TIF files (700x300) of the dotblot that must be analysed 
-	Out_dir = folder where all the output files are going to end up (registered images in grayscale, and long format tables with grey values) 

To give the right directions, go on the three dots next to the folder of interest and click on “Copy path”, then past this in the right correspondent directory. 
## Load Data 
Here we load the required data from the correspondent directory: 
-	The first mask is going to be the one used to get values out of every labeled dot. 
-	The second one is used to register the images to the Reference Spots only
-	The Table consists of the list of conditions of each Human Chemokine Array coordinates taken from the protocol. 

## Registration 
This loop will access the TIF files folder and consequently register, quantify, and design output tables for each file. 

