# Mentoría--Diplodatos-2025
Consignas de mentoría "Conexiones Transparentes: Descubriendo Relaciones Cruciales para la Calidad del Agua en el Río de La Plata"

# "Conexiones Transparentes: Descubriendo Relaciones Cruciales para la Calidad del Agua en el Río de La Plata"

En este repositorio se encuentran alojados: el dataset de trabajo para la mentoría y las consignas correspondientes a cada uno de los trabajos prácticos de la misma. 

## Descripción y Objetivos propuestos: 
El estudio de los cuerpos de agua es fundamental para garantizar su uso sostenible y preservar la salud de los ecosistemas. A nivel mundial, existen diversas guías que establecen metodologías para este fin, utilizando el Índice de Calidad del Agua (ICA). Este índice se calcula a partir de varios parámetros clave. Sin embargo, no hay un único índice estándar global. Cada organismo puede definir su propia fórmula de cálculo según parámetros específicos para su contexto local, como el tipo de cuerpo de agua, el uso previsto (potable, recreativo, agrícola, etc.) y las normativas ambientales [1]. En el proyecto se propone analizar un conjunto de datos de monitoreo del Río de La Plata, que incluye mediciones de variables físicas, químicas, microbiológicas y organolépticas, sumadas a características demográficas de los municipios correspondientes a los sitios de monitoreo. Este set aporta también el ICA calculado bajo la normativa canadiense a partir de algunas de estas dimensiones. 

El objetivo propuesto es desarrollar un modelo predictivo del ICA utilizando técnicas de aprendizaje supervisado. Esto permitirá evaluar la sensibilidad y el impacto de las variables medidas y explorar patrones relacionados con la estacionalidad y las características industriales y de saneamiento de las poblaciones cercanas a las estaciones de monitoreo. A partir de este análisis, se podrán hacer insights sobre qué parámetros deberían ser monitoreadas con mayor frecuencia y cuáles requieren estudios adicionales para implementar acciones que reduzcan su valor y mejoren el ICA. Además, permitirá inferir si la forma de medir el ICA es apropiada mediante el análisis descriptivo de los factores más relevantes.

A su vez, también es importante reconocer que algunos parámetros de control son costosos de evaluar, tanto en términos de recursos materiales como de tiempo necesario. En este contexto, resulta particularmente interesante explorar las posibles correlaciones entre las variables utilizando diferentes herramientas de la estadística descriptiva y del aprendizaje supervisado. Este enfoque permitirá no solo comprender las relaciones intrínsecas entre los diversos aspectos del agua, sino también identificar oportunidades para optimizar los recursos, centrándose en la predicción de variables mediante la observación y monitorización de aquellas menos costosas y que incluso en algunos casos pueden ser medidas en tiempo real.


## DATOS
El dataset constará de la conjunción de algunos datos públicos del Ministerio de Ambiente y Desarrollo Sostenible (2015-2023)[2]. El registro cuenta con información de 42 estaciones, monitoreadas entre una y cuatro veces por año (primavera, verano, otoño e invierno). Se compilará información del periodo 2022 a 2024 ya que son los registros más completos en cuanto a número de variables, pero también se puede utilizar años previos. La cantidad de variables monitoreados para calidad de agua son: 7 físicas-organolepticas, 11 químicas, 5 biológicas y 2 indicadores. A su vez fueron agregados datos demográficos de los municipios a los cuales pertenece cada sitio de monitoreo. En este sentido, se recopiló información adicional sobre el número de habitantes, acceso a servicio de cloacas y actividades industriales utilizando datos del CENSO 2022 [3] y del Programa de Estudios del Conurbano [4].

En este repositorio puede encontrar los conjuntos de datos originales, el código merge para lograr el csv de trabajo y la metadata (mapa, variables, unidades) en la carpeta "DataSet-crudos". El resultado es el csv con el que trabajaremos "Conexiones_Transparentes.csv". Las features disponibles, sus unidades o categorías son las siguientes:

## Variables principales

* Las columnas 'orden', 'sitio' y 'codigo' se relacionan con las estaciones de monitoreo. El monitoreo abarca de Tigre a Berisso, porque lo que el orden 1 corresponde a estaciones de Tigre mientras que 42 a Berisso. A su vez la columna sitio informa exactamente de que lugar se trata, mientras que la última la códifica.
* campaña: estación del año en que fue monitoreada.
* tem_agua: temperatura del agua [°C]
* tem_aire: temperatura del aire [°C]
* od: óxigeno disuelto [mg/L]
* pH: potencial hidrogeno - escala 1-14
* olores: presencia/ausencia
* color: presencia/ausencia
* espumas: presencia/ausencia
* mat_susp: material suspendido - presencia/ausencia
* colif_fecales_ufc_100ml: coliformes fecales [U.F.C/100mL] (unidades formadoras de colonia/100mL)
* escher_coli_ufc_100ml: Escherichia coli [U.F.C/100mL]
* enteroc_ufc_100ml: Enterococos [U.F.C/100mL]
* nitrato_mg_l: Nitratos (NO3-) [mg/L]
* nh4_mg_l: Amonio (NH4+) [mg/L]
* p_total_l_mg_l: Fósforo Total [mg/L]
* fosf_ortofos_mg_l: Fosfatos (PO4) [mg/L]
* dbo_mg_l: demanda biológica de óxigeno [mg/L]
* dqo_mg_l: demanda química de óxigeno [mg/L]
* turbiedad_ntu: Turbidez NTU: Unidades Nefelométricas de Turbidez
* hidr_deriv_petr_ug_l: Hidrocarburos derivados del Petróleo [ug/L]
* cr_total_mg_l: Cromo Total [mg/L]
* cd_total_mg_l: Cadmio Total [mg/L]
* clorofila_a_ug_l: Clorofila ‘a’ [ug/L]
* microcistina_ug_l: Microcistina  [ug/L]
* ica: Indice de calidad de agua. Deberiva de ecuaciones que relacionan las características organolepticas, biologicas, químicas y físicas del agua.
* calidad_de_agua: Clasificación que depende del ICA

## Variables sitio de monitoreo
* gobierno_local: Municipio al cual pertenece el sitio
* latitud: del sitio
* longitud: del sitio
* Poblacion_partido: Número de personas que pueblan el partido/municipio
* Personas_con_cloacas: Número de personas/población que tienen cloaca
* Actividad_principal: que se desarrolla en el municipio (variable categórica)

Las siguientes columnas ordenan al municipio al que pertenece el sitio respecto a la actividad, siendo el que más aporta a dicha actividad el número 1 (variables ordinales).

* Agricultura, ganadería, caza y silvicultura:
* Pesca explotación de criaderos de peces y granjas piscícolas y servicios conexos
* Explotación de minas y canteras
* Industria Manufacturera
* Electricidad, gas y agua
* Construcción
* Servicios


[1] Torres, P., Hernán Cruz, C., & Janeth Patiño, P. (2019). Índices de calidad de agua en fuentes superficiales utilizadas en la producción de agua para consumo humano. Una revisión crítica.. Revista Ingenierías Universidad de Medellín, 80–93.

[2] Ministerio de Ambiente y Desarrollo Sostenible. (2023). Repositorio de datos sobre calidad del agua. Recuperado 14 de marzo de 2024 de https://ciam.ambiente.gob.ar/repositorio.php?tid=1

[3] Instituto Nacional de Estadística y Censos (INDEC). (2022). Censo Nacional de Población, Hogares y Viviendas 2022 (Censo 2022). Recuperado 14 de marzo de 2024 de https://www.indec.gob.ar/

[4] Programa de Estudios del Conurbano. Universidad Nacional de Avellaneda. (2015). Municipios. Recuperado 14 de marzo de 2024 de http://www.atlasconurbano.info/pagina.php?id=169
