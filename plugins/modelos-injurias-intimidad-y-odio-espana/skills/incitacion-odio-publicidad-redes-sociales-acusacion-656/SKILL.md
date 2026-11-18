---
name: incitacion-odio-publicidad-redes-sociales-acusacion-656
description: "Redacta el escrito «Incitación al odio con publicidad en redes sociales: acusación» (formulario 656 de honor, intimidad y delitos de odio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Incitación al odio con publicidad en redes sociales: acusación

> Formulario 0656 del plugin **Honor, intimidad y delitos de odio** · revisado el 17-11-2026.

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
- [ ] Nº (2 veces)
- [ ] NOMBRE Y APELLIDOS (10 veces)
- [ ] COLEGIO
- [ ] LOCALIDAD
- [ ] CIRCUNSTANCIA
- [ ] IMPORTE (3 veces)
- [ ] LUGAR
- [ ] FECHA (2 veces)
- [ ] Otros 8 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…subió por la red social»; «…tiene una relación con una mujer llamada»; «…habría que hacer con los homosexuales es»; «…porque»; «…roferida con publicidad en la red social»; «… retirada de contenidos de la red social»; «…, el bloqueo del acceso a la web»; «…que leyó la publicación en la red social»

## Elecciones que hay que hacer

- a continuación / en escrito aparte

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (3)

Inclúyelos solo si encajan en los hechos:

- 1.- Interrogatorio del/de la acusado/a.…
- .- Testifical (5): declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte…
- - D./Dña. [NOMBRE Y APELLIDOS], que leyó la publicación en la red social [COMPLETAR] en fecha [FECHA].…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 510.1 a) CP
- artículo 780.1 de la Ley de Enjuiciamiento Criminal
- art. 781 LECRIM
- art. 780 LECRIM
- art. 650 LECRIM
- art. 510.1.a) CP
- art. 22 CP
- art. 510 CP
- art. 510.3 CP

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

### Formulario 0656 · Incitación al odio con publicidad en redes sociales: acusación

- Año del modelo: 2017
- Revisión 17-11-2026: saltos de párrafo recuperados (texto venía pegado); restos de formato retirados; notas del formulario agrupadas al final (8); 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 1 bloques de alternativas señalados; 2 párrafos opcionales señalados; 27 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la acusación presenta sus conclusiones provisionales calificando los hechos como un delito de incitación al odio del art. 510.1 a) CP por colgar en redes sociales comentarios hostiles contra los homosexuales. Se presenta pericial informática y acta notarial acreditativa de la prueba digital.

Actualizado conforme a la LO 6/2022, con entrada en vigor desde el 14 de julio de 2022.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales del Ilustre Colegio de Procuradores de [COLEGIO] y con despacho profesional abierto en [LOCALIDAD], en representación del acusador particular Dña. [NOMBRE Y APELLIDOS], comparezco ante este órgano judicial y como mejor proceda en derecho, DIGO:

En aplicación del artículo 780.1 de la Ley de Enjuiciamiento Criminal, mediante el presente escrito formulo solicitud de apertura de juicio oral ante la Sección de lo Penal del Tribunal de Instancia por la vía del art. 781 LECRIM y en plazo (1) escrito de acusación por la vía del art. 780 LECRIM, en relación con el art. 650 LECRIM, contra D./Dña. [NOMBRE Y APELLIDOS], con base en las siguientes:

CONCLUSIONES

PRIMERA.- El/La acusado/a D./Dña. [NOMBRE Y APELLIDOS] subió por la red social [COMPLETAR], desde su propio ordenador, un comentario consistente en que mi mandante es homosexual y que tiene una relación con una mujer llamada [COMPLETAR] y que lo que habría que hacer con los homosexuales es [COMPLETAR] porque [COMPLETAR].

Ello fue hecho en la citada red social desde el propio ordenador del/de la acusado/a.

Por ello, esta difusión ha provocado en Dña. un cuadro de depresión fuerte que consta en dictamen pericial por la gran difusión que ha tenido esta manifestación de odio por su condición sexual, dada la utilización de un medio de gran repercusión social.

SEGUNDA.- Tales hechos son constitutivos del delito de INCITACIÓN AL ODIO con publicidad del art. 510.1.a) CP. (2)

TERCERA.- Es responsable del delito del art. 510.1.a) CP en concepto de autor/a el/la acusado/a.

CUARTA.-

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

No concurre con respecto al/a la acusado/a ninguna circunstancia agravante.

Concurre con respecto al/a la acusado/a la agravante de [CIRCUNSTANCIA] del art. 22 CP.

QUINTA.- Procede imponer al/a la acusado/a por el delito del art. 510.1-a) CP la pena de prisión de [Nº] años y multa de [IMPORTE] con cuota de [IMPORTE] euros diarios al haber sido proferida con publicidad en la red social [COMPLETAR].

Se interesa por la vía del art. 510.6.2º CP la retirada de contenidos de la red social [COMPLETAR], el bloqueo del acceso a la web [COMPLETAR] o la interrupción de la prestación de la misma. (3)

SEXTA.- En concepto de responsabilidad civil se indemnizará con el importe de [IMPORTE] euros por daño moral.

Las costas deberán ser satisfechas por el/la acusado/a.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita y tenga por realizado el trámite de traslado para acusación.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que para el juicio oral intereso la práctica de los siguientes:

MEDIOS DE PRUEBA (4)

Los propuestos por el Ministerio Fiscal y además los siguientes:

[OPCIONAL — incluir si procede]

1.- Interrogatorio del/de la acusado/a.

[OPCIONAL — incluir si procede]

.- Testifical (5): declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados/as
judicialmente
mediante exhorto

- D./Dña. [NOMBRE Y APELLIDOS] y D./Dña. [NOMBRE Y APELLIDOS], agentes de la Brigada tecnológica que llevaron a cabo las diligencias de identificación del/de la autor/a del delito.

- D./Dña. [NOMBRE Y APELLIDOS], agente que llevó a cabo las diligencias de investigación para detectar el IP del ordenador desde el que se llevó a cabo la suplantación de identidad.

- D./Dña. [NOMBRE Y APELLIDOS], agente que redactó el oficio policial para interesar la entrada y registro para la intervención del ordenador.

- D./Dña. [NOMBRE Y APELLIDOS], agente que intervino en la diligencia de entrada y registro en el domicilio del/de la acusado/a.

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS], que leyó la publicación en la red social [COMPLETAR] en fecha [FECHA].

.- Pericial:

- Pericial informática con dictamen del/de la perito informático/a que llevó a cabo esta pericial específica del examen del ordenador desde el que se realizó la operación. (6)
- Pericial psicológica para acreditar el daño moral y tensión causada a la víctima. (7)

.- Documental: acta notarial levantada para acreditar el contenido de la red social a nombre de la perjudicada. (8)

Por todo lo expuesto,

SUPLICO A LA SECCIÓN: Que declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 10 días desde la notificación del auto del juez por la vía del art. 780 LECRIM, solicitando la apertura del juicio oral formulando escrito de acusación.

(2) La regulación del art. 510 CP tipifica dos grupos de conductas:

• De una parte, y con una penalidad mayor, las acciones de incitación al odio o la violencia contra grupos o individuos por motivos racistas, antisemitas, antigitanos u otros relativos a su ideología, religión, etnia o pertenencia a otros grupos minoritarios, así como los actos de negación o enaltecimiento de los delitos de genocidio, lesa humanidad o contra las personas o bienes protegidos en caso de conflicto armado que hubieran sido cometidos contra esos grupos, cuando ello promueva o favorezca un clima de violencia, hostilidad u odio contra los mismos.
• De otra parte, los actos de humillación o menosprecio contra ellos y el enaltecimiento o justificación de los delitos cometidos contra los mismos o sus integrantes con una motivación discriminatoria, sin perjuicio de su castigo más grave cuando se trate de acciones de incitación al odio o a la hostilidad contra los mismos, o de conductas idóneas para favorecer un clima de violencia.

Esquema del delito de incitación al odio del art. 510.1.a) CP

Acción	Públicamente fomenten, promuevan o inciten directa o indirectamente al odio, hostilidad, discriminación o violencia contra un grupo, una parte del mismo o contra una persona determinada
Objetivo, intención o destino de la acción	Por razón de su pertenencia a aquél, por motivos racistas, antisemitas, antigitanos u otros referentes a la ideología, religión o creencias, situación familiar, la pertenencia de sus miembros a una etnia, raza o nación, su origen nacional, su sexo, orientación o identidad sexual, por razones de género, aporofobia, enfermedad o discapacidad.
Elemento subjetivo	Delito estrictamente doloso
Pena

-Básica: Prisión de uno a cuatro años y multa de seis a doce meses

-Agravada cuando los hechos se cometan a través de internet: penas anteriores en su mitad superior (art. 510.3 CP)

(3) Destacar que el art. 510.6º CP recoge una especialidad que debe interesarse, aunque puede acordarse por el juez de oficio:

El juez o tribunal acordará la destrucción, borrado o inutilización de los libros, archivos, documentos, artículos y cualquier clase de soporte objeto del delito a que se refieren los apartados anteriores o por medio de los cuales se hubiera cometido.

Cuando el delito se hubiera cometido a través de tecnologías de la información y la comunicación, se acordará la retirada de los contenidos.

En los casos en los que, a través de un portal de acceso a internet o servicio de la sociedad de la información, se difundan exclusiva o preponderantemente los contenidos a que se refiere el apartado anterior, se ordenará el bloqueo del acceso o la interrupción de la prestación del mismo.

En la reforma del CP que se está tramitando en el Parlamento con ocasión de la reforma sobre violencia de género se ha propuesto en el informe del Senado de propuestas de reforma la inclusión de la pena menos grave de prohibición de uso de redes sociales para todos los delitos cometidos utilizando internet o por publicidad, por la gravedad del alcance de la difusión que se produce cuando se realiza una manifestación integrante de un delito de odio por redes como Facebook, twitter, o cualesquiera otras redes sociales con gran capacidad de difusión.

(4) En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos al comienzo del juicio oral pueden aportarse más pruebas.

También debe pedirse que se reproduzca la grabación o lectura literal de la prueba practicada anticipadamente en la fase de diligencias previas (art. 777.2. LECr.).

(5) No harían falta las pruebas si se reconociera por el acusado la autoría.

(6) Si la prueba digital es impugnada es preciso aportar pericial informática.

(7) No es preciso aportar pericial psicológica de afectación para reclamar daño moral. Este se desprende ya de los hechos probados. Ahora bien, para poder reclamar más, si esa afectación se ha producido, es positivo aportar un informe que acredite la afectación psicológica realizada, lo que permitirá reclamar una cuantía mayor.

(8) Dado que se trata de delito cometido on line es necesario aportar acta notarial de constancia on line y probar su difusión.

================================================================================
