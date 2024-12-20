# git_cod_stability

This repository contains three folders: data, script, and output, to reproduce all the results of the paper 'Tracking changes in stability of North Sea Atlantic cod in 40 years'. 

a. The data folder contains two files:

1. [mc_NorthSea_CPUE per age per subarea_19772021.csv] file, which is fish abundance time series data downloaded from ices data portal <https://datras.ices.dk/Data_products/Download/Download_Data_public.aspx>

2. [fishing_mortality_ices_report_2020.xlsx] file, which is compiled from the 2020 ICES report https://ices-library.figshare.com/articles/_/18620651


b. The script folder contains five R scripts:

1. [Demo_MDR_function.R] 
This script is from Chang et al. 2021 https://onlinelibrary.wiley.com/doi/10.1111/ele.13897. It provides functions to run MDR-Smap. We modified two places in this script to fit our data.

2. [Demo_MDR_Smap_20210625.R] 
This script is from Chang et al. 2021 https://onlinelibrary.wiley.com/doi/10.1111/ele.13897. This script provides demonstration on running the functions in [Demo_MDR_function.R]. 
  
   To reproduce the results of this paper, run the following three scripts subsequently: 

1. [mc_nonlinearity.qmd] prepares the data and checks nonlinearity of the data.

2. [mc_mdr_smap.Rmd] identifies optimal embedding dimension of age groups, and run MDR S-map to obtain the jacobian matrices of the population. 

3. [mc_stability_analysis.Rmd] derives population stability and sensitivity of age groups from the jacobian matrices, and plots all the graphs in the manuscript.


c. The output folder contains the outputs from each step of MDR S-map, when running [mc_mdr_smap.Rmd]. 

Running [mc_mdr_smap.Rmd] takes about one hour. To check the reproducibility of the results, one can also skip [mc_mdr_smap.Rmd] and use the jacobian matrix [jcof_1809.csv] in the output folder to run [mc_stability_analysis.Rmd].


Note: use rEDM package version 1.2.3 for reproducibility; other versions may generate different results.


