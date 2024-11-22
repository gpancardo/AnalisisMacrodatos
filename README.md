# AnalisisMacrodatos
Proyecto final de Análisis de Macrodatos


10 CONSULTAS BASICAS (DEBEMOS DE CAMBIAR NUESTRAS CONSULTAS EN BASE A LOS NOMBRES QUE LE PONGAMOS A NUESTRAS TABLAS)


1. Número de accidentes por día de la semana
SELECT DIA_SEMANA, COUNT(*) AS nr
FROM accidentes
GROUP BY DIA_SEMANA
ORDER BY nr DESC;


2. Número de accidentes por tipo de vehículo involucrado
SELECT TIPO_VEHICULO, COUNT(*) AS nr
FROM accidentes
GROUP BY TIPO_VEHICULO
ORDER BY nr DESC;


3. Accidentes clasificados por gravedad
SELECT CLASACC AS CLASIFICACION, COUNT(*) AS nr
FROM accidentes
GROUP BY CLASACC
ORDER BY nr DESC;


4. Número de accidentes en intersecciones
SELECT INTERSECCION, COUNT(*) AS nr
FROM accidentes
WHERE INTERSECCION IS NOT NULL
GROUP BY INTERSECCION
ORDER BY nr DESC;


5. Número de accidentes relacionados con condiciones climáticas
SELECT CONDICION_CLIMATICA, COUNT(*) AS nr
FROM accidentes
GROUP BY CONDICION_CLIMATICA
ORDER BY nr DESC;


6. Promedio de edad de los involucrados en accidentes por año
SELECT ANIO, AVG(ID_EDAD) AS promedio_edad
FROM accidentes
GROUP BY ANIO
ORDER BY ANIO;


7. Comparativa de accidentes en zonas rurales vs urbanas
SELECT ZONA, COUNT(*) AS nr
FROM accidentes
WHERE ZONA IN ('Rural', 'Urbana')
GROUP BY ZONA
ORDER BY nr DESC;


8. Accidentes por estado y tipo de vía
SELECT e.NOM_ENT, TIPOVIA, COUNT(*) AS nr
FROM accidentes a
JOIN entidadesfederativas e ON a.ID_ENTIDAD = e.CVE_ENT
GROUP BY e.NOM_ENT, TIPOVIA
ORDER BY e.NOM_ENT, nr DESC;


9. Accidentes en función del límite de velocidad
SELECT LIMITE_VELOCIDAD, COUNT(*) AS nr
FROM accidentes
GROUP BY LIMITE_VELOCIDAD
ORDER BY LIMITE_VELOCIDAD;


10. Accidentes por ocupación del conductor
SELECT OCUPACION, COUNT(*) AS nr
FROM accidentes
GROUP BY OCUPACION
ORDER BY nr DESC;
