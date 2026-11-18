---
name: ciberbullying-denuncia-ante-fiscalia-menores-670
description: "Redacta el escrito «Ciberbullying: denuncia ante la Fiscalía de Menores» (formulario 670 de honor, intimidad y delitos de odio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Ciberbullying: denuncia ante la Fiscalía de Menores

> Formulario 0670 del plugin **Honor, intimidad y delitos de odio** · revisado el 17-11-2026.

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

- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] DNI/NIE
- [ ] CALLE (2 veces)
- [ ] Nº (2 veces)
- [ ] COLEGIO
- [ ] LUGAR
- [ ] FECHA
- [ ] Otros 7 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…art. 169 CP. A la Fiscalía de Menores de»; «…con DNIs nº [DNI/NIE] y»; «…, padres del/de la menor»; «…Desde hace varios meses nuestro/a hijo/a»; «…ternet por parte del/de la también menor»; «…SEGUNDO.- El/La autor/a de los hechos es»; «…compañero/a del colegio»

## Elecciones que hay que hacer

- denunciante / representante del/de la menor

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 169 CP
- art. 7 LO 5/2000
- art. 468.2 CP
- art. 7.1 i) LO 5/2000
- art. 7.1 LO 5/2000

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

### Formulario 0670 · Ciberbullying: denuncia ante la Fiscalía de Menores

- Año del modelo: 2017
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (4); 1 desplegables y casillas convertidos en elección en blanco; 15 campos de relleno marcados en blanco; 1 huecos del original que se habían perdido sin marca, marcados (NOMBRE Y APELLIDOS)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que se ponen en conocimiento de la fiscalía de menores unos actos de ciberbullying que un menor ejerce sobre otro menor a través de Facebook, para que proceda a averiguar si pueden ser constitutivos de delito de amenazas del art. 169 CP.

A la Fiscalía de Menores de [COMPLETAR]

D. y Dña. [NOMBRE Y APELLIDOS] con DNIs nº [DNI/NIE] y [COMPLETAR], y con domicilio en la C/ [CALLE], padres del/de la menor [COMPLETAR] de [Nº] años de edad y con domicilio en la C/ [CALLE], comparecemos y, como mejor proceda en derecho, DECIMOS:

Que por medio del presente escrito formulamos denuncia ante esta Fiscalía (1), con base en los siguientes:

HECHOS

PRIMERO.- Desde hace varios meses nuestro/a hijo/a [COMPLETAR] de [Nº] años de edad, viene siendo objeto de amenazas por internet por parte del/de la también menor [COMPLETAR] quien le ha enviado diversos mensajes privados por Facebook, y también usando esta plataforma on line, para humillarle públicamente por medio de expresiones tales como: "no vales para nada, vete del colegio o te partiremos las piernas, eres un enano, no queremos empollones en este colegio, no te queremos ver más, la próxima vez que vengas a clase lo pagarás caro", y frases semejantes de la que adjuntamos acta notarial por conducto del/de la Notario/a D./Dña. [NOMBRE Y APELLIDOS] del Ilustre Colegio de Notarios de [COLEGIO] donde puede comprobarse la fecha de las amenazas y actos de acoso y su contenido adverado por el/la citado/a notario/a, así como la identidad del/de la autor/a de las amenazas y actos de acoso y ciberbullying (2).

SEGUNDO.- El/La autor/a de los hechos es [COMPLETAR] compañero/a del colegio [COMPLETAR] de nuestro/a hijo/a, a quien se está acosando de forma constante para que no acuda al centro escolar incitándole a que deje de estudiar y no obtenga buenas notas que es lo que molesta al/a la denunciado/a y a otros/as compañeros/as que no paran tampoco de atosigarle, aunque siendo el/la denunciado/a el/la principal exponente de estos actos.

En consecuencia, y dado que consideramos a nuestro/a hijo/a víctima de un delito, lo pongo en conocimiento de esta Fiscalía para que se sirva acordar lo pertinente para la comprobación y averiguación de los hechos y sus autores.

Dada la gravedad de los hechos se interesa que, como medida cautelar, por la vía de los arts. 13 y 544 bis LECRIM, 2º párrafo, con relación al art. 7 LO 5/2000, se adopte la medida cautelar de prohibición de comunicación del/de la denunciado/a con el/la denunciante por cualquiera de los medios admitidos, incluido el de redes sociales o tecnológicos realizándose el preceptivo requerimiento/apercibimiento de la posibilidad de comisión de un delito del art. 468.2 CP en el caso de que quebrante la orden que, como medida cautelar, se postula, comunicándose por cualquier medio con la parte denunciante. (3)

Del mismo modo, se interesa que se adopte, también, como medida cautelar la de prohibición de aproximación a la víctima en su lugar de residencia, o en cualquiera de los que frecuente, apercibiendo y requiriendo de ello al/a la denunciado/a con las advertencias legales.

Se interesa también se proceda a la adopción de la medida cautelar, ex art. 13 y 544 bis LECRIM, de la prohibición de acceso a internet del investigado y sujeto a medidas cautelares, en atención a la prohibición de regreso al lugar del delito, que en este caso ha sido la red de internet en cualquiera de sus modalidades, apercibiendo al/a la querellado/a con las advertencias legales. (4)

En su caso, ofíciese a los prestadores de servicio de uso de internet para dar cuenta de la presente prohibición a los efectos de que se suspenda la posibilidad de acceso del investigado a internet por orden judicial, y de la imposibilidad de efectuar nuevas contrataciones con otros operadores, sea cuales sean, a fin de asegurar el no acceso a internet del investigado, dada la gravedad de los hechos que se están investigando y la elevada potencialidad de causar perjuicios a terceros por el efecto multiplicador de los delitos cometidos por internet y para la protección del interés general y no solo el particular del perjudicado en la presente causa.

En [LUGAR], a [FECHA].

Firma del/de la [ELEGIR: denunciante / representante del/de la menor]:

NOTAS DEL FORMULARIO

(1) La denuncia se presenta ante la fiscalía de menores al ser el denunciado menor de edad.

(2) El ciberbullying es el uso de los medios telemáticos (Internet, telefonía móvil y videojuegos online principalmente) para ejercer el acoso psicológico entre iguales. Un elemento exigente es que tiene que haber menores en ambos extremos del ataque para que se considere ciberbullying: si hay algún adulto, entonces estamos ante algún otro tipo de ciberacoso.

Las formas que adopta son muy variadas. (www.ciberbullying.com)

Según Álvaro ÉCIJA BERNAL (2017) es posible identificar siete categorías de acoso verbal y escrito a través de las nuevas tecnologías:

1. Flaming: Envío de mensajes violentos o que muestran enfado sobre una persona a un grupo o a esa persona vía email o SMS.
2. Acoso online: Envío continuado de mensajes ofensivos vía email o SMS a una persona.
3. Ciberstalking: Acoso online a través de amenazas de daño o intimidación físicas.
4. Denigración: Envío de información perjudicial, falsa y cruel sobre una persona a otra o publicación de la información en foros o redes sociales.
5. Suplantación de la persona: Simulación de la identidad de una persona y envío de información o subida de imágenes, videos o textos que agredan y hagan quedar mal a la víctima.
6. Outing: Subida de imágenes, videos o texto sobre una persona que contenga información privada o embarazosa.
7. Exclusión: Expulsión de un usuario de un grupo online formado en alguna plataforma.

(3) La adopción de esta medida cautelar es fundamental para evitar la reiteración delictiva mientras se sustancie el procedimiento y concluya en sentencia condenatoria con medida del art. 7.1 i) LO 5/2000 relativa a La prohibición de comunicarse con la víctima o con aquellos de sus familiares u otras personas que determine el juez o tribunal.

Como señala la SAP de Madrid 291/2017, de 20 de Noviembre, Rec.1591/2017: "En muchas ocasiones las víctimas sienten temor no solo por la presencia física del condenado, sino, también, por un acto de comunicación virtual del investigado (medida cautelar) o pena (condenado), ya que una víctima que lo ha sido de un hecho del condenado puede incrementar su grado de victimización si recibe comunicaciones de quien le ha amenazado, incluso aunque estas comunicaciones no constituyan un hecho delictivo."

Es por ello por lo que, con independencia de que se interese la medida del art. 7.1 LO 5/2000, se inste como medida cautelar para anticipar los efectos de la prohibición, dado el peligro de la reiteración y el temor que ello le reporta a la víctima, para quien igual que se adopta con frecuencia la medida cautelar de alejamiento es igual de importante la medida cautelar de prohibición de comunicación.

(4) La cautelar que se solicita tiene su base y razón de ser, no solo en la protección de los derechos del perjudicado por el delito, sino en aras a una protección general para evitar la reiteración delictiva de la comisión del ilícito penal por medio de las tecnologías de la comunicación y especialmente por el uso de internet a cualquier futuro perjudicado mientras se tramita la causa y hasta sentencia y su posible transformación en pena.

================================================================================
