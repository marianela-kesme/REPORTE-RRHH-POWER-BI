
<div align="center">

# Reporte Recursos Humanos Con Power BI <img src="https://1000logos.net/wp-content/uploads/2022/08/Microsoft-Power-BI-Logo-768x432.png" alt="Power Bi2" width="100"/>

</div>

<br/><br/>

## Introduccion &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   <img src="https://cdn-icons-png.flaticon.com/512/3891/3891613.png" alt="Power Bi2" width="30"/>


Los recursos humanos son un departamento dentro de las empresas en el que se gestiona todo lo relacionado con las personas que trabajan en ella. Esto incluiría desde el reclutamiento, selección, contratación, onboarding o bienvenida, formación, promoción, nóminas y despidos.

A través de la Administración de Recursos Humanos, se puede identificar, comprender, evaluar y gestionar el comportamiento de las personas en el ámbito laboral. De igual modo, aplicando los métodos correctos, es posible la atracción y retención de trabajadores en una organización. De esta manera, se sentirán más confortables en el lugar de trabajo y aumentarán su productividad, aportando a la expansión del negocio.

<br/>

##  Objetivo  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  <img src="https://cdn-icons-png.flaticon.com/512/6821/6821002.png" alt="Power Bi3" width="30"/>
Analisis de datos, obtencion de Indicadores y elaboracion de un Dashboard sobre Recursos Humanos de una empresa peruana.

<br/>

## Obtencion de Indicadores     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  <img src= "https://cdn-icons-png.flaticon.com/512/7665/7665562.png" alt="Power Bi2" width="35"/>
El Dashboard que se realizó fue para tener una visión general de la gestión de talento humano con el fin de establecer mejoras dentro del departamento. 

Se hallaron indicadores como: 

• Total del colaboradores por género en porcentaje y cantidad. 

• Tiempo en el cargo (años) 

• Porcentaje de insatisfacción del personal 

• Tasa de ausencia 

• Promedio de evaluación 

• Costo de planilla

## Dataset   &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  <img src= "https://c0.klipartz.com/pngpicture/619/922/gratis-png-microsoft-excel-ilustracion-microsoft-excel-microsoft-office-macos-excel-thumbnail.png" alt="Power Bi2" width="35"/>

Nos conectamos a la fuente de datos que en este caso es un archivo de Excel donde estan todos los datos de los colaboradores:

•	ID identificador del empleado

•	Nombre

•	Edad

•	Genero

•	Departamento al que pertenecen

•	Nombre de su supervisor

•	Fecha de ingreso a la empresa

•	Salario mensual

•	Nota de su evaluación

•	Nivel de satisfaccion dentro de la organización

•	Las horas de ausencia

## Preliminares 
Se procedio a importar el dataset llamado Datos y la tabla colaboradores en power BI, realice varias transformaciones en mi conjunto de datos de colaboradores utilizando Power Query. Estas transformaciones incluyen correcciones de mayúsculas y minúsculas para asegurar la consistencia en los datos de texto. Además, he ajustado los tipos de datos a numéricos donde corresponde para facilitar análisis posteriores y asimismo con los datos categoricos. También he corregido errores en el formato de fechas para garantizar la precisión en la visualización y análisis de datos. Hubo la necesidad de añadir 2 columnas mas al dataset llamados Total años(puesto) y la columna grupo edad, estas columnas se crearon con el fin de poder hallar los indicadores que se nos solicito.

<img src="https://github.com/marianela-kesme/REPORTE-RRHH-POWER-BI/blob/main/datos/transformacion.png" alt="imagen1" width="800"/>

<br/>

Se procedio a calcular mediante DAX las medidas para hallar los indicadores

<img src="https://github.com/marianela-kesme/REPORTE-RRHH-POWER-BI/blob/main/datos/medidas.png" alt="imagen1" width="200"/>

<br/>

###  Medida para hallar el Total del colaboradores por género en porcentaje y cantidad:

<br/>
Total colaboradores = COUNTA( colaboradores [Nombre Empleado])  
<br/>
total mujeres = CALCULATE([Total colaboradores],colaboradores[Género] ="femenino")
<br/>
total varones = CALCULATE([Total colaboradores],colaboradores[Género] ="Masculino")
<br/>
%mujeres = DIVIDE([total mujeres],[Total colaboradores],0)
<br/>
%varones = DIVIDE([total varones],[Total colaboradores],0)
<br/>
<br/>

<img src="https://github.com/marianela-kesme/REPORTE-RRHH-POWER-BI/blob/main/datos/Captura%20de%20pantalla%202024-05-31%20162925.png" alt="Descripción de la imagen" width="200">
<br/>

### medida para hallar el tiempo en el cargo en años:
Tiempo en el cargo(años) = DIVIDE(SUM(colaboradores[Total años (puesto)]), [total colaboradores],0) 

### medida para hallar el porcentaje de insatisfaccion del personal:
% personal insatisfecho = DIVIDE([total insatisfechos],[Total colaboradores],0)
<br/>

### Medida para hallar la tasa de ausencia:
Tasa Ausencia = [#Total horas ausentismo]/[#total horas planificadas]

<br/>

<img src="https://github.com/marianela-kesme/REPORTE-RRHH-POWER-BI/blob/main/datos/Captura%20de%20pantalla%202024-05-31%20162859.png" alt="Descripción de la imagen" width="600">

<br/>

<img src="https://github.com/marianela-kesme/REPORTE-RRHH-POWER-BI/blob/main/datos/Captura%20de%20pantalla%202024-05-31%20162938.png" alt="Descripción de la imagen" width="200">

<br/>

### luego, se procedio a realizar los graficos que se solicitaron para saber total de colaboradores por departamento, donde se observa que el area de Produccion es el que mas cantidad de colaboradores posee.
<br/>
<img src="https://github.com/marianela-kesme/REPORTE-RRHH-POWER-BI/blob/main/datos/Captura%20de%20pantalla%202024-05-31%20162955.png" alt="Descripción de la imagen" width="300">

