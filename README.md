# incendiosMX v1
Un detector de incendios que lee actualizaciones de satélites multiespectrales y la plataforma de la Agencia Espacial Europea Copernicus

![Captura de pantalla 2024-06-06 a la(s) 6 47 37 p m](https://github.com/ArkVault/incendiosMX/assets/77123356/afe973b9-47fe-4013-a549-d05df8c26ffe)




2023 y 2024 consecutivamente han sido los años más calurosos de la historia del país y un reflejo de ello son los incendios en México han sido una maifestación más del cambio climático por causas antropogénicas, y las evidencias de ello están directaamente relacionadas con su cantidad, frecuencia y magnitud, que se salen de los patrones habituales de estos fenómenos en décadas anteriores.


A pesar de que se han utilizados imágenes satelitaes covencionales, estas al mostrar el rango de la luz visibl,e no permiten distinguir con claridad las áreas afectadas en su verdadera dimensión. Es por ello que desarrollé este código que aprovecha los sensores infrarrojos de los satélites para delimitar mejor las áreas ya incendiadas y las que estan bajo fuego activo, lo cual permitirá analizar la posible dirección de los mismos y  estimar las afectaciones con mayor precisión.

![Captura de pantalla 2024-06-05 a la(s) 8 40 04 p m](https://github.com/ArkVault/incendiosMX/assets/77123356/ae59b865-f281-410c-aff4-259fb2888008)

Para ejecutar este script es necesario utilizar Copernicus Browser y dirigirse a Visualize > Custom Script
Y alli ejecutar el script. Eligiendo previamente: Sentinel 2 > SL2-A > Most recent

Se puede implementar como un servicio WMS en plataformas como Arcgis, ejemplo: https://www.arcgis.com/apps/instant/basic/index.html?appid=65bb8774bd1847688622e15bbe53247c
