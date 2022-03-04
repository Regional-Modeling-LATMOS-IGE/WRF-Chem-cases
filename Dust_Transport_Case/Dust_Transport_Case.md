## Domain

### parent_grid_ratio = 1,3,3, 
    Grids are Arakawa C-staggered: mass points are at cell centers, u-velocities are at east-west cell edges, v-velocities are at north-south cell edges
    it is more computationally efficient and accurate to use a nesting ratio of 3 or 5
    We have tried 5 but did not work in our case
    
### i_parent_start & j_parent_start
    Mountain regions : nest boundaries should not be at mountain edges to avoid instabilities

## Physics

### mp_physics  = 10,  10,  10, or 2, 2, 2, 
    both options Morrisonet al., (2005) and Lin et al. (1983) are microphysical two-moment schemes

### slope_rad= 0,0,1 
Use only with high-resolution runs with grid size less than a few kilometers.
Slope effects, modifies surface solar radiation flux according to terrain slope.

### topo_shading = 0,0,1
Use only with high-resolution runs with grid size less than a few kilometers.
Allows for shadowing of neighboring grid cells

### topo_wind = 1
Topographic correction for surface winds to represent extra drag from sub-grid topography and enhanced flow at hill tops (Jimenez and Dudhia, JAMC 2012). Works with YSU PBL only.

## noah_mp 
### opt_snf = 2
Noah land surface model  + with enhanced Multi-Physics 
Important for snow cover areas 

## dynamics
### diff_6th_slopeopt =1
turns on 6th-order numerical diffusion - terrain-slope tapering
### w_damping   
vertical motion can be damped to prevent the model from becoming unstable with locally large vertical velocities. (for operational use)
### damp_opt                  
a layer of increased diffusion or an implicit gravity-wave damping can be added near the model top to control reflection from the upper boundary.
### epssm = 0.1,0.3,0.6,
time off-centering for vertical sound waves
