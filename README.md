# S4OQ

## Notes

Basic approach is as follows: 

- Upscaling all textures by 2
- replacing all textures with high res versions as close as possible to originals
- export textures from packages via Swat editor as .dds files, but export from Photoshop as 32bit .tga files
- import into editor for an existing, or new package. Choose generate mipmaps. dxt1 for greatest compression, dxt3, or dxt5 for alpha channels
- Create shader for all textures, except UI elements, within texture browser, with File > New, name item "shader_itemname", click New, move new window to side and highlight texture in browser, select diffuse channel in new window and select Use then close window. When finished, save package as packagename.utx. 

### CrazyBump

- All Normal Map settings to zero
- Intensity: -30
- Shape Recognition: 30
- Medium Detail: 30
- Large Detail: 30
- Very Large Detail: 30
- Bump/Normal Map needs to be saved as 24bit .tga, convention is _norm as end of file name. 
- Within editor texture browser, File > import. Choose package to import into, choose DXT5-NORM compression. When asked if you want to set LODset value for your Normal map to LODSET_NormalMap, click Yes. 
- In texture browser choose a shader, right-click and select Properties. Put new window to side, select correct normal map in texture browser, return to new window, select NormalMap channel and select Use and close window.