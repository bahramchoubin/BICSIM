# BICSIM
BICSIM: Bias Correction using Similarity Matrix

Introduction:
This algorithm corrects Bias in daily TRMM precipitation data. Bias correction method in this study is included two steps: (i) construction of the similarity matrix/homogeneous condition based on the periodicity and different amount of precipitation for correcting Bias in gauged pixels, (ii) identification of the best donor pixel to each ungauged pixel based on the similarity (elevation, latitude, and longitude) for correcting Bias in ungauged pixels. 

Software required: 
Matlab R2016b or later.

Required data from GitHub:
	BICSIM Algorithm: Download BICSIM.p.
	Elevation data: Download the global elevation data (Elevation.nc4). 
	Sample station data: Download the sample excel file (StationsData.xlsx). 

Required data from user:
	Station (observation data): Provide your station data in an excel file with the name of “StationsData.xlsx”. See the sample excel file (StationsData.xlsx) in GitHub. Put name, X (longitude), and Y (latitude) of stations, respectively, in rows 1 to 3. In column 1 (row 4 to end) insert date. In other columns (row 4 to end) insert precipitation data. 
	Daily TRMM precipitation data (TRMM 3B42) as NetCDF (nc4) files: These data are available in the NASA website (https://pmm.nasa.gov/data-access/downloads/trmm). 

Run: 
1)	Put all required data in a local file in your computer. 
2)	Open Matlab and change the current directory (current folder) on the local file.
3)	Right click on BICSIM.p and select 'run'. 
4)	Response to following questions and click enter:
5)	Please enter the precipitation classes based on the percentiles: You should enter the desired precipitation class based on the “percentiles”. For example [5, 50, 100] means precipitation classes < 5, 5-50, > 50. Or [10:10:100] means classes < 10, 10-20, 20-30, …80-90, and 90-100. Or [5,10:10:90,95,100] means classes < 5, 5-10, 10-20, …80-90, 90-95, 95-100.
6)	Please select the Bias Correction method: You have two option. Enter 1 for the Mean Bias Remove (MBR) method, and 2 for the Multiplicative Ratio (MR) method.
7)	In the first opened windows please select the station data file “StationsData.xlsx” containing the information and precipitation of stations for your study area. More details described in the Required data section. 
8)	In the second opened windows please select all daily TRMM data files (as nc4). You can select all files using click on the first file, keeping down shift and click on the last file.
9)	In the third opened windows please select the “Elevation.nc4” file. 
10)	You can wait to finish the calculations. The running time depends on the number of stations and the area of the study. 


Results: 
	On the opened figure you can see the Bias before (TRMM) and after (Corrected TRMM) correction for all stations. If the results are not satisfied, please run again and change the precipitation classes (step 5 in the run section). Also, you can change the methods (step 6 in the run section). 
	Results of the Bias correction is saved within 3 excels in the Results folder (at your local folder in the computer). You can find the path of the Results folder through the current folder in Matlab, too, after that the running was completed (Current folder will be on the Results folder paths). 
	In the results folder, Performance.xls indicates Bias, MAE, and RMSE for before (TRMM) and after (Corrected TRMM) correction for all stations.
	In the results folder, PixelPrecipitation.xls indicates precipitation of TRMM and Corrected TRMM for all pixels of the study. Elevation, latitude, and longitude of the pixels are provided. 
	In the results folder, TRMM.xls indicates observations, TRMM, and corrected TRMM for the corresponding pixel of stations. 

For any information or bug report please email me:
Bahram Choubin
Email: Bahram.choubin@ut.ac.ir 
Bahram368@gmail.com 

Citation: 

