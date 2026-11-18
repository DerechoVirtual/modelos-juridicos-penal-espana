---
name: corrupcion-menores-acusacion-827
description: "Redacta el escrito «Corrupción de menores: acusación» (formulario 827 de delitos sexuales, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Corrupción de menores: acusación

> Formulario 0827 del plugin **Delitos sexuales** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (7 veces)
- [ ] COLEGIO
- [ ] LOCALIDAD
- [ ] NOMBRE DEL REPRESENTADO/A
- [ ] FECHA (3 veces)
- [ ] PENA
- [ ] DISTANCIA EN METROS
- [ ] DURACIÓN
- [ ] IMPORTE
- [ ] LUGAR
- [ ] Otros 4 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…de la menor de edad»; «…su minoría de edad, llevándola al centro»; «…los hechos fue la amiga de»; «…, de nombre»

## Elecciones que hay que hacer

- el padre / la madre
- padre / madre
- del padre / de la madre
- a continuación / en escrito aparte
- judicialmente / mediante exhorto

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (5)

Inclúyelos solo si encajan en los hechos:

- 1.- Interrogatorio del/de la acusado/a.…
- .- Declaración de la víctima, a fin de que sea reproducida la declaración grabada llevada a cabo como prueba p…
- .- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y …
- .- Pericial: declaración del/de la perito que se menciona a continuación, que deberá ser citado/a judicialment…
- .- Documental: por lectura de todo lo actuado hasta el momento de la vista oral.…

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 188.1 CP
- art. 77 RDL 6/2023
- art. 24.1 LEC
- artículo 780.1 de la Ley de Enjuiciamiento Criminal
- art. 781 LECRIM
- art. 780 LECRIM
- art. 650 LECRIM
- art. 188.1 del Código Penal
- art. 57 CP
- art. 192 CP
- art. 192.3 CP
- art. 681.3 LECRIM
- art. 449 ter LECRIM
- art. 777.3 LECRIM
- art. 730.2 LECRIM
- art. 14.6 LECRIM
- art. 14.5 LECRIM
- art. 89.5 LOPJ
- artículos 14.7 LECrim
- art. 188 CP
- art. 191 CP

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

### Formulario 0827 · Corrupción de menores: acusación

- Año del modelo: 2016
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; restos de formato retirados; notas del formulario agrupadas al final (3); 4 desplegables y casillas convertidos en elección en blanco; 2 desplegables convertidos en elección en blanco; 1 bloques de alternativas señalados; 5 párrafos opcionales señalados; 23 campos de relleno marcados en blanco; 3 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito de la acusación particular en procedimiento abreviado por el que se solicita la apertura del juicio oral y se presentan sus conclusiones provisionales calificando los hechos como delito de corrupción de menores del art. 188.1 CP

Encabezamiento actualizado conforme al art. 77 RDL 6/2023, vigente desde 9-1-2024 y art. 24.1 LEC, vigente desde 20-3-2024.

Actualizado conforme a la LO 1/2025, de Eficiencia de la Justicia.

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

A la Sección de Violencia sobre la Mujer del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

A la Sección de Violencia contra la Infancia y la Adolescencia del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a del Ilustre Colegio de Procuradores de [COLEGIO], con nº de colegiado y con despacho profesional abierto en [LOCALIDAD], en representación del acusador particular D./Dña. [NOMBRE Y APELLIDOS], comparezco ante este órgano judicial y como mejor proceda en derecho, DIGO:

En aplicación del artículo 780.1 de la Ley de Enjuiciamiento Criminal, mediante el presente escrito formulo solicitud de apertura de juicio oral ante la Sección de lo Penal del Tribunal de Instancia por la vía del art. 781 LECRIM y, en plazo (1), escrito de acusación por la vía del art. 780 LECRIM, en relación con el art. 650 LECRIM, contra D.Dña. con base en las siguientes:

CONCLUSIONES

PRIMERA.- Mi representado/a D./Dña. [NOMBRE Y APELLIDOS] es [ELEGIR: el padre / la madre] de la menor de edad [COMPLETAR].

ElLa acusado/a D./Dña. [NOMBRE Y APELLIDOS] indujo a la prostitución a la hija de mi mandante [NOMBRE DEL REPRESENTADO/A], menor de edad, al convencerla para acudir a un centro de contactos sexuales aprovechándose de la debilitada situación económica de la familia y de la baja estructura social y familiar, así como de su minoría de edad, llevándola al centro [COMPLETAR] donde la convenció para que ejerciera la prostitución, lucrándose por ello, lo que ha venido realizando desde el día [FECHA] hasta el día [FECHA] que su [ELEGIR: padre / madre] la localizó y la sacó del local.

La persona que puso en conocimiento [ELEGIR: del padre / de la madre] los hechos fue la amiga de [COMPLETAR], de nombre [COMPLETAR], mayor de edad, quien quiso comunicárselo a su [ELEGIR: padre / madre] para que conociera el lugar donde se encontraba su hija por haber estado ella trabajando allí.

A consecuencia de estos hechos la menor de edad sufrió trastornos por depresión como se constata en informe pericial que consta en autos.

SEGUNDA.- Tales hechos son constitutivos del delito de corrupción de menores del art. 188.1 del Código Penal al concurrir los elementos del apartado 1º. (2)

TERCERA.- Es responsable del delito de corrupción de menores en concepto de autor/a el/la acusado/a.

CUARTA.- No concurre con respecto al/a la acusado/a ninguna circunstancia modificativa de la responsabilidad penal.

QUINTA.- Procede imponer al/a la acusado/a por el delito de corrupción de menores la pena de [PENA]; así como la pena de alejamiento de la víctima del art. 57 CP, a fin de que no se le acerque a menos de [DISTANCIA EN METROS] metros durante [Nº] años, así como la pena de prohibición de comunicación por cualquier medio.

Además, en caso de imponer prisión, procederá también la libertad vigilada por [Nº] años, después de cumplida la pena de prisión, del art. 192 CP.

Igualmente, deberá imponérsele la pena de inhabilitación especial para cualquier profesión, oficio o actividades, sean o no retribuidos, que conlleve contacto regular y directo con personas menores de edad, por un tiempo de [DURACIÓN], conforme al art. 192.3 CP.

De conformidad con lo dispuesto en el art. 681.3 LECRIM, según redacción dada por LO 10/2022, se interesa que se acuerde la prohibición de la divulgación o publicación de información relativa a la identidad de la víctima, y de datos que puedan facilitar la identificación de forma directa o indirecta, o de aquellas circunstancias personales que hubieran sido valoradas para resolver sobre mis necesidades de protección, así como la obtención, divulgación o publicación de imágenes de la víctima o de sus familiares.

SEXTA.- Los hechos han causado un daño moral que se valora en la suma de [IMPORTE] euros.

Las costas deberán ser satisfechas por el/la acusado/a.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita y tenga por realizado el trámite de traslado para acusación.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que para el juicio oral intereso la práctica de los siguientes:

MEDIOS DE PRUEBA (3)

[OPCIONAL — incluir si procede]

1.- Interrogatorio del/de la acusado/a.

[OPCIONAL — incluir si procede]

.- Declaración de la víctima, a fin de que sea reproducida la declaración grabada llevada a cabo como prueba preconstituida, en base al art. 449 ter LECRIM, en relación con el art. 777.3 LECRIM y el art. 730.2 LECRIM.

[OPCIONAL — incluir si procede]

.- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados/as [ELEGIR: judicialmente / mediante exhorto],

- Dña. [NOMBRE Y APELLIDOS], que trabajaba en el club de alterne.

- Dña. [NOMBRE Y APELLIDOS], amiga de la hija del/de la querellante.

[OPCIONAL — incluir si procede]

.- Pericial: declaración del/de la perito que se menciona a continuación, que deberá ser citado/a judicialmente:

D./Dña. [NOMBRE Y APELLIDOS] que elaboró el informe sobre los trastornos de depresión de la hija de mi mandante.

[OPCIONAL — incluir si procede]

.- Documental: por lectura de todo lo actuado hasta el momento de la vista oral.

Por todo lo expuesto,

SUPLICO A LA SECCIÓN: Que declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 10 días desde la notificación del auto del juez por la vía del art. 780 LECRIM solicitando la apertura del juicio oral formulando escrito de acusación.

Cuando la víctima sea un niño, niña o adolescente la competencia para la instrucción es de la Sección de Violencia contra la Infancia y la Adolescencia, si la hay (art. 14.6 LECRIM y art. 89 bis 5 LOPJ). Pero lo es la Sección de Violencia sobre la Mujer del Tribunal de Instancia cuando la víctima sea o haya sido su esposa, o mujer que esté o haya estado ligada al autor por análoga relación de afectividad, aun sin convivencia, así como de los cometidos sobre los descendientes, propios o de la esposa o conviviente, o sobre los menores o personas con discapacidad que con él convivan o que se hallen sujetos a la potestad, tutela, curatela, acogimiento o guarda de hecho de la esposa o conviviente, cuando también se haya producido un acto de violencia de género y, desde el 3 de octubre de 2025, tras la reforma operada por la LO 1/2025, de Eficiencia de la Justicia, también instruye estos delitos cuando la víctima sea una mujer (art. 14.5 LECRIM y art. 89.5 LOPJ). Los artículos 14.7 LECrim y art. 89 bis 7 LOPJ disponen que "en caso de que los hechos objeto de instrucción por la Sección de Violencia contra la Infancia y Adolescencia también pudieran ser conocidos por la Sección de Violencia sobre la Mujer, la competencia corresponderá, en todo caso, a la segunda". Entonces, si la víctima fuera niña o chica correspondería a las Secciones de Violencia sobre la Mujer, pero el grupo de expertos del Observatorio de Violencia Doméstica y de Género del CGPJ interpreta que solo irá a la Sección de Violencia sobre la Mujer en los siguientes casos: (I) En los supuestos de violencia vicaria, cuando los niños, niñas o adolescentes son víctimas de la violencia ejercida sobre la madre; (II) Cuando la violencia sobre la menor es ejercida por su pareja o ex pareja.

(2) Los elementos objetivos del tipo del art. 188 CP son: la mecánica de la acción se centra en que esta se lleve a cabo por acción de quien induzca, promueva, favorezca o facilite la prostitución de un menor de edad o una persona con discapacidad necesitada de especial protección, o se lucre con ello, o explote de algún otro modo a un menor o a una persona con discapacidad para estos fines.

El sujeto pasivo es una persona menor de edad.

El fin es ejercer o a mantenerse en la prostitución.

Se aplicará una agravación en la pena del apartado 2º si los hechos descritos se cometieran con violencia o intimidación.

En el apartado 3º se incluyen más agravantes:

Es un delito perseguible de oficio, aunque se puede ejercitar querella si el sujeto pasivo es un familiar, porque a tenor del art. 191 CP, en los casos de los delitos de agresiones sexuales y acoso sexual [NOTA DE REVISIÓN: Desde la LO 10/2022 el art. 191.1 CP exige denuncia solo para las agresiones sexuales y el acoso sexual; la categoría de abusos sexuales ha desaparecido. Fuente: Código Penal, BOE-A-1995-25444, art. 191 (redacción LO 10/2022, BOE-A-2022-14630).], será precisa denuncia de la persona agraviada, de su representante legal o querella del Ministerio Fiscal, que actuará ponderando los legítimos intereses en presencia.

Resulta importante destacar que, a tenor del art. 192 CP, a los condenados a pena de prisión por uno o más delitos comprendidos en este Título VIII se les impondrá además la medida de libertad vigilada, que se ejecutará con posterioridad a la pena privativa de libertad.

(3) En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos, al comienzo del juicio oral pueden aportarse más pruebas.

También debe pedirse que se reproduzca la grabación o lectura literal de la prueba practicada anticipadamente en la fase de diligencias previas (art. 777.2. LECr.).

================================================================================
