---
layout: project-layout
title: "Temperature of the Baltic Sea"
subtitle: "animated using QGIS and ffmpeg"
thumbnail: "/assets/img/baltic-sea/banner.png"
description: "A detailed look at my second big build."
---

This animated map was made for the day 20 of the #30DayMapsChallenge , for the theme "water". 


### A quick explanation of the workflow

I first downloaded the Copernicus dataset "Baltic Sea Physics Reanalysis" ([https://doi.org/10.48670/moi-00013](https://doi.org/10.48670/moi-00013)). 

The dataset consists of multiple NetCDF files, for years 1993-2024. 
I used QGIS to explore the the NetCDF files and reprojected them to EPSG:3035. I used the Temperature (thetao) layer (band 01) for surface temperature. After deciding on a color ramp, I wrote a short python script to export as a png the same layer and band for each NetCDF file (one per year). 

The result: 
![Exported .png](/assets/img/baltic-sea/1994.png){: width="50%"}

I then styled another layer (natural earth data) to get the country outlines. Final styling was done using Affinity Designer 2, and a png file was created for each year. 

![Country outline](/assets/img/baltic-sea/overlay.png){: width="50%"}

Finally, using FFmpeg, I combined every frame into an animation. 

Result: 
<video width="50%" controls muted autoplay loop playsinline>
  <source src="{{ '/assets/img/baltic-sea/output.mp4' | relative_url }}" type="video/mp4">
</video>

