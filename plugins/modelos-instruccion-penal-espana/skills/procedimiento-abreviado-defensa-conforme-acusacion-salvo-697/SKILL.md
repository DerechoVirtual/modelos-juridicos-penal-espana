---
name: procedimiento-abreviado-defensa-conforme-acusacion-salvo-697
description: "Redacta el escrito «Procedimiento abreviado: defensa conforme con la acusación salvo en la responsabilidad civil» (formulario 697 de instrucción y procedimiento penal, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Procedimiento abreviado: defensa conforme con la acusación salvo en la responsabilidad civil

> Formulario 0697 del plugin **Instrucción y procedimiento penal** · revisado el 17-11-2026.

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
- [ ] FECHA
- [ ] LOCALIDAD
- [ ] LUGAR
- [ ] DÍA
- [ ] MES
- [ ] AÑO
- [ ] Otros 3 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…D»; «…3.- Pericial de los peritos»; «…a, se reciba declaración testifical a Dª»

## Párrafos opcionales (6)

Inclúyelos solo si encajan en los hechos:

- 1.- Interrogatorio de mi representado/a.…
- 2.- Testifical de:…
- D [COMPLETAR], con domicilio en [LOCALIDAD]…
- 3.- Pericial de los peritos [COMPLETAR]…
- 4.- Documental contraída a la lectura de los siguientes folios de las actuaciones:…
- OTROSÍ DIGO: De conformidad con lo dispuesto en el artículo 781.1.III de la Ley de Enjuiciamiento Criminal, es…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 784.3 LECRIM
- artículo 784.3 de la Ley de Enjuiciamiento Criminal
- artículo 784.2 de la Ley de Enjuiciamiento Criminal

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

### Formulario 0697 · Procedimiento abreviado: defensa conforme con la acusación salvo en la responsabilidad civil

- Año del modelo: 2017
- Revisión 17-11-2026: 1 párrafos repetibles señalados; 5 párrafos opcionales señalados; 9 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que el acusado se conforma con la más grave de las acusaciones en un procedimiento abreviado, conforme al art. 784.3 LECRIM, pero no con la responsabilidad civil que se le exige, de manera que solicita que se abra el juicio oral únicamente para depurar la responsabilidad civil.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, actuando en nombre y representación de D./Dña. [NOMBRE Y APELLIDOS], según consta acreditado en autos, comparezco en el Procedimiento Abreviado nº [Nº DE PROCEDIMIENTO] que se tramita en ese órgano judicial, y como mejor proceda en Derecho, DIGO:

Que en fecha [FECHA] se ha dado traslado a esta representación de los escritos de calificación provisional presentados por las acusaciones y en los que se interesaba la apertura de Juicio Oral contra mi mandante, por lo que, en virtud de lo dispuesto en el artículo 784.3 de la Ley de Enjuiciamiento Criminal, muestro mi conformidad con la más grave de las acusaciones, que ha sido formulada por el Ministerio Fiscal.

No obstante, esta representación se muestra disconforme con la petición de responsabilidad civil postulada por el Ministerio Fiscal en la Conclusión sexta de su escrito de acusación, por lo que solicita la celebración del Juicio Oral únicamente en lo que atañe a la petición de responsabilidad civil e interesa la práctica de los siguientes

MEDIOS DE PRUEBA

[OPCIONAL — incluir si procede]

1.- Interrogatorio de mi representado/a.

[OPCIONAL — incluir si procede]

2.- Testifical de:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

D [COMPLETAR], con domicilio en [LOCALIDAD]

[OPCIONAL — incluir si procede]

3.- Pericial de los peritos [COMPLETAR]

[OPCIONAL — incluir si procede]

4.- Documental contraída a la lectura de los siguientes folios de las actuaciones:

De conformidad con lo establecido en el artículo 784.2 de la Ley de Enjuiciamiento Criminal, la reclamación de los documentos, así como las citaciones de los peritos y los testigos deberán realizarse por medio de la oficina judicial.

Por lo expuesto,

SUPLICO A LA SECCIÓN

Tener por hecha la calificación y dar a las diligencias el curso legal correspondiente.

[OPCIONAL — incluir si procede]

OTROSÍ DIGO: De conformidad con lo dispuesto en el artículo 781.1.III de la Ley de Enjuiciamiento Criminal, esta representación interesa que, como prueba anticipada, se reciba declaración testifical a Dª [COMPLETAR].

SUPLICO A LA SECCIÓN: tener por solicitada la prueba anticipada.

En [LUGAR], a [DÍA] de [MES] de [AÑO].

Firma de Abogado/a	Firma de Procurador/a

================================================================================
