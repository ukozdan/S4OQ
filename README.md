# S4OQ

## Basic approach

- Upscaling all textures by 2
- replacing all textures with high res versions as close as possible to originals. Yes, even the Shoalin Cyborgs Vs Ninja Pirates VII poster!
- If deviating from original then honour the colour, saturation, brightness and general feel
- virtually nothing in S4TSS is clean and new, so some dirt and wear is required
- Be aware and preserve original alpha channel; it appears to be used for opacity, reflection, highlights and illumination. If the texture changes then the alpha channel may need changing too. 

### SwatEd/Photoshop

- export textures from packages via Swat editor texture browser as .dds files, but export from Photoshop as 32bit .tga files
- import into editor for an existing, or new package. 
  - Choose "generate mipmaps". 
    - dxt1 for greatest compression, 
	- dxt3, or dxt5 for alpha channels
- Create shader for all textures, except UI elements, 
  - within texture browser, with "File > New", 
  - name item "shader_itemname", 
  - click "New", 
  - move new window to side 
  - and highlight texture in browser, 
  - select "diffuse" channel in new window 
  - and select "Use" 
  - then close window. 
  - When finished, save package as "packagename.utx". 

### CrazyBump

Nvidia provides tools for photoshop and textures (https://developer.nvidia.com/gameworks-tools-overview), but under Windows 10 and Photoshop CC 2017 the bump map filter plug-in crashed Photoshop. 

- All Normal Map settings to zero
- Intensity: -30
- Shape Recognition: 30
- Medium Detail: 30
- Large Detail: 30
- Very Large Detail: 30
- Experiment with these values. The originals went bump crazy in places; ideally just pick out details that really need it. 
- Bump/Normal Map needs to be saved as 24bit .tga, convention is "_norm" as end of file name. 

### SwatEd

- Within editor texture browser, 
  - "File > import". 
  - Choose package to import into, 
  - choose "DXT5-NORM" compression. 
  - When asked if you want to set "LODset value" for your Normal map to "LODSET_NormalMap", click "Yes". 
- In texture browser 
  - choose a shader, 
  - right-click and select "Properties". 
  - Put new window to side, 
  - select correct normal map in texture browser, 
  - return to new window, 
  - select "NormalMap" channel 
  - and select "Use" 
  - and close window.