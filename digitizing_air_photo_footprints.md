# Instructions & Methods for Digitizing Air Photo Footprints

## Getting Started:
### Start with the Issues Tracker
1. In the Issues section of the Air Photo Index project GitHub page, you should find an Issue for each photo set (identified by the call number).  All photo sets in need of digitizing have an issue open on the github repository.  The issues are closed for photo set as they are finished.  Photo sets are given labels to indicate their status.  Open issues labeled as "In Progress" are currently being digitized by a contributor.  Choose a photo set to work on that does not have an "In Progress" label.  
2. Write a comment for your chosen photoset that you are working on the boundary.  Michele will Add the "In Progress" label to the Issue for the set you've chosen to work on.  (Depending on your permissions, you may be able to add the label yourself.)  
3. Add additional comments if any issues or questions arise about this particular photo set.  The issues section is a great place to track problems and solutions as the arrise.


## Download Relevant Topo Maps
*Note* Google Chrome browswer has occasionally had difficulties downloading files from topoView, resulting in an error message saying "Failed - Network error".  If this happens, try another browswer.  Microsoft Edge has worked well in the past for Windows users.
1. Go to the USGS National Geologic Map Database’s topoView: https://ngmdb.usgs.gov/maps/TopoView/viewer 
2. On the right side of the map in the side panel you have the option to select the scale.  For this project, you may find different map scales work better for different photosets.
3.	Zoom into the general region of the photo sest, and the names of the maps will appear inside the index bounding boxes.  Alternatively you can search for the name of a map with the Map Name search at the top of the side panel if you know it's official name.
4. Select the map of interest by clicking on the map.
5. In the lower section of the side panel, a dialog box should appear with details about the map you selected and the maps that are available.  Choose an option or options that seem relevant to the photo set at hand.  For example, if your photo set was taken in 1950, a map from a similar time period could be helpful.  
7. Click the GEOTIFF download option for the map you would like to download.
8. Save the file to your local computer.  The file saved will be a zipped folder containing GeoTIFF files.
9. Navigate to the folder where you saved the file.  Right click the file and select “Extract All”.  Browse to the folder you would like to unzip the folder to, then click the “Extract” button.  The new unzipped folder should contain 4 files.

Further assistance in interpreting which scale of map to use can be found in the [USGS' Map Scales Report](https://pubs.usgs.gov/fs/2002/0015/report.pdf).

## Other Potential Sources of Imagery
1. The Quick Map Services PlugIn for QGIS can provide current aerial imagery for reference.  Adding the contributed resources (in the settings) adds many more options.
1. [USGS Earth Explorer](https://earthexplorer.usgs.gov/)
1. [USGS National Map Viewer](https://viewer.nationalmap.gov)


 
## Get the most recent project files from GitHub 
We’ll describe how to do this with the GitHub for Desktop tool, but you may use the tool of your choice.  We’ll also assume you’ve already set up your GitHub account and the GitHub for Desktop program.:
1.	Fork the air-photo-index repository: https://github.com/UCDavisLibrary/air-photo-index Details about how to fork a repository and work with it in GitHub Desktop are here: https://guides.github.com/activities/forking/ 
2.	Open GitHub for Desktop
3.	Select the forked air-photo-index repository on the left sides of the window.
4.	In your computer’s file navigation system, navigate to your GitHub folder and open the air-photo-index folder.  You should have a folder called "indexes" which will contain completed indexes of map sets and an AirPhotoIndex_Template.geojson file.

Once you've set up your fork, you'll need to update it regularly to make sure you have all the current files.  There is unfortunately no way to do this with the GitHub Desktop tool, but it's not too complicated to update it.
1. Open GitHub Desktop
1. Click on your fork to open it.
1. Right click on the name of the fork and select "Open Command Prompt" or "Open in Git Shell" (depending on the version you have the text will be different).  A command line shell will open.  The path before the > should be where you store your data (probably the GitHub folder on your computer).
1. You will now run a few commands to update your fork ([reference](https://gist.github.com/CristinaSolana/1885435)).
    1. The first time you'll need to set an upstream repository for your fork:
    ```
        git remote add upstream git://github.com/UCDavisLibrary/air-photo-index.git
    ```
        
    2. Now you'll fetch any changes:
    ```
        git fetch upstream
    ```
    
    3. Finally, you'll update your folder with the changes you just fetched:
    ```
        git pull upstream master
    ```


## Digitizing
### Set Up Your Project File:
1.  In your file browser, COPY the template.geojson file into the indexes folder.  Change the name to the call number (without spaces or punctuation) of the index you are working on.
1.	Open QGIS
1.	Load data:
    * Your photo set geojson file - the file you will edit
    * Relevant topop maps
1.	Set Project Projection
    * Open the Project Properties (Project menu → Project Properties)
    * Set the Coordinate Reference System to California Albers (EPSG:3310)


### Digitizing the Boundary:

1.	Toggle Editing on for the new photo set GeoJSON file.
2.	Add new polygon with the Add Feature tool. Digitize the boundary adding vertices (one for each corner of the photo).  You can switch between the Add Feature tool and navigating tools as needed.  Right click to finish.  
3.  Finally, delete the rectangle template.
4.	Some things to keep in mind:
    * Note that as you near the edge of a map, you may need to turn off or reorder some of the maps to adjust for the white edges of the scanned maps that obscure the maps underneath.
    * Natural features such as river banks my have shifted over time and may not be in the precisely the same location as the air photo shows.  Do your best to reconcile these differences - the point of this file is to provide a guide to the photo locations and cannot be 100% accurate. 
5.	When you are done digitizing, fill out the attribute data based on the information provided on the photo itself or the UC Davis Library catalog record.
6.	Save Layer Edits.
7.	Toggle Editing off.
8.	Close QGIS if you’re done making new polygons, or start over from Step 2 above to make another.


## Submit your changes to the GitHub Repository
1.	In GitHub for Desktop, you should see a list of changes you’ve made to the files.  Fill in the Summary and Description fields at the bottom of the window and then click the Commit button.  https://guides.github.com/activities/forking/#making-changes 
2.	If you are ready to incorporate your changes into the main branch, submit a pull request for your fork: https://help.github.com/articles/creating-a-pull-request-from-a-fork/ 
3.  If your changes are accepted, project adminsitrators will incorporated your changes and close the issue for your photo set.  If there is any problems or questions, the project administrators will contact you.

## Notes for pull request reviewers:
If you want to accept only some of the changes offered in a pull request, you will need to use the command line to [cherry-pick](https://mattstauffer.co/blog/how-to-merge-only-specific-commits-from-a-pull-request) the committs that you want to keep.

## Additional Reference Material:
1.	QGIS editing geometry manual: http://docs.qgis.org/2.14/en/docs/user_manual/working_with_vector/editing_geometry_attributes.html 
2.	Understanding the GitHub Flow: https://guides.github.com/introduction/flow/
3.	USGS Topographic Map Symbols: https://pubs.usgs.gov/gip/TopographicMapSymbols/topomapsymbols.pdf 



