---
name: denunciante-pedir-notifique-auto-inadmite-denuncia-122
description: "Redacta el escrito «Denunciante: pedir que se notifique el auto que inadmite la denuncia» (formulario 122 de instrucción y procedimiento penal, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Denunciante: pedir que se notifique el auto que inadmite la denuncia

> Formulario 0122 del plugin **Instrucción y procedimiento penal** · revisado el 17-11-2026.

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

- Si la inadmisión se acuerda por auto de sobreseimiento, este debe comunicarse a las víctimas en la dirección electrónica o postal que hayan designado. La comunicación se tiene por hecha a los cinco días, y las víctimas pueden recurrir en 20 días aunque no estén personadas (arts. 636 y 779.1.1.ª LECrim; art. 12 de la Ley 4/2015, del Estatuto de la víctima del delito).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión. Empieza con una nota explicativa (para qué sirve el escrito y cuándo se usa), revisada en el BOE: léela antes de redactar, pero no la copies en el escrito.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS (5 veces)
- [ ] FECHA
- [ ] DELITO
- [ ] NOMBRE DEL REPRESENTADO/A
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «… contra D./Dña. [NOMBRE Y APELLIDOS], al»; «…a los efectos oportunos. En»

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 24 de la Constitución
- art. 269 LECrim
- art. 779.1 de la LECrim

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

### Formulario 0122 · Denunciante: pedir que se notifique el auto que inadmite la denuncia

- Año del modelo: 2023
- Revisión 17-11-2026: 10 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)
- Nota explicativa incorporada desde la colección Procesal (formulario 114) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Escrito por el que el denunciante solicita que se le notifique el auto de inadmisión de su denuncia, conforme a los arts. 269 y 779.1 LECRIM., este último para el p. abreviado.

---

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales y de D./Dña. [NOMBRE Y APELLIDOS], según consta acreditado en autos, ante ese órgano judicial comparezco y, como mejor proceda en derecho, DIGO:

1) Que mi mandante D./Dña. [NOMBRE Y APELLIDOS] presentó denuncia en fecha [FECHA] por un presunto delito de [DELITO], contra D./Dña. [NOMBRE Y APELLIDOS], al [COMPLETAR].

Transcurridos más de dos meses desde la presentación de la denuncia, mi representado/a no ha recibido notificación alguna, si bien ha sido informado/a verbalmente por la oficina judicial de que se había dictado resolución de inadmisión de la denuncia.

2) Atendidos los antecedentes, y al amparo de lo dispuesto en el art. 24 de la Constitución en relación con el art. 269 LECrim y art. 779.1 de la LECrim, esta representación solicita la notificación de la meritada resolución de inadmisión, a fin de evitar cualquier situación de indefensión, para poder valorar los fundamentos que han llevado al Juez al archivo de la causa y, en su caso, ejercitar los correspondientes medios de impugnación contra la citada resolución, caso de estar disconformes con su fundamentación.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que admita este escrito, me tenga por personado en representación de [NOMBRE DEL REPRESENTADO/A] y, en su virtud, acuerde notificar a esta parte la resolución de inadmisión de la denuncia presentada por mi representado/a D./Dña. [NOMBRE Y APELLIDOS] a los efectos oportunos.

En [COMPLETAR]

Firma de Abogado/a	Firma de Procurador/a

================================================================================

---

#### Notas al pie

[NOTA DE REVISIÓN: Si la inadmisión se acuerda por auto de sobreseimiento, este debe comunicarse a las víctimas en la dirección electrónica o postal que hayan designado. La comunicación se tiene por hecha a los cinco días, y las víctimas pueden recurrir en 20 días aunque no estén personadas (arts. 636 y 779.1.1.ª LECrim; art. 12 de la Ley 4/2015, del Estatuto de la víctima del delito).]
