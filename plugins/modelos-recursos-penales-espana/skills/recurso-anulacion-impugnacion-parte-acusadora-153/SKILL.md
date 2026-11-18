---
name: recurso-anulacion-impugnacion-parte-acusadora-153
description: "Redacta el escrito «Recurso de anulación: impugnación de la parte acusadora» (formulario 153 de recursos penales, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Recurso de anulación: impugnación de la parte acusadora

> Formulario 0153 del plugin **Recursos penales** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (3 veces)
- [ ] FECHA (3 veces)
- [ ] LUGAR
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…dora en este proceso con número de Rollo»; «… la representación del/de la condenado/a»

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 790.5 de la LECrim
- art. 793 de la LECrim
- art. 786.1 de la LECrim

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

### Formulario 0153 · Recurso de anulación: impugnación de la parte acusadora

- Año del modelo: 2023
- Revisión 17-11-2026: 1 puntualizaciones normativas añadidas en el texto; 1 bloques de alternativas señalados; 8 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

A la Sección de lo Penal del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

A la Sala

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, en nombre y representación de D./Dña. [NOMBRE Y APELLIDOS], parte acusadora en este proceso con número de Rollo [COMPLETAR], según tengo acreditado en autos, ante este órgano judicial comparezco y como mejor proceda en derecho DIGO:

Que habiendo recibido traslado del recurso de anulación contra la sentencia de fecha [FECHA] interpuesto por la representación del/de la condenado/a D./Dña. [NOMBRE Y APELLIDOS], y al amparo de lo dispuesto en el art. 790.5 de la LECrim, en relación con el art. 793 de la LECrim, mediante el presente escrito IMPUGNO el recurso de anulación interpuesto por los siguientes

MOTIVOS

ÚNICO.-

El recurso de anulación interpuesto no recoge ninguna alegación ni impugnación en relación a la concurrencia de los requisitos del juicio en ausencia. La parte recurrente pretende que se revise la declaración de hechos probados y la calificación jurídica de los hechos, articulando varios motivos en relación a la infracción del derecho a la presunción de inocencia y a la indebida aplicación del art. del Código Penal.

Por tanto, la simple lectura del escrito de interposición del recurso de anulación pone de manifiesto que se está utilizando indebidamente esta vía impugnatoria, para combatir el pronunciamiento de fondo.

La jurisprudencia del Tribunal Supremo, entre otras en Sentencia de 12 de mayo de 2000, afirma que las cuestiones relativas a la discrepancia sobre los hechos debe plantearse a través de la interposición del recurso de apelación (o, en su caso, casación) contra la sentencia. En el mismo sentido, la citada Sentencia y otras tales como las de 8 de marzo de 2000, de acuerdo con la interpretación realizada por el Pleno del Alto Tribunal de 25 de febrero de 2000, indican que el recurso de anulación es de carácter extraordinario y tiene naturaleza rescindente, debiendo ceñirse a comprobar si se han respetado los requisitos establecidos en el art. 786.1 de la LECrim para la celebración del juicio en ausencia [NOTA DE REVISIÓN: Desde el 3-4-2025 los requisitos del juicio en ausencia están en el art. 787.1 LECrim (pena más grave de hasta dos años de prisión, seis si es de otra naturaleza, o multa, y suma de penas privativas de hasta cinco años); el art. 793.1 sigue remitiendo al art. 786.1. Fuente: LECrim, BOE-A-1882-6036, arts. 787.1 y 793 (redacción LO 1/2025, BOE-A-2025-76).].

Cualquier otra cuestión ha de plantearse a través del recurso contra la sentencia.

En este caso, ninguna de las cuestiones planteadas en el recurso de anulación se refieren a los requisitos establecidos en el art. 786.1 de la LECrim; antes al contrario, todas ellas se refieren a cuestiones relativas al pronunciamiento de fondo, pretendiendo utilizar el recurso de anulación para revisar una sentencia firme, lo que a todas luces es improcedente.

Por tanto, esta parte impugna el recurso interpuesto por exceder del objeto del recurso establecido en el art. 793 de la LECrim y en la jurisprudencia que lo interpreta.

Por lo expuesto,

SUPLICO A LA SECCIÓN (or SALA)

Que tenga por impugnado el recurso de anulación interpuesto contra la sentencia de fecha [FECHA] por la representación del/de la condenado/a [COMPLETAR] y que declare no haber lugar al recurso de anulación interpuesto por la citada representación contra la sentencia antes mencionada.

En [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a

================================================================================
