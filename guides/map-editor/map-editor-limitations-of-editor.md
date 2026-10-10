# Limitations of editor

The old province-count limits based on fixed texture slots no longer apply: the current editor uses dynamic textures. A single province's bounding rectangle, including smoothing, is still limited to **2044x2044**.

You cannot load a map image larger than 4096x4096. I have set this limitation. This map size should be sufficient. Larger map images and provinces require more device memory (Can be changed in the source)

The overall 1,024-province limit is obsolete. The current exporter reserves buffers for 4,096 provinces, but the practical limit depends on memory and build resources. Test the finished map in the editor and game on the intended devices.
