#Walkability Model 
\*
The model was created with the QGIS model builder tool. The model inputs consist of mandatory spatial data and optional weight-values for the data-derived variables of the model.  The area of interest –polygon is used to cut the other input data into more manageable size. This done so that the user doesn’t need to filter the data themselves. The grid/index unit data is used as the basic unit in which to the walkability score is calculated. Each of the other spatial data are joined to the index units based on location. The way how they are joined is based on the input data type: Point data is joined by “points in polygon” -method, line and polygon data is first intersected and then joined, and raster data is either polygonised and then joined, or summarized for each unit to calculate distinct land use classes.  

 

Multiple different variables are then derived from the data for each grid cell / unit: amenity density, heavy traffic area share, street network coverage (total length), intersection density, total floor area of residential buildings, average speed limit, distinct land use types, and park area share. These values are then rescaled to allow comparison. Some of variables are also divided by the unit area, this allows the use of an index unit data that is not uniform in area eg. Postal areas. Optional weights are then used to scale the final values of each input type. This allows weighting wanted characteristics like green areas or amenities and e.g., to increase the negative effects of heavy traffic or to disregard a variable all together. As a result, a walkability index layer is created. Its spatial coverage is determined by the features of the index unit layer (Preferably a uniform grid layer) that fall within the area if interest, thus it is recommended that all the other input datasets exceed the spatial coverage of the area of interest polygon. The index layer contains each of the variables that are summed up with weights as the walkability score, as well as a normalized walkability score that is rescaled between 0 and 10 based on the minimum and maximum values of the calculated walkability score.

*[mandatory]* 
\*


*Input data parameters needed for the model to work. Model can be used in any geographical location where these parameters are available. In Finland, the nation-wide coverage of the data should be quite good.* 
\*


- *Area of interest polygon <vector>* 
- *OSM - OSMNX python library* 
- *Amenities <vector>* 
- *OSM - OSMNX python library.* 
- *Buildings <vector>* 
- *National Land Survery of Finland (MML), Terrain Database (MTK)* 
- *NLSF’s QGIS WFS / OGC API service* 
- *Corine land cover <raster>* 
- *Finnish Environment Institute (SYKE). 20m.* 
- *Finnish Environment Institute official website* 
- *GRID <vector>* 
- *250m \* 250m* 
- *Speed limit <vector>*  
- *Digiroad’s QGIS WFS / OGC API service* 
- *Street network (edges) <vector>* 
- *OSM Graph - Python script* 
- *Source code in Githug* 
- *Street network (nodes) <vector>* 
- *OSM Graph - Python script* 
\*


*[optional]* 
\*


*Weight inputs can be used for weighting certain characteristics of the AOI. Analysis can e.g., favour green areas, or services/amenities, increase the negative effects of roads and high-speed traffic or completely exclude some variables e.g., land use or network classes.* 
\*


- *Amenity weight <float>* 
- *Range: 0-10* 
- *Value gets multiplied by this weight, increasing the cell’s overall walkability index. This class will also only affect the walkability index positively, never negatively. Value 0 excludes this class from the walkability index.* 
- *Building weight <float>* 
- *Range: 0-10* 
- *Value gets multiplied by this weight, increasing the cell’s overall walkability index. This class will also only affect the walkability index positively, never negatively. Value 0 excludes this class from the walkability index.* 
- *Heavy traffic weight <float>* 
- *Range: 0-10* 
- *Value gets reversed to minus, making the weight NEGATIVE. E.g., value 5 will increase the negative weight of this class multiplied by 5. This class will also only affect the walkability index negatively, never positively. Value 0 excludes this class from the walkability index.* 
- *Land use weight <float>* 
- *Range: 0-10* 
- *Value gets multiplied by this weight, increasing the cell’s overall walkability index. This class will also only affect the walkability index positively, never negatively. Value 0 excludes this class from the walkability index.* 
- *Network weight <float>* 
- *Range: 0-10* 
- *Value gets multiplied by this weight, increasing the cell’s overall walkability index. This class will also only affect the walkability index positively, never negatively. Value 0 excludes this class from the walkability index.* 
- *Park weight <float>* 
- *Range: 0-10* 
- *Value gets multiplied by this weight, increasing the cell’s overall walkability index. This class will also only affect the walkability index positively, never negatively. Value 0 excludes this class from the walkability index.* 
- *Speed limit weight <float>* 
- *Range: 0-10* 
- *Value gets reversed to minus, making the weight NEGATIVE. E.g., value 5 will increase the negative weight of this class multiplied by 5. This class will also only affect the walkability index negatively, never positively. Value 0 excludes this class from the walkability index.* 
\*


*Output:* 

- *Walkability index <raster>* 
- *Sum of all individual classes. Respects the optional weight inputs.* 
- *Yields a layer which should be used with base map. Layer symbology should then be configured using graduated classes for a proper visualisation.* 

