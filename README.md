# Random Forest Land Classification


# 1. Overview

Using ESA SNAP toolbox together with Sklearn and Jupyter notebook to perform land
classification over Finland. Random Forest algorithm with 20 trees has been utilized to perform the land classification. 

# 2. Sentinel-1A Product

![](Random-Forest-Images/study-area.png) 
_Study area_

![](Random-Forest-Images/latlong.png)   

![](Random-Forest-Images/S1AIW2imageVH.png)    
_S1A IW2 band before processing_

![](Random-Forest-Images/S1ACalibrated.png)   
_S1A product after radiometric calibration_

![](Random-Forest-Images/after-deburst-vh.jpg)  
_S1A VH band after TOPS deburst

![](Random-Forest-Images/multilooked-vh.jpg)
_S1A after multilooking_

![](Random-Forest-Images/s1aspecklefiltered.png)              
_S1A after speckle filtering using Refined Lee filter_

![](Random-Forest-Images/subset-terrain-corrected.png)
_Sentinel-1A product after terrain correction_

![](Random-Forest-Images/s1rgb.png)
_S1A RGB product_

# 3. Sentinel-2B product
![](Random-Forest-Images/s2rgb.png)
_S2B RGB product with B4 as red, B3 as green and B2 as blue_

![](Random-Forest-Images/s2b-bands.jpg)                         
_S2B bands_

# 4. Sentinel-1A and Sentinel-2B RGB Mix

![](Random-Forest-Images/s1s2mix.png)
_S2 B4 as red, S1 VH as green, S2 B2 as blue_

# 5. Corine2012 Product
Corine2012 product has been resampled from 100 m resolution to 20 m resolution to match
Sentinel-1 product and Sentinel-2 product resolution. 

![](Random-Forest-Images/corine12.png)
_Corine2012 product of the study area_

During Python processing Corine land classes have been converted to five major classes:
* Artificial surfaces
* Agricultural areas
* Forest and semirural areas
* Wetlands
* Water bodies


# 6. Collocation of Products

The collocated data has been converted into three separate CSV formatted data sets to be run on the random forest algorithm. Each CSV products has a total of 21,855,475 rows. Sentinel-1 product has three attributes as columns, red color, green color and blue color. Sentinel-2 product has 13 attributes in total corresponding to all of the Sentinel-2 bands. Sentinel-1 and Sentinel-2 RGB product has three attributes and Sentinel-1 VV+VH has two attributes.

# 7. Results

![](Random-Forest-Images/results-new.png)       
_Land class prediction accuracy results on test data with 20 trees_

## 7.1 Band Importances For Making Prediction

For Sentinel-1 RGB product land classification green color attribute is the most important for correct prediction followed by
red color attribute and blue color attribute being the least important. 

![](Random-Forest-Images/s1rgbvars.png)                
_Sentinel-1 RGB attributes relative importance for correctly predicting land class.
B1 = red, B2 = green, B3 = blue_

![](Random-Forest-Images/s1s2rgbvars.png)                      
_S1 and S2 RGB product attribute importances,
in figure B1 = sentinel-2 B4, B2 = Sentinel-1 VH, B3 = Sentinel-2 B2_

![](Random-Forest-Images/s2bandsvars.png)      
_Sentinel-2 bands relative importance for correctly predicting land class_

## 7.2 Confusion Matrices

![](Random-Forest-Images/s1basicconfusion.png)      
_Sentinel-1 VV and VH sigma0 confusion matrix_

![](Random-Forest-Images/s1rgbconfusion.png)      
_Sentinel-1 RGB dual pol ratio sigma0 VV+VH confusion matrix_

![](Random-Forest-Images/s1s2confusion-new.png)      
_Sentinel-1 and Sentinel-2 RGB mix confusion matrix_

![](Random-Forest-Images/s2confusion-new-new.png)      
_Sentinel-2 confusion matrix_
