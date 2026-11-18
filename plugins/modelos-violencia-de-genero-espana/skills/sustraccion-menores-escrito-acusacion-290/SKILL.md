---
name: sustraccion-menores-escrito-acusacion-290
description: "Redacta el escrito «Sustracción de menores: escrito de acusación» (formulario 290 de violencia de género y delitos en la familia, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Sustracción de menores: escrito de acusación

> Formulario 0290 del plugin **Violencia de género y delitos en la familia** · revisado el 17-11-2026.

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
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS (3 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] FECHA (4 veces)
- [ ] NÚMERO
- [ ] LOCALIDAD (4 veces)
- [ ] CIRCUNSTANCIA
- [ ] PENA
- [ ] DURACIÓN
- [ ] IMPORTE
- [ ] LUGAR
- [ ] Otros 4 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «… acusado/a y progenitor/a de los menores»; «…y»; «…on su pareja y progenitor de los menores»; «… agravantes. Concurre en el/la acusado/a»

## Elecciones que hay que hacer

- manteniendo / solicitando

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (4)

Inclúyelos solo si encajan en los hechos:

- 1.- Interrogatorio del/ de la acusado/a que declarará en último lugar, tras la práctica de la prueba.…
- .- Testifical:…
- D./Dña. [NOMBRE Y APELLIDOS]…
- .- Documental:…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 781.1 de la LECrim
- artículo 650 LECrim
- artículo 780 de la Ley de Enjuiciamiento Criminal
- artículo 14 de la LECrim
- art. 225 bis CP
- art. 22 del CP
- art. 57 CP
- art. 544 bis LECRIM

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

### Formulario 0290 · Sustracción de menores: escrito de acusación

- Año del modelo: 2021
- Revisión 17-11-2026: 3 llamadas a nota sin texto retiradas; 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 1 bloques de alternativas señalados; 3 párrafos opcionales señalados; 22 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales, actuando en representación de D./Dña. [NOMBRE Y APELLIDOS], acusador particular, según consta acreditado en el Procedimiento Abreviado [Nº DE PROCEDIMIENTO] seguido ante ese órgano judicial, comparezco y como proceda en Derecho DIGO:

Que evacuando el traslado conferido por auto de fecha [FECHA], de conformidad con lo establecido en el artículo 781.1 de la LECrim, en relación con el artículo 650 LECrim, presento ESCRITO DE ACUSACIÓN Y SOLICITO LA APERTURA DEL JUICIO ORAL ante la Sección de lo Penal del Tribunal de Instancia de [SEDE] plaza nº [NÚMERO], al amparo del artículo 780 de la Ley de Enjuiciamiento Criminal, con arreglo a lo dispuesto en el artículo 14 de la LECrim, con base en las siguientes

CONCLUSIONES

PRIMERA.- Con fecha [FECHA] el/la acusado/a y progenitor/a de los menores [COMPLETAR] y [COMPLETAR] trasladó su domicilio habitual del que compartía con su pareja y progenitor de los menores [COMPLETAR] de al domicilio sito en [LOCALIDAD], de forma permanente, llevándose a él a sus hijos, sin consentimiento del otro progenitor.

SEGUNDA.- Tales hechos son constitutivos de un delito de sustracción de menores del art. 225 bis CP.

TERCERA.- Es responsable del delito en concepto de autor/a el/la acusado/a.

CUARTA.-

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

No concurren en el/la acusado/a circunstancias agravantes.

Concurre en el/la acusado/a [COMPLETAR] la circunstancia agravante de [CIRCUNSTANCIA] del art. 22 del CP.

QUINTA.- Procede imponer al/a la acusado/a por el delito del art. 225 bis CP la pena de [PENA] y la pena de alejamiento por el art. 57 CP respecto de los menores por tiempo de [DURACIÓN].

SEXTA.- El importe de la responsabilidad civil por daño moral es de [IMPORTE] euros.

Las costas deberán ser satisfechas por el/la acusado/a.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita y tenga por realizado el trámite de traslado para acusación.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que para el juicio oral intereso la práctica de los siguientes:

MEDIOS DE PRUEBA

[OPCIONAL — incluir si procede]

1.- Interrogatorio del/ de la acusado/a que declarará en último lugar, tras la práctica de la prueba.

[OPCIONAL — incluir si procede]

.- Testifical:

Testifical de personas que conozcan lo ocurrido sobre el abandono del domicilio habitual del querellado y de haberse llevado consigo a los menores:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

D./Dña. [NOMBRE Y APELLIDOS]

[OPCIONAL — incluir si procede]

.- Documental:

-Empadronamiento de la pareja en el domicilio habitual sito en [LOCALIDAD]
-Documental del colegio al que acudían los menores sito en [LOCALIDAD]
-Oficio del Excmo. Ayto. de. que acredita que reside en el municipio el/la acusado/a.
-Oficio del colegio del municipio al que se ha desplazado el/la acusado/a sin consentimiento del otro progenitor.
-Oficios cumplimentados de la compañía de luz y agua que certifican el consumo del inmueble sito en [LOCALIDAD] desde el día [FECHA].

Por todo lo expuesto,

SUPLICO A LA SECCIÓN: Que declare pertinentes las pruebas interesadas y acuerde su práctica, así como se adopten las medidas cautelares para asegurar las responsabilidades civiles y las costas, [ELEGIR: manteniendo / solicitando] la medida cautelar de alejamiento respecto de los menores, en base a lo dispuesto en el art. 544 bis LECRIM en relación al art. 57 CP, en la nueva redacción dada por la LO 8/2021, de 4 de junio, al incluir los delitos contra las relaciones familiares.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a	Firma de Procurador/a

================================================================================
