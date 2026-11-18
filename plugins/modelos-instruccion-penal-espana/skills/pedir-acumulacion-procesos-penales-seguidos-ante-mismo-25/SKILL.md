---
name: pedir-acumulacion-procesos-penales-seguidos-ante-mismo-25
description: "Redacta el escrito «Pedir la acumulación de procesos penales seguidos ante el mismo órgano» (formulario 25 de instrucción y procedimiento penal, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Pedir la acumulación de procesos penales seguidos ante el mismo órgano

> Formulario 0025 del plugin **Instrucción y procedimiento penal** · revisado el 17-11-2026.

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
- [ ] Nº (5 veces)
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] NÚMERO (2 veces)
- [ ] FECHA (2 veces)
- [ ] Otros 5 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…de DP»; «…de DP»; «…de DP [COMPLETAR] son los siguientes»; «… ocurrido en fecha mismo delito cometido»; «…a interesada acumulación de procesos. En»

## Elecciones que hay que hacer

- querellante / denunciante / querellado / denunciado
- querella / denuncia
- distintos/as / los/las mismos/as
- perjudicados / víctimas
- los mismos / conexos
- los mismos hechos / hechos conexos

## Normas que cita el formulario

No cita artículos concretos. Si añades alguno, compruébalo con `buscar_articulo`.

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

### Formulario 0025 · Pedir la acumulación de procesos penales seguidos ante el mismo órgano

- Año del modelo: 2026
- Revisión 17-11-2026: 7 desplegables y casillas convertidos en elección en blanco; 13 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 3 huecos del original que se habían perdido sin marca, marcados (FECHA, Nº)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, actuando en representación D/Dña. [NOMBRE Y APELLIDOS], [ELEGIR: querellante / denunciante / querellado / denunciado] según consta acreditado en DP nº [NÚMERO] seguido por delito de del CP, en causa seguida ante el Tribunal al que me dirijo, comparezco y, como proceda en Derecho, DIGO:

Que en fecha [FECHA] se incoaron las presentes diligencias en virtud de [ELEGIR: querella / denuncia] interpuesta por presunto delito de del CP, en las que aparece como investigado/a Pero también se están practicando diligencias de instrucción en esta misma Sección de Instrucción de este Tribunal de Instancia con el nº [Nº] de DP [COMPLETAR] en base a otra denuncia presentada por

FUNDAMENTOS JURÍDICOS

PRIMERO.- Conforme a lo dispuesto en los arts. 17, 18.1.2º de la LECRIM y concordantes, solicito a esta Sección que se proceda a la acumulación de procesos, al referirse ambas investigaciones a los mismos hechos, con [ELEGIR: distintos/as / los/las mismos/as]

[ELEGIR: perjudicados / víctimas].

La causa que se investiga con el número arriba indicado se incoó en fecha [FECHA] y la citada bajo el nº [Nº] de DP lo fue en fecha siendo esta causa la primera que inició la investigación, lo que atraería la competencia a esta sección de instrucción en base al art. 18.1.2º LECRIM al tratarse del mismo delito el objeto de investigación.

SEGUNDO.- Los hechos objeto de investigación son [ELEGIR: los mismos / conexos], ya que en la causa tramitada al nº [Nº] de DP [COMPLETAR] son los siguientes [COMPLETAR] similares a los tramitados en la presente causa, con
distintos/as
los/las mismos/as

[ELEGIR: perjudicados / víctimas]. Por ello, hay identidad de sujeto activo que es coincidencia temporal por haber ocurrido en fecha mismo delito cometido [COMPLETAR] y las víctimas del mismo autor, en la misma fecha, cometidos en unidad de acción son

TERCERO.- No es procedente la tramitación separada de ambos procedimientos, por cuanto se refieren a [ELEGIR: los mismos hechos / hechos conexos] y, en caso de no acumularse, se corre el riesgo de que se dicten resoluciones contradictorias.

La acumulación de procesos resulta procedente cuando coincida una conexión relevante que permita el enjuiciamiento conjunto y, de forma anticipada, su instrucción, también común.

Por todo ello,

SUPLICO A LA SECCIÓN:

Que, habiendo por presentado este escrito con sus copias, se digne admitirlo y se tenga por interesado que se acumulen a las presentes DP nº [NÚMERO] a las incoadas al nº [Nº] y, tras el trámite correspondiente y la audiencia al Ministerio Fiscal, se proceda a la interesada acumulación de procesos.

En [COMPLETAR]

Firma Abogado/a y Procurador/a

================================================================================
