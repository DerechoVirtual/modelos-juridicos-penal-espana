---
name: victima-menor-discapacitada-videoconferencia-juicio-oral-354
description: "Redacta el escrito «Víctima menor o discapacitada: videoconferencia en el juicio oral (hasta el 19 de marzo de 2024)» (formulario 354 de víctimas y justicia restaurativa, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Víctima menor o discapacitada: videoconferencia en el juicio oral (hasta el 19 de marzo de 2024)

> Formulario 0354 del plugin **Víctimas y justicia restaurativa** · revisado el 17-11-2026.

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

## Nota explicativa: puntualizaciones de la revisión

La nota explicativa de este formulario se ha revisado en el BOE. Tenlo en cuenta al redactar:

- El art. 707 LECrim (redacción LO 8/2021) sigue vigente; la indicación «hasta el 19 de marzo de 2024» del título no significa que se haya derogado. Desde el 20-3-2024, la declaración telemática de las víctimas menores de edad o con discapacidad tiene además apoyo en el art. 258 bis.3.a) LECrim (RDL 6/2023).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión. Empieza con una nota explicativa (para qué sirve el escrito y cuándo se usa) y acaba con sus notas al pie, revisadas en el BOE: léela antes de redactar, pero no la copies en el escrito.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] Nº
- [ ] LOCALIDAD (3 veces)
- [ ] NOMBRE Y APELLIDOS (5 veces)
- [ ] NÚMERO
- [ ] DELITO
- [ ] FECHA (2 veces)
- [ ] LUGAR
- [ ] Otros 3 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…cia Señala el art. 707 LECRIM párrafo 2º»; «…to en la ley". Y en el apartado 3 añade:»; «…se acuerde la citación para el juicio de»

## Elecciones que hay que hacer

- este juzgado / esta sala
- menor de 18 años de edad / persona con discapacidad necesitada de especial protección
- menor de 18 años / con discapacidad
- AL TRIBUNAL / A LA SALA

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 707 LECRIM
- art. 707 LECRIM
- art. 731 bis LECRIM
- art. 229 LOPJ
- art. 229.2 LOPJ

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

### Formulario 0354 · Víctima menor o discapacitada: videoconferencia en el juicio oral (hasta el 19 de marzo de 2024)

- Año del modelo: 2021
- Revisión 17-11-2026: 1 llamadas a nota sin texto retiradas; 6 desplegables y casillas convertidos en elección en blanco; 1 bloques de alternativas señalados; 16 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 2 menciones a juzgados penales actualizadas (LO 1/2025); 2 menciones a órganos y cargos actualizadas (LO 1/2025; LO 7/2015)
- Nota explicativa incorporada desde la colección Procesal (formulario 162) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Escrito por el que la acusación particular, que actúa en representación de la víctima menor de 18 años o con discapacidad necesitada de especial protección, solicita que la comparecencia de la víctima en el juicio oral se haga a través de videoconferencia, conforme admite el art. 707 LECRIM, según redacción dada por la LO 8/2021, de protección integral a la infancia y la adolescencia frente a la violencia, con entrada en vigor a partir del 25 de junio de 2021.

---

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

A la Sección de lo Penal del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

A la Audiencia Provincial de [LOCALIDAD]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, en la representación que tengo acreditada de D./Dña. [NOMBRE Y APELLIDOS], acusación particular en las DP número [NÚMERO], instruidas por el Tribunal de Instancia (Sección de Instrucción) de [LOCALIDAD], y pendiente de señalamiento de juicio en [ELEGIR: este juzgado / esta sala] por el presunto delito de [DELITO], contra D./Dña. [NOMBRE Y APELLIDOS], como mejor proceda en derecho, DIGO:

Que la víctima del delito es [ELEGIR: menor de 18 años de edad / persona con discapacidad necesitada de especial protección] por quien actúa esta acusación particular como representante legal.

Que la persona [ELEGIR: menor de 18 años / con discapacidad] ha declarado ya en fase de instrucción ante el Tribunal de Instancia (Sección de Instrucción) de [LOCALIDAD] el día [FECHA].

Que esta representación ha propuesto como prueba para el juicio la declaración de la persona [ELEGIR: menor de 18 años / con discapacidad].

Que estando pendiente de la celebración de juicio y en base a lo dispuesto en párrafo segundo del artículo 707 LECRIM, conforme a la redacción dada por la LO 8/2021, de protección de la infancia y la adolescencia frente a la violencia, se interesa que para el día del juicio se proceda a citar a la persona [ELEGIR: menor de 18 años / con discapacidad] para que intervenga por videoconferencia

Señala el art. 707 LECRIM párrafo 2º [COMPLETAR]:

«Fuera de los casos previstos en el artículo 703 bis, cuando una persona menor de dieciocho años o una persona con discapacidad necesitada de especial protección deba intervenir en el acto del juicio, su declaración se llevará a cabo, cuando resulte necesario para impedir o reducir los perjuicios que para ella puedan derivar del desarrollo del proceso o de la práctica de la diligencia evitando la confrontación visual con la persona inculpada. Con este fin podrá ser utilizado cualquier medio técnico que haga posible la práctica de esta prueba, incluyéndose la posibilidad de que lo testigos puedan ser oídos sin estar presentes en la sala mediante la utilización de tecnologías de la comunicación accesible.»

El Tribunal Supremo, Sala Segunda, de lo Penal, STS 331/2019 de 27 de junio, Rec. 1376/2018 señaló que:

"Se puede recurrir al sistema previsto en el art. 731 bis LECRIM, que señala que:

"El Tribunal, de oficio o a instancia de parte, por razones de utilidad, seguridad o de orden público, así como en aquellos supuestos en que la comparecencia de quien haya de intervenir en cualquier tipo de procedimiento penal como imputado, testigo, perito, o en otra condición resulte gravosa o perjudicial, podrá acordar que su actuación se realice a través de videoconferencia u otro sistema similar que permita la comunicación bidireccional y simultánea de la imagen y sonido, de acuerdo con lo dispuesto en el apartado 3 del art. 229 LOPJ ".

Además, el art. 229.2 LOPJ dice:

"2. Las declaraciones, confesiones en juicio, testimonios, careos, exploraciones, informes, ratificación de los periciales y vistas, se llevarán a efecto ante Juez o Tribunal con presencia o intervención, en su caso, de las partes y en audiencia pública, salvo lo dispuesto en la ley".

Y en el apartado 3 añade: [COMPLETAR]

"Estas actuaciones podrán realizarse a través de videoconferencia u otro sistema similar que permita la comunicación bidireccional y simultánea de la imagen y sonido y la interacción visual, auditiva y verbal entre dos personas o grupos de personas geográficamente distantes, asegurando en todo caso la posibilidad de contradicción de las partes y la salvaguarda del derecho de defensa, cuando así lo acuerde el juez o Tribunal.

En estos casos, el Letrado/a de la Administración de Justicia del juzgado o Tribunal que haya acordado la medida acreditará desde la propia sede judicial la identidad de las personas que intervengan a través de la videoconferencia mediante la previa remisión o exhibición directa de documentación, por conocimiento personal o por cualquier otro medio procesal idóneo".

El uso de la videoconferencia permite la total conexión en los puntos de origen y destino como si estuvieran presentes en el mismo lugar, con lo que se da cumplimiento a la premisa de que se celebre la actuación judicial en unidad de acto. No se vulnera ningún principio procesal al poder dirigir las partes a los testigos las preguntas que sean declaradas pertinentes con contradicción y sin que pueda existir indefensión ni vulneración de la tutela judicial efectiva.

Además, el Estatuto de la Corte Penal Internacional aprobado en Roma el 17 de julio de 1998, cuya ratificación ha sido autorizada mediante LO 6/2000, de 4 de octubre (BOE de 5 de octubre de 2000), incorpora entre sus previsiones algunos preceptos que abren la puerta a la práctica de actos procesales conforme a las nuevas tecnologías. Del mismo modo, ya lo avalaron el Convenio de la Unión Europea relativo a la asistencia judicial en materia penal celebrado por Acto del Consejo de 29 de mayo de 2000, o la Decisión Marco del Consejo de la UE de 15 de marzo de 2001 relativa al Estatuto de la víctima en el proceso penal.

Por lo expuesto,

SUPLICO [ELEGIR: AL TRIBUNAL / A LA SALA]

Que tenga por presentado este escrito, se sirva admitirlo y se acuerde la citación para el juicio de [COMPLETAR] para intervenir el día del juicio oral por videoconferencia, facilitándose con antelación el mecanismo de conexión a llevar a cabo para su comparecencia, al haber sido propuesto como testigo para el día del juicio.

Por ser de Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a

Firma de Procurador/a

D./Dña. [NOMBRE Y APELLIDOS] 	D./Dña. [NOMBRE Y APELLIDOS]

================================================================================

---

#### Notas al pie

(1) Véase también Instrucción 3/2002 de la Fiscalía General del Estado

[NOTA DE REVISIÓN: El art. 707 LECrim (redacción LO 8/2021) sigue vigente; la indicación «hasta el 19 de marzo de 2024» del título no significa que se haya derogado. Desde el 20-3-2024, la declaración telemática de las víctimas menores de edad o con discapacidad tiene además apoyo en el art. 258 bis.3.a) LECrim (RDL 6/2023).]
