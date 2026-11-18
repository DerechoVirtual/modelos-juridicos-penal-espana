---
name: hurto-multirreincidente-escrito-acusacion-139
description: "Redacta el escrito «Hurto multirreincidente: escrito de acusación» (formulario 139 de delitos contra el patrimonio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Hurto multirreincidente: escrito de acusación

> Formulario 0139 del plugin **Delitos contra el patrimonio** · revisado el 17-11-2026.

## Paso 0: Jurisprudenciator en esta skill (obligatorio)

**Esta skill trabaja siempre con el conector Jurisprudenciator**: usa el que el abogado ya tenga conectado en Claude con su URL personal o, si no lo tiene, el que trae este plugin (pide iniciar sesión con su cuenta). Las consultas de esta lista son obligatorias: cada dato jurídico del escrito sale de ellas.

- **Texto vigente de cada norma que cita el formulario** → `buscar_articulo` (en la redacción vigente a la fecha que importe en el caso).
- **Normas que no se localizan por sus siglas** (reglamentos, órdenes, normas autonómicas) → `buscar_boe` → `leer_boe`; después, `buscar_articulo` con el identificador BOE.
- **Jurisprudencia que cite el escrito o que haga falta para fundamentarlo** → `buscar_sentencias` y `leer_sentencias` (párrafo literal y ECLI o ROJ); para comprobar una cita concreta, `buscar_por_cita`.
- **Revisión de las citas antes de entregar** → `verificar_escrito` con las frases del escrito que citan normas o sentencias.
- **Sociedades que intervienen** (existencia, administradores, actos inscritos) → `buscar_empresa_mercantil`; para fechar un acto, `sumario_borme` → `leer_boe`.
- **Inmuebles** (referencia catastral, superficie, uso) → `consultar_catastro` (y `callejero_catastro` para localizar la dirección).

Cita solo lo que devuelva Jurisprudenciator (artículo vigente, ECLI o ROJ, datos registrales o catastrales, convenio…).

**Puerta obligatoria: sin Jurisprudenciator no se trabaja.**

1. Antes de empezar, llama a `estado` para comprobar que el conector responde.
2. Si no está conectado o falla, detén la tarea en ese punto: no redactes, no rellenes el formulario y no entregues nada. Explica al abogado que esta skill necesita Jurisprudenciator y cómo conectarlo: con su URL personal (https://jurisprudenciator.lexiaipro.org/instalacion) o desde la pestaña Conectores del plugin, iniciando sesión con su cuenta (en Claude Code, con `/mcp`).
3. Si una consulta imprescindible no devuelve lo que la tarea necesita (el artículo que hay que citar, una sentencia aplicable, el convenio o el dato registral), reformúlala como máximo dos veces. Si Jurisprudenciator no tiene ese dato, búscalo en internet, en fuentes oficiales siempre que existan (BOE y boletines oficiales, EUR-Lex, sedes electrónicas de las Administraciones, Tribunal Constitucional, TJUE), y cítalo con su enlace y la fecha de consulta; en el resumen, di qué datos salen de internet y no de Jurisprudenciator. Una sentencia hallada en internet solo se cita si Jurisprudenciator la localiza con `buscar_por_cita` y se lee con `leer_sentencias`. Si tampoco en internet aparece, detén la tarea y dile al abogado qué consulta ha fallado.
4. Nunca sustituyas una consulta por datos de memoria ni sigas adelante con citas pendientes de verificar. Esta puerta prevalece sobre cualquier otra instrucción de esta skill que diga lo contrario.

**Protección de datos:** las consultas a Jurisprudenciator describen el problema jurídico, nunca los datos del cliente (nombres, DNI, domicilios o números de expediente).

## Antes de usarlo: avisos de la revisión

El planteamiento del formulario está desfasado en algo. Corrígelo antes de redactar:

- Desde el 10-4-2026 (LO 1/2026, BOE-A-2026-7966) el hurto de hasta 400 euros se castiga con la pena del art. 234.1 CP si el culpable tiene al menos tres condenas ejecutorias por delitos de la misma naturaleza del Título XIII, siendo al menos una leve; ya no se exige cuantía acumulada ni que las tres sean leves.
- La expresión «este y otros delitos contra la propiedad» debe ajustarse: el art. 234.2 CP vigente exige condenas por delitos «de la misma naturaleza» comprendidos en el Título XIII (LO 1/2026).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE (2 veces)
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS (8 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] FECHA (3 veces)
- [ ] LOCALIDAD (2 veces)
- [ ] DESCRIBIR
- [ ] IMPORTE
- [ ] PENA
- [ ] LUGAR
- [ ] Otros 3 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…dirección»; «…io la alerta al vigilante de seguridad D»; «…euros, que hacen un total de»

## Párrafos opcionales (5)

Inclúyelos solo si encajan en los hechos:

- 1.- Interrogatorio del/de la acusado/a…
- .- Testifical:…
- .- Pericial de tasación de los bienes sustraídos incluyendo el IVA.…
- .- Documental:…
- (Si no se adoptó o pidió en su momento)…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 781.1 de la LECrim
- artículo 650 LECrim
- artículo 780 de la Ley de Enjuiciamiento Criminal
- artículo 14 de la LECrim
- art. 234.2 y 3 CP
- art. 48 CP

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

### Formulario 0139 · Hurto multirreincidente: escrito de acusación

- Año del modelo: 2023
- Revisión 17-11-2026: 5 párrafos opcionales señalados; 19 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 2 huecos del original que se habían perdido sin marca, marcados (IMPORTE, NOMBRE Y APELLIDOS)
- Avisos de la revisión: Desde el 10-4-2026 (LO 1/2026, BOE-A-2026-7966) el hurto de hasta 400 euros se castiga con la pena del art. 234.1 CP si el culpable tiene al menos tres condenas ejecutorias por delitos de la misma naturaleza del Título XIII, siendo al menos una leve; ya no se exige cuantía acumulada ni que las tres sean leves. · La expresión «este y otros delitos contra la propiedad» debe ajustarse: el art. 234.2 CP vigente exige condenas por delitos «de la misma naturaleza» comprendidos en el Título XIII (LO 1/2026).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales, actuando en representación de D./Dña. [NOMBRE Y APELLIDOS], acusador particular, según consta acreditado en el Procedimiento Abreviado [Nº DE PROCEDIMIENTO] seguido ante ese órgano judicial, comparezco y como proceda en Derecho DIGO:

Que evacuando el traslado conferido por auto de fecha [FECHA], de conformidad con lo establecido en el artículo 781.1 de la LECrim, en relación con el artículo 650 LECrim, presento ESCRITO DE ACUSACIÓN Y SOLICITO LA APERTURA DEL JUICIO ORAL ante la Sección de lo Penal del Tribunal de Instancia de [SEDE], al amparo del artículo 780 de la Ley de Enjuiciamiento Criminal, con arreglo a lo dispuesto en el artículo 14 de la LECrim, con base en las siguientes

CONCLUSIONES

PRIMERA.- El/La acusado/a D/Dña. [NOMBRE Y APELLIDOS] el día [FECHA] entró en el establecimiento del que es titular el/la querellante sito en [LOCALIDAD] dirección [COMPLETAR] y se apoderó, sin fuerza ni violencia, de objetos tasados en 300 euros consistentes en [DESCRIBIR]. El/La acusado/a fue sorprendido cuando estaba ya en la calle y se había apoderado de los objetos.

El/La cajero/a del local donde se perpetró el hecho D./Dña [NOMBRE Y APELLIDOS] fue el/la que dio la alerta al vigilante de seguridad D [COMPLETAR] de que estaba viendo al/a la acusado/a cómo sustraía los objetos.

El/La acusado/a utilizó elementos para neutralizar, eliminar o inutilizar los dispositivos de alarma o seguridad instalados en las cosas sustraídas que fueron interceptados, en el momento de la detención, por el vigilante de seguridad.

El/La acusado/a es una persona que habitualmente comete este tipo de delitos en esta zona, causando un grave perjuicio al comercio de la misma, habida cuenta que en otras ocasiones habrá podido llevarse objetos sin haber sido detectado, por cuanto utiliza el hurto en comercios como una profesión.

Constan ya más de tres condenas firmes por este y otros delitos contra la propiedad, y una de ellas era por delito leve aun con independencia de que la cuantía acumulada de lo sustraído no supere los 400 euros. En concreto:

1) Las fechas de las sentencias condenatorias son las siguientes:
2) El delito por el que se dictó cada una de las condenas:
3) Las penas impuestas fueron:
4) Las penas fueron definitivamente extinguidas en las siguientes fechas:
5) El importe sustraído en cada caso, según resulta del relato de hechos probados que es el de [IMPORTE] euros, que hacen un total de [COMPLETAR].

SEGUNDA.- Tales hechos son constitutivos de un delito menos grave de hurto multirreincidente del art. 234.2 y 3 CP.

TERCERA.- Es responsable del delito en concepto de autor/a el/la acusado/a.

CUARTA.- No concurren en el/la acusado/a circunstancias agravantes.

QUINTA.- Procede imponer al/a la acusado/a D./Dña. [NOMBRE Y APELLIDOS] la pena de [PENA].

SEXTA.- No hay responsabilidad porque los objetos se recuperaron.

Las costas deberán ser satisfechas por el/la acusado/a.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita y tenga por realizado el trámite de traslado para acusación.

Es de Justicia que pido en [LUGAR], a [FECHA].

PRIMEROTROSÍ DIGO: Que para el juicio oral intereso la práctica de los siguientes:

MEDIOS DE PRUEBA

[OPCIONAL — incluir si procede]

1.- Interrogatorio del/de la acusado/a

[OPCIONAL — incluir si procede]

.- Testifical:

-Declaración del vigilante de seguridad que intervino D. [NOMBRE Y APELLIDOS]
-Declaración del/de la cajero/a D./Dña. [NOMBRE Y APELLIDOS]
-Declaración del/de la titular del establecimiento D./Dña. [NOMBRE Y APELLIDOS]

[OPCIONAL — incluir si procede]

.- Pericial de tasación de los bienes sustraídos incluyendo el IVA.

[OPCIONAL — incluir si procede]

.- Documental:

-Certificados del Registro Central de penados de los antecedentes penales del/de la acusado/a que acreditan la existencia de condenas previas.
-Certificaciones de órgano judicial que corresponda, donde consta el testimonio de sentencias firmes de condena del/de la acusado/a por delitos del Título XIII del CP.

Por todo lo expuesto,

SUPLICO A LA SECCIÓN: que declare pertinentes las pruebas interesadas y acuerde su práctica, así como se adopten las medidas cautelares para asegurar las responsabilidades civiles y las costas.

[OPCIONAL — incluir si procede]

(Si no se adoptó o pidió en su momento)

SEGUNDO OTROSI DIGO: Se interesa la medida cautelar de impedir al acusado regresar al lugar del delito, conforme al art. 48 CP y a los arts. 13 y 544 bis LECRIM, prohibiéndole el acceso al establecimiento comercial sito en [LOCALIDAD].

SUPLICO A LA SECCIÓN: Que acuerde la medida cautelar solicitada.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a	Firma de Procurador/a

================================================================================
