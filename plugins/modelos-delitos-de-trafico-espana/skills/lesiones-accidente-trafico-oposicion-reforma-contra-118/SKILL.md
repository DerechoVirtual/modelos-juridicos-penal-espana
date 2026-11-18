---
name: lesiones-accidente-trafico-oposicion-reforma-contra-118
description: "Redacta el escrito «Lesiones en accidente de tráfico: oposición a la reforma contra el sobreseimiento» (formulario 118 de seguridad vial, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Lesiones en accidente de tráfico: oposición a la reforma contra el sobreseimiento

> Formulario 0118 del plugin **Seguridad vial** · revisado el 17-11-2026.

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

- El argumento de la segunda alegación se apoya en la STS 421/2020, anterior a la LO 11/2022 (BOE-A-2022-14965), que reputa en todo caso imprudencia menos grave la causada por una infracción grave de tráfico determinante (art. 152.2 CP); el escrito debe centrarse en negar la infracción o su carácter determinante.

## Nota explicativa: puntualizaciones de la revisión

La nota explicativa de este formulario se ha revisado en el BOE. Tenlo en cuenta al redactar:

- Desde la LO 11/2022 (vigente desde el 15-9-2022), el art. 152.2, párrafo segundo, CP considera en todo caso imprudencia menos grave la que, sin ser grave, se debe de forma determinante a una infracción grave de las normas de tráfico, circulación de vehículos y seguridad vial, y obliga a valorarlo en resolución motivada. La impugnación debe descartar expresamente esa infracción grave. Este delito solo es perseguible mediante denuncia de la persona agraviada.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión. Empieza con una nota explicativa (para qué sirve el escrito y cuándo se usa), revisada en el BOE: léela antes de redactar, pero no la copies en el escrito.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] FECHA (3 veces)
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «… confirmando la resolución recurrida. En»

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- arts. 222 y 766 de la LECrim
- art. 779.1 de la LECrim
- artículos 269, 313 y 779 de la LECrim
- art. 152.2 del Código Penal
- artículo 25 del Real Decreto Legislativo 6/2015
- arts. 142 y 152 CP
- artículo 152 CP

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

### Formulario 0118 · Lesiones en accidente de tráfico: oposición a la reforma contra el sobreseimiento

- Año del modelo: 2023
- Revisión 17-11-2026: 1 puntualizaciones normativas añadidas en el texto; 7 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)
- Avisos de la revisión: El argumento de la segunda alegación se apoya en la STS 421/2020, anterior a la LO 11/2022 (BOE-A-2022-14965), que reputa en todo caso imprudencia menos grave la causada por una infracción grave de tráfico determinante (art. 152.2 CP); el escrito debe centrarse en negar la infracción o su carácter determinante.
- Nota explicativa incorporada desde la colección Procesal (formulario 107) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Escrito por el que el investigado en diligencias previas impugna el recurso de la parte denunciante lesionada en un accidente de tráfico, presentado contra el auto de sobreseimiento puesto que, conforme a lo dispuesto en los artículos 269, 313 y 779 de la LECrim, el Juez considera que los hechos no son constitutivos de delito y la práctica de diligencias prolongaría innecesariamente la causa. Se impugnan las consideraciones del recurso en base a que no concurre una conducta negligente que pueda ser calificada como imprudencia menos grave, exigible para la relevancia penal de los hechos en el art. 152.2 del Código Penal.

---

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D/Dª [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, actuando en representación de D/Dª [NOMBRE Y APELLIDOS], según consta acreditado en las diligencias previas número [Nº DE PROCEDIMIENTO], seguidas ante ese órgano judicial, comparezco y como proceda en Derecho, DIGO:

Que el día [FECHA] se ha dado traslado a esta parte del escrito de interposición de recurso de reforma formulado por la parte denunciante contra el auto de sobreseimiento de fecha [FECHA], por lo que, por medio del presente escrito y al amparo de lo dispuesto en los arts. 222 y 766 de la LECrim, y preceptos concordantes, formulo IMPUGNACIÓN del recurso de reforma, en base a los siguientes,

MOTIVOS

PRIMERO.- El auto recurrido acuerda el sobreseimiento de las diligencias previas por no ser los hechos constitutivos de infracción penal, el cual se dicta una vez realizadas todas las diligencias de instrucción, al amparo de lo dispuesto en el art. 779.1 de la LECrim, expresando motivadamente las razones por las que no concurre responsabilidad penal en los hechos denunciados por la parte recurrente, por lo que el recurso de reforma interpuesto por la denunciante debe ser desestimado.

La resolución que pone fin a la instrucción se ajusta a derecho, puesto que se dicta una vez se han practicado todas las diligencias necesarias para el esclarecimiento de los hechos, debiendo impugnarse la pretensión de la recurrente de la práctica de nuevas diligencias, las cuales que resultan totalmente innecesarias.

La jurisprudencia ha expresado que la finalidad que el ordenamiento jurídico atribuye a la instrucción penal no es otra que la de aportación de los datos relevantes que respecto de los hechos objeto de la denuncia o querella resultan necesarios para valorar si los mismos poseen trascendencia penal; por lo que no asiste al denunciante un derecho a agotar la instrucción, pues, el derecho a la tutela judicial puede satisfacerse igualmente a través del sobreseimiento y archivo de la causa. Ello procede cuando, como en este caso y de conformidad con lo dispuesto en los artículos 269, 313 y 779 de la LECrim, el Juez considera que los hechos no son constitutivos de delito y la práctica de diligencias no harían sino prolongar innecesariamente la causa, máxime tomando en consideración el carácter fragmentario que posee el derecho penal sujeto al principio de legalidad y tipicidad.

De las diligencias de investigación practicadas resulta que el peatón denunciante lesionado, cruzaba por un lugar inadecuado de la vía, extremo ratificado tanto por el investigado, como el testigo que lo observó y por el propio denunciante, verificado sobre la base de que el vehículo se hallaba pasado el paso de peatones, tal como se recoge en el atestado de la policía local. Las fotografías del lugar son lo suficientemente esclarecedoras al respecto. Igualmente lo es que dicho peatón denunciante cruzó de derecha a izquierda, lo que supone que lo hizo de forma sorpresiva para el conductor del vehículo. Asimismo, los agentes manifiestan en el atestado que la velocidad a la que circulaba el vehículo era muy escasa, lo que se corresponde con que el vehículo no sufrió ningún daño.

En estas condiciones, la proposición de nuevas diligencias de declaración testifical y pericial técnica de la forma en que ocurrió el accidente carece de sentido, máxime cuando existe un informe técnico policial que recoge extensamente todas las circunstancias del accidente.

La jurisprudencia ha reiterado que el derecho a la práctica de diligencias instructoras que la ley otorga a las partes procesales no constituye un derecho absoluto, incondicionado e ilimitado, que obligue al Juez a practicar todas las solicitadas por las partes, pues únicamente pueden exigirse las que, en prudente ponderación, quepa estimar necesarias y suficientes a los fines instructores, siempre que, además por tener directa relación con el objeto del procedimiento, resulten pertinentes, habiéndose motivado en el auto recurrido las razones por las que no son necesarias nuevas diligencias, al haber finalizado la fase de instrucción, por lo que el auto se ajusta a lo que dispone el art. 779.1 de la LECrim.

SEGUNDO.- Se impugnan, asimismo, las consideraciones del recurso relativas a la culpa de mi representado/a, puesto que, en ningún caso, concurre una conducta negligente que pueda ser calificada como imprudencia menos grave, la cual es exigible para la relevancia penal de los hechos en el art. 152.2 del Código Penal.

Según los hechos que recoge el auto recurrido en reforma, en modo alguno se puede encuadrar la acción de mi representado/a, conductor/a del vehículo, en una infracción de las normas de circulación. Cuando aconteció el accidente, el/la denunciante ya había rebasado el paso de peatones, su presencia fue sorpresiva para mi representado/a, quien circulaba a una velocidad moderada, habiendo irrumpido el peatón por el medio de la calzada, cuando tenía un paso de peatones distante a apenas diez metros, según se recoge en el croquis levantado por los agentes de tráfico.

El artículo 25 del Real Decreto Legislativo 6/2015, de 30 de octubre, sobre Tráfico, Circulación de Vehículos a Motor y Seguridad Vial, establece que el conductor de un vehículo tiene preferencia de paso respecto de los peatones, salvo, entre otros supuestos, en los pasos para peatones. Por tanto, podría encuadrarse en una imprudencia menos grave si mi representado no hubiera respetado el paso de peatones, pero no es el caso, en tanto que el peatón irrumpió en la calzada de forma inopinada y por lugar inadecuado.

La Sentencia del Pleno de la Sala Segunda del Tribunal Supremo número 421/2020, de 22 de julio, recoge expresamente que es necesario que se aprecie una infracción grave de la ley (RDLeg 6/2015, de 30 de octubre), para que pueda darse un caso de imprudencia menos grave a los efectos de los arts. 142 y 152 CP. Incluso, se afirma que la mera presencia de una infracción grave de tráfico, según la catalogación administrativa, no significa que la imprudencia haya de ser calificada de menos grave [NOTA DE REVISIÓN: Criterio superado por la LO 11/2022: los arts. 142.2 y 152.2 CP reputan en todo caso imprudencia menos grave la no calificada como grave en la que haya sido determinante una infracción grave de tráfico. Fuente: Código Penal, BOE-A-1995-25444, arts. 142.2 y 152.2 (LO 11/2022, BOE-A-2022-14965).]"

Mi representado en ningún momento cometió ninguna infracción de tráfico, conforme se razona ampliamente en el auto de sobreseimiento, por lo que no existe ningún indicio del que se infiera que puedan ser los hechos constitutivos de imprudencia menos grave del artículo 152 CP.

TERCERO.- En definitiva, resulta improcedente la pretensión de la recurrente de que se mantenga abierto el proceso penal o que se transforme en un proceso por delito, cuando, como en el caso, no existe ningún elemento que determine indiciariamente que los hechos puedan ser constitutivos de infracción penal.

La mera presentación de denuncia o querella no obliga al órgano instructor a proceder a la incoación de un proceso penal ni a la práctica de unas determinadas diligencias. Por el contrario, el auto recurrido cumple los mandatos de la jurisprudencia constitucional, cuando establece que el Juez, cuando aprecie de forma evidente que los hechos denunciados carecen de relevancia penal, debe realizar, con la mayor premura, las actuaciones necesarias para el inmediato archivo de la causa, según se recoge, entre otras muchas, en la STC núm. 138/1997, de 22 de julio.

Por tanto, la decisión de sobreseimiento es totalmente conforme a derecho, por lo que solicitamos que se desestime el recurso de reforma interpuesto, confirmando la resolución recurrida en todos sus extremos.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito y, en su virtud, por impugnado el recurso de reforma interpuesto por la parte acusadora contra el auto de sobreseimiento de fecha [FECHA], solicitando que se acuerde su desestimación, confirmando la resolución recurrida.

En [COMPLETAR]

Firma de Abogado/a	Firma de Procurador/a

================================================================================

---

#### Notas al pie

[NOTA DE REVISIÓN: Desde la LO 11/2022 (vigente desde el 15-9-2022), el art. 152.2, párrafo segundo, CP considera en todo caso imprudencia menos grave la que, sin ser grave, se debe de forma determinante a una infracción grave de las normas de tráfico, circulación de vehículos y seguridad vial, y obliga a valorarlo en resolución motivada. La impugnación debe descartar expresamente esa infracción grave. Este delito solo es perseguible mediante denuncia de la persona agraviada.]
