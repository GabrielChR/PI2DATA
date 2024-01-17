

## **Proyecto Individual N° 2** -Siniestros Viales usando base de datos de Buenos Aires Data -(2016-2021) 

## **Introducción**

Este proyecto se realizó simulando un pedido solicitado por el `Observatorio de Movilidad y Seguridad Vial (OMSV)` para el análisis de datos de sisientros viales, bajo la órbita de la Secretaría de Transporte del Gobierno de la Ciudad Autónoma de Buenos Aires (CABA).

Cabe resaltar que el análisis de estos datos es importante para que la información brindada sea tomada en cuenta por autoridades para que se tomen decisiones en que aspectos se tiene que brindar una mayor atención y tomar medidas al respecto con el fin de ir reduciendo este tipo de accidentes

Para cumplir con ello, los datos iniciales que se utilizan son derivados de un dataset con información sobre homicidios de siniestros viales en la Ciudad de Buenos Aires, durante los años 2016-2021, que es de público acceso en la página oficial de CABA. 
Podemos acceder a ellos desde 

[Datos oficiales](https://data.buenosaires.gob.ar/dataset/victimas-siniestros-viales)

## **Desarrollo**

### Datos⛔

Para este proyecto se trabajó con la **Bases de Víctimas Fatales en Siniestros Viales** 
Base datos HOMICIDIOS
que se encuentra en formato de Excel y contiene dos pestañas de datos:

 * **HECHOS**: que contiene una fila de hecho con id único y las variables temporales, espaciales y participantes asociadas al mismo.

 * **VICTIMAS**: contiene una fila por cada víctima de los hechos y las variables edad, sexo y modo de desplazamiento asociadas a cada víctima. Se vincula a los HECHOS mediante el id del hecho.
En este [documento](NOTAS_HOMICIDIOS_SINIESTRO_VIAL.pdf) se detallan todas las definiciones manejadas en los datos y en el desarrollo de este proyecto. Por otra parte, en este [link](https://data.buenosaires.gob.ar/dataset/victimas-siniestros-viales) se encuentran los datos utilizados en el análisis.


### Análisis de los datos⛔

- Se analizan las variables numéricas del dataset su correlación por medio de una matriz, donde se encuentra una relación positiva entre las variables `Edad`y `Hora`
- La máyoria de los siniestros resultan con una víctima fatal, rara vez involucran 3 víctimas.
  
-`Análisis Temporal:` 
![Relacion total eventos / año](/images/img años.png)
En el período 2016-2018 una tendencia alta , que luego baja debido al comienzo de la Pandemia por COVID19 durante 2020; luego de este período hay un pico de siniestros pero vuelve a bajar para los proximos trimestres.

Los meses con más victimas fatales son **Diciembre** (86) y **Agosto**(71); mientras que los días de la semana **Sábado** (114) y **Domingo** (114) tienen la mayor cantidad de víctimas.

![Mapa deCalor](/images/img años.png)


Los horarios críticos de los siniestros viales están relacionados con los momentos del ingreso a la jornada laboral (5-9h), el momento del almuerzo (12-14h) y la salida del trabajo (17-18h). Mientras que los fines de semana están relacionados con las salidas nocturnas (4-7h)


-`Análisis Participativo:`

Para el caso de la variable `Participantes` de los sinietros; se analiza a `Acusados`, como el vehículo que tiene la responsabilidad del hecho, de lo que resultan los Autos, Colectivos y Vehículos de Carga como mayores involucrados. Para el análisis de las `Victimas`, que en momento del accidente resultaban mayormente en el **Rol** de Conductor o Peatón; y el siniestro se produce en la mayoría de los casos en Motos y luego como Peaton.

### Indicadores de Rendimiento Clave KPI⛔

Una vez finalizado el Análisis Exploratorio, se utiliza el dataset resultante [Siniestros](data/siniestos_limpio.csv) y los extraidos de la página oficial de CABA con los datos de las comunas [Comunas](data/comunas.xlsx); para trabajar en la herramienta PowerBi a fin de obtener los KPI (Indicadores de Rendimiento Clave) y un `dashboard` de presentación del informe y Visualización de datos.

KPI Propuestos

 - **Reducir en un 10% la tasa de homicidios en siniestros viales de los últimos seis meses, en CABA, en comparación con la tasa de homicidios en siniestros viales del semestre anterior**

Se define la tasa de homicidios en siniestros viales como el número de víctimas fatales en accidentes de tránsito por cada 100,000 habitantes en un área geográfica durante un período de tiempo específico. Su fórmula es: (Número de homicidios en siniestros viales / Población total) * 100,000

Número de Homicidios de Siniestros = Tomando la variable `Num víctimas` del dataset
Población Total = Tomada del Censo 2022. (Fuente:INDEC)


 - **Reducir en un 7% la cantidad de accidentes mortales de motociclistas en el último año, en CABA, respecto al año anterior**

Se define la cantidad de accidentes mortales de motociclistas en siniestros viales como el número absoluto de accidentes fatales en los que estuvieron involucradas víctimas que viajaban en moto en un determinado periodo temporal. Su fórmula para medir la evolución de los accidentes mortales con víctimas en moto es: (Número de accidentes mortales con víctimas en moto en el año anterior - Número de accidentes mortales con víctimas en moto en el año actual) / (Número de accidentes mortales con víctimas en moto en el año anterior) * 100

Cantidad de Accidentes Mortales en Moto = Tomando la variable `Victima` que se iguale a el campo [MOTO] del dataset 



 - **Reducir en un 15% la cantidad de accidentes con víctimas fatales de peatones en el último semestre, en CABA, respecto al semestre anterior.**

Se define la cantidad de accidentes fatales de peatones en siniestros viales como el número absoluto de accidentes fatales en los que estuvieron involucradas víctimas que circulaban a pie en un determinado periodo temporal. Su fórmula para medir la evolución de los accidentes mortales con víctimas peaton es: (Número de accidentes mortales con víctimas peaton en el semestre anterior - Número de accidentes mortales con víctimas peaton en el semestre actual) / (Número de accidentes mortales con víctimas peaton en el semestre anterior) * 100

Cantidad de Accidentes Mortales en Moto = Tomando la variable `Victima` que se iguale a el campo [PEATON] del dataset 


## **Conclusiones**⚠️ 🚧

A partir del análisis exahustivo de los datos y su posterior visualización a través del dashboard en PowerBi; se concluye que las víctimas fatales por siniestros de tránsito entre los años 2016 a 2021 fueron 717 personas.
Que la franja horaria de mayor problemática es la del ingreso laboral (5-9h), la del almuerzo (12-14h)y la del regreso a casa(17-18h); aunque durante los fines de semana (Sábado y Domingo), los accidentes se manifiestan en los horarios de salidas nocturnas (3-7h).
Las víctimas son en un 76% Masculinas, y sus edades entre el rango etario de 20-40 años.
Además en los siniestros de Masculinos los mayores casos se dan en su rol como Conductor.
Los tipos de vehículos más frecuentes con Víctimas son las Motos y luego los Peatones; mientras que para los Acusados los vehículos más frecuentes son Autos, Colectivos y cargas.
En cuanto a el lugar donde se producen los siniestros, las Avenidas a lo largo de los años han sido los espacios de mayor cantidad de siniestros; y en Cruce mayor a las calles. 
Se observo un patrón en relación con la variable Edad, Hora y Sexo. Donde los Masculinos de entre 20 a 40 años y en los horarios de entrada y salida laboral o para el caso de los fines de semana en horas de salidas nocturnas.

Asi se concluye que deberían mejorarse las señales y controles en las Avenidas sobre todo en las comunas 1 y 4 de CABA. Que podrían generarse campañas de prevención dirigidas a los Masculinos de entre 20 y 40 años .

