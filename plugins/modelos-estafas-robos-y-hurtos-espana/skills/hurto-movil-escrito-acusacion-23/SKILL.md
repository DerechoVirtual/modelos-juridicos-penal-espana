---
name: hurto-movil-escrito-acusacion-23
description: "Redacta el escrito «Hurto de móvil: escrito de acusación» (formulario 23 de delitos contra el patrimonio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Hurto de móvil: escrito de acusación

> Formulario 0023 del plugin **Delitos contra el patrimonio** · revisado el 17-11-2026.

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

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] NOMBRE Y APELLIDOS (11 veces)
- [ ] COLEGIO
- [ ] Nº DE COLEGIADO/A
- [ ] LOCALIDAD
- [ ] FECHA
- [ ] Nº
- [ ] CIRCUNSTANCIA
- [ ] DELITO
- [ ] PENA
- [ ] IMPORTE
- [ ] LUGAR
- [ ] Otros 12 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…sobre las [Nº] horas el citado»; «…sustraído un teléfono móvil propiedad de»; «…uando este se encontraba en la cafetería»; «… gritos de la víctima al salir detrás de»; «…y»; «…ores a una tercera persona no localizada»; «…del artículo»; «…o Penal y con respecto al/a la acusado/a»; «…las circunstancias»; «…, la pena principal de»; «…, y a ambos las accesorias de»; «…, a»

## Elecciones que hay que hacer

- a continuación / en escrito aparte
- judicialmente / mediante exhorto

## Párrafos opcionales (3)

Inclúyelos solo si encajan en los hechos:

- 1.- Interrogatorio del/de la acusado/a.…
- .- Testifical, interrogatorio de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte]…
- .- Documental consistente en factura del teléfono no recuperado.…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 800.4 de la Ley de Enjuiciamiento Criminal

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

### Formulario 0023 · Hurto de móvil: escrito de acusación

- Año del modelo: 2026
- Revisión 17-11-2026: 1 desplegables y casillas convertidos en elección en blanco; 1 desplegables convertidos en elección en blanco; 3 párrafos opcionales señalados; 34 campos de relleno marcados en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Al Juez en servicio de Guardia del Tribunal de Instancia de [SEDE]

D./Dña. [NOMBRE Y APELLIDOS], Letrado/a del Ilustre Colegio de Abogados de [COLEGIO], con nº de colegiado/a [Nº DE COLEGIADO/A] y con despacho profesional abierto en [LOCALIDAD], en representación del acusador particular D./Dña. [NOMBRE Y APELLIDOS], comparezco ante este órgano judicial y como mejor proceda en derecho, DIGO:

En aplicación del artículo 800.4 de la Ley de Enjuiciamiento Criminal, mediante el presente escrito formulo en plazo escrito de acusación contra D./Dña. [NOMBRE Y APELLIDOS] con base en las siguientes:

CONCLUSIONES

PRIMERA

El día [FECHA] sobre las [Nº] horas el citado [COMPLETAR] ha sustraído un teléfono móvil propiedad de [COMPLETAR] cuando este se encontraba en la cafetería [COMPLETAR] momento en el que D./Dña. [NOMBRE Y APELLIDOS] le despistó ante una pregunta que le hizo y, durante el descuido, le sustrajo el teléfono móvil que estaba encima de la mesa, siendo detenidos los dos de inmediato por los agentes policiales que estaban en las inmediaciones ante los gritos de la víctima al salir detrás de [COMPLETAR] y [COMPLETAR]. El teléfono móvil no ha aparecido, posiblemente al haberlo pasado los autores a una tercera persona no localizada [COMPLETAR].

SEGUNDA

Tales hechos son constitutivos del delito de hurto del artículo 235.1.10º del Código Penal.

TERCERA

Son responsables del delito, D./Dña. [NOMBRE Y APELLIDOS], en concepto de autor/a y D./Dña. [NOMBRE Y APELLIDOS], en concepto de cómplice.

CUARTA

Con respecto al/a la acusado/a D./Dña. [NOMBRE Y APELLIDOS] concurren las circunstancias agravantes de [CIRCUNSTANCIA] del artículo [COMPLETAR] del Código Penal y con respecto al/a la acusado/a [COMPLETAR] las circunstancias [COMPLETAR].

QUINTA

Procede imponer al/a la acusado/a D./Dña. [NOMBRE Y APELLIDOS], por el delito de [DELITO], la pena principal de [COMPLETAR], y a D./Dña. [NOMBRE Y APELLIDOS] la pena de [PENA], y a ambos las accesorias de [COMPLETAR].

SEXTA

Los/as acusados/as deberán indemnizar solidariamente a D./Dña. [NOMBRE Y APELLIDOS], por importe de [IMPORTE] euros, correspondiente a la tasación del teléfono, según factura que se aporta. Las costas deberán ser satisfechas por ambos/as acusados/as.

Por lo expuesto,

SUPLICO A LA SECCIÓN

Que tenga por presentado este escrito, lo admita y tenga por realizado el trámite de traslado para acusación.

Por ser de Justicia que pido [LUGAR], a [COMPLETAR].

OTROSÍ DIGO: Que para el juicio oral intereso la práctica de los siguientes:

MEDIOS DE PRUEBA

Los propuestos por el Ministerio Fiscal y además los siguientes:

[OPCIONAL — incluir si procede]

1.- Interrogatorio del/de la acusado/a.

[OPCIONAL — incluir si procede]

.- Testifical, interrogatorio de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados/as [ELEGIR: judicialmente / mediante exhorto].

[OPCIONAL — incluir si procede]

.- Documental consistente en factura del teléfono no recuperado.

Por todo lo expuesto,

SUPLICO A LA SECCIÓN: que declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a y número de colegiado/a:

D./Dña. [NOMBRE Y APELLIDOS]

================================================================================
