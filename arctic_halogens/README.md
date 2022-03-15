# WRF-Chem Arctic Halogen Case

## Case study of implementing surface and blowing snow sources of Arctic bromine activation

This is the case study of implementing and testing surface and blowing snow sources of Arctic bromine activation in WRF-Chem 4.1.1. This is described in more detail in Marelle et al. (2021b) - https://doi.org/10.1029/2020MS002391.

## Description of the model run
The model version used is an updated version of WRF-Chem 4.1.1 (Marelle et al., 2021a). The model domain is set up with 100 x 100 km horizontal resolution and 72 vertical levels up to a pressure of 50 hPa. The domain is centered on the North Pole with a North Polar Stereographic projection. The simulation period is between the dates of March 1, 2012 and April 31, 2012.

Meterological conditions from NCEP-FNL (National  Centers  for  Environmental  Prediction Final  Analysis; https://rda.ucar.edu/datasets/ds083.2/) was used to drive the WRF dynamics following extensive testing of boundary layer schemes and land-surface models. Sea ice and snow depth information was updated using data from ASR2 (Arctic System Reanalysis version 2; https://rda.ucar.edu/datasets/ds631.1/). 

New halogen developments are integrated into the SAPRC-99 gas-phase chemistry scheme, coupled with the MOSAIC-8bin sectional aerosol scheme (saprc99_mosaic_8bin_vbs2_aq_halogens). Initial and boundary conditions for aerosols and trace gases are from the Model for Ozone and Related chemical Tracers, version 4 (MOZART-4; https://www2.acom.ucar.edu/gcm/mozart-4). A modified mozbc input file is used specifically for this run (mozbc_saprc99_mosaic_halogens.inp).

## Steps for running:
1. Download and compile modified WRF-Chem code from Marelle et al. (2021a) - https://doi.org/10.5281/zenodo.4607934.
2. Run WPS using the namelist.wps.
3. Download ASR2 sea ice data from: https://rda.ucar.edu/datasets/ds631.1/
5. Run update_seaice_depth_and_snow.m to update the WRF met_em files with sea ice and snow depth information.
6. Follow the instructions in WRF-Chem-Preprocessors to run WRF-Chem preprocessors. NOTE: Use the mozbc_saprc99_mosaic_halogens.inp input file when running the mozbc preprocessor.
7. Use namelist.input to run WRF-Chem.

## References:
Modified WRF-Chem version:
Marelle, Louis, Thomas, Jennie L., Ahmed, Shaddy, Tuite, Katie, Stutz, Jochen, Dommergue, Aurelien, Simpson, William R., Frey, Markus M., & Baladima, Foteini. (2021a). lmarelle/WRF-halogens: WRF-Chem 4.1.1 version including polar bromine chemistry and emissions (v1.0). Zenodo. https://doi.org/10.5281/zenodo.4607934

Article:
Marelle, L., Thomas, J. L., Ahmed, S., Tuite, K., Stutz, J., Dommergue, A., et al. (2021b). Implementation and impacts of surface and blowing snow sources of Arctic bromine activation within WRF-Chem 4.1.1. Journal of Advances in Modeling Earth Systems, 13, e2020MS002391. https://doi.org/10.1029/2020MS002391
