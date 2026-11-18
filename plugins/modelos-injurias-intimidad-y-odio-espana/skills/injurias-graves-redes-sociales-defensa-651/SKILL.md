---
name: injurias-graves-redes-sociales-defensa-651
description: "Redacta el escrito «Injurias graves en redes sociales: defensa» (formulario 651 de honor, intimidad y delitos de odio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Injurias graves en redes sociales: defensa

> Formulario 0651 del plugin **Honor, intimidad y delitos de odio** · revisado el 17-11-2026.

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

- [ ] SEDE
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] LUGAR
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «…n en sí mismas trascendencia difamatoria»

## Párrafos opcionales (2)

Inclúyelos solo si encajan en los hechos:

- 1.- Interrogatorio del/de la acusado/a.…
- .- Documental: por lectura de la propia transcripción aportada del contenido de la expresión subida a la red s…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 208 del CP
- art. 208 CP
- artículo 784.1 de la Ley de Enjuiciamiento Criminal
- art. 784 LECRIM
- art. 208 del Código Penal
- art. 777.2 LECrim

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

### Formulario 0651 · Injurias graves en redes sociales: defensa

- Año del modelo: 2017
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (3); 2 párrafos opcionales señalados; 5 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la defensa presenta sus conclusiones provisionales en procedimiento abreviado alegando que los hechos no constituyen un delito de injurias del art. 208 del CP porque los comentarios subidos a la red social no tienen la suficiente gravedad como para integrar el tipo penal.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales en la representación que tiene acreditada de D./Dña. [NOMBRE Y APELLIDOS], acusado/a en las diligencias previas número [Nº DE PROCEDIMIENTO] por el supuesto delito de injurias graves con publicidad del art. 208 CP, comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

Que, conforme a lo preceptuado en el artículo 784.1 de la Ley de Enjuiciamiento Criminal, manifiesto mi disconformidad con los escritos de acusación y formulo escrito de defensa (1) en base a las siguientes:

CONCLUSIONES

PRIMERA.- Disconforme con la correlativa del Ministerio Fiscal y del acusador particular. Mi representado/a solo hizo un comentario en tono burlón que, puede no ser muy afortunado, pero que no integra las exigencias del tipo penal del art. 208 CP que, tras la LO 1/2015, despenalizó las injurias leves. El hecho de que se haya realizado por redes sociales no eleva la gravedad de los hechos al objetivarse un mero comentario sarcástico que, puede no ser acertado, pero que en virtud del principio de intervención mínima del derecho penal, no es lo suficientemente grave como para integrar las exigencias del tipo.

Así, desde el 1 de Julio de 2015, la injuria leve ha sido despenalizada y entendemos que, en el peor de los escenarios puede existir, si acaso, una injuria leve, pero nunca una grave, por desafortunada que fuera la expresión no pudiendo alcanzar tal consideración. (2)

SEGUNDA.- Los hechos no son constitutivos de un delito de injurias graves del art. 208 CP

TERCERA.- Niego las correlativas. Mi representado/a no es el/la autor/a del delito por el que se procede ni de ningún otro.

CUARTA.- Disconforme con las correlativas. Al no ser autor/a de ningún delito no pueden existir circunstancias modificativas de la responsabilidad inexistente.

QUINTA.- Disconforme con las correlativas. Procede absolver a mi representado/a con todos los pronunciamientos favorables, por no ser el/la autor/a.

SEXTA.- No existiendo delito no ha lugar a realizar pronunciamiento alguno en torno a la responsabilidad civil.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito con sus copias, los admita y por realizada la calificación.

Es de Justicia que pido en [LUGAR]

OTROSÍ DIGO: Que para el acto del juicio oral propongo los siguientes:

MEDIOS DE PRUEBA (3)

Todos los propuestos por el Ministerio fiscal y el acusador particular y además los siguientes:

[OPCIONAL — incluir si procede]

1.- Interrogatorio del/de la acusado/a.

[OPCIONAL — incluir si procede]

.- Documental: por lectura de la propia transcripción aportada del contenido de la expresión subida a la red social, que es reconocida por el/la acusado/a, aun negando la gravedad de la expresión.

Por lo expuesto,

SUPLICO A LA SECCIÓN: Declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a	Firma de Procurador/a

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 10 días desde el traslado del art. 784 LECRIM por el letrado de la administración de Justicia.

(2) Solo se perseguirá penalmente la injuria grave desde la LO 1/2015, dejando la leve para la persecución civil por la vía de atentado al derecho al honor.

Para entender que las injurias son graves (SAP Asturias Sección 3ª, 264/2017 de 30 de mayo, Rec. 517/2017) hay que recordar que en estos casos el delito de injurias graves debe aparecer nítidamente perfilado en cada caso por concurrir el elemento objetivo consistente en las expresiones proferidas que por su significación deben ser gravemente atentatorias a la dignidad de la persona afectada y el elemento subjetivo integrado por el propósito de menoscabar tal dignidad.

Es un delito estrictamente doloso.

También la SAP Salamanca 27/2017 de 15 de mayo, Rec. 8/2017 recuerda que constituye una doctrina ya reiterada, que para la existencia del delito de injurias, cuyo bien jurídico protegido lo constituye el honor inherente a la dignidad de la persona, se requiere la concurrencia de dos elementos fundamentales: uno objetivo, constituido por actos o expresiones que tengan en si la suficiente potencia ofensiva para lesionar la dignidad de la persona, menoscabando su fama o atentando contra su propia estimación; el concepto de honor debe construirse desde puntos de vista valorativos, y en consecuencia, con relación a aquella dignidad personal, constituyendo el honor desde esta perspectiva, la pretensión del respeto que corresponde a cada persona (natural o jurídica) corno consecuencia del reconocimiento de su dignidad. La acción ha de tener en la injuria un significado objetivamente ofensivo, según los parámetros sociales en los que la expresión se efectúe, y es imprescindible que concurra el elemento intencional de lesionar la dignidad, menoscabando la fama o estimación personal.

El elemento subjetivo del injusto en la injuria lo constituye lo que se ha venido denominando "animus injuriandi", que como dolo específico de esta infracción penal, eminentemente tendencial, implica la intención de causar un ataque a la dignidad ajena, el propósito de ofender la dignidad personal, de menoscabar la fama de la persona, o atentar contra su propia estima. La determinación de si concurre o no en el sujeto esa intención o animus, no puede, generalmente, hacerse de modo directo, sino que, por afectar a la esfera íntima de la persona, habrá de inferirse indirectamente, a través, o a partir, de las manifestaciones externas de su conducta debidamente acreditadas, y por tanto, atendiendo a la serie de hechos que integran el núcleo de tipo penal y sirven tanto para investigar el ánimo de injurias, como la gravedad de la injuria. La jurisprudencia ha venido admitiendo la presunción "iuris tantum" del referido ánimo, cuando las frases empleadas manifiestan objetivamente y revisten en sí mismas trascendencia difamatoria [COMPLETAR]. De modo que ciertas expresiones y vocablos son de tal modo insultantes o difamantes que el ánimo de injurias se encuentra ínsito en ellos, y cuando son empleados corresponde a quien los utiliza contra alguien, demostrar y acreditar que le movía otro ánimo distinto del de injurias. Para ello, puede probarse que el ánimo no fue ese, y puede diluirse o desplazarse por otro ánimo diferente que excluya el del injusto típico, contrarrestando o anulando este último.

Así mismo, otras Sentencias recogen lo expresado en las anteriores delimitando tres elementos en el tipo que estamos analizando. Así el Tribunal Supremo (SSTS de 29 de noviembre de 1985, 2 de diciembre de 1989 y 21 de diciembre de 1990) ha señalado que para la perfección del delito de injurias, recogido en el art. 208 del Código Penal, se precisa la concurrencia de los siguientes elementos:

1º Uno de carácter objetivo, comprensivo de las expresiones proferidas o acciones ejecutadas que lesionen la dignidad de otra persona, menoscabando su fama o atentando contra su propia estimación.
2º Otro de índole subjetiva, acusadamente intencional, en cuanto que aquellas frases o actitudes han de responder al propósito específico de ofender, vilipendiar, desacreditar, complejo y circunstancial vejar, menospreciar, escarnecer, etc., a la persona destinataria de ellas o a la que vienen referidas, "animus iniuriandi". La concurrencia de éste debe llevar al juzgador a rechazar que la conducta típica se haya llevado a cabo por otras motivaciones internas (animus criticandi o retrohendi o retorquendi).

Así, muchas veces, las expresiones o acciones presuntamente injuriosas quedan desvirtuadas o enervadas, por faltar el elemento esencial o nuclear del delito: "deshonrar", por la apreciación de otros motivos o ánimos que las explican, como por ejemplo: defenderse, criticar, narrar, bromear...etc, estudiados por la doctrina desde antiguos tiempos, que demuestran y ponen de manifiesto, una vez más, la indeterminación y circunstancialidad de este delito.

3º Un último elemento circunstancial, que aglutina cuantos factores o datos personales, de ocasión, lugar, tiempo, forma, etc., valorativamente apreciados, contribuyan, de una parte, a esclarecer la verdadera intención o propósito que animaba al sujeto proferidor de la ofensa, y, de otra, coadyuven a determinar la importancia y magnitud de los tipos del Código Penal.

La gravedad, o no, de las injurias dependerá de la expresión proferida y su contexto, así como del elemento intencional también grave de injuriar al sujeto pasivo del delito, valorándose en cada caso su inclusión en la vía penal o civil, atendiendo al contexto propio de cada caso.

Añadir un dato relevante, ya que el Artículo 210 CP señala que el acusado de injuria quedará exento de responsabilidad probando la verdad de las imputaciones cuando estas se dirijan contra funcionarios públicos sobre hechos concernientes al ejercicio de sus cargos o referidos a la comisión de infracciones administrativas. Se trata de una exceptio veritatis un tanto extraña de aplicar en las injurias, ya que estas patrocinan de un insulto por lo que resultará complicada su aplicación práctica. En todo caso se estaría refiriendo a términos tales como "chorizo", o "ladrón" cuando se prueben tales extremos; es decir, en los delitos considerados como de corrupción.

(3) En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos, al comienzo del juicio oral pueden aportarse más pruebas.

También debe pedirse que se reproduzca la grabación o lectura literal de la prueba practicada anticipadamente en la fase de diligencias previas (art. 777.2 LECrim.)

================================================================================
