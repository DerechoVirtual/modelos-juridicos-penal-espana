---
name: corrupcion-menores-defensa-824
description: "Redacta el escrito «Corrupción de menores: defensa» (formulario 824 de delitos sexuales, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Corrupción de menores: defensa

> Formulario 0824 del plugin **Delitos sexuales** · revisado el 17-11-2026.

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
- [ ] Nº (3 veces)
- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] LUGAR
- [ ] DÍA
- [ ] MES
- [ ] AÑO
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…/»; «…establecimiento, sin conocer si la menor»

## Elecciones que hay que hacer

- a continuación / en escrito aparte
- judicialmente / mediante exhorto

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS
- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 188 CP
- artículo 784.1 de la Ley de Enjuiciamiento Criminal
- art. 188.1 CP
- art. 730 LECRIM
- art. 14.6 LECRIM
- art. 14.5 LECRIM
- art. 89.5 LOPJ
- artículos 14.7 LECrim
- art. 191 CP
- art. 192 CP
- art. 777.2 LECr
- art. 449 bis LECRIM
- art. 449 ter LECRIM

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

### Formulario 0824 · Corrupción de menores: defensa

- Año del modelo: 2016
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; restos de formato retirados; notas del formulario agrupadas al final (4); 1 desplegables y casillas convertidos en elección en blanco; 1 desplegables convertidos en elección en blanco; 2 bloques de alternativas señalados; 8 campos de relleno marcados en blanco; 3 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la defensa en procedimiento abreviado presenta sus conclusiones provisionales frente a acusación por delito de corrupción de menores del art. 188 CP

Actualizado conforme a la LO 10/2022, de garantía integral de la libertad sexual, con entrada en vigor el 7 de octubre de 2022.

Actualizado conforme a la LO 1/2025, de Eficiencia de la Justicia.

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

A la Sección de Violencia sobre la Mujer del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

A la Sección de Violencia contra la Infancia y la Adolescencia del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales en la representación que tiene acreditada de D./Dña. [NOMBRE Y APELLIDOS], acusado/a en las diligencias previas [Nº DE PROCEDIMIENTO] / [COMPLETAR], por el supuesto delito de corrupción de menores comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

Que, conforme a lo preceptuado en el artículo 784.1 de la Ley de Enjuiciamiento Criminal, manifiesto mi disconformidad con los escritos de acusación y formulo en plazo (1) escrito de defensa en base a las siguientes:

CONCLUSIONES

PRIMERA.- Disconforme con la correlativa del Ministerio Fiscal y del acusador particular. Mi representado no hizo lo que se le atribuye ya que no realizó ningún acto de inducción, promoción, favorecimiento o de facilitar la prostitución de una menor de edad como se expone en el escrito de acusación, ya que el acusado/la acusada solo regenta el establecimiento, sin conocer si la menor [COMPLETAR] realizaba allí contactos sexuales, ya que el establecimiento es un motel de carretera donde van clientes sobre los que no debe conocer el acusado/la acusada ni el objeto de su estancia ni con quien están. Cierto y verdad es que el acusado/la acusada ha visto allí en ocasiones a la menor, sin saber que lo era por su aspecto externo, con algunas personas, pero sin que mi representado hubiera intervenido para nada.

SEGUNDA.- Los hechos no son constitutivos de un delito de corrupción de menores del art. 188.1 CP. (2)

TERCERA.- Niego las correlativas. Mi representado no es el autor del delito por el que se procede ni de ningún otro.

CUARTA.- Disconforme con las correlativas. Al no ser autor de ningún delito no pueden existir circunstancias modificativas de la responsabilidad inexistente.

QUINTA.- Disconforme con las correlativas. Procede absolver a mi representado con todos los pronunciamientos favorables, por no ser el autor.

SEXTA.- Disconforme con las correlativas. No puede existir responsabilidad civil cuando no existe delito. Y por lo mismo procede declarar las costas de oficio.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito con sus copias, los admita y por realizada la calificación.

Es de Justicia que pido en [LUGAR], a [DÍA] de [MES] de [AÑO].

OTROSÍ DIGO:

Que para el acto del juicio oral propongo los siguientes:

MEDIOS DE PRUEBA (3)

1.- Testifical: declaración de los testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados [ELEGIR: judicialmente / mediante exhorto],

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

- Exploración del/de la menor por videoconferencia

- Reproducción en plenario de la declaración sumarial del/de la menor como exploración practicada, vía art. 730 LECRIM. (4)

- D./Dña. [NOMBRE Y APELLIDOS] trabajador del local.

- D./Dña. [NOMBRE Y APELLIDOS] trabajador del local.

2.- Documental: se adjunta la documentación del local acreditativa de que es un motel.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 10 días desde que se recibe traslado del escrito de acusación.

Cuando la víctima sea un niño, niña o adolescente la competencia para la instrucción es de la Sección de Violencia contra la Infancia y la Adolescencia, si la hay (art. 14.6 LECRIM y art. 89 bis 5 LOPJ). Pero lo es la Sección de Violencia sobre la Mujer del Tribunal de Instancia cuando la víctima sea o haya sido su esposa, o mujer que esté o haya estado ligada al autor por análoga relación de afectividad, aun sin convivencia, así como de los cometidos sobre los descendientes, propios o de la esposa o conviviente, o sobre los menores o personas con discapacidad que con él convivan o que se hallen sujetos a la potestad, tutela, curatela, acogimiento o guarda de hecho de la esposa o conviviente, cuando también se haya producido un acto de violencia de género y, desde el 3 de octubre de 2025, tras la reforma operada por la LO 1/2025, de Eficiencia de la Justicia, también instruye estos delitos cuando la víctima sea una mujer (art. 14.5 LECRIM y art. 89.5 LOPJ). Los artículos 14.7 LECrim y art. 89 bis 7 LOPJ disponen que "en caso de que los hechos objeto de instrucción por la Sección de Violencia contra la Infancia y Adolescencia también pudieran ser conocidos por la Sección de Violencia sobre la Mujer, la competencia corresponderá, en todo caso, a la segunda". Entonces, si la víctima fuera niña o chica correspondería a las Secciones de Violencia sobre la Mujer, pero el grupo de expertos del Observatorio de Violencia Doméstica y de Género del CGPJ interpreta que solo irá a la Sección de Violencia sobre la Mujer en los siguientes casos: (I) En los supuestos de violencia vicaria, cuando los niños, niñas o adolescentes son víctimas de la violencia ejercida sobre la madre; (II) Cuando la violencia sobre la menor es ejercida por su pareja o ex pareja.

(2) Los elementos objetivos del tipo del art. 188 CP son: la mecánica de la acción se centra en que esta se lleve a cabo por acción de quien induzca, promueva, favorezca o facilite la prostitución de un menor de edad o una persona con discapacidad necesitada de especial protección, o se lucre con ello, o explote de algún otro modo a un menor o a una persona con discapacidad para estos fines.

El sujeto pasivo es una persona menor de edad.

El fin es ejercer o a mantenerse en la prostitución.

Se aplicará una agravación en la pena del apartado 2º si los hechos descritos se cometieran con violencia o intimidación.

En el apartado 3º se incluyen más agravantes:

Es un delito perseguible de oficio, aunque se puede ejercitar querella si el sujeto pasivo es un familiar, porque a tenor del art. 191 CP, en los casos de los delitos de agresiones sexuales y acoso sexual [NOTA DE REVISIÓN: Desde la LO 10/2022 el art. 191.1 CP exige denuncia solo para las agresiones sexuales y el acoso sexual; la categoría de abusos sexuales ha desaparecido. Fuente: Código Penal, BOE-A-1995-25444, art. 191 (redacción LO 10/2022, BOE-A-2022-14630).], será precisa denuncia de la persona agraviada, de su representante legal o querella del Ministerio Fiscal, que actuará ponderando los legítimos intereses en presencia.

Resulta importante destacar que, a tenor del art. 192 CP, a los condenados a pena de prisión por uno o más delitos comprendidos en este Título VIII se les impondrá además la medida de libertad vigilada, que se ejecutará con posterioridad a la pena privativa de libertad.

(3) En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos, al comienzo del juicio oral pueden aportarse más pruebas.

También debe pedirse que se reproduzca la grabación o lectura literal de la prueba practicada anticipadamente en la fase de diligencias previas (art. 777.2 LECr).

(4) A instancia de la parte interesada se procederá a la reproducción de la grabación audiovisual de la declaración de testigos efectuada como prueba preconstituida, sin que sean necesaria la presencia del testigo en la vista (art. 449 bis LECRIM).

En el caso de la declaración del testigo menor de 14 años o discapacitado como prueba preconstituida (art. 449 ter LECRIM), el juez solo puede acordar la intervención del testigo en el acto del juicio, excepcionalmente, cuando sea solicitada por alguna de las partes, siempre que la considere necesaria en resolución motivada, asegurando que la grabación audiovisual cuenta con los apoyos de accesibilidad cuando el testigo sea un discapacitado.

En todo caso, si la prueba preconstituida no reúne todos los requisitos legales y causa indefensión a alguna de las partes, el juez, previa petición de parte, podrá acordar su intervención en la vista. (Art. 703 bis LECRIM)

================================================================================
