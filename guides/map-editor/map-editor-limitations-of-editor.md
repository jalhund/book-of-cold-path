# Limitations of editor

Limit on the number and size of provinces:\
\<number of provinces> - \<maximum size>\
1024 - 124x124\
256 - 252x252\
64 - 508x508\
16 - 1020x1020\
4 - 2044x2044\
(124x124 instead of 128x128 due to the extrude borders set to 2. This is to prevent incorrect texture mapping. See the Common texture problems section on the engine forum)

Example: you can create a thousand very small provinces (less than 124x124), but you can create only 4 sizes 1500x1500 (for example)

You cannot load a map image larger than 4096x4096. I have set this limitation. This map size should be sufficient. The larger the size of the map image is supported, the more textures need to be prepared for this, therefore the higher the device requirements (Can be changed in the source)

The game cannot handle more than 1024 provinces. This is the limit
