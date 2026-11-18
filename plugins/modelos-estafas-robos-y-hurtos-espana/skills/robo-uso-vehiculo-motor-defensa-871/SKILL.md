---
name: robo-uso-vehiculo-motor-defensa-871
description: "Redacta el escrito «Robo de uso de vehículo de motor: defensa» (formulario 871 de delitos contra el patrimonio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Robo de uso de vehículo de motor: defensa

> Formulario 0871 del plugin **Delitos contra el patrimonio** · revisado el 17-11-2026.

## Paso 0: Jurisprudenciator en esta skill (obligatorio)

**Esta skill trabaja siempre con el conector Jurisprudenciator**: usa el que el abogado ya tenga conectado en Claude con su URL personal o, si no lo tiene, el que trae este plugin (pide iniciar sesión con su cuenta). Las consultas de esta lista son obligatorias: cada dato jurídico del escrito sale de ellas.

- **Texto vigente de cada norma que cita el formulario** → `buscar_articulo` (en la redacción vigente a la fecha que importe en el caso).
- **Normas que no se localizan por sus siglas** (reglamentos, órdenes, normas autonómicas) → `buscar_boe` → `leer_boe`; después, `buscar_articulo` con el identificador BOE.
- **Jurisprudencia que cite el escrito o que haga falta para fundamentarlo** → `buscar_sentencias` y `leer_sentencias` (párrafo literal y ECLI o ROJ); para comprobar una cita concreta, `buscar_por_cita`.
- **Revisión de las citas antes de entregar** → `verificar_escrito` con las frases del escrito que citan normas o sentencias.
- **Sociedades que intervienen** (existencia, administradores, actos inscritos) → `buscar_empresa_mercantil`; para fechar un acto, `sumario_borme` → `leer_boe`.
- **Inmuebles** (referencia catastral, superficie, uso) → `consultar_catastro` (y `callejero_catastro` para localizar la dirección).

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

- [ ] SEDE
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS (3 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] AÑO
- [ ] IMPORTE
- [ ] LUGAR
- [ ] FECHA (3 veces)
- [ ] Otros 4 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «… de los hechos se encontraba de viaje en»; «…rabajos en beneficio de la comunidad por»; «…acompañó al/a la acusado/a en el viaje a»; «…stente en el billete de tren del viaje a»

## Elecciones que hay que hacer

- judicialmente / mediante exhorto

## Párrafos opcionales (4)

Inclúyelos solo si encajan en los hechos:

- 1:- INTERROGATORIO del/de la acusado/a.…
- .- TESTIFICAL: declaración del siguiente testigo, que acompañó al/a la acusado/a en el viaje a [COMPLETAR], el…
- .- PERICIAL, consistente en que por el Médico Forense de este órgano judicial se ratifique o amplíe el Informe…
- .- DOCUMENTAL consistente en el billete de tren del viaje a [COMPLETAR] el día [FECHA].…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 244.2 CP
- artículo 784.1 de la Ley de Enjuiciamiento Criminal
- artículo 244.2 del Código Penal
- art. 784.2 de la LECrim
- art. 777.2 LECrim
- artículo 656 LECrim

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

### Formulario 0871 · Robo de uso de vehículo de motor: defensa

- Año del modelo: 2016
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (2); 1 desplegables y casillas convertidos en elección en blanco; 4 párrafos opcionales señalados; 13 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito de conclusiones provisionales de la defensa en un procedimiento abreviado por presunto delito de robo de uso de vehículo del art. 244.2 CP, por haber entrado en vehículo ajeno, forzándolo, haberlo usado y haberlo dejado abandonado posteriormente en la vía pública.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales, en la representación que tiene acreditada de D./Dña. [NOMBRE Y APELLIDOS], acusado/a en las diligencias previas número [Nº DE PROCEDIMIENTO] del año [AÑO] por el supuesto delito de robo de uso de vehículo de motor, comparezco ante este órgano judicial y, como mejor proceda en derecho (1), DIGO:

Que, conforme a lo preceptuado en el artículo 784.1 de la Ley de Enjuiciamiento Criminal, manifiesto mi disconformidad con los escritos de acusación y formulo escrito de defensa en base a las siguientes:

CONCLUSIONES

PRIMERA.- Disconforme con la correlativa del Ministerio Fiscal y del acusador/a particular. Mi representado/a no hizo lo que se le atribuye, ya que el día de los hechos se encontraba de viaje en [COMPLETAR], y las huellas que constan se pueden deber a su relación con el dueño del vehículo, por habérselo dejado recientemente para su uso.

SEGUNDA.- Disconforme con las correlativas. Los hechos no son constitutivos de un delito de robo de uso de vehículo de motor del artículo 244.2 del Código Penal.

TERCERA.- Niego las correlativas. Mi representado/a no es el/la autor/a del delito por el que se procede, ni de ningún otro.

CUARTA.- Disconforme con las correlativas. Al no ser autor/a de ningún delito no pueden existir circunstancias modificativas de la responsabilidad inexistente.

QUINTA.- Disconforme con las correlativas. Procede absolver a mi representado/a con todos los pronunciamientos favorables, por no ser el/la autor/a. Subsidiariamente, para el caso de que no lo estime así este órgano judicial, procede la imposición a mi representado/a de la pena de trabajos en beneficio de la comunidad por [COMPLETAR], por concurrir atenuante de drogodependencia, del artículo 21.2ª del CP.

SEXTA.- Disconforme con las correlativas. No puede existir responsabilidad civil cuando no existe delito. Y por lo mismo procede declarar las costas de oficio.

Subsidiariamente, la responsabilidad civil asciende a la cifra de [IMPORTE] euros.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito con sus copias, los admita y por realizada la calificación.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ PRIMERO DIGO: Que, de acuerdo con lo dispuesto en el art. 784.2 de la LECrim., solicito como prueba anticipada, la siguiente:

Pericial Médico-Forense, consistente en que, por parte del médico Forense de este órgano judicial, previo examen del acusado, se emita Dictamen con anterioridad al acto de Juicio Oral sobre los siguientes extremos:

— Grado de dependencia del acusado a sustancias estupefacientes.
— Cantidad, calidad y frecuencia de las ingestas.
— Incidencia de la drogodependencia en la capacidad volitiva e intelectiva del acusado, en el momento de producirse los hechos.
— Las que se deriven.

OTROSÍ SEGUNDO DIGO: Que, para el acto del juicio oral, propongo los siguientes:

MEDIOS DE PRUEBA

Todos los propuestos por el Ministerio fiscal y el acusador particular y además los siguientes:

[OPCIONAL — incluir si procede]

1:- INTERROGATORIO del/de la acusado/a.

[OPCIONAL — incluir si procede]

.- TESTIFICAL: declaración del siguiente testigo, que acompañó al/a la acusado/a en el viaje a [COMPLETAR], el día [FECHA] que deberá ser citado [ELEGIR: judicialmente / mediante exhorto] (2):

D./Dña. [NOMBRE Y APELLIDOS]

[OPCIONAL — incluir si procede]

.- PERICIAL, consistente en que por el Médico Forense de este órgano judicial se ratifique o amplíe el Informe que redacte respecto del acusado, en el solemne acto del Juicio Oral, que ha sido solicitado como prueba anticipada por esta parte.

[OPCIONAL — incluir si procede]

.- DOCUMENTAL consistente en el billete de tren del viaje a [COMPLETAR] el día [FECHA].

Por lo expuesto,

SUPLICO A LA SECCIÓN: declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a	Firma de Procurador/a

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 10 días hábiles desde que se recibe traslado de la causa, por la vía del art 784 LECrim .

En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos al comienzo del juicio oral pueden aportarse más pruebas.

También debe pedirse que se reproduzca la grabación o lectura literal de la prueba practicada anticipadamente en la fase de diligencias previas (art. 777.2 LECrim ).

Si el acusado padece drogodependencia se aportaría la documentación pertinente y se podría alegar la circunstancia modificativa de responsabilidad penal.

(2) Debe tenerse en cuenta lo dispuesto en el artículo 656 LECrim, que dispone que hay que identificar bien a los testigos.

================================================================================
