---
name: inhibitoria-ante-juez-violencia-sobre-mujer-375
description: "Redacta el escrito «Inhibitoria ante el Juez de Violencia sobre la Mujer» (formulario 375 de violencia de género y delitos en la familia, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Inhibitoria ante el Juez de Violencia sobre la Mujer

> Formulario 0375 del plugin **Violencia de género y delitos en la familia** · revisado el 17-11-2026.

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
- [ ] Nº (3 veces)
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] Nº DE PROCEDIMIENTO (3 veces)
- [ ] NÚMERO (3 veces)
- [ ] FECHA (5 veces)
- [ ] LUGAR
- [ ] Otros 4 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «… en el ámbito familiar por la ex cónyuge»; «…a las [Nº] horas, en la localidad de»; «… Comisaría de Policía de la localidad de»; «…haber ocurrido el suceso en la localidad»

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- arts. 26 y 759 de la LECrim
- art. 15 bis LECrim
- art. 15 bis de la LECrim
- arts. 147 y 153 del Código Penal
- art. 171.2 del Código Penal
- art. 33 de la LECrim
- art. 89.5 de la LOPJ
- art. 14.5 a) LECrim
- art. 89.5.a) LOPJ

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

### Formulario 0375 · Inhibitoria ante el Juez de Violencia sobre la Mujer

- Año del modelo: 2021
- Revisión 17-11-2026: 20 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 1 huecos del original que se habían perdido sin marca, marcados (NOMBRE Y APELLIDOS)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que se solicita a la Sección de Violencia sobre la Mujer que requiera de inhibición, conforme a los arts. 26 y 759 LECIRM, a la Sección de Instrucción a favor de la de Violencia, por tratarse de un único suceso acaecido en unidad de acto en el que median amenazas y agresiones recíprocas entre una pareja, lo que hace necesaria una tramitación conjunta.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Violencia sobre la Mujer del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, actuando en representación del investigado en esta causa D. [NOMBRE Y APELLIDOS], según tengo acreditado en estas diligencias previas número [Nº DE PROCEDIMIENTO], comparezco y, como proceda en Derecho, DIGO:

Que, mediante el presente escrito, al amparo de lo dispuesto en los arts. 26 y 759 de la LECrim., promuevo cuestión de competencia por inhibitoria, en relación al conocimiento de las diligencias previas número [Nº DE PROCEDIMIENTO] seguidas ante la Sección de Instrucción del Tribunal de Instancia de [SEDE] plaza nº [NÚMERO], en base a los siguientes

MOTIVOS

PRIMERO.- Las presentes diligencias se iniciaron por presunto delito de amenazas en el ámbito familiar por la ex cónyuge [COMPLETAR] de mi representado, sucedidas el día [FECHA] a las [Nº] horas, en la localidad de [COMPLETAR], las cuales fueron incoadas a raíz de la denuncia formulada ante el Juez al que me dirijo por parte de la presunta víctima el día [FECHA], siendo competente territorialmente por ser el Juez del domicilio de la denunciante, conforme al art. 15 bis LECrim.

El mismo día [FECHA], mi representado formuló denuncia contra su ex cónyuge por lesiones y amenazas respecto de estos mismos hechos sucedidos el día [FECHA] a las [Nº] horas, la cual fue formalizada ante la Comisaría de Policía de la localidad de [COMPLETAR], lugar donde se produjeron los hechos, que fue remitida al Tribunal de Instancia de dicha localidad, incoándose por la Sección de Instrucción plaza número [NÚMERO] las diligencias previas número [Nº DE PROCEDIMIENTO], donde se ha acordado la citación de mi representado como denunciante y de su ex cónyuge en calidad de investigada (acompaño como documento número 1 testimonio del atestado y del auto de incoación de diligencias previas).

De ello se evidencia que ambas denuncias obedecen a unos mismos hechos acaecidos, con identidad de lugar y tiempo, en los que se encuentran implicados mi representado y su ex pareja, en su doble condición de denunciantes y denunciados. Pese a haber ocurrido el suceso en la localidad [COMPLETAR], la competencia corresponde a la Sección a la que nos dirigimos, en razón del art. 15 bis de la LECrim, dado que la víctima tiene su domicilio en este partido judicial, pudiendo revestir los hechos los caracteres de un delito de lesiones de los arts. 147 y 153 del Código Penal y de amenazas del art. 171.2 del Código Penal, derivados de un mismo incidente, acaecido en unidad de acto en el que median amenazas y agresiones recíprocas, lo que hace necesaria una tramitación conjunta, de tal forma que hacen imposible el enjuiciamiento por separado, so pena de dividir la continencia de la causa, debiendo, en todo caso, prevalecer la jurisdicción especializada, según reiterada jurisprudencia expresada, entre otros, en ATS de 27 de noviembre de 2019 (Recurso núm. 20276/2019), lo que nos lleva a plantear esta inhibitoria, solicitando de la Sección de Violencia sobre la Mujer a la que nos dirigimos que reclame el conocimiento de la causa seguida ante la Sección de Instrucción del Tribunal de Instancia de [SEDE].

SEGUNDO.- A los efectos del art. 33 de la LECrim., esta parte hace constar expresamente que no se ha empleado la declinatoria.

TERCERO.- Tal como se ha expresado, esta parte entiende que la competencia para la instrucción de la causa corresponde a la Sección de Violencia sobre la Mujer, al ser jurisdicción especializada que ostenta la competencia, al ser denunciante una supuesta víctima mujer, conforme a lo que establece el art. 89.5 de la LOPJ, puesto que, como indica el ATS 17 de septiembre de 2013, Rec. 20335/2013, es claro que no cabe desglosar las denuncias cruzadas para su conocimiento por separado, al tratarse, no de hechos distintos ni producidos en diferentes momentos, sino de un único episodio o suceso con dos diferentes versiones, por lo que su conocimiento por separado rompería la continencia de la causa. Y se encuentran comprendidos en el ámbito de la competencia de la Sección de Violencia sobre la Mujer, a tenor de dispuesto en el art. 14.5 a) LECrim. y art. 89.5.a) LOPJ.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito con los documentos que se acompañan, y previos los trámites legales, dicte auto por el cual acuerde requerir de inhibición a la Sección de Instrucción plaza nº [NÚMERO], interesando remita la causa a la Sección de Violencia sobre la Mujer a la que nos dirigimos, por ser la competente para su instrucción.

En [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a

================================================================================
