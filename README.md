# Índice territorial de opacidad, violencia y conflicto — Honduras

Mapa interactivo de los 18 departamentos de Honduras. Metodología, datos y advertencias incluidos.

**Mapa:** https://USUARIO.github.io/indice-territorial-honduras/

## Qué mide

Media geométrica de tres dimensiones, en escala 0 a 100 donde el valor alto indica mayor cierre.

| Dimensión | Qué contiene |
|---|---|
| Opacidad e impunidad | Municipios nunca auditados por el TSC y sin auditoría reciente; hallazgos con indicio penal sobre los municipios auditados; perjuicio económico por auditoría; pliegos de responsabilidad sin resolver; denuncias del MP contra autoridades locales; señalamiento formal de la fiscalía |
| Violencia | Tasa de homicidios 2023–2025 y su variación frente al trienio 2015–2017 |
| Conflicto territorial | Desalojos, expedientes de personas defensoras y plantaciones de droga aseguradas, todos por habitante |

La agregación es geométrica para que un departamento no compense una dimensión con otra. Las dimensiones con menos del 60 % de sus indicadores calculados quedan como insuficientes y no se imputan.

## Decisiones metodológicas que conviene conocer

- **Las denuncias del MP se cuentan por episodio único**, no por fila. Un solo caso electoral en Sinuapa generaba 97 registros y colocaba a Ocotepeque como el departamento con más denuncias del país.
- **La criminalidad de funcionarios se puntúa por señalamiento formal de la fiscalía, no por el desenlace judicial.** Un sobreseimiento puede ser producto del mismo control que el índice intenta medir.
- **Los hallazgos del TSC se normalizan por auditoría realizada**, no por habitante, para que la dimensión no termine midiendo dónde fue el TSC. Se aplica encogimiento hacia la media nacional ponderado por número de auditorías.
- **La ausencia de auditoría se trata como indicador, no como dato faltante.** Que el TSC no haya auditado un municipio dice algo sobre el control externo, aunque no diga nada sobre las cuentas de ese municipio.
- **Un cero significa ausencia de registro en la fuente, nunca ausencia del fenómeno.**

## Robustez

El índice se recalculó en 25 escenarios: media aritmética en lugar de geométrica, perturbaciones de peso por dimensión y por bloque, eliminación de un indicador a la vez, y sin winsorizar. Los 18 departamentos se mantienen dentro de dos posiciones en al menos el 80 % de los escenarios.

Con una salvedad: **la cabeza de la tabla es sólida y la cola no.** Los seis primeros son idénticos en todas las variantes. Copán, Lempira y Ocotepeque, los tres con una dimensión por debajo de 5 puntos, se mueven hasta ocho posiciones según el método de agregación. Copán pasa del puesto 16 al 8 con media aritmética.

## Lo que el índice no incluye

No hay dimensión de control político: falta el resultado electoral municipal de 2025 del CNE. Tampoco entran extorsión, desplazamiento forzado interno, incautaciones de cocaína ni pistas clandestinas, que son las fuentes que registrarían el control criminal de corredores de tránsito. Por eso Cortés aparece abajo pese a ser el principal corredor portuario del país.

## Fuentes

Homicidios: Sepol. Auditorías, pliegos y perjuicio económico: Tribunal Superior de Cuentas. Denuncias contra alcaldes, regidores y diputados: Ministerio Público. Expedientes de personas defensoras: Secretaría de Derechos Humanos. Desalojos: registro de la comisión de seguridad agraria vía Cespad. Plantaciones aseguradas: Sedena y Dirección de Lucha Contra el Narcotráfico. Población: censo 2013 del INE. Geometría departamental: geoBoundaries / OpenStreetMap, ODbL 1.0.

## Datos

`datos/base_unificada_indice_v5.csv` — una fila por departamento con valores brutos, normalizados, las tres subpuntuaciones, el índice, el tramo y la estabilidad.

`datos/indicadores_departamentales_v1.csv` — formato largo, un indicador por fila, con fuente y ventana temporal.

## Cómo publicarlo

1. Crear un repositorio público en GitHub llamado `indice-territorial-honduras`.
2. Subir estos archivos manteniendo la estructura. `index.html` debe quedar en la raíz.
3. En el repositorio, entrar a Settings, luego Pages.
4. En Source elegir "Deploy from a branch", rama `main`, carpeta `/ (root)`, y guardar.
5. Esperar uno o dos minutos. El sitio queda en `https://USUARIO.github.io/indice-territorial-honduras/`.
6. Reemplazar `USUARIO` en el enlace de arriba.

Para incrustarlo en una nota:

```html
<iframe src="https://USUARIO.github.io/indice-territorial-honduras/"
        width="100%" height="820" style="border:0"></iframe>
```

El archivo `index.html` lleva la geometría de los departamentos incrustada, así que el mapa no depende de que un servicio externo siga en línea. Lo único que carga de la red es la librería D3.

## Licencia

Datos y metodología: CC BY 4.0, citando a Contracorriente. La geometría departamental proviene de geoBoundaries bajo ODbL 1.0.
