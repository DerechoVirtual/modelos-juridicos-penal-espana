---
name: victima-pedir-juicio-celebre-puerta-cerrada-752
description: "Redacta el escrito «Víctima: pedir que el juicio se celebre a puerta cerrada» (formulario 752 de víctimas y justicia restaurativa, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Víctima: pedir que el juicio se celebre a puerta cerrada

> Formulario 0752 del plugin **Víctimas y justicia restaurativa** · revisado el 17-11-2026.

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
- [ ] LOCALIDAD
- [ ] NOMBRE Y APELLIDOS (5 veces)
- [ ] COLEGIO
- [ ] Nº DE PROCEDIMIENTO
- [ ] AÑO
- [ ] DELITO (2 veces)
- [ ] FECHA (2 veces)
- [ ] LUGAR
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «…del artículo»

## Elecciones que hay que hacer

- testigo / víctima

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 681 de la LECRIM
- art. 681 LECRIM
- artículo 25.2 de la Ley 4/2015
- artículo 707 LECRIM

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

### Formulario 0752 · Víctima: pedir que el juicio se celebre a puerta cerrada

- Año del modelo: 2016
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (3); 1 desplegables y casillas convertidos en elección en blanco; 1 bloques de alternativas señalados; 12 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 1 huecos del original que se habían perdido sin marca, marcados (Nº DE PROCEDIMIENTO)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la víctima de un delito solicita, ante el órgano de enjuiciamiento, que las sesiones del juicio se celebren a puerta cerrada, para proteger su derecho a la intimidad, conforme permite el artículo 25 de la L 4/15 del Estatuto de la Víctima del delito y artículo 681 de la LECRIM.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

A la Sección de lo Penal del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

A la Audiencia Provincial de [LOCALIDAD]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales del Ilustre Colegio de Procuradores de [COLEGIO] ejercitando la acusación particular en nombre y representación de D./Dña. [NOMBRE Y APELLIDOS] (1) (2) en el Juicio oral nº [Nº DE PROCEDIMIENTO]/[AÑO] que se sigue en este órgano judicial por delito de [DELITO] contra D./Dña. [NOMBRE Y APELLIDOS], ante este órgano judicial comparezco y, como más procedente sea en derecho, DIGO:

Con fecha [FECHA] se ha citado a mi representador/a para que comparezca en su calidad de [ELEGIR: testigo / víctima].

Que, al tratarse de un procedimiento por delito de [DELITO] del artículo [COMPLETAR] del CP, en el que el/la compareciente en su momento lo hará en calidad de víctima, es por lo que solicito se celebre el juicio a puerta cerrada en garantía de preservar su intimidad por las características del proceso penal y el derecho que tiene a ello en base al art. 681 LECRIM, que señala que (3):

"1. El Juez o Tribunal podrá acordar, de oficio o a instancia de cualquiera de las partes, previa audiencia a las mismas, que todos o alguno de los actos o las sesiones del juicio se celebren a puerta cerrada, cuando así lo exijan razones de seguridad u orden público, o la adecuada protección de los derechos fundamentales de los intervinientes, en particular, el derecho a la intimidad de la víctima, el respeto debido a la misma o a su familia, o resulte necesario para evitar a las víctimas perjuicios relevantes que, de otro modo, podrían derivar del desarrollo ordinario del proceso"

Además, el artículo 25.2 de la Ley 4/2015, de 27 de abril, del Estatuto de la Víctima señala que:

"2. Durante la fase de enjuiciamiento podrán ser adoptadas, conforme a lo dispuesto en la Ley de Enjuiciamiento Criminal, las siguientes medidas para la protección de las víctimas: ...

d) Celebración de la vista oral sin presencia de público. En estos casos, el Juez o el Presidente del Tribunal podrán autorizar, sin embargo, la presencia de personas que acrediten un especial interés en la causa."

Por ello, intereso se acepte la petición y se acuerde, al inicio de las sesiones, que el juicio se celebre a puerta cerrada.

Por todo ello,

SUPLICO A LA SECCIÓN

Se admita el presente escrito y se tenga por efectuadas las alegaciones.

Por ser de Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a
D./Dña. [NOMBRE Y APELLIDOS] 	D./Dña. [NOMBRE Y APELLIDOS]

NOTAS DEL FORMULARIO

(1) Este escrito puede presentarse tanto en este órgano judicial de lo penal como en la Sección Penal de la Audiencia Provincial; es decir, ante el órgano de enjuiciamiento que corresponda para celebrar el juicio, que es quien tiene que tomar la decisión sobre este tema.

(2) No es obligatorio que la víctima se persone en el proceso penal para presentar este escrito. Puede hacerlo por sí misma y el órgano judicial debería ofrecerle esta opción en la citación a juicio a fin de que pueda presentar, o no, este escrito.

(3) Presentado este escrito, el juez o presidente del tribunal, antes del inicio del juicio dará traslado a las partes de esta petición para dar cumplimiento al traslado a las partes y audiencia del escrito para alegaciones y resolverá en el acto.

De aceptarse dictará más tarde auto acordándolo y documentándolo en la causa.

Se admite en la LECRIM que en estos casos el Juez o el Presidente del Tribunal podrán autorizar la presencia de personas que acrediten un especial interés en la causa.

La anterior restricción, sin perjuicio de lo dispuesto en el artículo 707 LECRIM, no será aplicable al Ministerio Fiscal, a las personas lesionadas por el delito, a los procesados, al acusador privado, al actor civil y a los respectivos defensores.

================================================================================
