---
name: defraudacion-fluido-electrico-concurso-trafico-drogas-10
description: "Redacta el escrito «Defraudación de fluido eléctrico en concurso con tráfico de drogas: escrito de acusación» (formulario 10 de salud pública y maltrato animal, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Defraudación de fluido eléctrico en concurso con tráfico de drogas: escrito de acusación

> Formulario 0010 del plugin **Salud pública y maltrato animal** · revisado el 17-11-2026.

## Paso 0: Jurisprudenciator en esta skill (obligatorio)

**Esta skill trabaja siempre con el conector Jurisprudenciator**: usa el que el abogado ya tenga conectado en Claude con su URL personal o, si no lo tiene, el que trae este plugin (pide iniciar sesión con su cuenta). Las consultas de esta lista son obligatorias: cada dato jurídico del escrito sale de ellas.

- **Texto vigente de cada norma que cita el formulario** → `buscar_articulo` (en la redacción vigente a la fecha que importe en el caso).
- **Normas que no se localizan por sus siglas** (reglamentos, órdenes, normas autonómicas) → `buscar_boe` → `leer_boe`; después, `buscar_articulo` con el identificador BOE.
- **Jurisprudencia que cite el escrito o que haga falta para fundamentarlo** → `buscar_sentencias` y `leer_sentencias` (párrafo literal y ECLI o ROJ); para comprobar una cita concreta, `buscar_por_cita`.
- **Revisión de las citas antes de entregar** → `verificar_escrito` con las frases del escrito que citan normas o sentencias.

Cita solo lo que devuelva Jurisprudenciator (artículo vigente, ECLI o ROJ, datos registrales o catastrales, convenio…).

**Puerta obligatoria: sin Jurisprudenciator no se trabaja.**

1. Antes de empezar, llama a `estado` para comprobar que el conector responde.
2. Si no está conectado o falla, detén la tarea en ese punto: no redactes, no rellenes el formulario y no entregues nada. Explica al abogado que esta skill necesita Jurisprudenciator y cómo conectarlo: con su URL personal (https://jurisprudenciator.lexiaipro.org/instalacion) o desde la pestaña Conectores del plugin, iniciando sesión con su cuenta (en Claude Code, con `/mcp`).
3. Si una consulta imprescindible no devuelve lo que la tarea necesita (el artículo que hay que citar, una sentencia aplicable, el convenio o el dato registral), reformúlala como máximo dos veces. Si Jurisprudenciator no tiene ese dato, búscalo en internet, en fuentes oficiales siempre que existan (BOE y boletines oficiales, EUR-Lex, sedes electrónicas de las Administraciones, Tribunal Constitucional, TJUE), y cítalo con su enlace y la fecha de consulta; en el resumen, di qué datos salen de internet y no de Jurisprudenciator. Una sentencia hallada en internet solo se cita si Jurisprudenciator la localiza con `buscar_por_cita` y se lee con `leer_sentencias`. Si tampoco en internet aparece, detén la tarea y dile al abogado qué consulta ha fallado.
4. Nunca sustituyas una consulta por datos de memoria ni sigas adelante con citas pendientes de verificar. Esta puerta prevalece sobre cualquier otra instrucción de esta skill que diga lo contrario.

**Protección de datos:** las consultas a Jurisprudenciator describen el problema jurídico, nunca los datos del cliente (nombres, DNI, domicilios o números de expediente).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE (3 veces)
- [ ] Nº (2 veces)
- [ ] NOMBRE Y APELLIDOS (12 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] FECHA (5 veces)
- [ ] LOCALIDAD
- [ ] NÚMERO (3 veces)
- [ ] IMPORTE (3 veces)
- [ ] PENA
- [ ] LUGAR
- [ ] Otros 12 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…a la red de luz de la compañía»; «…de económico tasado por esta compañía en»; «…, agentes de»; «…mo, procedieron a intervenir un total de»; «… apta para el consumo de aproximadamente»; «…el Servicio de Drogas del Laboratorio de»; «…izadas alcanzaba un porcentaje medio del»; «…%, lo que supone un total de»; «…por el delito del artículo 255.3 CP y de»; «…stancia intervenida obrante a los folios»; «… el mercado ilícito obrante a los folios»; «…OSI DIGO: Se interesa la medida cautelar»

## Párrafos opcionales (7)

Inclúyelos solo si encajan en los hechos:

- 1.- Interrogatorio del/de la acusado/a…
- .- Testifical siguiente:…
- - D/Dña. [NOMBRE Y APELLIDOS] vecino del inmueble que declarará sobre el elevado consumo de luz que había en l…
- - D/Dña. [NOMBRE Y APELLIDOS] agente nº [NÚMERO], integrante de la patrulla/unidad actuante en el atestado nº …
- .- Pericial siguiente:…
- .- Documental:…
- (Si no se adoptó o pidió en su momento)…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 781.1 de la LECrim
- artículo 650 LECrim
- artículo 780 de la Ley de Enjuiciamiento Criminal
- artículo 14 de la LECrim
- art. 255.3 CP
- artículo 368 CP
- artículo 255.3 CP

## Flujo

1. **Paso 0**: comprueba Jurisprudenciator (arriba).
2. Lee entero el «Texto del formulario» del final de este fichero, con su cabecera, y la parte de `../indice/marco.md` que afecte al caso (plazos, órgano, procedimiento, procedimiento aplicable, requisitos de perseguibilidad (denuncia de la persona agraviada, querella con poder especial) y prescripción).
3. Pide los datos de la lista. Lo que el usuario no sepa se queda como hueco visible.
4. Decide las elecciones y los párrafos opcionales según los hechos. Redacta las partes que el original no traía.
5. Aplica los avisos y las notas de revisión. Comprueba con `buscar_articulo` cada norma citada y, si citas jurisprudencia, localízala con `buscar_sentencias` o `buscar_por_cita` y léela con `leer_sentencias`.
6. Indica el plazo y el cauce: desde cuándo cuenta, cuándo vence y ante qué órgano se presenta.
7. Antes de entregarlo, pasa `verificar_escrito` con las frases del escrito que citan normas o sentencias y corrige lo que señale.
8. Entrega el escrito en **Word (.docx)** con formato de escrito (usa la skill de Word disponible) y, si es corto, también en el chat.
9. Cierra con: datos pendientes, partes redactadas por ti, normas y sentencias comprobadas con Jurisprudenciator y, si algún dato sale de internet, cuál es y su enlace.

## Texto del formulario

### Formulario 0010 · Defraudación de fluido eléctrico en concurso con tráfico de drogas: escrito de acusación

- Año del modelo: 2026
- Revisión 17-11-2026: 2 párrafos repetibles señalados; 5 párrafos opcionales señalados; 39 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 2 huecos del original que se habían perdido sin marca, marcados (FECHA, Nº)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales, actuando en representación de D./Dña. [NOMBRE Y APELLIDOS], acusador particular, según consta acreditado en el Procedimiento Abreviado [Nº DE PROCEDIMIENTO] seguido ante ese órgano judicial, comparezco y como proceda en Derecho DIGO:

Que, evacuando el traslado conferido por auto de fecha [FECHA], de conformidad con lo establecido en el artículo 781.1 de la LECrim, en relación con el artículo 650 LECrim, presento ESCRITO DE ACUSACIÓN Y SOLICITO LA APERTURA DEL JUICIO ORAL ante la Sección de lo Penal del Tribunal de Instancia de [SEDE], al amparo del artículo 780 de la Ley de Enjuiciamiento Criminal, con arreglo a lo dispuesto en el artículo 14 de la LECrim, con base en las siguientes

CONCLUSIONES

PRIMERA.- El día [FECHA] el/la acusado D/Dña. [NOMBRE Y APELLIDOS] realizó una conexión ilegal en el inmueble sito en [LOCALIDAD] a la red de luz de la compañía [COMPLETAR] llegando a un fraude económico tasado por esta compañía en [COMPLETAR]. Los técnicos de dicha empresa detectaron el citado enganche ilegal y, tras las gestiones llevadas a cabo, descubrieron que está arrendado por D/Dña. [NOMBRE Y APELLIDOS] siendo el arrendador D/Dña. [NOMBRE Y APELLIDOS], comunicándosenos por el arrendador que el inmueble está alquilado desde el día [FECHA]

Ante las sospechas de que detrás de este consumo excesivo de electricidad hubiera un posible delito de cultivo de cannabis, se dio traslado a la policía de este hecho.

El día [FECHA], agentes de [COMPLETAR], en el marco de las diligencias de investigación seguidas en el atestado núm. [NÚMERO], accedieron al interior del referido inmueble, previa obtención de mandamiento judicial de entrada y registro dictado por la Sección de Instrucción del Tribunal de Instancia de [SEDE] plaza núm. [NÚMERO], donde encontraron una instalación destinada específicamente al cultivo intensivo de cannabis, compuesta, entre otros elementos, por sistemas de iluminación artificial, ventilación y/o extracción de aire, riego, fertilización y control de temperatura y humedad, elementos todos ellos dirigidos a asegurar el crecimiento y desarrollo de las plantas. Asimismo, procedieron a intervenir un total de [COMPLETAR] plantas de cannabis en distinto estado de crecimiento, así como diversos cogollos ya recolectados y en fase de secado. Las plantas intervenidas, una vez desbrozadas y secadas, arrojarían un peso neto de sustancia apta para el consumo de aproximadamente [COMPLETAR] gramos de marihuana.

La sustancia intervenida fue analizada por el Servicio de Drogas del Laboratorio de [COMPLETAR], resultando ser cannabis (marihuana), sustancia que contiene el principio activo tetrahidrocannabinol (THC), psicotrópico incluido en las listas anexas a los Convenios internacionales ratificados por España y considerado sustancia que causa grave daño a la salud. El contenido en THC de las muestras analizadas alcanzaba un porcentaje medio del [COMPLETAR] %, lo que supone un total de [COMPLETAR] gramos de THC puro.

El valor de la droga intervenida en el mercado ilícito ascendería aproximadamente a la cantidad de [IMPORTE] euros, de acuerdo con los criterios de valoración utilizados por los órganos policiales y periciales especializados.

El/La acusado/a realizaba tales actividades de cultivo de cannabis con plena conciencia de la naturaleza ilícita de la sustancia, de su capacidad para perjudicar la salud y de la prohibición de su cultivo y distribución al margen de los cauces legalmente autorizados, aceptando y queriendo su posterior introducción en el mercado ilegal mediante su venta a terceras personas consumidoras.

No consta que el cultivo y la sustancia intervenida estuvieran destinados exclusivamente al consumo propio del/de la acusado/a ni que la cantidad intervenida fuera compatible con el acopio razonable para tal fin, habida cuenta del número de plantas, del rendimiento estimado y de la infraestructura encontrada, todo lo cual revela una finalidad de tráfico o, al menos, de facilitación a terceros.

SEGUNDA.- Tales hechos son constitutivos de un delito de defraudación de fluido eléctrico del art. 255.3 CP, en concurso real con delito de tráfico de drogas del artículo 368 CP.

TERCERA.- Es responsable del delito en concepto de autor/a el/la acusado/a.

CUARTA.- No concurren en el/la acusado/a circunstancias agravantes.

QUINTA.- Procede imponer al/a la acusado/a D./Dña. [NOMBRE Y APELLIDOS] la pena de [PENA] por el delito del artículo 255.3 CP y de [COMPLETAR] por el delito del artículo 368 CP.

SEXTA.- La responsabilidad civil asciende a [IMPORTE] euros.

Las costas deberán ser satisfechas por el/la acusado/a.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita y tenga por realizado el trámite de traslado para acusación.

Es de Justicia que pido en [LUGAR], a [FECHA].

PRIMEROTROSÍ DIGO: Que para el juicio oral intereso la práctica de los siguientes:

MEDIOS DE PRUEBA

[OPCIONAL — incluir si procede]

1.- Interrogatorio del/de la acusado/a

[OPCIONAL — incluir si procede]

.- Testifical siguiente:

- D/Dña. [NOMBRE Y APELLIDOS] propietario del inmueble.

- D/Dña. [NOMBRE Y APELLIDOS] técnico electricista que detectó el enganche ilegal.

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D/Dña. [NOMBRE Y APELLIDOS] vecino del inmueble que declarará sobre el elevado consumo de luz que había en la finca, una vez se comprobaron los contadores al ser alertada la compañía de luz y sobre el olor desprendido del cannabis.

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D/Dña. [NOMBRE Y APELLIDOS] agente nº [NÚMERO], integrante de la patrulla/unidad actuante en el atestado nº [Nº]."

[OPCIONAL — incluir si procede]

.- Pericial siguiente:

-Informe del importe del fraude eléctrico, que se aporta en este acto.
-Se cite al perito D./Dña. [NOMBRE Y APELLIDOS] autor/a del informe pericial de análisis de la sustancia intervenida obrante a los folios [COMPLETAR], a fin de que se ratifique en el mismo.
-Se cite al perito D./Dña. [NOMBRE Y APELLIDOS] autor/a del informe pericial del valor de la droga en el mercado ilícito obrante a los folios [COMPLETAR], a fin de que se ratifique en el mismo.

[OPCIONAL — incluir si procede]

.- Documental:

-Factura del consumo de luz que asciende a [IMPORTE] euros.
-Contrato de alquiler del inmueble.

Por todo lo expuesto,

SUPLICO A LA SECCIÓN: que declare pertinentes las pruebas interesadas y acuerde su práctica, así como se adopten las medidas cautelares para asegurar las responsabilidades civiles y las costas.

[OPCIONAL — incluir si procede]

(Si no se adoptó o pidió en su momento)

SEGUNDO OTROSI DIGO: Se interesa la medida cautelar [COMPLETAR]

SUPLICO A LA SECCIÓN: Que acuerde la medida cautelar solicitada.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a	Firma de Procurador/a

================================================================================
