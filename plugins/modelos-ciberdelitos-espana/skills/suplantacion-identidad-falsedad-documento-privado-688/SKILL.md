---
name: suplantacion-identidad-falsedad-documento-privado-688
description: "Redacta el escrito «Suplantación de identidad (falsedad en documento privado): defensa con conformidad» (formulario 688 de ciberdelitos y propiedad intelectual, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Suplantación de identidad (falsedad en documento privado): defensa con conformidad

> Formulario 0688 del plugin **Ciberdelitos y propiedad intelectual** · revisado el 17-11-2026.

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

- [ ] SEDE
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] COLEGIO
- [ ] Nº DE COLEGIADO/A
- [ ] LOCALIDAD
- [ ] Nº DE PROCEDIMIENTO
- [ ] PENA
- [ ] LUGAR
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «…y, como mejor proceda en derecho, DICEN:»

## Párrafos opcionales (1)

Inclúyelos solo si encajan en los hechos:

- Se solicita se conceda la suspensión de la ejecución de la pena del art. 80 CP y ss que por la defensa se inte…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 395 CP
- art. 395 CP
- art. 784.3 LECRIM
- art. 787 LECRIM
- art. 787 ter LECRIM
- art. 390 CP
- art. 785 LECRIM
- art. 80 CP
- art. 401 CP
- art. 26 CP

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

### Formulario 0688 · Suplantación de identidad (falsedad en documento privado): defensa con conformidad

- Año del modelo: 2017
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (4); 1 párrafos opcionales señalados; 8 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que el acusado se conforma con la pena solicitada por la acusación y el fiscal y solicita la suspensión de la ejecución de la pena, en un procedimiento abreviado por delito por falsedad en documento privado del artículo 395 CP por haber suplantado la identidad de otra persona en una red social.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a del Ilustre Colegio de procuradores de [COLEGIO], con nº de colegiado [Nº DE COLEGIADO/A] y con despacho profesional abierto en [LOCALIDAD], en representación del/de la acusado/a D./Dña. [NOMBRE Y APELLIDOS], en el procedimiento abreviado número [Nº DE PROCEDIMIENTO], por el supuesto delito de falsedad en documento privado del art. 395 CP, por usurpación de identidad, comparecen ante este órgano judicial y, como mejor proceda en derecho,

DICEN: [COMPLETAR]

Que, conforme al Protocolo de conformidades suscrito entre la Fiscalía General del Estado y el Consejo General de la Abogacía de fecha 1 de abril de 2009 (1) y el art. 784.3 LECRIM, en relación con el art. 787 LECRIM (hasta el 2/4/2025) art. 787 ter LECRIM (desde el 3/4/2025), se formula escrito de conformidad con los hechos calificados de delito de falsedad en documento privado por usurpación de identidad del art. 395 CP, en relación con el art. 390 CP. (2)

En este sentido, la defensa se conforma con la petición formulada por la Fiscalía a la pena de [PENA] de prisión (3) a ratificar en la audiencia preliminar del art. 785 LECRIM (desde el 3/4/2025).

[OPCIONAL — incluir si procede]

Se solicita se conceda la suspensión de la ejecución de la pena del art. 80 CP y ss que por la defensa se interesa con ocasión del presente escrito, por concurrir los requisitos legales, al no existir antecedentes penales. (4)

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita, tenga por evacuado el trámite por la conformidad de la defensa y por interesada la medida de suspensión de la ejecución de la pena.

Es de Justicia que pido en [LUGAR]

Firma de Abogado/a:	Firma de acusado/a:

NOTAS DEL FORMULARIO

(1) En base al protocolo de conformidades suscrito entre la Fiscalía General del Estado y el Consejo General de la Abogacía de fecha 1 de abril de 2009 se puede presentar escrito del abogado defensor antes del señalamiento de juicio oral incluso después de evacuado el trámite de calificación.

(2) Se ha intentado ubicar la persecución de este tipo de hechos en el delito del art. 401 CP, que sanciona al que usurpare el estado civil de otro. No obstante, la doctrina y la jurisprudencia han puesto de manifiesto las serias dificultades para perseguir estos hechos antes expuestos por este tipo penal. Y ello porque, aunque aparentemente se trataría de una usurpación de la identidad de otra persona para crear ese perfil de otro, la jurisprudencia lo relaciona con la usurpación del "estado civil", que no se produce en estos supuestos. Nótese que si se tratara de un perfil falso de alguien que no existe no habría problema, porque el autor está creando un perfil falso de una identidad supuesta para enmascararse en esa identidad para que no se conozca su autoría.

En estos casos podría acudirse a la vía de considerar los supuestos de suplantación de identidad como un delito de falsificación de documento del art. 395 CP. Y ello porque los servicios prestados por Internet suelen estar soportados por un contrato mercantil, y la página web no deja de ser un documento, aunque sea electrónico, por lo que el falseamiento de los datos implica que se ha falsificado un documento mercantil. Además, el art. 26 CP considera documento todo soporte material que exprese o incorpore datos, hechos o narraciones con eficacia probatoria o cualquier otro tipo de relevancia jurídica, y, por lo tanto, no solo el documento papel, sino también los archivos electrónicos, han de ser considerados documentos, al contener información con aquellas características.

Se configura la creación de un perfil de una red social como un "archivo electrónico", y, por consecuencia, como un documento, de tal manera que si creamos ese perfil a nombre de otra persona se estará actuando de forma falsaria y faltando a la verdad en la identidad de la persona que ha abierto ese perfil, y se hace pasar por ella, por lo que no tendrá cabida en el art. 401 CP por no suplantarse "el estado civil", pero sí que se estará cometiendo una falsedad en "archivo electrónico". Así lo ha entendido la Audiencia Provincial de Madrid en su Auto AP Madrid 461/2017, de 25 de mayo, Rec. 706/2017.

Para averiguar esta autoría se hace precisa la intervención de la Brigada de Investigación Tecnológica es la Unidad policial destinada a responder a los retos que plantean las nuevas formas de delincuencia. Pornografía infantil, estafas y fraudes por Internet, fraudes en el uso de las comunicaciones, ataques cibernéticos, piratería...

La Brigada de Investigación Tecnológica está encuadrada en la Unidad de Delincuencia Económica y Fiscal (UDEF) que es el órgano de la Dirección General de la Policía y de la Guardia Civil encargado de la investigación y persecución de las actividades delictivas, de ámbito nacional e internacional, en materia de delincuencia económica y fiscal, así como la coordinación operativa y apoyo técnico a las respectivas Unidades Territoriales.

Podría ocurrir que a la hora de acceder a determinados datos para conocer la autoría la brigada de delitos tecnológicos necesitara una orden judicial por la vía de los arts. 588 sexies a y ss LECRIM, introducidos por la LO 13/2015, para poder conseguir pruebas en casos de delitos cometidos por medio de la informática.

(3) La defensa puede llegar a pactar una conformidad con la fiscalía y acusación y bajar a la pena mínima de 6 meses de prisión.

(4) Es importante instar ya ambos la petición de suspensión de ejecución de la pena con el apoyo de la fiscalía para garantizarla y evitar el ingreso en prisión.

================================================================================
