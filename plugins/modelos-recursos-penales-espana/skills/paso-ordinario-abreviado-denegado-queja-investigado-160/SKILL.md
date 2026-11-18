---
name: paso-ordinario-abreviado-denegado-queja-investigado-160
description: "Redacta el escrito «Paso del ordinario al abreviado denegado: queja del investigado» (formulario 160 de recursos penales, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Paso del ordinario al abreviado denegado: queja del investigado

> Formulario 0160 del plugin **Recursos penales** · revisado el 17-11-2026.

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

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión. Empieza con una nota explicativa (para qué sirve el escrito y cuándo se usa), revisada en el BOE: léela antes de redactar, pero no la copies en el escrito.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] LOCALIDAD
- [ ] NOMBRE Y APELLIDOS (5 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] SEDE
- [ ] NÚMERO
- [ ] FECHA (4 veces)
- [ ] LUGAR
- [ ] DÍA
- [ ] MES
- [ ] AÑO

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 218 de la LECrim
- art. 760 de la LECrim

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

### Formulario 0160 · Paso del ordinario al abreviado denegado: queja del investigado

- Año del modelo: 2023
- Revisión 17-11-2026: 12 campos de relleno marcados en blanco; 2 huecos del original que se habían perdido sin marca, marcados (NOMBRE Y APELLIDOS)
- Nota explicativa incorporada desde la colección Procesal (formulario 124) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Escrito por el que se presenta recurso de queja, en base al art. 218 LECRIM, contra la desestimación de la solicitud de transformación de procedimiento ordinario a procedimiento abreviado, conforme al art. 760 LECRIM. Recuerde que....

---

A la Audiencia Provincial de [LOCALIDAD]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, actuando en representación de D./Dña. [NOMBRE Y APELLIDOS], investigado/a en el Sumario número [Nº DE PROCEDIMIENTO] seguido ante la Sección de Instrucción del Tribunal de Instancia de [SEDE] plaza nº [NÚMERO], según acredito mediante escritura de poder que acompaño y solicito me sea devuelta previo testimonio en el Rollo, comparezco y como proceda en Derecho, DIGO:

Que en fecha [FECHA] ha sido notificada esta representación del auto de fecha [FECHA] dictado por el órgano judicial que desestimaba el recurso de reforma contra la denegación del cambio de este procedimiento a abreviado (acompaño como documento número 1 copia de la mencionada resolución).

Que, mediante el presente escrito, y al amparo de lo dispuesto en el art. 218 de la LECrim, interpongo recurso de QUEJA ante la Sala, en base a los siguientes,

MOTIVOS

PRIMERO.- Con fecha [FECHA] se incoó el sumario de referencia por un presunto delito de homicidio en grado de tentativa, resultando investigado/a mi representado/a, en base a unas lesiones con arma blanca que presentaba D./Dña. [NOMBRE Y APELLIDOS]

SEGUNDO.- Seguidos los trámites legales, en fecha [FECHA] fue reconocido el/la lesionado/a por los Médicos Forenses D./Dña. [NOMBRE Y APELLIDOS] y D. [NOMBRE Y APELLIDOS] que emitieron dictamen en el sentido de que el/la lesionado/a presentaba diversas heridas por arma blanca en los brazos y piernas, así como herida con 1 cm. de profundidad a nivel de hombro izquierdo, tardando en curar dichas lesiones treinta y cinco días (Acompañamos como documento número 2 copia del referido dictamen).

Tal como es de ver en dicho dictamen, se afirma por ambos peritos que, en ningún caso, las heridas pudieron afectar a órganos vitales ni pusieron en peligro la vida del lesionado, a lo que hay que añadir que las heridas se produjeron en el curso de una reyerta, tal como ha reconocido el propio perjudicado en su declaración (acompañamos como documento número 3 copia de la declaración del perjudicado).

TERCERO.- Conforme a los anteriores antecedentes, es indudable que el hecho delictivo objeto de este proceso debe seguirse por los trámites del procedimiento abreviado, conforme dispone el art. 760 de la LECrim, puesto que, en ningún caso puede hablarse de homicidio intentado, ya que no se reúne ninguno de los elementos exigidos jurisprudencialmente para apreciar la tentativa en el delito contra la vida.

Así, la jurisprudencia, en sentencia del Tribunal Supremo de fecha 24 de marzo de 2005, 7 de marzo de 2006 y 29 de enero de 2009, entre otras, viene concediendo singular relevancia para apreciar el animus necandi a la región del cuerpo elegida para agredir, circunstancias del hecho, así como relaciones personales entre agresor y agredido.

En este caso, resulta palmario que mi representado/a y el/la perjudicado/a no se conocían, enzarzándose en una reyerta de forma mutuamente aceptada, donde ambos esgrimieron armas blancas tal como reconocen en sus declaraciones. De las regiones del cuerpo donde mi representado dirigió los golpes, brazos y piernas, y de dichas circunstancias se infiere claramente que estamos ante un posible delito de lesiones, por lo que debe acomodarse el proceso a los trámites del abreviado, tal como hemos solicitado.

Por lo expuesto,

SUPLICO A LA SALA:

Que tenga por presentado este recurso de queja y, previos los trámites legales, dicte auto por el cual se acuerde se sigan las diligencias por los trámites del procedimiento abreviado.

En [LUGAR], a [DÍA] de [MES] de [AÑO].

Firma de Abogado/a	Firma de Procurador/a

================================================================================
