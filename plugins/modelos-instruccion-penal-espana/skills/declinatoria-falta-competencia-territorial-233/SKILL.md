---
name: declinatoria-falta-competencia-territorial-233
description: "Redacta el escrito «Declinatoria por falta de competencia territorial» (formulario 233 de instrucción y procedimiento penal, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Declinatoria por falta de competencia territorial

> Formulario 0233 del plugin **Instrucción y procedimiento penal** · revisado el 17-11-2026.

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

- [ ] SEDE (5 veces)
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS
- [ ] NOMBRE DEL REPRESENTADO/A
- [ ] LOCALIDAD
- [ ] NÚMERO DE LA CALLE
- [ ] Otros 3 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…alizado la escritura pública de venta en»; «…e haberla, se produjo en la localidad de»; «…nto delito en dicho partido judicial. En»

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 26 LECrim
- artículo 14 de la LECrim
- art. 14 de la LECrim
- art. 26 de la LECrim

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

### Formulario 0233 · Declinatoria por falta de competencia territorial

- Año del modelo: 2022
- Revisión 17-11-2026: 10 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 1 huecos del original que se habían perdido sin marca, marcados (NÚMERO DE LA CALLE)
- Nota explicativa incorporada desde la colección Procesal (formulario 137) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Escrito por el que la defensa del investigado plantea una declinatoria por falta de competencia territorial a una Sección de Instrucción de un Tribunal de Instancia, solicitando que se inhiba en favor de las Secciones de Instrucción del Tribunal de Instancia del lugar de comisión del delito, por ser de su competencia, conforme al art. 14 de la LECRIM y en base al art. 26 LECRIM. Recuerde que....

---

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D/Dª [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, actuando en representación de [NOMBRE DEL REPRESENTADO/A], investigado/a en este procedimiento, según consta acreditado en autos, comparezco y como proceda en Derecho, DIGO:

Que mediante el presente escrito promuevo DECLINATORIA por falta de competencia territorial, conforme al art. 26 LECrim, al corresponder el conocimiento de esta causa a las Secciones de Instrucción del Tribunal de Instancia de [SEDE], por haberse cometido el delito en dicho partido judicial, conforme dispone el artículo 14 de la LECrim, al amparo de los siguientes,

MOTIVOS

PRIMERO.- Las presentes actuaciones se siguen por presunto delito de estafa contra mi representado/a por la venta de la finca sita en [LOCALIDAD], habiéndose realizado la escritura pública de venta en [COMPLETAR], sede del órgano judicial al que nos dirigimos.

SEGUNDO.- El art. 14 de la LECrim establece la competencia a favor de la de Instrucción del Tribunal de Instancia del lugar donde se cometió el presunto delito, siendo que en los delitos de estafa el TS ha reiterado en numerosos autos, de los que son ejemplo los de 15 de abril de 1988 y 7 de diciembre de 1995, que al ser un delito de lesión patrimonial, es donde se produce dicha lesión donde se comete el delito.

En este caso, la lesión, de haberla, se produjo en la localidad de [COMPLETAR], lugar donde se halla sita la finca vendida, y no en el lugar donde se otorgó la escritura de venta, por lo que son competentes las Secciones de Instrucción del Tribunal de Instancia de [SEDE] para el conocimiento de esta causa.

TERCERO.- Por lo anterior, instamos de la Sección de Instrucción del Tribunal de Instancia de plaza nº [NÚMERO DE LA CALLE] que se inhiba del conocimiento del asunto a favor de las Secciones de Instrucción del Tribunal de Instancia de [SEDE], por corresponderles la competencia conforme al art. 14 de la LECrim, y de acuerdo a lo establecido en el art. 26 de la LECrim.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito con los documentos que se acompañan, y previos los trámites legales, dicte auto inhibiéndose del conocimiento del asunto a favor de las Secciones de Instrucción del Tribunal de Instancia de [SEDE] por ser el competente por haberse cometido el presunto delito en dicho partido judicial.

En [COMPLETAR]

Firma de Abogado/a	Firma de Procurador/a

================================================================================
