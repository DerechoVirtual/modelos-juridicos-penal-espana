---
name: pedir-apertura-correspondencia-ya-intervenida-714
description: "Redacta el escrito «Pedir la apertura de la correspondencia ya intervenida» (formulario 714 de investigación tecnológica y prueba digital, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Pedir la apertura de la correspondencia ya intervenida

> Formulario 0714 del plugin **Investigación tecnológica y prueba digital** · revisado el 17-11-2026.

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
- [ ] LOCALIDAD (4 veces)
- [ ] FECHA (2 veces)
- [ ] DELITO
- [ ] FECHA DEL AUTO
- [ ] LUGAR
- [ ] Otros 4 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…tipificado en el artículo»; «…castigados con pena con límite máximo de»; «…castigados con pena con límite máximo de»; «…enó. No requieren autorización judicial:»

## Elecciones que hay que hacer

- es doloso y está castigado con pena de al menos tres años / se ha cometido en el seno de un grupo criminal / es de terrorismo

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 579 LECRIM
- artículo 584 LECRIM
- arts. 586 a 588 LECRIM

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

### Formulario 0714 · Pedir la apertura de la correspondencia ya intervenida

- Año del modelo: 2017
- Revisión 17-11-2026: restos de formato retirados; 1 rangos de artículos despegados («25 a31» → «25 a 31»); notas del formulario agrupadas al final (2); 1 desplegables y casillas convertidos en elección en blanco; 17 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 1 huecos del original que se habían perdido sin marca, marcados (FECHA DEL AUTO)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que se interesa que se procede a la apertura de la correspondencia del investigado que había sido intervenida, para lo que debe citarse al acto al investigado, en base a los arts. 584 y ss. LECRIM.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales del Ilustre colegio de procuradores de [COLEGIO] y con despacho profesional abierto en [LOCALIDAD], en representación de D./Dña. [NOMBRE Y APELLIDOS], comparezco ante este órgano judicial y como mejor proceda en derecho, DIGO:

Que con fecha [FECHA] se presentó denuncia que fue turnada a ese órgano judicial por D./Dña. [NOMBRE Y APELLIDOS] contra D./Dña. [NOMBRE Y APELLIDOS] por la comisión de un delito de [DELITO] tipificado en el artículo [COMPLETAR] CP habiéndonos personado en las actuaciones por escrito de fecha

Que por esta parte se consideró imprescindible para la investigación la medida de intervención de la correspondencia del denunciado que fue acordada por auto de fecha [FECHA DEL AUTO] y por el espacio de 3 meses.

Que mediante el presente escrito se interesa la apertura de la correspondencia intervenida (1), con base en las siguientes

ALEGACIONES

PRIMERA.- Señala el artículo 579 LECRIM que:

"1. El juez podrá acordar la detención de la correspondencia privada, postal y telegráfica, incluidos faxes, burofaxes y giros, que el investigado remita o reciba, así como su apertura o examen, si hubiera indicios de obtener por estos medios el descubrimiento o la comprobación del algún hecho o circunstancia relevante para la causa, siempre que la investigación tenga por objeto alguno de los siguientes delitos:
1.º Delitos dolosos castigados con pena con límite máximo de [COMPLETAR], al menos, tres años de prisión.
2.º Delitos cometidos en el seno de un grupo u organización criminal.
3.º Delitos de terrorismo."

SEGUNDA.- Dado que el delito que se investiga [ELEGIR: es doloso y está castigado con pena de al menos tres años / se ha cometido en el seno de un grupo criminal / es de terrorismo] se interesó se interviniera la correspondencia de todo tipo que fuera dirigida a el/la investigado/a a su domicilio sito en [LOCALIDAD] o a su lugar de trabajo sito en [LOCALIDAD] para cuyo fin se debía expedir oficio a la Central de Correos sita en [LOCALIDAD] para la retención de la correspondencia y puesta a disposición de este órgano judicial, lo que se verificó en legal forma (2).

TERCERA.- Transcurrido el periodo de tres meses acordado por este órgano judicial, y en base al artículo 584 LECRIM, se interesa se señale día para la apertura de la correspondencia y se cite al acto al investigado/a. Y se lleve a cabo conforme prevén los arts. 586 a 588 LECRIM .

Por lo expuesto,

SUPLICO A LA SECCIÓN

Que tenga por presentado este escrito, lo admita y tenga por realizado el trámite de petición de apertura de la correspondencia intervenida al investigado/a en los términos que se indican anteriormente, siendo citado/a a tal efecto para la práctica de la diligencia.

Por ser de Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a
D./Dña. [NOMBRE Y APELLIDOS] 	D./Dña. [NOMBRE Y APELLIDOS]

NOTAS DEL FORMULARIO

(1) La detención de la correspondencia privada, postal y telegráfica, incluidos faxes, burofaxes y giros, que el investigado remita o reciba, así como su apertura o examen, para investigar delitos dolosos castigados con pena con límite máximo de [COMPLETAR], al menos, 3 años de prisión, delitos cometidos por grupo u organización criminal, o de terrorismo requieren autorización judicial previa.

En caso de urgencia, cuando las investigaciones se realicen para la averiguación de delitos relacionados con la actuación de bandas armadas o elementos terroristas y existan razones fundadas que hagan imprescindible la medida prevista, es posible autorización judicial posterior. Se puede ordenar por el Ministro del Interior o, en su defecto, por el Secretario de Estado de Seguridad. Se comunicará al Juez en el plazo máximo de 24 horas y el juez revocará o confirmará la actuación en el plazo de 72 horas desde que se ordenó.

No requieren autorización judicial: [COMPLETAR]

-Envíos postales que, por sus propias características externas, no sean usualmente utilizados para contener correspondencia individual sino para servir al transporte y tráfico de mercancías o en cuyo exterior se haga constar su contenido.
-Otras formas de envío de la correspondencia bajo el formato legal de comunicación abierta, en las que resulte obligatoria una declaración externa de contenido o que incorporen la indicación expresa de que se autoriza su inspección.
-Inspecciones llevadas a cabo de acuerdo con la normativa aduanera o procedentes con arreglo a las normas postales que regulan una determinada clase de envío.

(2) La solicitud y las actuaciones posteriores relativas a esta medida se sustanciarán en una pieza separada y secreta, sin necesidad de que se acuerde expresamente el secreto de la causa. (Artículo 579.5 LECRIM )

================================================================================
