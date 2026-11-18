---
name: acumular-causas-penales-conexas-pedir-inhibicion-seccion-234
description: "Redacta el escrito «Acumular causas penales conexas y pedir la inhibición a la Sección competente» (formulario 234 de instrucción y procedimiento penal, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Acumular causas penales conexas y pedir la inhibición a la Sección competente

> Formulario 0234 del plugin **Instrucción y procedimiento penal** · revisado el 17-11-2026.

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

- [ ] SEDE (6 veces)
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS (3 veces)
- [ ] NÚMERO (5 veces)
- [ ] Nº DE PROCEDIMIENTO (3 veces)
- [ ] FECHA (2 veces)
- [ ] Otros 5 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…do/a, actuando por cuenta de la sociedad»; «…entregados, realizada en la localidad de»; «…s vehículos realizada en la localidad de»; «… actuaba por cuenta de la misma sociedad»; «…actuando ambos por cuenta de la sociedad»

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 18.1 LECrim
- art. 18.2 de la LECrim

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

### Formulario 0234 · Acumular causas penales conexas y pedir la inhibición a la Sección competente

- Año del modelo: 2022
- Revisión 17-11-2026: 23 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)
- Nota explicativa incorporada desde la colección Procesal (formulario 138) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Escrito por el que se solicita a una Sección de Instrucción que se inhiba en favor de otra que está conociendo de una causa por ser delitos conexos (art. 17 LECRIM) que deben acumularse en un solo proceso, conforme al art. 18 LECRIM. Recuerde que.... Actualizado conforme a la LO 1/2025, de Eficiencia de la Justicia.

---

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, actuando en representación de D./Dña. [NOMBRE Y APELLIDOS], investigado/a en este procedimiento, según consta acreditado en autos, comparezco y, como proceda en Derecho, DIGO:

Que, mediante el presente escrito, promuevo la acumulación de esta causa a la seguida en la Sección de Instrucción del Tribunal de Instancia de [SEDE] nº [NÚMERO], conforme dispone el art. 18.1 LECrim, al amparo de los siguientes:

Motivos

Las presentes actuaciones se siguen por presunto delito de estafa contra mi representado/a, actuando por cuenta de la sociedad [COMPLETAR], por una presunta venta de dos vehículos que no fueron entregados, realizada en la localidad de [COMPLETAR].

Por su parte, en la Sección de Instrucción del Tribunal de Instancia de [SEDE] número [NÚMERO], se siguen diligencias previas número [Nº DE PROCEDIMIENTO] por el mismo delito, en relación a otra presunta venta de tres vehículos realizada en la localidad de [COMPLETAR] y que se imputa a D./Dña. [NOMBRE Y APELLIDOS], socio/a de mi representado/a y que también actuaba por cuenta de la misma sociedad [COMPLETAR], tal como acredito mediante copia de la querella presentada en dichas diligencias y auto de incoación, que acompaño como documentos número 1 y 2 de este escrito.

Entre ambas causas hay una evidente relación de conexidad, conforme al art. 17.2.2º de la LECrim, puesto que se imputa la misma conducta a mi representado/a y a su socio/a, actuando ambos por cuenta de la sociedad [COMPLETAR] en un espacio temporal reducido, al existir una diferencia de quince días entre los hechos imputados en una y otra causa, por lo que habría una situación de concierto en el improbable caso de que se acreditaran como ciertos los hechos imputados.

Habida cuenta de la relación de conexidad, y tratándose de delito que tiene señalada igual pena, corresponde el conocimiento del asunto a la Sección de Instrucción del Tribunal de Instancia de [SEDE] plaza nº [NÚMERO], conforme a lo dispuesto en el art. 18.2 de la LECrim, puesto que fue el primero que comenzó a conocer de la causa, tal como se constata de los documentos acompañados, tanto de la fecha de presentación de la querella el día [FECHA] como del auto de incoación de diligencias previas dictado por dicha Sección el día [FECHA], anteriores a la presentación de la querella iniciadora de estas diligencias.

Por lo anterior, instamos de esta Sección de Instrucción que se inhiba del conocimiento del asunto a favor de la Sección de Instrucción del Tribunal de Instancia de [SEDE] plaza nº [NÚMERO], para su acumulación a las diligencias previas número [Nº DE PROCEDIMIENTO], por tratarse de delitos conexos y ser la competente esta última, al haber conocido de la primera causa.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito con los documentos que se acompañan, y previos los trámites legales, dicte auto inhibiéndose del conocimiento del asunto a favor de la Sección de Instrucción del Tribunal de Instancia de [SEDE] plaza nº [NÚMERO] para su acumulación a las diligencias previas número [Nº DE PROCEDIMIENTO].

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a	Firma de Procurador/a

================================================================================
