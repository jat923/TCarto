# TCarto
TCarto is a simple, scalable, parallel code optimization for Table Cartograms written in Python.
This README demonstrates the data repository and data preparation guide.

#Dataset Description
We have build a rich database containing both Real-life and Synthetic Datasets of different grid sizes.

## Real-life Dataset
We examined the  `car' dataset, which is one of the commonly used dataset for infographic examples.
We also examined the Weather Research and Forecasting (WRF) model output for five weather parameters  Soil Moisture (SMOIS), Surface Skin Temperature (TSK), Planetary Boundary Layer  Height (PBLH), Soil Liquid Water (SH2O) and Surface Emissivity (EMISS). This geospatial dataset spans the western provinces of Canada. 

## Synthetic Dataset
We generated a synthetic dataset using the ELKI data mining frameworks, which is one of the widely used software for clustering and generating cluster datasets with user specified distribution. Our motivation for using  synthetic data was to examine data characteristics that may influence the cartographic accuracy of a table cartogram. Hence we found ELKI to be an excellent choice for generating synthetic data. We also used a benchmark `Shape' dataset to see whether table cartograms preserve various shapes. 

Our ELKI dataset contains two sets: (Set-I) varies the cluster number (2,4,8), and  (SET-II) varies the standard deviation $\sigma$ (0.25,0.5,0.75). The other input  parameters are chosen at random. For each group (e.g., 4 clusters in Set-I), we generate 10 instances. All the instances are two dimensional and the clusters have a Gaussian distribution in both dimensions.

There is an intuitive reason to  generate Set-I and Set-II. A sharp peak in a cluster seems to contribute to the corresponding cell a high value compared to its neighboring cells, requiring for a face of large area. Hence we believe both the number of clusters and the standard deviation of each cluster are capable of influencing the cartographic accuracy.

# Input Data Format:

TCarto takes one simple text file as input which contains the desired positive weights of the $m\times n$ table $T$ according to which the cells are transformed.
In each line of the text file, all the weights of the i th row are written and separated by commas.
One example of the data format of 4\times 4  is as follows:

1.4416243655,0.6091370558,0.4670050761,1.1776649746,   Weights of the cells of first row of the table
1.1370558376,0.4873096447,0.2233502538,1.4213197970,   Weights of the cells of second row of the table
0.7918781726,1.2182741117,0.4467005076,1.0964467005,   Weights of the cells of third row of the table
0.9543147208,2.3553299492,1.1573604061,0.9746192893    Weights of the cells of fourth row of the table
