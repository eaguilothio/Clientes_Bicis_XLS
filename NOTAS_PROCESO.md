# NOTAS_PROCESO — Clientes_Bicis_XLS

Registro técnico del proceso completo. Útil para replicar el proyecto o como referencia futura.

---

## Fase 1: Importar y explorar los datos

1. **Importar el CSV:** `Datos → Desde texto → selecciona el archivo → Importar`
   - Tipo: Delimitado, fila 1 como encabezado
   - Origen: Unicode 65001 (evita errores con tildes y caracteres especiales)
   - Separador: coma
   - Formato de columnas: Texto para IDs y fechas, General para el resto
   - Situar en nueva hoja

   > Si hay pocos errores de caracteres puntuales, se pueden corregir con `Ctrl+B` (buscar y reemplazar).

2. **Estructura del libro:** El libro debe tener dos hojas iniciales diferenciadas:
   - `datos_crudos` — datos originales, nunca se modifican
   - `hoja_trabajo` — copia de trabajo sobre la que se opera siempre

3. **Convertir a tabla:** `Ctrl+E` para seleccionar todo → `Ctrl+T` para convertir a tabla.
   Cambiar el diseño en `Pestaña Diseño → Estilos de tabla`.

4. **Ver tamaño del dataset:** 
   - Para conocer cuántos registros (filas): seleccionar una columna cualquiera completa y restar -1 (cabecera) y ver el recuento en la barra inferior de Excel. 
   - Para conocer cuántas variables ( columnas): tenemos: con `Ctrl+Shift+►`.

5. **Diccionario de datos:** Crear una hoja adicional describiendo cada columna: nombre, tipo de dato y descripción.

---

## Fase 2: Limpiar los datos

6. **Eliminar duplicados:** `Datos → Quitar duplicados`. Excel indica cuántas filas se han eliminado.

7. **Renombrar valores poco intuitivos:** Para columnas con valores abreviados (como M/S):
   - Seleccionar la columna
   - `Inicio → Buscar y seleccionar → Reemplazar`
   - Buscar: M → Reemplazar con: Married
   - Buscar: S → Reemplazar con: Single
   - Aplicar `Reemplazar todos`

   Hacer lo mismo para la columna de género (M/F → Male/Female).

8. **Segmentar por edad (Age Brackets):** Crear una nueva columna al lado de Age llamada Age Brackets. Usar la siguiente fórmula en español:

   =SI(L2<18,"Junior",SI(L2<36,"Young Rider",SI(L2<51,"Adult Rider","Senior Rider")))

   Si Excel está en inglés, usar IF en lugar de SI. El error #NOMBRE? indica que la función no se reconoce en el idioma del sistema.

   Lógica de los rangos — justificación de negocio:

   Junior (< 18): Sin ingresos propios. La decisión de compra la toman los padres. Interés en BMX y mountain bikes pequeñas.
   Young Rider (18–35): Mayor tasa de compra. Ingresos propios, activos físicamente. Usan la bici para deporte y movilidad urbana. Valoran rendimiento y diseño.
   Adult Rider (36–50): Mayor poder adquisitivo. Priorizan calidad, comodidad y marcas reconocidas sobre el precio.
   Senior Rider (51+): Interés creciente en bicicletas eléctricas. Priorizan ergonomía, manillar alto y sillín cómodo.

   La fórmula no necesita repetir los rangos inferiores en cada condición. Si un cliente pasa el primer SI, Excel ya descarta que sea Junior y continúa evaluando.

---

## Fase 3: Tablas dinámicas y estadísticas

9. **Crear tabla dinámica:** Seleccionar la tabla (Ctrl+E) → Insertar → Tabla dinámica en nueva hoja. Renombrar la hoja con el nombre del análisis.

   Las 4 áreas de una tabla dinámica:
   - Filas: variable a analizar (ej. Age Bracket, Gender)
   - Columnas: variable de comparación (ej. Purchased Bike → Yes/No en paralelo)
   - Valores: métrica a medir (ej. promedio de ingresos, conteo de clientes)
   - Filtros: variables de segmentación global (ej. Region, Marital Status)

10. **Tablas creadas en este proyecto:**
    - Compras por género
    - Compras por grupo de edad
    - Distancia al trabajo por grupo de edad
    - Número de coches
    - Distribución por región

---

## Fase 4: Dashboard

11. **Configuración visual:** Nueva hoja dashboard_insights.
    - Fondo blanco para mayor claridad de los gráficos
    - Insertar gráficos desde cada tabla dinámica (copiar el gráfico y pegar en la hoja dashboard)


