---
name: pedir-instalacion-dispositivos-tecnicos-localizacion-715
description: "Redacta el escrito «Pedir la instalación de dispositivos técnicos de localización y seguimiento» (formulario 715 de investigación tecnológica y prueba digital, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Pedir la instalación de dispositivos técnicos de localización y seguimiento

> Formulario 0715 del plugin **Investigación tecnológica y prueba digital** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (6 veces)
- [ ] COLEGIO
- [ ] LOCALIDAD
- [ ] FECHA (2 veces)
- [ ] DELITO
- [ ] LUGAR
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «…tipificado en el artículo»

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículos 311 y 776.3 LECRIM

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

### Formulario 0715 · Pedir la instalación de dispositivos técnicos de localización y seguimiento

- Año del modelo: 2017
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (1); 12 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que se solicita al juez la instalación de dispositivos de localización y seguimiento del investigado, por ser necesario para monitorizar sus movimientos y poder conocer a las personas que se relacionan con él en la comisión de los hechos delictivos.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales del Ilustre colegio de procuradores de [COLEGIO] y con despacho profesional abierto en [LOCALIDAD], en representación de D./Dña. [NOMBRE Y APELLIDOS], comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

Que con fecha [FECHA] se presentó denuncia que fue turnada a ese órgano judicial por D./Dña. [NOMBRE Y APELLIDOS] contra D./Dña. [NOMBRE Y APELLIDOS], por la comisión de un delito de [DELITO] tipificado en el artículo [COMPLETAR] CP, habiéndonos personado en las actuaciones por escrito de fecha

Que por esta parte se consideró imprescindible para el esclarecimiento de los hechos el que se trasladara al equipo de investigación de la policía judicial que realizara las investigaciones oportunas.

ALEGACIONES

ÚNICA.-

Que, tras la investigación policial, en base a los artículos 311 y 776.3 LECRIM(Para el procedimiento abreviado), se hace preciso proceder a la instalación de dispositivos de seguimiento y localización de la persona investigada para monitorizar sus movimientos en orden a poder conocer a las personas que se relacionan con ella en la comisión de los hechos objeto de denuncia y desde dónde se está cometiendo el delito o si existen copartícipes en la comisión, tal y como prevé el artículo 588 quinquies.b LECRIM.

Para ello debe identificarse por la autoridad policial el dispositivo técnico que se precise para incluirlo en la autorización judicial como prevé el artículo 588 quinquies.b 2 LECRIM. (1)

Por lo expuesto,

SUPLICO A LA SECCIÓN

Que tenga por presentado este escrito, lo admita y tenga por realizada la petición conforme a lo interesado.

Por ser de Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a
D./Dña. [NOMBRE Y APELLIDOS] 	D./Dña. [NOMBRE Y APELLIDOS]

NOTAS DEL FORMULARIO

(1) Cuando concurran acreditadas razones de necesidad y la medida resulte proporcionada, el juez competente podrá autorizar la utilización de dispositivos o medios técnicos de seguimiento y localización. No será necesario autorización judicial previa cuando concurran razones de urgencia que hagan razonablemente temer que de no colocarse inmediatamente el dispositivo o medio técnico de seguimiento y localización se frustrará la investigación. La Policía Judicial podrá proceder a su colocación, dando cuenta a la mayor brevedad posible, y en todo caso en el plazo máximo de veinticuatro horas, a la autoridad judicial, quien podrá ratificar la medida adoptada o acordar su inmediato cese en el mismo plazo. En este último supuesto, la información obtenida a partir del dispositivo colocado carecerá de efectos en el proceso.

El artículo 588 bis.b LECRIM establece que esta medida puede adoptarse de oficio, a instancia del fiscal o de la policía judicial. Ello no impide que una acusación particular pueda instarlo al juez si de esa manera puede conseguir avanzar en las diligencias de investigación. No puede privarse a la parte de ese derecho.

================================================================================
