---
name: uso-imagen-ajena-sin-consentimiento-medios-difusion-227
description: "Redacta el escrito «Uso de la imagen ajena sin consentimiento en medios de difusión pública: escrito de acusación» (formulario 227 de honor, intimidad y delitos de odio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Uso de la imagen ajena sin consentimiento en medios de difusión pública: escrito de acusación

> Formulario 0227 del plugin **Honor, intimidad y delitos de odio** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (17 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] FECHA (3 veces)
- [ ] NÚMERO
- [ ] LOCALIDAD
- [ ] CIRCUNSTANCIA
- [ ] PENA
- [ ] IMPORTE (2 veces)
- [ ] LUGAR
- [ ] Otros 3 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…abrió en»; «…tarialmente para el cierre del perfil en»; «… agravantes. Concurre en el/la acusado/a»

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (6)

Inclúyelos solo si encajan en los hechos:

- 1. Interrogatorio del/ de la acusado/a.…
- .- Testifical:…
- D./Dña. [NOMBRE Y APELLIDOS]…
- .- Pericial:…
- .- Documental siguiente:…
- (Si no se adoptó o pidió en su momento)…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 781.1 de la LECrim
- artículo 650 LECrim
- artículo 780 de la Ley de Enjuiciamiento Criminal
- artículo 14 de la LECrim
- art. 22 del CP
- art. 13 LECRIM
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

### Formulario 0227 · Uso de la imagen ajena sin consentimiento en medios de difusión pública: escrito de acusación

- Año del modelo: 2022
- Revisión 17-11-2026: 5 llamadas a nota sin texto retiradas; 1 párrafos repetibles señalados; 1 bloques de alternativas señalados; 5 párrafos opcionales señalados; 31 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales, actuando en representación de D./Dña. [NOMBRE Y APELLIDOS], acusador particular, según consta acreditado en el Procedimiento Abreviado [Nº DE PROCEDIMIENTO] seguido ante ese órgano judicial, comparezco y como proceda en Derecho DIGO:

Que evacuando el traslado conferido por auto de fecha [FECHA], de conformidad con lo establecido en el artículo 781.1 de la LECrim, en relación con el artículo 650 LECrim, presento ESCRITO DE ACUSACIÓN Y SOLICITO LA APERTURA DEL JUICIO ORAL ante la Sección de lo Penal del Tribunal de Instancia de [SEDE] plaza nº [NÚMERO], al amparo del artículo 780 de la Ley de Enjuiciamiento Criminal, con arreglo a lo dispuesto en el artículo 14 de la LECrim, con base en las siguientes

CONCLUSIONES

PRIMERA.- El/La acusado/a D./Dña. [NOMBRE Y APELLIDOS] abrió en [COMPLETAR] un perfil falso incluyendo fotografías del/de la querellante D./Dña. [NOMBRE Y APELLIDOS] y en la parte superior su nombre al objeto de aparentar y/o simular que, en realidad, el perfil es del/de la querellante, cuando no consta autorización alguna para esta finalidad.

El/la querellante rompió su relación de pareja con el/la acusado/a, razón por la cual este/a último/a llevó a cabo esta conducta.

En el perfil falso abierto en [LOCALIDAD] del/de la querellante se incluyen fotografías personales del/de la mismo/a de contenido sexual, así como datos relativos a que ofrece servicios sexuales a cambio de precio. Ello le ha ocasionado una situación de acoso y hostigamiento, tanto en redes sociales como en la vida real, por parte de muchas personas que contactan para solicitar dichos servicios sexuales, así como humillación por ello, habiendo recibido muchos comentarios denigrantes y vejatorios en las redes sociales.

Esta situación ha provocado al/a la querellante un estado de depresión al punto de necesitar asistencia psicológica en la consulta del especialista D./Dña. [NOMBRE Y APELLIDOS]

El/La acusado/a fue requerido notarialmente para el cierre del perfil en [COMPLETAR] negándose a ello.

SEGUNDA.- Tales hechos son constitutivos de un delito del art. 172.ter 5 CP.

TERCERA.- Es responsable del delito en concepto de autor/a el/la acusado/a.

CUARTA.-

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

No concurren en el/la acusado/a circunstancias agravantes.

Concurre en el/la acusado/a [COMPLETAR] la circunstancia agravante de [CIRCUNSTANCIA] del art. 22 del CP.

QUINTA.- Procede imponer al/a la acusado/a D./Dña. [NOMBRE Y APELLIDOS] la pena de [PENA].

SEXTA.- Se solicita se imponga al/a la acusado/a la responsabilidad civil por daño moral de [IMPORTE] euros y facturas de asistencia psicológica de D./Dña. [NOMBRE Y APELLIDOS] por importe de [IMPORTE] euros.

Las costas deberán ser satisfechas por el/la acusado/a.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita y tenga por realizado el trámite de traslado para acusación.

Es de Justicia que pido en [LUGAR], a [FECHA].

PRIMEROTROSÍ DIGO: Que para el juicio oral intereso la práctica de los siguientes:

MEDIOS DE PRUEBA

[OPCIONAL — incluir si procede]

1. Interrogatorio del/ de la acusado/a.

[OPCIONAL — incluir si procede]

.- Testifical:

-Testifical de los siguientes testigos que han visualizado el perfil falso y sus contenidos:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

D./Dña. [NOMBRE Y APELLIDOS]

-Testifical del/de la psicólogo/a D./Dña. [NOMBRE Y APELLIDOS], a cuya consulta asiste el/la querellante a raíz de los hechos.

- Testifical de la víctima D./Dña. [NOMBRE Y APELLIDOS] que declarará sobre los hechos y sobre el impacto que han provocado en su realidad diaria.

- Testifical de D./Dña. [NOMBRE Y APELLIDOS] y D./Dña. [NOMBRE Y APELLIDOS], agentes de la brigada de delitos tecnológicos de la policía nacional para que declaren sobre la averiguación del lugar desde donde se abrió la página en la red social.

[OPCIONAL — incluir si procede]

.- Pericial:

-Informe pericial psicológico emitido por el/la perito D./Dña. [NOMBRE Y APELLIDOS] sobre la situación de humillación provocada en la víctima por los hechos ocurridos y estado de depresión causado
-Pericial informática sobre el contenido del perfil de la red social recibido realizada por D./Dña. [NOMBRE Y APELLIDOS] como perito judicial informático.

[OPCIONAL — incluir si procede]

.- Documental siguiente:

- Facturas pagadas en el despacho del/de la psicólogo/a D./Dña. [NOMBRE Y APELLIDOS]
- Requerimiento notarial emitido por el/la notario/a D./Dña. [NOMBRE Y APELLIDOS] al/a la querellado en fecha [FECHA] para el cierre del perfil en redes.
- Acta notarial del/de la notario/a D./Dña. [NOMBRE Y APELLIDOS] sobre el contenido del perfil en la red social y reportaje de la misma de constancia en dicha acta notarial.

Por todo lo expuesto,

SUPLICO A LA SECCIÓN: que declare pertinentes las pruebas interesadas y acuerde su práctica, así como se adopten las medidas cautelares para asegurar las responsabilidades civiles y las costas

[OPCIONAL — incluir si procede]

(Si no se adoptó o pidió en su momento)

SEGUNDO OTROSI DIGO: Se interesa que se acuerde, ex art. 13 LECRIM, la medida cautelar de cierre provisional del perfil falso del/de la querellante para evitar la continuidad en la causación de daños y perjuicios.

Se interesa, además, se proceda a la adopción de la medida cautelar, ex art. 544 bis LECRIM, de la prohibición de acceso a internet del/de la investigado/a, en atención a la prohibición de regreso al lugar del delito, que en este caso ha sido la red de internet en cualquiera de sus modalidades, apercibiendo al/a la querellado/a con las advertencias legales.

En su caso, ofíciese a los prestadores de servicio de uso de internet para dar cuenta de la presente prohibición a los efectos de que se suspenda la posibilidad de acceso del/de la investigado/a a internet por orden judicial, y de la imposibilidad de efectuar nuevas contrataciones con otros operadores, sea cuales sean, a fin de asegurar el no acceso a internet del investigado, dada la elevada potencialidad de causar perjuicios a terceros por el efecto multiplicador de los delitos cometidos por internet y para la protección del interés general y no solo el particular del/ de la perjudicado/a en la presente causa.

SUPLICO A LA SECCIÓN: Que acuerde la medida cautelar solicitada.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a	Firma de Procurador/a

================================================================================
