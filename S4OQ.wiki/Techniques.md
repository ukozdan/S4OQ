## Exporting and editing textures/diffuse maps

- Download and install Nvidia's various tools 
  - GameWorks Tools Overview (https://developer.nvidia.com/gameworks-tools-overview)
    - all games related applications
  - NVIDIA Texture Tools for Adobe Photoshop (https://developer.nvidia.com/nvidia-texture-tools-adobe-photoshop)
    - specific Photoshop plug-ins. However, for me, under Windows 10 and Photoshop CC 2017, the bump map filter kept crashing Photoshop
  - Legacy Texture Tools (https://developer.nvidia.com/legacy-texture-tools)
    - some file viewers and importers, including DDS files
- export textures from packages via Swat editor texture browser as .dds files
  - not all files within a package are textures, some are bump/normal maps and shaders
- export completed textures from image editor (Photoshop, Gimp etc.) as 32bit .tga files

## Importing textures/diffuse maps

import into SwatEd editor for an existing package (i.e. replacing existing textures), or a new package (i.e. entirely new textures for new objects). 

- Choose "generate mipmaps". 
  - dxt1 for greatest compression
  - dxt3, or dxt5 for alpha channels
	
## Assigning textures/diffuse maps to shaders

Shaders determine reflection, absorbtion, translucency and glow. As mentioned previously, the texture/diffuse map alpha channel informs this. Create a shader for all textures, except UI elements. 

- Open SwatEd texture browser
- "File > New" 
- name item "shader_itemname"
- click "New"
- move new window to side 
- highlight texture in browser
- select "diffuse" channel in new window 
- select "Use" 
- close window 
- save package as "packagename.utx"

## Creating bump/normal maps with CrazyBump

As mentioned previously, the Nvidia Photoshop plug-in can provide the bump/normal maps, but were unusable for me in Windows 10 Photoshop CC 2017. 

- All Normal Map settings to zero
- Intensity: -30
- Shape Recognition: 30
- Medium Detail: 30
- Large Detail: 30
- Very Large Detail: 30
- Experiment with these values. The originals went bump crazy in places; ideally just pick out details that really need it. 
- Bump/Normal Map needs to be saved as 24bit .tga, convention is "_norm" as end of file name. 

## Importing bump/normal maps

Within the editor texture browser: 

- "File > import"
- Choose package to import into
- choose "DXT5-NORM" compression 
- When asked if you want to set "LODset value" for your Normal map to "LODSET_NormalMap", click "Yes"
  
## Assigning bump/normal maps to shaders
  
Within the editor texture browser: 

- choose a shader
- right-click and select "Properties"
- Put new window to side 
- select correct normal map in texture browser
- return to new window
- select "NormalMap" channel 
- select "Use" 
- close window 