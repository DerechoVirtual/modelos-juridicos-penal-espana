---
name: querella-inadmitida-reforma-subsidiario-apelacion-121
description: "Redacta el escrito «Querella inadmitida: reforma y subsidiario de apelación» (formulario 121 de recursos penales, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Querella inadmitida: reforma y subsidiario de apelación

> Formulario 0121 del plugin **Recursos penales** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] FECHA (4 veces)
- [ ] DELITO (2 veces)
- [ ] LOCALIDAD
- [ ] LUGAR

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 766 de la LECrim
- art. 24 de la CE
- art. 24 de la Constitución
- art. 766.4 de la LECrim

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

### Formulario 0121 · Querella inadmitida: reforma y subsidiario de apelación

- Año del modelo: 2023
- Revisión 17-11-2026: 10 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, actuando en representación de D./Dña. [NOMBRE Y APELLIDOS], según consta acreditado en Diligencias Previas número [Nº DE PROCEDIMIENTO] seguidas ante ese órgano judicial, comparezco y como proceda en Derecho, DIGO:

Que el día [FECHA] se ha notificado a esta representación el auto de fecha [FECHA] de inadmisión de querella y archivo de las actuaciones, y entendiendo dicha resolución no ajustada a derecho y lesiva para mis representado/as, dicho sea en términos de defensa, por medio del presente escrito, al amparo de lo dispuesto en el art. 766 de la LECrim y preceptos concordantes INTERPONGO RECURSO DE REFORMA Y SUBSIDIARIO DE APELACIÓN, en base a los siguientes

MOTIVOS

PRIMERO.- INFRACCIÓN DEL ART. 24 DE LA CONSTITUCIÓN. FALTA DE MOTIVACIÓN EN LA RESOLUCIÓN DE INADMISIÓN.

El auto que recurrimos entendemos infringe el derecho fundamental de esta parte a la tutela judicial efectiva reconocido en el art. 24 de la CE, puesto que el auto dictado es un mero formulario que no contiene ningún razonamiento individualizado para el caso concreto planteado en la querella, presentando una absoluta ausencia de motivación.

El Tribunal Constitucional ha venido exigiendo, con reiteración, que la decisión de cierre del proceso contenga una motivación suficiente, como garantía del derecho fundamental, y así las Sentencias 314/2005, de 12 de diciembre y 94/2007, de 7 de mayo, y en el mismo sentido el Tribunal Supremo en numerosas resoluciones, pudiendo citarse la de 16 de marzo de 1998 y 23 de abril de 1998, entre otras.

La resolución recurrida no realiza ningún razonamiento sobre los hechos relatados en la querella, limitándose a citar algunos preceptos de la LECrim utilizando un formato de resolución preconstituido, impidiendo a esta parte el acceso al proceso sin conocer los motivos que llevan al Instructor a tal decisión, lo que ocasiona una situación de total indefensión a esta parte.

Nos vemos en la obligación, ad cautelam, para el caso de desestimación, de invocar expresamente la vulneración del art. 24 de la Constitución en el auto recurrido.

SEGUNDO.- EN CUANTO AL FONDO, LOS HECHOS RELATADOS EN EL ESCRITO DE QUERELLA PUEDEN SER CONSTITUTIVOS DE UN DELITO DE [DELITO]

Tanto el relato de hechos de la querella como la documental aportada ponen de manifiesto serios indicios de la posible comisión de un delito de [DELITO], lo cual es imputable a los querellados.

Desde un punto de vista indiciario quedan pocas dudas sobre las intenciones de los querellados y voluntad de sustraer el cuantioso patrimonio que tenían de sus acreedores. De la mera lectura de los documentos 1 y 2, se desprende la maniobra de transmisión a la querellada de todo el patrimonio del querellado A. y de su empresa, con clara connivencia por parte de ésta.

En cuanto a la deuda mantenida con mis representados, los propios querellados reconocen adeudar estas cantidades en el documento número 5, quedando acreditado indiciariamente que el querellado Sr. hizo desaparecer todo su patrimonio y al efecto se comprueba en la documental aportada la transmisión de todas sus fincas a la querellada, o la adquisición de un vehículo Mercedes a nombre de la querellada, para evitar tener bienes a su nombre, todo con conexión temporal con las deudas derivadas de la renta vitalicia que suscribió con mi representado/a.

Está acreditada indiciariamente la conducta delictiva de los querellados, constatándose indicios de delito de estafa que deben llevar a la admisión de la querella.

Por lo expuesto, es de justicia y

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito y, en su virtud, por formulado RECURSO DE REFORMA y, caso de no ser estimado, SUBSIDIARIO DE APELACIÓN contra el auto de fecha [FECHA] por el que se acordaba la inadmisión a trámite de la querella, dictando otro en virtud del cual se admita a trámite y se practiquen las diligencias interesadas por esta representación.

OTROSÍ DIGO: que, en caso de ser desestimado el recurso de reforma, al formularse el recurso de apelación con carácter subsidiario, se eleven las actuaciones a la Audiencia Provincial de [LOCALIDAD] para la resolución del recurso, dando traslado previo a esta parte a los efectos del art. 766.4 de la LECrim.

SUPLICO A LA SECCIÓN: acuerde de conformidad.

Es Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a

================================================================================
