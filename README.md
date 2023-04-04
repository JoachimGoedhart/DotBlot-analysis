


[![Foo](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/JoachimGoedhart/DotBlot-analysis/blob/main/DotBlot_analysis.ipynb)


# DotBlot-analysis

Repository with Python code in a Jupyter Notebookto to perform automated (image) analysis on dotblot data.

## Introduction 
Levels of chemokines are measured through an array that produces a dotblot as result. Every dot is linked to different antibodies, and we must quantify it in order to get informative data on levels. Previously, dot blot quantification has typically been done manually.

![](https://raw.githubusercontent.com/JoachimGoedhart/DotBlot-analysis/main/Dotblot_Example-data.png)

Therefore, the aim of this Jupyter Notebook is to automate the processing and analysis of dotblots. It is developed to analyze dotblots of the Proteome Profiler Human Chemokine Array Kit from R&D Systems, Inc. [(Catalog Number ARY017)](https://www.rndsystems.com/products/proteome-profiler-human-chemokine-array-kit_ary017). The different steps are registering each single dotblot to the mask, to get the grey value from each dot, and finally to arrange the values in a [tidy table](https://thenode.biologists.com/converting-excellent-spreadsheets-tidy-data/education/) to allow for a reproducible (and possibly automated) analysis. 

## Before Starting

> If you don’t provide data, the notebook will still run and use example data.

To run the program on Google Colab, ensure that the data is saved in your Google Drive. Alternatively, if you prefer to use as Jupyter Notebook, download the Notebook and ensure that the data is stored in a local directory.

For the code to work, Images of dotblots must be 700 by 300 pixels (width x height) and in .tif format. This is best done in FIJI/ImageJ before starting the analysis. A file that defines an ROI of the correct size in FIJI/ImageJ is included in this repo (700x300.roi). To use it, open an image and drop the `700x300.roi` file on the toolbar to add it to the image. You can move it around and use 'Image > Duplicate...' to extract the image in the right dimensions.


## Initialization & Packages

The notebook requires several libraries and these will be remotely initialized in Google Colab. If you are running the notebook locally, you need to install the relevant packages in your environment.

## Data input and output 

The notebook loads all TIF files from a directory (specified as `in_dir`). When running it on Colab, make sure that the TIF files are on your Drive in a single folder. The resulting registered images and CSV files will be stored in another directory (`out_dir`)

---------------------

### Limitations

The notebook is dedicated to the analysis of a specific Array kit. It can be extended to other arrays by providing a TF file with a 'mask' that defines the locations of the spots and the CSV that defines the labels of the spots.

### Contact

If you run into trouble, or want to request a feature, file [an issue](https://github.com/JoachimGoedhart/DotBlot-analysis/issues) on GitHub. 


### Credits

- [Nico Schramma](https://twitter.com/nicoschramma) improved the registration
- A similar workflow that uses ImageJ/FIJI is reported by Anna H. Klemm: [https://f1000research.com/articles/9-1385]



