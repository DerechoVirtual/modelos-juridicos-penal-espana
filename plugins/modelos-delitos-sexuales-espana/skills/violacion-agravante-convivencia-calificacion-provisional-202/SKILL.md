---
name: violacion-agravante-convivencia-calificacion-provisional-202
description: "Redacta el escrito «Violación con agravante de convivencia: calificación provisional de la acusación» (formulario 202 de delitos sexuales, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Violación con agravante de convivencia: calificación provisional de la acusación

> Formulario 0202 del plugin **Delitos sexuales** · revisado el 17-11-2026.

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

## Antes de usarlo: avisos de la revisión

El planteamiento del formulario está desfasado en algo. Corrígelo antes de redactar:

- Desde la LO 4/2023 la agravante de prevalimiento de convivencia o parentesco (arts. 180.1.5.ª y 181.5.e CP) alcanza a cualquier pariente, sin limitarse a ascendientes o hermanos, y la violación del art. 179.2 agravada tiene pena de doce a quince años.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] LOCALIDAD (2 veces)
- [ ] NOMBRE Y APELLIDOS (6 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] SEDE
- [ ] NÚMERO
- [ ] DESCRIBIR
- [ ] Nº (2 veces)
- [ ] CIRCUNSTANCIA
- [ ] PENA
- [ ] DURACIÓN (2 veces)
- [ ] IMPORTE
- [ ] LUGAR
- [ ] FECHA
- [ ] Otros 6 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «… PRIMERA.- El/La acusado/a, desde el año»; «…u libertad sexual teniendo acceso carnal»; «…desde»; «…desde [COMPLETAR] a»; «…uedado como secuelas a la víctima las de»; «…s genéricas. Concurre en el/la acusado/a»

## Elecciones que hay que hacer

- privación de la patria potestad / inhabilitación especial para el ejercicio de los derechos de la patria potestad, / inhabilitación especial para el ejercicio de los derechos de tutela / inhabilitación especial para el ejercicio de los derechos de curatela / inhabilitación especial para el ejercicio de los derechos de guarda / inhabilitación especial para el ejercicio de los derechos de acogimiento

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si la víctima tiene 16 años o más / Si la víctima es menor de 16 años — el texto de cada opción no venía en el formulario original
- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (5)

Inclúyelos solo si encajan en los hechos:

- (Si el sujeto pasivo es padre, madre, tutor, curador, guardador o acogedor)…
- 1.- Interrogatorio del acusador…
- .-Interrogatorio del/ de la acusado/a.…
- .- Testifical de las siguientes personas:…
- - D./Dña. [NOMBRE Y APELLIDOS] que conoce de los hechos.…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 651 LECrim
- art. 22 del CP
- art. 57 CP
- art. 192.1 CP
- art. 192.3 CP
- art. 544 bis LECrim
- art. 681.3 LECrim

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

### Formulario 0202 · Violación con agravante de convivencia: calificación provisional de la acusación

- Año del modelo: 2022
- Revisión 17-11-2026: 1 llamadas a nota sin texto retiradas; 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 1 bloques de alternativas señalados; 4 párrafos opcionales señalados; 25 campos de relleno marcados en blanco; 1 huecos del original que se habían perdido sin marca, marcados (IMPORTE)
- Avisos de la revisión: Desde la LO 4/2023 la agravante de prevalimiento de convivencia o parentesco (arts. 180.1.5.ª y 181.5.e CP) alcanza a cualquier pariente, sin limitarse a ascendientes o hermanos, y la violación del art. 179.2 agravada tiene pena de doce a quince años.

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la Audiencia Provincial de [LOCALIDAD]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales, actuando en representación de D./Dña. [NOMBRE Y APELLIDOS], acusador particular, según consta acreditado en el Procedimiento sumario ordinario nº [Nº DE PROCEDIMIENTO] procedente de la Sección de Instrucción del Tribunal de Instancia de [SEDE] plaza nº [NÚMERO], comparezco ante la sala y como proceda en Derecho DIGO:

En aplicación del artículo 651 LECrim. y concordantes formulo escrito de calificación, con base en las siguientes:

CONCLUSIONES PROVISIONALES

PRIMERA.- El/La acusado/a, desde el año [COMPLETAR] hasta la fecha ha realizado sobre [DESCRIBIR], de [Nº] años de edad, actos contra su libertad sexual teniendo acceso carnal [COMPLETAR] aprovechando la situación de convivencia que tenían al residir juntos en el inmueble sito en [LOCALIDAD] desde [COMPLETAR] a [COMPLETAR], llevando a cabo tales conductas mediante la presión psicológica que ejercía, advirtiéndole de que o le dejaba hacerlo o la tiraba del piso donde ella vivía y/o, produciéndose los hechos de forma repetida.

De tales hechos le han quedado como secuelas a la víctima las de [COMPLETAR].

SEGUNDA.-

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si la víctima tiene 16 años o más / Si la víctima es menor de 16 años — el texto de cada opción no venía en el formulario original]

TERCERA.- Es responsable del delito en concepto de autor/a el/la acusado/a.

CUARTA.-

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

No concurren en el/la acusado/a circunstancias agravantes genéricas.

Concurre en el/la acusado/a [COMPLETAR] la circunstancia agravante genérica de [CIRCUNSTANCIA] del art. 22 del CP.

QUINTA.- Procede imponer al/a la acusado/a D./Dña. [NOMBRE Y APELLIDOS] la pena de [PENA] de prisión, así como la pena de alejamiento de la víctima y sus familiares, del art. 57 CP, con prohibición de acercarse a menos de 500 metros y de comunicación por cualquier medio, incluidos los tecnológicos y la de libertad vigilada del art. 192.1 CP, por [Nº] años, después de cumplida la pena de prisión.

Además, se le impondrá la pena de inhabilitación especial para cualquier profesión, oficio o actividades, sean o no retribuidos, que conlleve contacto regular y directo con personas menores de edad, por un tiempo de [DURACIÓN], conforme al art. 192.3 CP.

[OPCIONAL — incluir si procede]

(Si el sujeto pasivo es padre, madre, tutor, curador, guardador o acogedor)

Procede también la pena de [ELEGIR: privación de la patria potestad / inhabilitación especial para el ejercicio de los derechos de la patria potestad, / inhabilitación especial para el ejercicio de los derechos de tutela / inhabilitación especial para el ejercicio de los derechos de curatela / inhabilitación especial para el ejercicio de los derechos de guarda / inhabilitación especial para el ejercicio de los derechos de acogimiento] por tiempo de [DURACIÓN], conforme al art. 192. 3 CP.

SEXTA.- Como responsabilidad civil a indemnizar a y a sus padres se postula se abone por los perjuicios causados por daño moral la cantidad de [IMPORTE] euros.

Las costas deberán ser satisfechas por el/la acusado/a.

Por lo expuesto,

SUPLICO A LA SALA:

Que tenga por presentado este escrito, lo admita y tenga por realizado el trámite de calificación.

Es de Justicia que pido en [LUGAR], a [FECHA].

PRIMER OTROSÍ DIGO: Que para el juicio oral intereso la práctica de los siguientes:

MEDIOS DE PRUEBA

[OPCIONAL — incluir si procede]

1.- Interrogatorio del acusador

[OPCIONAL — incluir si procede]

.-Interrogatorio del/ de la acusado/a.

[OPCIONAL — incluir si procede]

.- Testifical de las siguientes personas:

- El/La menor víctima, a fin de que se reproduzca la declaración grabada que se llevó a cabo en sede de instrucción ex art. 449 bis y ter y 703 bis LECrim..

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS] que conoce de los hechos.

- D./Dña. [NOMBRE Y APELLIDOS] y D./Dña. [NOMBRE Y APELLIDOS] agentes de las fuerzas y cuerpos de seguridad del Estado que llevaron a cabo la investigación.

Por lo expuesto.

SUPLICO A LA SALA: Que declare pertinentes las pruebas interesadas y acuerde su práctica.

SEGUNDO OTRO SÍ DIGO: Se interesa, asimismo, que en base al art. 544 bis LECrim., dado que el delito cometido está entre los incluidos en el art. 57 CP, se dicte una orden de alejamiento que le impida acercarse a la víctima y a sus familiares a menos de 500 metros, así como, sobre todo, una orden de prohibición de comunicación por cualquier tipo de medio, incluidos los tecnológicos.

De conformidad con lo dispuesto en el art. 681.3 LECrim., según redacción dada por LO 10/2022, se interesa que se acuerde la prohibición de la divulgación o publicación de información relativa a la identidad de la víctima, y de datos que puedan facilitar la identificación de forma directa o indirecta, o de aquellas circunstancias personales que hubieran sido valoradas para resolver sobre sus necesidades de protección, así como la obtención, divulgación o publicación de imágenes suyas o de sus familiares.

SUPLICO A LA SALA: que adopte las medidas cautelares interesadas y las necesarias para asegurar las responsabilidades civiles y las costas y se comunique a esta parte.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a	Firma de Procurador/a

================================================================================
