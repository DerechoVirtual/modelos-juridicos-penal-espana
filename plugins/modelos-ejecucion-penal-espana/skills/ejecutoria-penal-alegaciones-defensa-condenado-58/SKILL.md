---
name: ejecutoria-penal-alegaciones-defensa-condenado-58
description: "Redacta el escrito «Ejecutoria penal: alegaciones de la defensa del condenado» (formulario 58 de ejecución penal, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Ejecutoria penal: alegaciones de la defensa del condenado

> Formulario 0058 del plugin **Ejecución penal** · revisado el 17-11-2026.

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

## Antes de usarlo: avisos de la revisión

El planteamiento del formulario está desfasado en algo. Corrígelo antes de redactar:

- La regla 1.ª del art. 80.2 CP cambió con la LO 1/2026 (desde el 10-4-2026): computan las condenas anteriores por delitos leves que integren un tipo agravado por multirreincidencia; deben revisarse los antecedentes del penado antes de pedir u oponerse a la suspensión.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión. Empieza con una nota explicativa (para qué sirve el escrito y cuándo se usa), revisada en el BOE: léela antes de redactar, pero no la copies en el escrito.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] Nº (3 veces)
- [ ] LOCALIDAD
- [ ] NOMBRE Y APELLIDOS
- [ ] NÚMERO
- [ ] FECHA (4 veces)
- [ ] CIRCUNSTANCIA
- [ ] LUGAR
- [ ] Otros 9 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…e tiene acreditada del/de la condenado/a»; «… a la pena de y responsabilidad civil de»; «…dades civiles en los siguientes términos»; «…n de la pena se refiera a las siguientes»; «…ad se encuentra internado/a en el Centro»; «…, tratándose de Estimando que»; «…te escrito, mi representado/a trabaja en»; «…n emitida por el Centro Penitenciario de»; «…ue, en base al art. 988 bis.1 c) LECRIM,»

## Elecciones que hay que hacer

- haber sido confirmada / no interponerse recurso contra la misma
- A LA SECCIÓN / A LA SALA

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS
- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (7)

Inclúyelos solo si encajan en los hechos:

- PRIMERA.- Que, en base al art. 988 bis.1 a) LECRIM, se interesa la suspensión de la ejecución de la pena de pr…
- SEGUNDA.-…
- TERCERA.- Que, en base al art. 988 bis.1 c) LECRIM, en el caso de que se introduzca alguna de las condiciones …
- CUARTA.- Que a mi representado/a se le apreció la atenuante de [CIRCUNSTANCIA] y en la actualidad se encuentra…
- QUINTA.- Que mi representado/a fue condenado en la sentencia arriba referenciada a una pena de localización pe…
- SEXTA.- Habida cuenta que, en este mismo procedimiento, mi representado/a ha estado en prisión provisional des…
- SÉPTIMA.- Que, en base al art. 988 bis.1 c) LECRIM, [COMPLETAR]…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 988 bis de la Ley de Enjuiciamiento Criminal
- art. 988 bis.1 a) LECRIM
- arts. 80 CP
- art. 988 bis.1 b) LECRIM
- art. 988 bis.1 c) LECRIM
- art. 83 CP
- arts. 96.2 y 102 del CP
- artículo 37 del Código Penal
- artículo 58.1 del Código Penal
- art. 988 bis LECRIM

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

### Formulario 0058 · Ejecutoria penal: alegaciones de la defensa del condenado

- Año del modelo: 2025
- Revisión 17-11-2026: 2 desplegables y casillas convertidos en elección en blanco; 2 bloques de alternativas señalados; 7 párrafos opcionales señalados; 19 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)
- Avisos de la revisión: La regla 1.ª del art. 80.2 CP cambió con la LO 1/2026 (desde el 10-4-2026): computan las condenas anteriores por delitos leves que integren un tipo agravado por multirreincidencia; deben revisarse los antecedentes del penado antes de pedir u oponerse a la suspensión.
- Nota explicativa incorporada desde la colección Procesal (formulario 53) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Escrito del condenado por el que, frente al auto de incoación de la ejecutoria penal, presenta conjuntamente: la solicitud suspensión de la pena privativa de libertad impuesta, la forma de cumplimiento de la responsabilidad civil y cualquier otra solicitud relativa a la ejecución de los pronunciamientos de la sentencia, incluida la sustitución de la pena, en su caso, conforme al art. 988 bis LECRIM, introducido por LO 1/2025, de Eficiencia de la Justicia, vigente desde el 3 de abril de 2025, aunque este escrito puede también presentarse antes de dicha fecha. Recuerde que....

---

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

A la Sección de lo Penal del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

A la Audiencia Provincial de [LOCALIDAD]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales en la representación que tiene acreditada del/de la condenado/a [COMPLETAR] en EJECUTORIA PENAL nº [NÚMERO], tras sentencia nº [Nº] de condena por delito de a la pena de y responsabilidad civil de [COMPLETAR], siendo firme por [ELEGIR: haber sido confirmada / no interponerse recurso contra la misma], comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

Que, conforme a lo preceptuado en el artículo 988 bis de la Ley de Enjuiciamiento Criminal (según redacción dada por LO 1/2025) y tras el traslado dado del auto de incoación de la ejecutoria penal en fecha [FECHA] por este órgano judicial, realizamos en plazo las siguientes:

ALEGACIONES

[OPCIONAL — incluir si procede]

PRIMERA.- Que, en base al art. 988 bis.1 a) LECRIM, se interesa la suspensión de la ejecución de la pena de prisión impuesta al concurrir los requisitos de los arts. 80 CP y ss al tratarse de la pena de y
no existir antecedentes penales
existiendo antecedentes penales mi representado se compromete a no volver a delinquir, no siendo de gravedad el delito cometido

[OPCIONAL — incluir si procede]

SEGUNDA.-

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

Que, en base al art. 988 bis.1 b) LECRIM, se han satisfecho las responsabilidades civiles impuestas en sentencia.

Que, en base al art. 988 bis.1 c) LECRIM, solicitamos el aplazamiento del pago de las responsabilidades civiles en los siguientes términos [COMPLETAR].

[OPCIONAL — incluir si procede]

TERCERA.- Que, en base al art. 988 bis.1 c) LECRIM, en el caso de que se introduzca alguna de las condiciones del art. 83 CP anudada a la suspensión de la ejecución de la pena se refiera a las siguientes [COMPLETAR].

[OPCIONAL — incluir si procede]

CUARTA.- Que a mi representado/a se le apreció la atenuante de [CIRCUNSTANCIA] y en la actualidad se encuentra internado/a en el Centro [COMPLETAR], tratándose de

Estimando que [COMPLETAR], y con fundamento en lo dispuesto en los arts. 96.2 y 102 del CP, de aplicación analógica, en base al art. 988 bis.1 c) LECRIM solicitamos que acuerde el cumplimiento de la pena de prisión impuesta en el citado centro para continuar con su tratamiento.

[OPCIONAL — incluir si procede]

QUINTA.- Que mi representado/a fue condenado en la sentencia arriba referenciada a una pena de localización permanente de [Nº] días.

Como se deduce de la documentación que se adjunta al presente escrito, mi representado/a trabaja en [COMPLETAR] y su jornada de trabajo se prolonga de lunes a viernes, por lo que el cumplimiento, en días laborables, de la pena de localización permanente le resulta gravemente perjudicial.

Por ello, y de conformidad con lo dispuesto en el artículo 37 del Código Penal, esta representación interesa que la localización permanente se cumpla durante los siguientes días festivos:

[OPCIONAL — incluir si procede]

SEXTA.- Habida cuenta que, en este mismo procedimiento, mi representado/a ha estado en prisión provisional desde el día [FECHA], hasta el día [FECHA], intereso que, de conformidad con lo dispuesto en el artículo 58.1 del Código Penal, dicho periodo de privación de libertad sufrido provisionalmente sea abonado en su totalidad, para el cumplimiento de la pena impuesta en esta Causa.

En este sentido, se informa al Juez de que ese tiempo de prisión provisional no ha sido abonado en ningún otro procedimiento, tal y como se acredita en la certificación emitida por el Centro Penitenciario de [COMPLETAR], y que se adjunta al presente escrito.

[OPCIONAL — incluir si procede]

SÉPTIMA.- Que, en base al art. 988 bis.1 c) LECRIM, [COMPLETAR]

Por lo expuesto,

SUPLICO [ELEGIR: A LA SECCIÓN / A LA SALA]:

Que tenga por presentado este escrito con sus copias, los admita y por cumplimentada la respuesta al traslado de incoación de la presente ejecutoria penal a los efectos del art. 988 bis LECRIM.

Es de Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a

================================================================================
