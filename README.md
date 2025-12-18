# Relación entre ingresos regionales y vehículos en circulación en Chile (2022)

## Pregunta analítica
¿Existe una relación entre el ingreso promedio regional y la cantidad de vehículos en circulación en Chile en 2022?

El objetivo del análisis es identificar si las regiones con mayores niveles de ingreso presentan también una mayor concentración de vehículos en circulación, utilizando datos públicos oficiales y un enfoque exploratorio.

---

## Fuentes de datos

- **Encuesta CASEN 2022**
  - Fuente: Ministerio de Desarrollo Social y Familia
  - Link: https://bidat.gob.cl/details/ficha/dataset/1efce22b-d7cb-4f3b-931e-e882fce2a02c
  - Variables utilizadas:
    - `ytoth`: Ingreso total del hogar
    - `region`: Región
    - `nse`: Nivel socioeconómico
   

- **Permisos de circulación 2022**
  - Fuente: Instituto Nacional de Estadísticas (INE)
  - Tabla: `TBL_VehículosConMotor`
  - Link: https://www.ine.gob.cl/estadisticas/economia/transporte-y-comunicaciones/permiso-de-circulacion?utm_source=chatgpt.com
  - Variables utilizadas:
    - Bencinero, Diésel, Gas, Eléctrico, Otro
    - Glosa Región
    - Año

---

## Preparación e integración de datos

### CASEN 2022
- Se utilizó el ingreso total del hogar (`ytoth`) como indicador de nivel de ingreso.
- Se calculó el ingreso promedio del hogar por región utilizando promedio, evitando sesgos por tamaño poblacional.
- La variable `nse` se incorporó como segmentador para análisis exploratorio.
- Los datos se agregaron a nivel regional.

### Permisos de circulación
- Se filtró la base al año 2022 para asegurar consistencia temporal.
- Se construyó una medida de total de vehículos como la suma de vehículos por tipo de combustible.
- Los datos comunales se agregaron a nivel regional.
- No se utilizaron variables catalítico/no catalítico para evitar duplicidades.

### Integración
- Ambas fuentes se integraron mediante el nombre de la región.
- El modelo permite análisis dinámico mediante filtros.

---

## Decisiones de diseño del panel

- El panel fue diseñado para responder explícitamente la pregunta analítica.
- El gráfico central es un scatter plot que muestra la relación entre ingreso promedio regional y vehículos en circulación.
- Se incorporaron KPIs de contexto para facilitar la interpretación.
- El nivel socioeconómico se utilizó como filtro para explorar variaciones sin sobrecargar el análisis.
- Se priorizó claridad y simplicidad por sobre complejidad visual.
- Se agregó un ícono para limpiar filtros y facilitar la exploración del panel.

---

## Publicación

El dashboard fue publicado utilizando Power BI Service mediante la opción **Publicar en la web**, permitiendo acceso público sin requerir permisos.

---

## Alcances

- El análisis es exploratorio y descriptivo.
- No busca establecer relaciones causales.
- Los resultados deben interpretarse a nivel agregado regional.

---

## Limitaciones

- El análisis se realiza a nivel regional, por lo que no captura diferencias intra-regionales.
- El ingreso se utiliza como proxy de nivel socioeconómico y no incorpora otras dimensiones como educación u ocupación.
- Los datos corresponden a un solo año (2022), por lo que no se analizan tendencias temporales.

---

## Link dashboard

https://app.fabric.microsoft.com/view?r=eyJrIjoiMGIwZTJjYjEtZjU0Zi00YjY4LTk1OGYtOTkxYWUxOWU0ZDA2IiwidCI6IjZmZDQ4ZjQxLWFmODEtNDVhNS05YzFlLWUzOTkwYmMyN2U3YyIsImMiOjR9

