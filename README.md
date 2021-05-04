Here are some R scripts I use to process airborne LiDAR data collected over tropical forests. The processing steps are:
1. Re-sample las or laz data to a fixed grid size (default 250m) laz tiles
2. Create pulse density rasters for each tile and merge (geotiffs)
3. Thin point cloud to highest points only and create digital surface model (DSM) rasters and merge
4. Label ground returns in point cloud (save duplicate) and create digital terrain model (DTM)
5. Create approximate canopy height model (CHM=DSM-DTM) and plot a histogram of canopy heights
6. Using the histogram select height levels to create intermediate canopy height models which will be merged in to a pitfree CHM
7. Subtract local ground height from canopy height in the point cloud, giving CHM laz files
8. Run the pitfree CHM function (slow) which creates rasters for each tile and each height step and merges to give final CHM

They are mostly wrappers around LASTools functions, so you will need a license to use them (although some are free) http://lastools.org/. These scripts were based off those written by Tom Swinfield. 

You should work through 'Process_LiDAR_with_LASTools.R' line-by-line. The 'LASTools_functions.R' script just contains the functions and you shouldn't need to change them. 

Note: my approach saves quite a lot of intermediate data so that you can check it. I usually have a look at a few of the point clouds from each step to make sure they are OK, and then delete everything except the raw data and the rasters. 
