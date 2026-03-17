# Clientes_Bicis_XLS

Análisis de perfiles y comportamiento de compra de clientes de una tienda de bicicletas.  
**Herramienta:** Microsoft Excel

---

## Objetivo

Identificar qué tipo de cliente compra una bicicleta en función de variables demográficas y socioeconómicas, y comunicar los hallazgos a través de un dashboard interactivo.

---

## Dataset

- **Fuente:** Dataset simulado de clientes de una tienda de bicicletas
- **Registros:** 1.026 clientes
- **Variables:** 13 columnas — demografía, ingresos, distancia al trabajo, región, número de coches y compra de bicicleta (Sí/No)

---

## Fases del proyecto

| Fase | Descripción |
|------|-------------|
| 1. Importación y exploración | Carga del CSV, creación del libro de trabajo, diccionario de datos |
| 2. Limpieza de datos | Eliminación de duplicados, renombrado de valores, segmentación por edad |
| 3. Análisis con tablas dinámicas | Cruces por género, edad, distancia, coches y región |
| 4. Dashboard | Visualización de insights con gráficos y segmentadores |

---

## Estructura del libro Excel

```
📊 Clientes_Bicis_XLS.xlsx
├── datos_crudos         → Dataset original sin modificar
├── hoja_trabajo         → Copia limpia sobre la que se trabaja
├── diccionario_datos    → Descripción de cada variable
├── tabla_género         → Pivot: compras por género
├── tabla_edad           → Pivot: compras por grupo de edad
├── tabla_millas         → Pivot: distancia al trabajo por edad
├── tabla_coches         → Pivot: número de coches
├── tabla_regiones       → Pivot: distribución geográfica
└── dashboard_insights   → Radiografía del cliente
```

---

## Principales hallazgos

- El comportamiento de compra es equilibrado tanto para hombres como mujeres, sin distinción.
- El grupo Adult Rider es nuestro motor de ventas. De cada 10 que entran, más de 5 compran.
Acción: Aquí es donde debemos invertir más en publicidad.
-  Para un joven, la bici puede ser su único medio de transporte (necesidad), necesidad = Publicidad ( Acción: Regalar el primer año de mantenimiento básico. Eso cierra la venta al instante porque les das seguridad)
- Los Senior que viven muy cerca prefieren caminar, y los que viven muy lejos probablemente no ven la bicicleta como una opción de transporte viable o cómoda por el esfuerzo físico. Acción: promocionar bicis eléctricas que eliminan el factor esfuerzo y permiten recorrer mayores distancias. 
- Aunque hay menos gente viviendo en Pacific (menor volumen), la probabilidad de que compren una bici es mayor que en Europe o North America.


