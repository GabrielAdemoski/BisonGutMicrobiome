# Singh Lab Bison Gut Microbiome Graphical Analysis Project

This project is used for Bison gut microbiome research in Dr. Pallavi Singh's lab at Northern Illinois University.
The point of the code is to use abundance and significance data, generated separately using QIIME2, to build correlation 
networks between bacterial taxa in at the Genus and Phylum level. The changes in correlations are then computed over 
time to determine changes in bacterial relationships. For this analysis sequential time (year on year) and cyclical time
(season to season) are tracked. It is hoped that this analysis will help connect specific changes in environment with 
changes in microbial networks.

## Installation
All code should be run in a virtual environment, i.e. conda, with all libraries installed in that virtual environment.
The code requires two languages to run, R and Python 3. The main R packages needed are SpiecEasi, phyloseq, igraph and 
clustAnalytics. The main Python packages used are Pandas, igraph, tkinter and Pillow. All other dependencies are in 
requirements.txt

## User Guide

In order for this program to work, a folder called "data" must be placed into the root directory. Inside this folder the 
taxa abundance data should be in .xlsx files separated by taxonomical level. The significance data is a bit more 
complicated. Both seasons and consecutive years have their own folder with corresponding .json files containing the 
results of a thresholded log fold change analysis. All taxa in these files are considered significant.

Within the root directory the "src" folder and two files "main.R" and "main.py". The "src" folder contains all of the 
source code for the project. "main.R" contains the code to run the R files in "src" which handle all of the graphical 
analysis. "main.py" contains the code to run the Python files in "src" which load the data created by "main.R" and 
generate linear and cyclical time diagrams which are then saved in the "figs" folder in the root directory. If that 
folder does not already exist a new one will be created. "main.R" must be run before "main.py".

### Example Outputs
<img width="1000" height="1000" alt="lvl2_Winter_0" src="https://github.com/user-attachments/assets/01be15bc-595b-4bb4-b36c-fe2074b84eb7" />
The image above is an example of a Genus level correlations of taxa found in Bison fecal samples. Orange edges represent positive correlations whereas blue edges represent negative correlations. The width of an edge correlates to its relative weight.

<img width="3765" height="2830" alt="Genus Annual Changes" src="https://github.com/user-attachments/assets/ba6b4ffc-5155-4e82-8b05-549ccaea0da4" />
The image above is an example of the change in correlations from season to season. Time flows clockwise. Orange edges represent positive correlations whereas blue edges represent negative correlations. The width of an edge correlates to its relative weight.

<img width="3020" height="3020" alt="Genus Seasonal Changes Top 10" src="https://github.com/user-attachments/assets/8cbd1938-fd15-4356-bb16-261655f0ac53" />
The image above is an example of the change in correlations from year to year. Time flows from lower years (top) to higher years (bottom). Orange edges represent positive correlations whereas blue edges represent negative correlations. The width of an edge correlates to its relative weight.
















