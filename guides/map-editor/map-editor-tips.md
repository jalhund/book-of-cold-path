# Tips for modifying sources

### Adjust provinces smoothing. 

The map editor automatically applies the distance field method to improve the quality of the provinces and avoid the staircase effect. If the provincial boundaries are too smooth, then you can change the value in the file libs/drawpixels/src/drawpixels.cpp  
Below is an example of changing the blur strength from 2 to 1. You can adjust this as you need. Search for the blur function \(search for "static uint8\_t \* blur"\) and find below:  
`int box = 2; // set 1 to have a 3x3 box`  
Change the value 2 to 1 \(was `int box = 2;`, change to `int box = 1;)`

### Defold lags when working with the map editor.

Solution: open the main/main.script file and change the line `IMAGE_DATA_PATH = ""` with, for example, disk D `IMAGE_DATA_PATH = "D:/"` The main thing is that a folder outside the project is specified. Also delete the image\_data and exported\_map files in your project folder \(save if you need them. This is the map image data and the exported map\)

After changing IMAGE\_DATA\_PATH, the map data will not be saved to the project folder, but to the specified path. Fewer files in the project folder - fewer files are processed by Defold

