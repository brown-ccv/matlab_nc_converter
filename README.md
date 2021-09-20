# Matlab Scripts to get Data for VolumeViewer

1. Connect to Oscar by logging in to a VNC node with 1 GPU. [See Oscar docs on connecting with VNC.](https://docs.ccv.brown.edu/oscar/connecting-to-oscar/vnc)
   
2. Start by running `/gpfs/runtime/opt/volumeviewer/1.0/bin/start_volumeviewer_2D`
   Data folder: `/users/dullman1/data/dullman1/EPSCOR`

3. Convert Data from OSOM nc files to RAW
    1. `cd /gpfs/runtime/opt/volumeviewer/1.0/share/OSOM`
    2. Launch Matlab from the applications menu
    3. Run `createVolumeViewerData`
        - Input
          - ```matlab
            %    OsomGridFile	nc-file containing the layout for the grid, e.g. osom_grid4_mindep_smlp_mod7.nc
            %
            %    OsomDataFile   nc file containing the data for the viewer, e.g. ocean_his_0365.nc
            %
            %    OutputFolder	Outputfolder in which the data is generated
            %                    
            %    dataDescriptor description of the data in the nc-file, e.g 'temp'
            ```
          - Example
            `createVolumeViewerData('OSOM/osom_grid4_mindep_smlp_mod7.nc','OSOM/ocean_his_0365.nc', 'dataOut', 'temp')`
    4. To add more information and visuals using labels, description, or a model do the following
       - Check the file `exampleOSOMDatafile.txt` in `/gpfs/runtime/opt/volumeviewer/1.0/share/data`
       - You can add the labels directly from the data as well as the other lines to your txt file of your output.
       - If you use the description and/or the mesh also copy the files to your data folder and adjust the paths.
