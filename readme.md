Codes in this folder are used to automatically generate ray-tracing simulation results. 
### Generate the user and satellite trajectory
1. Run 'Generate_user_and_GNSS_trajectory.m' and 'Generate_LEO_satellite_path.m' to generate the trajectories of user and satellites with time intervals = IMU Sampling rate

2. Run 'Add_atmos_refraction_effects.m' to generate apparent positions for satellites as a consequence of atmospheric refractions


### Simulation process
1. Configure `./Boston_SatCom/batch_file.bat` which specify the Wireless Insite directory

2. Run 'GeneratingFolderMult.m' to generate copies of original simulation folder 'Boston_SatCom' and update the .xml and .txrx files of the copied version

3. Run 'batchfile_RunAll.bat' to run wireless insite simulation and generate .txt files that contain channel parameters

   * .bat coding: [for loop using .bat](https://blog.csdn.net/Victor2code/article/details/103555832)

### Results & post processing
After the simulation, in every "./LEO_SatCom#_channel#" ("./GNSS_SatCom_channel#") there will be a folder "x3d", which includes all the `.p2m` files generated containing all the channel information. 

1. Then we just need to extract the channel information using the code 'process_to_datasets.m'