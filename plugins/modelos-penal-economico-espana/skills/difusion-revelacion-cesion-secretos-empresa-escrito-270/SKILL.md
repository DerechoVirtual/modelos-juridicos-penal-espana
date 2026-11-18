---
name: difusion-revelacion-cesion-secretos-empresa-escrito-270
description: "Redacta el escrito «Difusión, revelación o cesión de secretos de empresa: escrito de acusación» (formulario 270 de delitos económicos y de empresa, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Difusión, revelación o cesión de secretos de empresa: escrito de acusación

> Formulario 0270 del plugin **Delitos económicos y de empresa** · revisado el 17-11-2026.

## Paso 0: Jurisprudenciator en esta skill (obligatorio)

**Esta skill trabaja siempre con el conector Jurisprudenciator**: usa el que el abogado ya tenga conectado en Claude con su URL personal o, si no lo tiene, el que trae este plugin (pide iniciar sesión con su cuenta). Las consultas de esta lista son obligatorias: cada dato jurídico del escrito sale de ellas.

- **Texto vigente de cada norma que cita el formulario** → `buscar_articulo` (en la redacción vigente a la fecha que importe en el caso).
- **Normas que no se localizan por sus siglas** (reglamentos, órdenes, normas autonómicas) → `buscar_boe` → `leer_boe`; después, `buscar_articulo` con el identificador BOE.
- **Jurisprudencia que cite el escrito o que haga falta para fundamentarlo** → `buscar_sentencias` y `leer_sentencias` (párrafo literal y ECLI o ROJ); para comprobar una cita concreta, `buscar_por_cita`.
- **Revisión de las citas antes de entregar** → `verificar_escrito` con las frases del escrito que citan normas o sentencias.
- **Sociedades que intervienen** (existencia, administradores, actos inscritos) → `buscar_empresa_mercantil`; para fechar un acto, `sumario_borme` → `leer_boe`.
- **Criterio de Hacienda y del TEAC** → `buscar_consultas_hacienda` → `leer_consulta_hacienda`; `buscar_doctrina_teac` → `leer_resolucion_teac`.

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
- [ ] Nº (2 veces)
- [ ] NOMBRE Y APELLIDOS (8 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] FECHA (3 veces)
- [ ] NÚMERO
- [ ] IMPORTE (5 veces)
- [ ] CIRCUNSTANCIA
- [ ] LUGAR
- [ ] Otros 7 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…do de la lista de clientes de la empresa»; «…ividad laboral en la misma en calidad de»; «…n la misma, la ha entregado a la entidad»; «…de la competencia asciende a la cifra de»; «… agravantes. Concurre en el/la acusado/a»; «…representante legal de la empresa»; «…que se requiera a la empresa competidora»

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (7)

Inclúyelos solo si encajan en los hechos:

- 1.- Interrogatorio del/ de la acusado/a.…
- .- Testifical:…
- D./Dña. [NOMBRE Y APELLIDOS]…
- D./Dña. [NOMBRE Y APELLIDOS]…
- .- Pericial siguiente:…
- .- Documental siguiente:…
- (Si no se adoptó o pidió en su momento)…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 781.1 de la LECrim
- artículo 650 LECrim
- artículo 780 de la Ley de Enjuiciamiento Criminal
- artículo 14 de la LECrim
- art. 279 CP
- art. 22 del CP

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

### Formulario 0270 · Difusión, revelación o cesión de secretos de empresa: escrito de acusación

- Año del modelo: 2022
- Revisión 17-11-2026: 3 llamadas a nota sin texto retiradas; 2 párrafos repetibles señalados; 1 bloques de alternativas señalados; 5 párrafos opcionales señalados; 28 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales, actuando en representación de D./Dña. [NOMBRE Y APELLIDOS], acusador particular, según consta acreditado en el Procedimiento Abreviado [Nº DE PROCEDIMIENTO] seguido ante ese órgano judicial, comparezco y como proceda en Derecho DIGO:

Que evacuando el traslado conferido por auto de fecha [FECHA], de conformidad con lo establecido en el artículo 781.1 de la LECrim, en relación con el artículo 650 LECrim, presento ESCRITO DE ACUSACIÓN Y SOLICITO LA APERTURA DEL JUICIO ORAL ante la Sección de lo Penal del Tribunal de Instancia de [SEDE] plaza nº [NÚMERO], al amparo del artículo 780 de la Ley de Enjuiciamiento Criminal, con arreglo a lo dispuesto en el artículo 14 de la LECrim, con base en las siguientes

CONCLUSIONES

PRIMERA.- El/La acusado/a se ha apropiado de la lista de clientes de la empresa [COMPLETAR] mientras ha ejercido su actividad laboral en la misma en calidad de [COMPLETAR] y, al cesar en la misma, la ha entregado a la entidad [COMPLETAR] para que esta, a su vez, pueda disponer de la información reservada con que contaba la primera, haciendo una distribución de correos electrónicos a los clientes, ofreciendo los servicios de la segunda empresa que se dedicaba al mismo objeto social de la primera, perjudicándola notablemente, como se demuestra en el descenso de los ingresos en [IMPORTE] euros, como se acredita con la declaración fiscal presentada este año de fecha [FECHA], en parte provocado por la pérdida de clientes por el apoderamiento y cesión de la lista de clientes a una empresa directa en la competencia.

La lista de clientes de una entidad con sus datos supone una información confidencial que es y tiene la categoría de secreto de empresa y que supone uno de los más fuertes patrimonios del desarrollo comercial de la organización que, si es cedido a tercero de la misma actividad, supone el apoderamiento de información reservada de importancia para la sociedad.

La lista de clientes apropiada y entregada a la empresa de la competencia asciende a la cifra de [COMPLETAR]

El perjuicio ocasionado a la organización del/de la querellante asciende a la suma de [IMPORTE] euros.

SEGUNDA.- Tales hechos son constitutivos de un delito de difusión, revelación o cesión de secretos de empresa del art. 279 CP.

TERCERA.- Es responsable del delito en concepto de autor/a el/la acusado/a.

CUARTA.-

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

No concurren en el/la acusado/a circunstancias agravantes.

Concurre en el/la acusado/a [COMPLETAR] la circunstancia agravante de [CIRCUNSTANCIA] del art. 22 del CP.

QUINTA.- Procede imponer al/a la acusado/a D./Dña. [NOMBRE Y APELLIDOS] la pena de [Nº] años de prisión y multa de [IMPORTE] a razón de [IMPORTE] euros/día.

SEXTA.- El importe de la responsabilidad civil por los daños causados es de [IMPORTE] euros.

Las costas deberán ser satisfechas por el/la acusado/a.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita y tenga por realizado el trámite de traslado para acusación.

Es de Justicia que pido en [LUGAR], a [FECHA].

PRIMEROTROSÍ DIGO: Que para el juicio oral intereso la práctica de los siguientes:

MEDIOS DE PRUEBA

[OPCIONAL — incluir si procede]

1.- Interrogatorio del/ de la acusado/a.

[OPCIONAL — incluir si procede]

.- Testifical:

- De D./Dña. [NOMBRE Y APELLIDOS] representante legal de la empresa [COMPLETAR] que recibió el listado de clientes del/de la querellado/a.

- De los siguientes testigos que pueden dar conocimiento del acceso del/de la querellado/a a la lista de clientes.

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

D./Dña. [NOMBRE Y APELLIDOS]

- De los siguientes testigos clientes del/de la querellante que declararán que han recibido el correo electrónico de la empresa a la que cedió la información el querellado.

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

D./Dña. [NOMBRE Y APELLIDOS]

[OPCIONAL — incluir si procede]

.- Pericial siguiente:

— Del perito D./Dña. [NOMBRE Y APELLIDOS] que refleja las pérdidas económicas
— Pericial informática del perito D./Dña. [NOMBRE Y APELLIDOS] que acredita el acceso al ordenador desde el que operaba el/la querellado/a para llevar a cabo la captación del fichero de clientes y la fecha en que ello se produjo.

[OPCIONAL — incluir si procede]

.- Documental siguiente:

— Información fiscal de la declaración de la empresa perjudicada donde consta el descenso de ingresos desde el apoderamiento.
— Correos electrónicos que recibieron los clientes de la empresa competidora.
— Lista de clientes apropiada.

Por lo expuesto,

SUPLICO A LA SECCIÓN: que declare pertinentes las pruebas interesadas y acuerde su práctica, así como se adopten las medidas cautelares para asegurar las responsabilidades civiles y las costas

[OPCIONAL — incluir si procede]

(Si no se adoptó o pidió en su momento)

SEGUNDO OTROSI DIGO: Se interesa la medida cautelar urgente de que se requiera a la empresa competidora [COMPLETAR] de que no puede proceder al uso de la información del listado de clientes sustraído y que proceda a su destrucción de forma inmediata.

SUPLICO A LA SECCIÓN: Que acuerde la medida cautelar solicitada.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a	Firma de Procurador/a

================================================================================
