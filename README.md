# incendiosMX v1
This is an EvalScript for the Sentinel Hub service, designed for detecting burned areas and active fires using satellite imagery. The setup function defines the input and output configurations for the script. The inputs are spectral bands from Sentinel-2 (B02, B03, B04, B08, B11, B12) and a dataMask, which is often used to exclude areas with no data or clouds. The output is configured to have four bands: Red (R), Green (G), Blue (B), and Alpha (transparency). The evaluatePixel function computes two well-known spectral indices: the Normalized Difference Water Index (NDWI) and the Normalized Difference Vegetation Index (NDVI), both used for distinguishing water bodies and healthy vegetation.The script calculates a custom index that involves thermal bands (B11 and B12) and the near-infrared band (B08) to identify burned areas and active fires.

The script classify the terrain based on the calculated indices and band values. If the custom index value (INDEX) is high or certain band values indicate non-burned areas, a grayscale color is assigned. For burned areas where the custom index is low and thermal band B12 is high, a semi-transparent yellow color is returned.


References

Chuvieco, E., & Kasischke, E. S. (2007). Remote Sensing Information for Fire Management and Decision Support. In this study, the authors discuss the importance of using different spectral bands and indices for detecting and monitoring wildfires, providing insights into the selection of suitable bands like B11 and B12 for thermal detection.

Roy, D. P., et al. (2005). MODIS-derived fire characteristics and their relation to the biomass burning record. This research highlights the application of remote sensing indices like NDVI and thermal bands for identifying active fire regions, offering a framework relevant to the indices used in the provided code.

Wooster, M. J., Roberts, G., Perry, G. L. W., & Kaufman, Y. J. (2005). Retrieval of biomass combustion rates and efficiencies using ATSR active fire data. This paper demonstrates methods for leveraging satellite imagery to detect and analyze fire activity, particularly using thermal infrared bands similar to B11 and B12.

*Read more in Spanish below

Un detector de incendios que lee actualizaciones de satélites multiespectrales y la plataforma de la Agencia Espacial Europea Copernicus

![Captura de pantalla 2024-06-06 a la(s) 6 47 37 p m](https://github.com/ArkVault/incendiosMX/assets/77123356/afe973b9-47fe-4013-a549-d05df8c26ffe)


2023 y 2024 consecutivamente han sido los años más calurosos de la historia del país y un reflejo de ello son los incendios en México han sido una maifestación más del cambio climático por causas antropogénicas, y las evidencias de ello están directaamente relacionadas con su cantidad, frecuencia y magnitud, que se salen de los patrones habituales de estos fenómenos en décadas anteriores.


Uno de los grandes problemas de mitigacion en los 4 meses seguidos de incendios forestales en el país es que ha sido muy difícil  estimar la cercanía del fuego a comunidades vulnerables antes de que sea tarde... 

La idea de trabajar en esto era mejorar un poco como anticiparse al curso deexpansión de losincendios, en lugar de imágenes ópticas que dificultan la apreciación,  este script aprovecha el infrarrojo de onda corta para separar el terreno sano y permite clasificar zonas incendiadas (amarillo) y zonas de fuego activo (rojo) y asi poder priorizar mejor como combatirlo. 

![Captura de pantalla 2024-06-05 a la(s) 8 40 04 p m](https://github.com/ArkVault/incendiosMX/assets/77123356/ae59b865-f281-410c-aff4-259fb2888008)

Para ejecutar este script es necesario utilizar Copernicus Browser y dirigirse a Visualize > Custom Script
Y alli ejecutar el script. Eligiendo previamente: Sentinel 2 > SL2-A > Most recent

Se puede implementar como un servicio WMS en plataformas como Arcgis, ejemplo: https://www.arcgis.com/apps/instant/basic/index.html?appid=65bb8774bd1847688622e15bbe53247c
