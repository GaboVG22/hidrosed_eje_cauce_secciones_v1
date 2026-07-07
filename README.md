# HidroSed · Módulo Eje Cauce y Secciones v1

Aplicación Streamlit independiente para construir y validar el eje hidráulico útil y las secciones transversales antes de integrarlo en HidroSed.

## Objetivo

Resolver tres etapas:

1. **Eje del cauce**
   - Ingreso obligatorio de eje en KMZ/KML.
   - Ingreso de PC hidrológico y PC cuenca soporte.
   - Definición del sentido aguas arriba → aguas abajo.
   - Definición de ribera izquierda y derecha mirando aguas abajo.
   - Recorte del eje útil entre PC hidrológico y PC cuenca soporte.
   - Perfil longitudinal DEM y perfil topográfico de respaldo opcional.

2. **Secciones del cauce**
   - Generación de secciones naturales desde DEM.
   - Generación de secciones trapeciales o rectangulares.
   - Carga de Excel de secciones prismáticas.
   - Carga de curvas de nivel de apoyo en KMZ/KML/DXF.
   - Evaluación de cobertura de curvas a ambos lados del eje.

3. **Eje + secciones en 3D**
   - Visualización 2D.
   - Visualización 3D referencial.
   - Exportación KMZ, Excel tipo HEC-RAS, perfil CSV y JSON técnico.

## Inputs obligatorios

- Eje del cauce: KMZ/KML con línea.
- PC hidrológico: KMZ/KML con punto.
- PC cuenca soporte: KMZ/KML con punto.

## Inputs opcionales

- DEM GeoTIFF: `.tif` o `.tiff`.
- Perfil longitudinal de respaldo: CSV, TXT, Excel, KMZ/KML o DXF.
- Curvas de nivel de apoyo: KMZ/KML/DXF.
- Excel de secciones prismáticas.

## Despliegue Streamlit Cloud

- Main file path: `app.py`
- Python version: `3.11`

## Dependencias

La app evita dependencias problemáticas para Streamlit Cloud como `pysheds`, `geopandas`, `scipy` y `earthengine-api`.

## Observaciones técnicas

- Los archivos DXF se asumen en coordenadas UTM WGS84 del sector de trabajo.
- Los KMZ/KML se leen en WGS84 lon/lat.
- La ribera izquierda y derecha se define mirando en sentido aguas arriba → aguas abajo.
- La plantilla Excel de secciones puede descargarse desde la app.
