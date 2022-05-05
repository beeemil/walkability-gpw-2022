README: 
\*


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

