---
name: abreviado-investigado-pide-sobreseimiento-tras-116
description: "Redacta el escrito «Abreviado: el investigado pide el sobreseimiento tras diligencias complementarias» (formulario 116 de instrucción y procedimiento penal, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Abreviado: el investigado pide el sobreseimiento tras diligencias complementarias

> Formulario 0116 del plugin **Instrucción y procedimiento penal** · revisado el 17-11-2026.

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

- El art. 782.1 LECrim se refiere al sobreseimiento que piden el Ministerio Fiscal y el acusador particular. Si, tras las diligencias complementarias (art. 780.2), alguna acusación presenta escrito de acusación, la defensa debe pedir al juez que deniegue la apertura del juicio oral y acuerde el sobreseimiento por falta de indicios racionales de criminalidad (art. 783.1, en relación con el art. 641.2).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión. Empieza con una nota explicativa (para qué sirve el escrito y cuándo se usa), revisada en el BOE: léela antes de redactar, pero no la copies en el escrito.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] DESCRIBIR
- [ ] LUGAR
- [ ] FECHA

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 780.2 de la LECrim
- art. 782.1 LECrim
- art. 641.2 de la LECrim

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

### Formulario 0116 · Abreviado: el investigado pide el sobreseimiento tras diligencias complementarias

- Año del modelo: 2023
- Revisión 17-11-2026: 5 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)
- Nota explicativa incorporada desde la colección Procesal (formulario 105) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Escrito por el que la defensa del investigado en un procedimiento abreviado solicita el sobreseimiento provisional de la causa, después de haberse practicado diligencias complementarias y considerar que no existen pruebas contra su defendido, conforme a lo prevenido en el art. 782.1 LECrim, en relación al art. 641.2 de la LECrim.

---

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales y de D./Dña. [NOMBRE Y APELLIDOS], investigado/a en el procedimiento abreviado número [Nº DE PROCEDIMIENTO], según tengo acreditado en estos autos, ante este órgano judicial comparezco y, como mejor proceda en derecho, DIGO:

Que habiéndose practicado las diligencias complementarias al amparo del art. 780.2 de la LECrim y, de conformidad con lo establecido en el último párrafo del citado artículo, en relación con el art. 782.1 LECrim, por medio del presente escrito solicito el SOBRESEIMIENTO PROVISIONAL, al amparo del art. 641.2 de la LECrim, en base a los siguientes

MOTIVOS

PRIMERO.- La parte acusadora solicitó diligencias complementarias consistentes en [DESCRIBIR], de cuyo resultado se deduce que, en ningún caso, el hecho punible puede ser imputado a mi representado/a, puesto que la pericial caligráfica practicada ha puesto de manifiesto que la firma dubitada no está hecha por mi mandante, por lo que es evidente que dicho extremo esencial no ha sido acreditado, siendo que la propia parte acusadora consideró necesario que el resultado de la diligencia fuera positivo para poder formular escrito de acusación.

SEGUNDO.- A mayor abundamiento, los indicios obrantes en la instrucción de la causa en fase de diligencias previas no son suficientes para decretar la apertura del juicio oral, puesto que la única vinculación de mi representado/a con la causa es su condición de gerente de la sociedad de donde no puede presumirse la autoría de la firma del cheque falso, mayormente cuando la diligencia complementaria antes citada ha evidenciado que mi representado/a no firmó el cheque, por lo que no puede determinarse la autoría de la presunta falsedad, debiendo decretarse el sobreseimiento provisional de la causa, conforme a lo prevenido en el art. 782.1 LECrim, en relación al art. 641.2 de la LECrim.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito y, en su virtud, acuerde la denegación de la apertura del juicio oral que pudiera interesarse por las partes acusadoras, decretando el sobreseimiento provisional de este proceso.

Es justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a

================================================================================

---

#### Notas al pie

[NOTA DE REVISIÓN: El art. 782.1 LECrim se refiere al sobreseimiento que piden el Ministerio Fiscal y el acusador particular. Si, tras las diligencias complementarias (art. 780.2), alguna acusación presenta escrito de acusación, la defensa debe pedir al juez que deniegue la apertura del juicio oral y acuerde el sobreseimiento por falta de indicios racionales de criminalidad (art. 783.1, en relación con el art. 641.2).]
