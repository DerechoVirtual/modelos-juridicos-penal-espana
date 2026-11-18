---
name: agresion-sexual-casacion-contra-denegacion-revision-79
description: "Redacta el escrito «Agresión sexual: casación contra la denegación de la revisión de condena» (formulario 79 de delitos sexuales, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Agresión sexual: casación contra la denegación de la revisión de condena

> Formulario 0079 del plugin **Delitos sexuales** · revisado el 17-11-2026.

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

- La LO 4/2023 (BOE-A-2023-10213) restableció desde el 29-4-2023 penas más altas: violación con violencia, intimidación o voluntad anulada, de seis a doce años (art. 179.2 CP). La rebaja a cuatro años solo cabe aplicando la LO 10/2022 como ley intermedia más favorable a hechos anteriores (art. 2.2 CP; DT 1.ª y 2.ª LO 4/2023).

## Nota explicativa: puntualizaciones de la revisión

La nota explicativa de este formulario se ha revisado en el BOE. Tenlo en cuenta al redactar:

- La LO 4/2023 (BOE-A-2023-10213), vigente desde el 29-4-2023, volvió a reformar el art. 179 CP: la violación se castiga con prisión de 4 a 12 años (179.1) y de 6 a 12 años si hay violencia o intimidación o la víctima tiene anulada su voluntad (179.2). La comparación para determinar la ley más favorable (art. 2.2 CP) debe incluir también esta redacción.
- La LO 10/2022 no tenía régimen transitorio de revisión de sentencias (solo una disposición transitoria única sobre medidas). Las disposiciones transitorias 1.ª y 2.ª de la LO 4/2023 regulan la revisión, pero solo por aplicación de esa ley.
- El art. 848 LECrim solo admite casación contra los autos para los que la ley lo autorice de modo expreso, y contra determinados autos definitivos de las Audiencias Provinciales o de la Audiencia Nacional. Conviene justificar en el escrito por qué el auto del TSJ es recurrible.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión. Empieza con una nota explicativa (para qué sirve el escrito y cuándo se usa), revisada en el BOE: léela antes de redactar, pero no la copies en el escrito.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] NOMBRE Y APELLIDOS
- [ ] Nº (6 veces)
- [ ] LOCALIDAD (4 veces)
- [ ] FECHA (6 veces)
- [ ] PENA
- [ ] LUGAR
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…unales, en nombre y representación de D.»; «… de fecha [FECHA] dictada por la Sección»

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículos 855 y 856 de la LECrim
- artículos 847.1 b) y 848 de la LECrim
- art. 2.2 del Código Penal
- art. 179 del Código Penal
- art. 9.3 CE
- art. 2.2 CP
- Ley Orgánica 10/2022

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

### Formulario 0079 · Agresión sexual: casación contra la denegación de la revisión de condena

- Año del modelo: 2023
- Revisión 17-11-2026: 1 puntualizaciones normativas añadidas en el texto; 19 campos de relleno marcados en blanco; 1 huecos del original que se habían perdido sin marca, marcados (NOMBRE Y APELLIDOS)
- Avisos de la revisión: La LO 4/2023 (BOE-A-2023-10213) restableció desde el 29-4-2023 penas más altas: violación con violencia, intimidación o voluntad anulada, de seis a doce años (art. 179.2 CP). La rebaja a cuatro años solo cabe aplicando la LO 10/2022 como ley intermedia más favorable a hechos anteriores (art. 2.2 CP; DT 1.ª y 2.ª LO 4/2023).
- Nota explicativa incorporada desde la colección Procesal (formulario 82) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Recurso de casación presentado por condenado por agresión sexual, contra auto del TSJ resolviendo recurso de apelación en el sentido de confirmar el auto de la AP que resolvió no revisar la condena, como consecuencia de la aplicación retroactiva de la LO 10/2022, de garantía integral de la libertad sexual, por ser más favorable al prever una pena inferior para el delito del art. 179 CP que la vigente en el momento de cometer los hechos.

---

A la Sala Segunda del Tribunal Supremo

D./Dª. [NOMBRE Y APELLIDOS], Procurador/a de los tribunales, en nombre y representación de D. [COMPLETAR], como acredito con la escritura de poder que acompaño, en el recurso de casación preparado contra el Auto núm. [Nº], dictado por el Tribunal Superior de Justicia de [LOCALIDAD], de fecha [FECHA], DIGO:

Que, por medio del presente escrito y en virtud de la representación que ostento, formalizo el RECURSO DE CASACIÓN alegando al efecto los siguientes hechos y fundamentos de derecho:

ANTECEDENTES DE HECHO

PRIMERO.- La Sentencia núm. [Nº], de fecha [FECHA] dictada por la Sección [COMPLETAR] de la Audiencia Provincial de [LOCALIDAD], condenó a mi representado como autor de un delito de agresión sexual, a la pena de [Nº] años de prisión.

SEGUNDO.- Una vez entrada en vigor la Ley Orgánica 10/2022, de 6 de septiembre, de garantía integral de la libertad sexual, esta parte, entendiendo que esta Ley supone un efecto favorable para mi representado, solicitó la revisión de la condena.

TERCERO.- La Audiencia Provincial, mediante Auto núm. [Nº] de fecha [FECHA] resolvió no revisar dicha condena.

CUARTO.- Contra el anterior Auto se interpuso recurso de apelación, que el Tribunal Superior de Justicia de [LOCALIDAD] resolvió, mediante Auto núm. [Nº] de fecha [FECHA], en el sentido de confirmar el Auto previo de la Audiencia Provincial.

QUINTO.- Disconforme con el sentido del fallo, esta parte preparó recurso de casación mediante escrito autorizado por abogado y procurador y presentado ante la Sala de lo Civil y Penal del Tribunal Superior de Justicia de [LOCALIDAD], dentro de los cinco días siguientes al de la última notificación de la resolución a las representaciones procesales, a tenor de los artículos 855 y 856 de la LECrim.

FUNDAMENTOS DE DERECHO

PRIMERO.- Contra la anterior resolución cabe recurso de casación, por infracción de ley, al amparo de los artículos 847.1 b) y 848 de la LECrim.

SEGUNDO.- El TS ha admitido el recurso de casación contra este tipo de resoluciones de revisión de condena. Véase, a estos efectos, la STS núm. 412/2012 de 21 mayo, que manifiesta que «esas resoluciones han de gozar del mismo régimen de recursos que la sentencia, a la que afectan y complementan de forma sobrevenida».

TERCERO.- En cuanto al fondo del asunto, al amparo de lo dispuesto en el art. 2.2 del Código Penal, se solicita la aplicación retroactiva del art. 179 del Código Penal, en su modificación dada por la Ley Orgánica 10/2022, de 6 de septiembre, por ser más favorable respecto de la redacción anterior, vigente al momento de producirse los hechos denunciados, que es la aplicada en la sentencia recurrida.

El motivo se insta amparado en dichos preceptos, al haber entrado en vigor la reforma operada por la citada Ley Orgánica 10/2022, con posterioridad al dictado de sentencia condenatoria, y habida cuenta que ha modificado las penas a imponer por el delito por el que resultó condenado mi representado, siendo una legislación más favorable para los hechos que fueron objeto de condena en la sentencia que se recurre.

La doctrina constitucional recogida en la STC 215/1998, de 11 de noviembre, declara que la retroactividad de la ley penal más favorable es un principio reconocido constitucionalmente a partir de una interpretación "a contrario" del art. 9.3 CE, y añade la STS de 25 de junio de 2012 (Recurso núm. 1432/2011) que el principio de retroactividad de las disposiciones penales más favorables alcanza en nuestro ordenamiento penal incluso a las sentencias ya firmes que no estén totalmente ejecutadas, según lo establecido en el art. 2.2 del Código Penal, por lo que resulta procedente la revisión de condena en sede de recurso devolutivo como aquí se pretende.

El TS se ha pronunciado sobre la aplicación de Ley Orgánica 10/2022 en la STS 930/2022, de 30 de noviembre, Rec. 2811/2020, explicando que la acomodación de la pena al nuevo texto penal tras la LO 10/2022 es obligatoria por aplicarse la retroactividad de la ley penal más favorable al reo en virtud de ley posterior más beneficiosa, (art. 2.2 CP), lo cual alcanza a un proceso de revisión de penas, no solo a las que se encuentren en fase de ejecución, sino, también, a las que se encuentren en fase de dictado de sentencia, bien en plena terminación de juicio oral, bien en virtud de resolución de recurso de apelación o de recurso de casación, valorando si la pena a imponer puede ser más beneficiosa. Dice también que la comparativa de la normativa debe hacerse en su conjunto, no por partes.

CUARTO.- Pues bien, en la sentencia se impuso a mi representado la pena de prisión mínima imponible de conformidad con la legislación vigente en la fecha de los hechos (seis años de prisión) y esa pena mínima es ahora de cuatro años de prisión [NOTA DE REVISIÓN: Desde el 29-4-2023 la LO 4/2023 castiga con seis a doce años la violación con violencia, intimidación o voluntad anulada (art. 179.2 CP). El marco de cuatro a doce años de la LO 10/2022 (hoy art. 179.1) solo opera como ley intermedia más favorable para hechos anteriores a esa fecha. Fuente: LO 4/2023, BOE-A-2023-10213, art. único.cuatro y DT 1.ª; Código Penal, BOE-A-1995-25444, arts. 2.2 y 179.], según el art. 179 del Código Penal, tras la modificación operada por Ley Orgánica 10/2022.

La sentencia que se recurre justifica la determinación de la pena en su grado mínimo en la apreciación de la atenuante analógica de dilaciones indebidas, sin concurrencia de agravantes, y en las circunstancias del hecho, lo que hizo que la pena se individualizara en su mínimo legal.

Con el nuevo marco penológico debe ajustarse la pena de prisión a ese nuevo mínimo legal de cuatro años, por imperio del principio de retroactividad de la ley penal más favorable establecido en el art. 2.2 del Código Penal, por lo que se solicita, subsidiariamente, la imposición de una pena de cuatro años de prisión para el caso de desestimarse la pretensión principal de absolución sostenida por esta representación.

Por todo ello,

SUPLICO A LA SALA:

que tenga por presentado este escrito y sus copias y, en su virtud, por interpuesto el RECURSO DE CASACIÓN contra el Auto núm. [Nº] de fecha [FECHA] y, previos los trámites legales, revoque el Auto recaído, y dicte otra por la que se condene a mi representado a la pena de [PENA].

Es justicia que pido, en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a

================================================================================

---

#### Notas al pie

[NOTA DE REVISIÓN: La LO 4/2023 (BOE-A-2023-10213), vigente desde el 29-4-2023, volvió a reformar el art. 179 CP: la violación se castiga con prisión de 4 a 12 años (179.1) y de 6 a 12 años si hay violencia o intimidación o la víctima tiene anulada su voluntad (179.2). La comparación para determinar la ley más favorable (art. 2.2 CP) debe incluir también esta redacción.]

[NOTA DE REVISIÓN: La LO 10/2022 no tenía régimen transitorio de revisión de sentencias (solo una disposición transitoria única sobre medidas). Las disposiciones transitorias 1.ª y 2.ª de la LO 4/2023 regulan la revisión, pero solo por aplicación de esa ley.]

[NOTA DE REVISIÓN: El art. 848 LECrim solo admite casación contra los autos para los que la ley lo autorice de modo expreso, y contra determinados autos definitivos de las Audiencias Provinciales o de la Audiencia Nacional. Conviene justificar en el escrito por qué el auto del TSJ es recurrible.]
