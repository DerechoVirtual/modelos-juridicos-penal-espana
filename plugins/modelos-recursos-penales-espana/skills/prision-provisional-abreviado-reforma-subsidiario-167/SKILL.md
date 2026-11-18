---
name: prision-provisional-abreviado-reforma-subsidiario-167
description: "Redacta el escrito «Prisión provisional en el abreviado: reforma y subsidiario de apelación» (formulario 167 de recursos penales, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Prisión provisional en el abreviado: reforma y subsidiario de apelación

> Formulario 0167 del plugin **Recursos penales** · revisado el 17-11-2026.

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

- [ ] SEDE (2 veces)
- [ ] Nº (2 veces)
- [ ] NOMBRE Y APELLIDOS (3 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] FECHA (4 veces)
- [ ] LUGAR
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «…, a [FECHA]. Firma de Abogado:»

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 766 de la LECrim
- art. 503 y 504 de la LECrim
- art. 24 de la Constitución
- art. 766.5 de la LECrim

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

### Formulario 0167 · Prisión provisional en el abreviado: reforma y subsidiario de apelación

- Año del modelo: 2022
- Revisión 17-11-2026: 1 bloques de alternativas señalados; 7 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco; 2 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 1 huecos del original que se habían perdido sin marca, marcados (NOMBRE Y APELLIDOS)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

A la Sección de lo Penal del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Abogado/a, actuando en representación y defensa de D./Dña. [NOMBRE Y APELLIDOS], según consta acreditado en Diligencias Previas número [Nº DE PROCEDIMIENTO] seguidas ante ese órgano judicial, comparezco y, como proceda en Derecho, DIGO:

Que el día [FECHA] se ha notificado a esta defensa el auto de prisión provisional de mi defendido/a de fecha [FECHA], y entendiendo dicha resolución no es ajustada a derecho, dicho sea en términos de defensa, por medio del presente escrito, al amparo de lo dispuesto en el art. 766 de la LECrim y preceptos concordantes INTERPONGO RECURSO DE REFORMA Y SUBSIDIARIO DE APELACIÓN, en base a los siguientes

MOTIVOS

PRIMERO.- INFRACCIÓN DEL ART. 24 CE (PRESUNCIÓN DE INOCENCIA) Y ARTS. 503 Y 504 LECRIM: INEXISTENCIA DE ELEMENTOS INDICIARIOS PARA DECRETAR LA MEDIDA CAUTELAR.

La doctrina jurisprudencial ha venido reiterando que la medida de prisión provisional ha de venir asentada en indicios racionales o motivos bastantes que permitan imputar la comisión de un delito de cierta entidad al destinatario de la medida, tal como establece el art. 503 y 504 de la LECrim, y así lo ha venido subrayando tanto el TEDH en sentencias de 28 de marzo de 1990 y 26 de enero de 1993, como también de forma reiterada el Tribunal Constitucional en sentencias de 26 de julio de 1995, 15 de abril de 1996, 20 de mayo de 1997 y 29 de mayo de 2008, entre otras muchas.

La resolución que ahora se recurre funda los indicios en la aparición de una huella dactilar en la ventana de mi defendido en la ventana de acceso a la vivienda, lo cual constituye un débil indicio de su presunta participación en el delito, si tenemos en cuenta la propia declaración de mi defendido que reconoce haber estado el día anterior a los hechos en compañía de unos amigos en ese lugar y atendido que la vivienda donde se produjo el robo es una planta baja y que la ventana en cuestión da a la vía pública, sin ningún tipo de protección. De ahí que la explicación dada por mi representado, en el sentido que se pudo apoyar en la ventana cuando estuvo en el lugar con sus amigos sea una explicación razonable, y debilite considerablemente el indicio sostenido por el Instructor en el auto de prisión, al punto de hacer la medida escasamente razonable, teniendo en cuenta que es una medida que se adopta vigente el derecho a la presunción de inocencia que asiste a mi defendido conforme al art. 24 de la Constitución.

SEGUNDO.- INFRACCIÓN DEL ART. 17 CE Y 503.1.3º LECRIM: INEXISTENCIA DE RIESGO DE FUGA.

El art. 503.1.3º LECRIM y la misma interpretación jurisprudencial antes expuesta, viene requiriendo, de forma cumulativa a la existencia de un fumus bonus iuris, la necesidad de que la prisión provisional responda a un motivo constitucionalmente lícito y congruente con su naturaleza, como es la necesidad de evitar el riesgo de fuga o el riesgo de desaparición de fuentes de prueba. Se viene reiterando que la prisión provisional no puede convertirse en una pena anticipada, de manera que ha de apreciarse algún peligro en la demora que legitime la medida de privación de un derecho fundamental como es el de la libertad personal.

En el caso contemplado, el Instructor indica que mi defendido no tiene domicilio ni actividad conocida, entendiendo que concurre un riesgo de fuga por este motivo, atendida la gravedad del delito.

No obstante, tal razonamiento se contradice con el resultado de las actuaciones, donde mi representado ha fijado un domicilio estable en esta localidad, donde reside habitualmente con sus padres, y también ha indicado, a preguntas de esta representación, que se hallaba trabajando de forma temporal en la empresa A., a cuyo efecto se aportaron recibos de salarios de los dos meses anteriores acreditativos de tal circunstancia.

Junto a ello, ha de tenerse en cuenta que mi representado carece de antecedentes penales y que el delito que se le imputa, si finalmente es probado, entra dentro del ámbito de la suspensión condicional de la pena, por lo que mi representado tiene la lícita expectativa de acceder a los beneficios de la suspensión, lo que disminuye notablemente la apreciación del riesgo de fuga.

Por tanto, cabe entender suficiente a los fines de aseguramiento del proceso, la constitución de la obligación apud-acta en los días que señale el Juez de Instrucción, siendo desproporcionada la medida de prisión provisional.

Por lo expuesto, es de justicia y

SUPLICO A LA SECCIÓN

que tenga por presentado este escrito y, en su virtud, por formulado RECURSO DE REFORMA y, caso de no ser estimado, SUBSIDIARIO DE APELACIÓN contra el auto de fecha [FECHA] por el que se acordaba la prisión provisional de D. [NOMBRE Y APELLIDOS], y, previos los trámites legales, se revoque la citada resolución, acordando la libertad provisional sin fianza de mi defendido/a, previa constitución de la obligación de comparecer apud-acta.

PRIMER OTROSÍ DIGO: que para el caso que se desestime el recurso de reforma, esta repreinteresa la incorporación al Rollo de Apelación, del testimonio de los siguientes particulares:

SUPLICO A LA SECCIÓN: se acuerde de conformidad.

SEGUNDO OTROSÍ DIGO: que, en caso de ser desestimado el recurso de reforma, al formularse el recurso de apelación con carácter subsidiario, interesa a esta parte la celebración de vista conforme al art. 766.5 de la LECrim.

SUPLICO A LA SECCIÓN: se acuerde de conformidad.

Es justicia que pido, en [LUGAR], a [FECHA].

Firma de Abogado: [COMPLETAR]

================================================================================
