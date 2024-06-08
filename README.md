# incendiosMX v1
Un detector de incendios que lee actualizaciones de satélites multiespectrales y la plataforma de la Agencia Espacial Europea Copernicus

![Captura de pantalla 2024-06-06 a la(s) 6 47 37 p m](https://github.com/ArkVault/incendiosMX/assets/77123356/afe973b9-47fe-4013-a549-d05df8c26ffe)


2023 y 2024 consecutivamente han sido los años más calurosos de la historia del país y un reflejo de ello son los incendios en México han sido una maifestación más del cambio climático por causas antropogénicas, y las evidencias de ello están directaamente relacionadas con su cantidad, frecuencia y magnitud, que se salen de los patrones habituales de estos fenómenos en décadas anteriores.


Uno de los grandes problemas de mitigacion en los 4 meses seguidos de incendios forestales en el país es que ha sido muy difícil  estimar la cercanía del fuego a comunidades vulnerables antes de que sea tarde... 

La idea de trabajar en esto era mejorar un poco como anticiparse al curso deexpansión de losincendios, en lugar de imágenes ópticas que dificultan la apreciación,  este script aprovecha el infrarrojo de onda corta para separar el terreno sano y permite clasificar zonas incendiadas (amarillo) y zonas de fuego activo (rojo) y asi poder priorizar mejor como combatirlo. 

![Captura de pantalla 2024-06-05 a la(s) 8 40 04 p m](https://github.com/ArkVault/incendiosMX/assets/77123356/ae59b865-f281-410c-aff4-259fb2888008)

Para ejecutar este script es necesario utilizar Copernicus Browser y dirigirse a Visualize > Custom Script
Y alli ejecutar el script. Eligiendo previamente: Sentinel 2 > SL2-A > Most recent

Se puede implementar como un servicio WMS en plataformas como Arcgis, ejemplo: https://www.arcgis.com/apps/instant/basic/index.html?appid=65bb8774bd1847688622e15bbe53247c
