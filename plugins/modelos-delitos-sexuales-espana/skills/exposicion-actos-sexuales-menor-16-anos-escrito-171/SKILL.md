---
name: exposicion-actos-sexuales-menor-16-anos-escrito-171
description: "Redacta el escrito «Exposición de actos sexuales a menor de 16 años: escrito de acusación» (formulario 171 de delitos sexuales, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Exposición de actos sexuales a menor de 16 años: escrito de acusación

> Formulario 0171 del plugin **Delitos sexuales** · revisado el 17-11-2026.

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

- [ ] SEDE (3 veces)
- [ ] Nº (5 veces)
- [ ] NOMBRE Y APELLIDOS (9 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] FECHA (2 veces)
- [ ] LOCALIDAD
- [ ] CIRCUNSTANCIA
- [ ] PENA
- [ ] DISTANCIA EN METROS
- [ ] DURACIÓN
- [ ] IMPORTE
- [ ] LUGAR
- [ ] Otros 7 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…A.- Durante el periodo comprendido entre»; «…D. se hacía cargo de la menor»; «…e viaje. En varias ocasiones, la llevó a»; «…. En el colegio»; «… En el colegio [COMPLETAR] el/la tutor/a»; «…ncias agravantes. Concurre en el acusado»; «…l colegio que conoce los hechos por ella»

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS
- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (6)

Inclúyelos solo si encajan en los hechos:

- 1.- Interrogatorio del acusado.…
- .- Declaración de la víctima, a fin de que sea reproducida la declaración grabada llevada a cabo como prueba p…
- .- Testifical. Declaración de los siguientes testigos:…
- -D./Dña. [NOMBRE Y APELLIDOS] amiga de la menor del colegio que conoce los hechos por ella [COMPLETAR]…
- .- Pericial. Declaración de los/as peritos que se mencionan a continuación, que deberán ser citados/as judicia…
- .- Documental, teniendo por reproducidos los documentos aportados hasta el juicio oral.…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 781.1 de la LECrim
- artículo 650 LECrim
- art. 780 de la LECrim
- art. 14 de la LECrim
- art. 182 CP
- art. 74 CP
- art. 22 del CP
- art. 57 CP
- art. 192.1 CP
- art. 192.3 CP
- art. 449 ter LECrim
- art. 777.3 LECrim
- art. 730.2 LECrim
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

### Formulario 0171 · Exposición de actos sexuales a menor de 16 años: escrito de acusación

- Año del modelo: 2022
- Revisión 17-11-2026: 3 llamadas a nota sin texto retiradas; 1 párrafos repetibles señalados; 2 bloques de alternativas señalados; 5 párrafos opcionales señalados; 27 campos de relleno marcados en blanco; 3 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

A la Sección de Violencia sobre la Mujer del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

A la Sección de Violencia contra la Infancia y la Adolescencia del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales, actuando en representación de Dña. [NOMBRE Y APELLIDOS], acusador particular, según consta acreditado en el Procedimiento Abreviado [Nº DE PROCEDIMIENTO] seguido ante ese órgano judicial, comparezco y como proceda en Derecho DIGO:

Que evacuando el traslado conferido por auto de fecha [FECHA], de conformidad con lo establecido en el art. 781.1 de la LECrim-, en relación con el artículo 650 LECrim, presento ESCRITO DE ACUSACIÓN Y SOLICITO LA APERTURA DEL JUICIO ORAL ante la Sección de lo Penal de [LOCALIDAD], al amparo del art. 780 de la LECrim., con arreglo a lo dispuesto en el art. 14 de la LECrim., con base en las siguientes

CONCLUSIONES

PRIMERA.- Durante el periodo comprendido entre [COMPLETAR] D. se hacía cargo de la menor [COMPLETAR] cuando sus padres se iban de viaje. En varias ocasiones, la llevó a [COMPLETAR] donde tenían lugar actos de contenido sexual para que los presenciara. Esto ocurrió desde que la menor tenía 8 años hasta los 11 años, diciéndole que no le dijera nada a sus padres porque era un secreto entre ellos. Finalmente, la menor se lo confesó todo a sus padres, formulando estos la presente querella.

La menor ha sufrido de ansiedad por estos hechos, estando sometida en la actualidad a tratamiento psicológico con el/la psicólogo/a D./Dña. [NOMBRE Y APELLIDOS]. En el colegio [COMPLETAR] el/la tutor/a [COMPLETAR] y encargado/a del protocolo de prevención en delincuencia sexual ha emitido informe señalando el extraño comportamiento de la menor en temas sexuales.

SEGUNDA.- Tales hechos son constitutivos de un delito continuado de exposición inmediata de actos sexuales a menor de 16 años del art. 182 CP, en relación con el art. 74 CP.

TERCERA.- Es responsable del delito en concepto de autor el acusado.

CUARTA.-

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

No concurren en el acusado circunstancias agravantes.

Concurre en el acusado [COMPLETAR] la circunstancia agravante de [CIRCUNSTANCIA] del art. 22 del CP.

QUINTA.- Procede imponer al acusado D. la pena de [PENA], así como la pena de alejamiento de la víctima del art. 57 CP, a fin de que no se le acerque a menos de [DISTANCIA EN METROS] metros durante [Nº] años, así como la pena de prohibición de comunicación por cualquier medio y la de libertad vigilada del art. 192.1 CP, por [Nº] años, después de cumplida la pena de prisión.

Además, se le impondrá la pena de inhabilitación especial para cualquier profesión, oficio o actividades, sean o no retribuidos, que conlleve contacto regular y directo con personas menores de edad, por un tiempo de [DURACIÓN], conforme al art. 192.3 CP.

SEXTA.- El importe de la responsabilidad civil por daño moral es de [IMPORTE] euros.

Las costas deberán ser satisfechas por el/la acusado/a.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita y tenga por realizado el trámite de traslado para acusación.

Es de Justicia que pido en [LUGAR], a [FECHA].

PRIMEROTROSÍ DIGO: Que para el juicio oral intereso la práctica de los siguientes:

MEDIOS DE PRUEBA

[OPCIONAL — incluir si procede]

1.- Interrogatorio del acusado.

[OPCIONAL — incluir si procede]

.- Declaración de la víctima, a fin de que sea reproducida la declaración grabada llevada a cabo como prueba preconstituida, en base al art. 449 ter LECrim., en relación con el art. 777.3 LECrim. y el art. 730.2 LECrim.

[OPCIONAL — incluir si procede]

.- Testifical. Declaración de los siguientes testigos:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

-D./Dña. [NOMBRE Y APELLIDOS] amiga de la menor del colegio que conoce los hechos por ella [COMPLETAR]

-D./Dña. [NOMBRE Y APELLIDOS] hermana de la menor.

-D./Dña. [NOMBRE Y APELLIDOS] tutor del colegio de la menor.

-D./Dña. [NOMBRE Y APELLIDOS] encargado del protocolo de prevención de delincuencia sexual.

[OPCIONAL — incluir si procede]

.- Pericial. Declaración de los/as peritos que se mencionan a continuación, que deberán ser citados/as judicialmente:

-D./Dña. [NOMBRE Y APELLIDOS] perito psicólogo que elaboró el dictamen sobre afectación psicológica de la menor tras los hechos ocurridos.
-D./Dña. [NOMBRE Y APELLIDOS] sobre credibilidad del testimonio.

[OPCIONAL — incluir si procede]

.- Documental, teniendo por reproducidos los documentos aportados hasta el juicio oral.

Por todo lo expuesto,

SUPLICO A LA SECCIÓN: que declare pertinentes las pruebas interesadas y acuerde su práctica, así como se adopten las medidas cautelares para asegurar las responsabilidades civiles y las costas.

De conformidad con lo dispuesto en el art. 681.3 LECrim., según redacción dada por LO 10/2022, de garantía integral de la libertad sexual, se interesa que se acuerde la prohibición de la divulgación o publicación de información relativa a la identidad de la menor, y de datos que puedan facilitar la identificación de forma directa o indirecta, o de aquellas circunstancias personales que hubieran sido valoradas para resolver sobre sus necesidades de protección, así como la obtención, divulgación o publicación de imágenes suyas o de sus familiares

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a	Firma de Procurador/a

================================================================================
