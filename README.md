Here are some R scripts I use to process airborne LiDAR data collected over tropical forests. They are mostly wrappers around LASTools functions, so you will need a license to use them (although some are free) http://lastools.org/. These scripts were based off those written by Tom Swinfield. 

You should work through 'Process_LiDAR_with_LASTools.R' line-by-line. The 'LASTools_functions.R' script just contains the functions and you shouldn't need to change them. 

Note: my approach saves quite a lot of intermediate data so that you can check it. I usually have a look at a few of the point clouds from each step to make sure they are OK, and then delete everything except the raw data and the rasters. 
