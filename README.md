# Centinela_propuesta1
# Centinela del Café Risaralda

Alerta temprana de roya del cafeto combinando fotos de hojas y datos de clima.

**Autor:** Tomás Rendón Bustamante - Juan Sebastián Gamba Aguirre 
**Programa:** Maestría en Ciencia de Datos, Universidad Santo Tomás
**Curso:** Profundización I: Redes Neuronales — Deep Learning
**Actividad:** Proyecto Centinela, Fase 1 (Módulo 1): línea base con un Perceptrón Multicapa (MLP)

## ¿De qué trata?

La roya (*Hemileia vastatrix*) es una de las enfermedades que más afecta al café. Este proyecto busca construir, por etapas, un sistema que avise a tiempo al pequeño caficultor del municipio de Santuario, Risaralda, y a su técnico cuando una hoja parece enferma.

- **Fase 1 (esta):** un MLP que clasifica una hoja como sana o enferma a partir de características tabulares de color y textura extraídas de la foto.
- **Fase 2:** el sistema pasa a ser multimodal: una red convolucional (imagen) y una red recurrente (serie de clima) se fusionan.
- **Fase 3:** industrialización y despliegue.

## Estado actual

- [x] Propuesta de Datos redactada
- [x] Datos de clima descargados y revisados
- [ ] Aprobación de la propuesta por el docente
- [ ] Descarga de RoCoLe y análisis exploratorio
- [ ] Notebook del MLP, informe técnico-ético y bitácora de IA

## Fuentes de datos

### Fuente 1 (imagen): RoCoLe

- **Qué es:** 1.560 fotos de hojas de café robusta (390 plantas, 4 imágenes por planta), con anotaciones de estado (sana/enferma) y severidad.
- **Enlace:** https://doi.org/10.17632/c5yvn32dzg.2
- **Licencia:** CC BY 4.0
- **Cita (APA 7):** Parraga-Alava, J., Cusme, K., Loor, A., & Santander, E. (2019). *RoCoLe: A robusta coffee leaf images dataset* (Version 2) [Data set]. Mendeley Data. https://doi.org/10.17632/c5yvn32dzg.2
- **Importante:** las imágenes **no están en este repositorio**. Deben descargarse desde el enlace oficial de Mendeley Data.

### Fuente 2 (serie temporal): NASA POWER

- **Qué es:** datos diarios de clima por punto geográfico.
- **Enlace:** https://power.larc.nasa.gov
- **Variables:** temperatura a 2 m (`T2M`, °C), humedad relativa a 2 m (`RH2M`, %) y precipitación corregida (`PRECTOTCORR`, mm/día).
- **Periodo:** 1 de enero de 2015 a 31 de diciembre de 2025 (4.018 días por sitio, sin datos faltantes).
- **Puntos consultados:**
  - Risaralda (aprox. 5,07° N, 75,97° O)
  - Sitio de captura de RoCoLe en Ecuador (−0,834, −80,177)
- **Consulta:** octubre de 2026.
- **Reconocimiento solicitado por NASA:** *The data was obtained from the National Aeronautics and Space Administration (NASA) Langley Research Center (LaRC) Prediction of Worldwide Energy Resource (POWER) Project funded through the NASA Earth Science/Applied Science Program.*
- **Cita (APA 7):** NASA Langley Research Center. (s. f.). *NASA POWER: Prediction Of Worldwide Energy Resources* [Data set]. NASA. https://power.larc.nasa.gov

## Archivos de este repositorio

| Archivo | Contenido |
|---|---|
| `README.md` | Este documento |
| `Propuesta_de_Datos.pdf` | Propuesta de Datos de 1 página |
| `nasa_power_risaralda.csv` | Clima diario de Risaralda, 2015–2025 |
| `nasa_power_manabi.csv` | Clima diario del sitio de RoCoLe, 2015–2025 |

Los CSV tienen una fila por día y tres columnas: `T2M`, `RH2M` y `PRECTOTCORR`.

## Resumen de los datos de clima

| Sitio | Temperatura media | Humedad relativa media | Lluvia media |
|---|---|---|---|
| Risaralda | 21,8 °C | 89,2 % | 8,0 mm/día |
| Sitio de RoCoLe (Ecuador) | 26,7 °C | 71,3 % | 3,4 mm/día |

## Limitaciones declaradas

- RoCoLe es café **robusta de Ecuador**, no arábica de Risaralda: hay sesgo de dominio y el modelo puede fallar en cafetales de Santuario.
- El clima de los dos sitios es distinto (ver tabla anterior).
- La alineación entre foto y clima en la Fase 2 será **agregada por sitio y periodo**, no foto a foto, porque una foto no tiene su propio registro climático.
- Es una herramienta de apoyo: **no reemplaza** al técnico ni da un diagnóstico.

## Protección de datos

- Las imágenes son de hojas de café; no contienen datos personales.
- Si en fases posteriores se usan fotos de fincas reales, se pedirá consentimiento informado, se explicará la finalidad y la ubicación se reportará solo a nivel de municipio (Ley 1581 de 2012).
- No se usan datos de Kaggle ni de réplicas: solo fuentes originales con su licencia y cita.

## Uso de inteligencia artificial

Se usó una herramienta de IA generativa como apoyo para elegir fuentes. Cada interacción relevante se registra en la **Bitácora de IA**, indicando qué se aceptó, qué se modificó y qué se rechazó, con su justificación.
