---
name: diputado-senador-acusacion-pide-remitir-causa-tribunal-99
description: "Redacta el escrito «Diputado o senador: la acusación pide remitir la causa al Tribunal Supremo» (formulario 99 de delitos contra la administración pública y de justicia, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Diputado o senador: la acusación pide remitir la causa al Tribunal Supremo

> Formulario 0099 del plugin **Delitos contra la Administración pública y de justicia** · revisado el 17-11-2026.

## Paso 0: Jurisprudenciator en esta skill (obligatorio)

**Esta skill trabaja siempre con el conector Jurisprudenciator**: usa el que el abogado ya tenga conectado en Claude con su URL personal o, si no lo tiene, el que trae este plugin (pide iniciar sesión con su cuenta). Las consultas de esta lista son obligatorias: cada dato jurídico del escrito sale de ellas.

- **Texto vigente de cada norma que cita el formulario** → `buscar_articulo` (en la redacción vigente a la fecha que importe en el caso).
- **Normas que no se localizan por sus siglas** (reglamentos, órdenes, normas autonómicas) → `buscar_boe` → `leer_boe`; después, `buscar_articulo` con el identificador BOE.
- **Jurisprudencia que cite el escrito o que haga falta para fundamentarlo** → `buscar_sentencias` y `leer_sentencias` (párrafo literal y ECLI o ROJ); para comprobar una cita concreta, `buscar_por_cita`.
- **Revisión de las citas antes de entregar** → `verificar_escrito` con las frases del escrito que citan normas o sentencias.
- **Ordenanzas municipales** (tráfico, urbanismo, tributos locales, convivencia) → `buscar_ordenanzas` → `leer_ordenanza`.
- **Inmuebles** (referencia catastral, superficie, uso) → `consultar_catastro` (y `callejero_catastro` para localizar la dirección).

Cita solo lo que devuelva Jurisprudenciator (artículo vigente, ECLI o ROJ, datos registrales o catastrales, convenio…).

**Puerta obligatoria: sin Jurisprudenciator no se trabaja.**

1. Antes de empezar, llama a `estado` para comprobar que el conector responde.
2. Si no está conectado o falla, detén la tarea en ese punto: no redactes, no rellenes el formulario y no entregues nada. Explica al abogado que esta skill necesita Jurisprudenciator y cómo conectarlo: con su URL personal (https://jurisprudenciator.lexiaipro.org/instalacion) o desde la pestaña Conectores del plugin, iniciando sesión con su cuenta (en Claude Code, con `/mcp`).
3. Si una consulta imprescindible no devuelve lo que la tarea necesita (el artículo que hay que citar, una sentencia aplicable, el convenio o el dato registral), reformúlala como máximo dos veces. Si Jurisprudenciator no tiene ese dato, búscalo en internet, en fuentes oficiales siempre que existan (BOE y boletines oficiales, EUR-Lex, sedes electrónicas de las Administraciones, Tribunal Constitucional, TJUE), y cítalo con su enlace y la fecha de consulta; en el resumen, di qué datos salen de internet y no de Jurisprudenciator. Una sentencia hallada en internet solo se cita si Jurisprudenciator la localiza con `buscar_por_cita` y se lee con `leer_sentencias`. Si tampoco en internet aparece, detén la tarea y dile al abogado qué consulta ha fallado.
4. Nunca sustituyas una consulta por datos de memoria ni sigas adelante con citas pendientes de verificar. Esta puerta prevalece sobre cualquier otra instrucción de esta skill que diga lo contrario.

**Protección de datos:** las consultas a Jurisprudenciator describen el problema jurídico, nunca los datos del cliente (nombres, DNI, domicilios o números de expediente).

## Nota explicativa: puntualizaciones de la revisión

La nota explicativa de este formulario se ha revisado en el BOE. Tenlo en cuenta al redactar:

- El art. 21 LECrim (sin reformas) atribuye al propio Tribunal Supremo la decisión: es el TS quien ordena al órgano inferior que se abstenga y le remita los antecedentes en el término de segundo día, de oficio, a excitación del Fiscal o a solicitud de parte. Por eso la petición también puede dirigirse directamente al TS. La competencia del TS para las causas contra senadores resulta de los arts. 71.3 CE y 57.1.2.º LOPJ.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión. Empieza con una nota explicativa (para qué sirve el escrito y cuándo se usa), revisada en el BOE: léela antes de redactar, pero no la copies en el escrito.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] Nº
- [ ] NOMBRE Y APELLIDOS (10 veces)
- [ ] LUGAR
- [ ] FECHA
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…y D. [NOMBRE Y APELLIDOS], y la sociedad»; «…, alcalde/sa de»

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- arts. 21 y 750 de la LECrim
- art. 71.3 CE

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

### Formulario 0099 · Diputado o senador: la acusación pide remitir la causa al Tribunal Supremo

- Año del modelo: 2023
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; 12 campos de relleno marcados en blanco; 2 huecos del original que se habían perdido sin marca, marcados (NOMBRE Y APELLIDOS, Nº)
- Nota explicativa incorporada desde la colección Procesal (formulario 100) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Escrito por el que la acusación solicita al juez de instrucción que remita la causa al Tribunal Supremo, al considerar que existen elementos suficientes para realizar la investigación, con sólido fundamento, de una persona que es senadora y, por lo tanto, aforada, por la vía del art. 21 LECRIM. Recuerde que....

---

A la Sección de instrucción del Tribunal de Instancia deplaza nº [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, actuando en representación de D./Dña. [NOMBRE Y APELLIDOS], parte acusadora en este proceso, según tengo acreditado en autos, comparezco y como mejor proceda en Derecho, DIGO:

Que, mediante el presente escrito, al amparo de lo dispuesto en los arts. 21 y 750 de la LECrim y ss, solicito que se eleve exposición razonada al Tribunal Supremo por corresponderle el conocimiento de estas diligencias previas, al aparecer indicios ciertos para la investigación de D./Dña. [NOMBRE Y APELLIDOS], senador/a, en base a los siguientes,

HECHOS

PRIMERO.- La presente causa se instruye por querella criminal interpuesta por mi representado/a contra D./Dña. [NOMBRE Y APELLIDOS] y D. [NOMBRE Y APELLIDOS], y la sociedad [COMPLETAR], en cuya iniciación ya se advirtió de la posible intervención en los hechos delictivos de D./Dña. [NOMBRE Y APELLIDOS], alcalde/sa de [COMPLETAR] y senador/a.

De la instrucción de la causa queda acreditado, por la declaración de los investigados, que efectivamente crearon la sociedad querellada, transmitiendo D./Dña. [NOMBRE Y APELLIDOS] las acciones a su hijo/a.

De la documental practicada, se desprende que fue el/la propio/a D./Dña. [NOMBRE Y APELLIDOS] quien concedió la licencia de actividad a precario, ordenando al arquitecto municipal que informara favorablemente a la licencia, amenazándole de prescindir de sus servicios como interino, tal como ha declarado éste.

Asimismo, la contestación de la Presidencia del Senado pone de manifiesto que D./Dña. [NOMBRE Y APELLIDOS] actualmente ostenta la condición de senador/a.

SEGUNDO.- Apareciendo evidentes indicios contra D./Dña. [NOMBRE Y APELLIDOS], procede elevar exposición razonada al Tribunal Supremo para que determine si le corresponde el conocimiento de la causa, puesto que únicamente el Alto Tribunal puede instruirla, conforme al art. 71.3 CE y al art. 57.1.2.º y 2 LOPJ [NOTA DE REVISIÓN (comprobar): La atribución de la instrucción y el enjuiciamiento al Tribunal Supremo está en el art. 57.1.2.º LOPJ; el apartado 2 regula el magistrado instructor. Fuente: LO 6/1985 del Poder Judicial, BOE-A-1985-12666, art. 57.], realizando la imputación tras la autorización de la Cámara.

TERCERO.- Entre tanto se tramita la remisión de las actuaciones al Tribunal Supremo, interesamos que se practiquen las diligencias pendientes, puesto que, en ningún caso, inciden en la prohibición de dirigir el procedimiento contra la persona aforada.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita y remita las actuaciones al Tribunal Supremo, continuando con la práctica de las diligencias pertinentes mientras tanto.

Es de Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a

================================================================================

---

#### Notas al pie

[NOTA DE REVISIÓN: El art. 21 LECrim (sin reformas) atribuye al propio Tribunal Supremo la decisión: es el TS quien ordena al órgano inferior que se abstenga y le remita los antecedentes en el término de segundo día, de oficio, a excitación del Fiscal o a solicitud de parte. Por eso la petición también puede dirigirse directamente al TS. La competencia del TS para las causas contra senadores resulta de los arts. 71.3 CE y 57.1.2.º LOPJ.]
