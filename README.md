# code_CTSM_MCR

## Introduction

This repository is supplementary to the manuscript "Sun, Y., Xia, J., Lindley S., Oleson, K. W., Bannan, T. J., Topping D. O., Schultz D. M., Zheng, Z. (2025). Urban heat characteristics of Greater Manchester (UK) in the heatwave year of 2022".

The objective of this project area:

- Examine the urban modeling capacity of [CTSM]() with local climate zones at the kilometer scale;
- Characterize urban heat in Greater Manchester using multiple observations (i.e., [HadISD](https://dx.doi.org/10.5285/b82b58d085d0433b821f4ae31cb608de), [Whitworth](http://www.cas.manchester.ac.uk/), [Manchester Air Quality Supersite (MAQS)](https://catalogue.ceda.ac.uk/uuid/91625bdf73944c5e896eb56d1fec35ee/), [QuantAQ sensors](https://www.quant-aq.com/products/modulair)), gridded datasets (i.e., [HadGrid-UK](https://catalogue.ceda.ac.uk/uuid/b963ead70580451aa7455782224479d5/), [UKCP18-Local](https://catalogue.ceda.ac.uk/uuid/d5822183143c4011a2bb304ee7c0baf7/), [ERA5-Land](https://dx.doi.org/10.24381/cds.e2161bac)), and simulations;
- Provide robust climatic data for urban climate adaptation.

## Script and data

### [1_input_data_description](./1_input_data_description )

The scripts listed below are used to describe input data and plots.

| Num. | Subject                                                      | Data process                                                 | Visualization                                                |
| ---- | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| 1.1  | [Percentage of urban areas](./1_input_data_description/1.1_percent_of_urban_areas/ ) | Using [UK boundary](./shapefile/UK)                          | [Figure.ipynb](./1_input_data_description/1.1_percent_of_urban_areas/Figure.ipynb) |
| 1.2  | [Percentage of urban areas over landunits](./1_input_data_description/1.2_percent_of_urban_landunit/) | Using [UK boundary](./shapefile/UK)                          | [Figure.ipynb](./1_input_data_description/1.2_percent_of_urban_landunit/Figure.ipynb) |
| 1.3  | [Map of observations](./1_input_data_description/1.3_map_of_observations/) | Using [UK boundary](./shapefile/UK) and [sensor metadata](./1_input_data_description/1.3_map_of_observations/meta_data_final_for_analyse.csv) | [Figure.ipynb](./1_input_data_description/1.3_map_of_observations/Figure.ipynb) |
| 1.4  | [Comparison of atmospheric data](./1_input_data_description/1.4_comparison_of_atmospheric_data/) | Using [HadISD](./1_input_data_description/1.4_comparison_of_atmospheric_data/final_hadisd.csv), [Whitworth](./1_input_data_description/1.4_comparison_of_atmospheric_data/final_whitworth.csv), [MAQS](./1_input_data_description/1.4_comparison_of_atmospheric_data/final_supersite_merged.csv), [ERA5-Land](./1_input_data_description/1.4_comparison_of_atmospheric_data/era5_hourly.csv), [bias corrected ERA5-Land](./1_input_data_description/1.4_comparison_of_atmospheric_data/era5_corrected.csv), and UKCP18-Local ensemble mean data by [hour](./1_input_data_description/1.4_comparison_of_atmospheric_data/ensemble_hourly.csv), [month](/1_input_data_description/1.4_comparison_of_atmospheric_data/ensemble_monthly.csv), and [year](/1_input_data_description/1.4_comparison_of_atmospheric_data/ensemble_yearly.csv) | [Figure.ipynb](/1_input_data_description/1.4_comparison_of_atmospheric_data/Figure.ipynb) |
| 1.5  | [Comparison of sensor and MAQS data](./1_input_data_description/1.5_comparison_of_sensors/) | Comparing data of 3 sensors installed in MAQS and [MAQS](./1_input_data_description/1.4_comparison_of_atmospheric_data/final_supersite_merged.csv) data | [Figure.ipynb](./1_input_data_description/1.5_comparison_of_sensors/Figure.ipynb) |
| 1.6  | [Bias in sensor data](./1_input_data_description/1.6_bias_in_sensor_data/) | Use [Export.ipynb](./1_input_data_description/1.6_bias_in_sensor_data/Export.ipynb) to calculate the diurnal mean bias by month | [Figure.ipynb](./1_input_data_description/1.6_bias_in_sensor_data/Figure.ipynb) |
| 1.7  | [Bias-corrected sensor data](./1_input_data_description/1.7_bias_corrected_sensor_data/) | Use [adjust_sensor_data.ipynb](./1_input_data_description/1.7_bias_corrected_sensor_data/adjust_sensor_data.ipynb) to conduct bias correction | [Figure.ipynb](./1_input_data_description/1.7_bias_corrected_sensor_data/Figure.ipynb) |

### [2_simulation_output_analysis](./2_simulation_output_analysis)

The scripts listed below are used for processing simulation output and visualization.

| Num. | Subject                                                      | Simulation      | Output data process                                          | Visualization                                                |
| ---- | ------------------------------------------------------------ | --------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| 2.1  | [Model performance](./2_simulation_output_analysis/2.1_model_performance/) | CNTL_PT, LCZ_PT | Use [Export.ipynb](./2_simulation_output_analysis/2.1_model_performance/Export.ipynb) to get *.csv over sensors | [Figure.ipynb](./2_simulation_output_analysis/2.1_model_performance/Figure.ipynb) |
| 2.2  | [Mondel performance by seasons](./2_simulation_output_analysis/2.2_model_performance_by_seasons/) | CNTL_PT, LCZ_PT | Use [Export.ipynb](./2_simulation_output_analysis/2.2_model_performance_by_seasons/Export.ipynb) to get *.csv over sensors  by four seasons | [Figure.ipynb](./2_simulation_output_analysis/2.2_model_performance_by_seasons/Figure.ipynb) |
| 2.3  | [Urban heat map](./2_simulation_output_analysis/2.3_heat_map/) | CNTL_GM, LCZ_GM | Use [Export.ipynb](./2_simulation_output_analysis/2.3_heat_map/Export.ipynb) to get urban air temperature at [grid-cell](./2_simulation_output_analysis/2.3_heat_map/grid/) and [landunit](./2_simulation_output_analysis/2.3_heat_map/landunit/) level, respectively | [Figure.ipynb](./2_simulation_output_analysis/2.3_heat_map/Figure.ipynb) |
| 2.4  | [Urban heat stress](./2_simulation_output_analysis/2.4_heat_stress/) | CNTL_GM, LCZ_GM | Use [Export.ipynb](./2_simulation_output_analysis/2.4_heat_stress/) to get urban heat stress indices at [landunit](./2_simulation_output_analysis/2.4_heat_stress/landunit/) level | [Figure.ipynb](./2_simulation_output_analysis/2.4_heat_stress/Figure.ipynb) |
| 2.5  | [Principle_component_analysis](./2_simulation_output_analysis/2.5_principle_component_analysis/) | LCZ_GM          | Use [Census 2021](https://www.nomisweb.co.uk/sources/census_2021) and simulation data to conduct [PCA](./2_simulation_output_analysis/2.5_principle_component_analysis/step1_pca.ipynb) | [Figure.ipynb](./2_simulation_output_analysis/2.5_principle_component_analysis/Figure.ipynb) |
| 2.6  | [Correlation between PC1 and PC2](./2_simulation_output_analysis/2.6_correlation_between_PC1_and_PC2/) | LCZ_GM          | USe PC scores over Output Areas (OAs)                        | [Figure.ipynb](./2_simulation_output_analysis/2.6_correlation_between_PC1_and_PC2/Figure.ipynb) |
| 2.7  | [Urban heat vulnerability map](./2_simulation_output_analysis/2.7_heat_vulnerability_map/) | LCZ_GM          | Use [Export.ipynb](./2_simulation_output_analysis/2.7_heat_vulnerability_map/Export.ipynb) to get [road](./2_simulation_output_analysis/2.7_heat_vulnerability_map/road/) and [river](./2_simulation_output_analysis/2.7_heat_vulnerability_map/river/) shapefiles | [Figure.ipynb](./2_simulation_output_analysis/2.7_heat_vulnerability_map/Figure.ipynb) |

### [3_illustration](./3_illustration)

The figures listed below are used to illustrate the details of input data processing and HVI map.

| Subject                                | Visualization |
| -------------------------------------- | ------------- |
| Input data processing                  | [Figure]()    |
| Mapping land cover and building height | [Figure]()    |
| Urban heat vulnerability map           | [Figure]()    |

## Acknowledgments

- This work used the [ARCHER2 UK National Supercomputing Service](https://www.archer2.ac.uk) and [JASMIN, the UK’s collaborative data analysis environment](https://www.jasmin.ac.uk).
- The authors appreciate [Dr. Michael Flynn](https://research.manchester.ac.uk/en/persons/michael.flynn) for managing the Whitworth station data and providing information to understand the measurement.
- The authors also thank [Dr. Ettore Murabito](https://research.manchester.ac.uk/en/persons/ettore.murabito) for assisting with the sensor data access.
- [Zhonghua Zheng](https://github.com/zhonghua-zheng) appreciates the support provided by the academic start-up funds from the Department of Earth and Environmental Sciences at The University of Manchester.
- [Yuan Sun](https://github.com/YuanSun-UoM) is supported by the PhD studentship of Zhonghua Zheng's academic start-up funds.
- Contributions from [Keith W Oleson](https://staff.ucar.edu/users/oleson) are based upon work supported by the NSF National Center for Atmospheric Research, which is a major facility sponsored by the U.S. National Science Foundation under Cooperative Agreement No. 1852977.
- The authors declare no conflict of interest.