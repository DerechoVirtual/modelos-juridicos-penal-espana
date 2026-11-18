---
name: danos-informaticos-ciberataque-defensa-conformidad-680
description: "Redacta el escrito «Daños informáticos (ciberataque): defensa con conformidad» (formulario 680 de ciberdelitos y propiedad intelectual, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Daños informáticos (ciberataque): defensa con conformidad

> Formulario 0680 del plugin **Ciberdelitos y propiedad intelectual** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] IMPORTE (2 veces)
- [ ] LUGAR

## Párrafos opcionales (1)

Inclúyelos solo si encajan en los hechos:

- (Si la pena con la que se conforma es igual o inferior a 2 años)…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 264.2 CP
- art. 784.3 LECRIM
- art. 787 LECRIM
- art. 787 ter LECRIM
- art. 785 LECRIM
- art. 80 CP
- artículo 264 ter CP

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

### Formulario 0680 · Daños informáticos (ciberataque): defensa con conformidad

- Año del modelo: 2017
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (3); 1 párrafos opcionales señalados; 7 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que el acusado en un procedimiento abreviado se conforma con la pena solicitada por las acusaciones por un delito de daños informáticos del art. 264.2 CP o ciberataque cometido por enviar un virus mediante email.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, en la representación que tengo acreditada de D./Dña. [NOMBRE Y APELLIDOS], acusado/a en las diligencias previas número [Nº DE PROCEDIMIENTO], por el supuesto delito del art. 264.2 CP, comparezco ante este órgano judicial y, como mejor proceda en derecho,

DIGO:

Que, conforme al Protocolo de conformidades suscrito entre la Fiscalía General del Estado y el Consejo General de la Abogacía de fecha 1 de abril de 2009 (1) y al art. 784.3 LECRIM, en relación con el art. 787 LECRIM (hasta el 2/4/2025) art. 787 ter LECRIM (desde el 3/4/2025), se formula escrito de conformidad con los hechos calificados de delito de daños informáticos del art. 264.2 CP (2).

En este sentido, la defensa se conforma con la petición formulada por la Fiscalía a la pena de [Nº] años de prisión y multa de [IMPORTE] euros y al pago de [IMPORTE] euros de indemnización al/a la querellante, a ratificar en la audiencia preliminar del art. 785 LECRIM (desde el 3/4/2025).

[OPCIONAL — incluir si procede]

(Si la pena con la que se conforma es igual o inferior a 2 años)

Se interesa se conceda la suspensión de la ejecución de la pena del art. 80 CP y ss (3) que por la defensa se solicita con ocasión del presente escrito por concurrir los requisitos legales.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita, tenga por evacuado el trámite por la conformidad de la defensa y por interesada la medida de suspensión de la ejecución de la pena.

Es de Justicia que pido en [LUGAR]

Firma de Abogado/a:	Firma del acusado/a:

NOTAS DEL FORMULARIO

(1) En base al protocolo de conformidades suscrito entre la Fiscalía General del Estado y el Consejo General de la Abogacía de fecha 1 de abril de 2009 se puede presentar escrito del abogado defensor antes del señalamiento de juicio oral, incluso después de evacuado el trámite de calificación.

(2) En los arts. 264, 264 bis, 264 ter y 264 quater CP se recogen diversas modalidades de daños informáticos:

a.- Art. 264.1 CP: se castiga a quien de manera grave borrase, dañase, deteriorase, alterase, suprimiese o hiciese inaccesibles datos informáticos, programas informáticos o documentos electrónicos ajenos, cuando el resultado producido fuera grave.

b.- Art. 264.2 CP: se incluye una agravación cuando en las conductas descritas concurra alguna de las siguientes circunstancias:

1.ª Se hubiese cometido en el marco de una organización criminal.
2.ª Haya ocasionado daños de especial gravedad o afectado a un número elevado de sistemas informáticos.
3.ª El hecho hubiera perjudicado gravemente el funcionamiento de servicios públicos esenciales o la provisión de bienes de primera necesidad.
4.ª Los hechos hayan afectado al sistema informático de una infraestructura crítica o se hubiera creado una situación de peligro grave para la seguridad del Estado, de la Unión Europea o de un Estado Miembro de la Unión Europea. A estos efectos se considerará infraestructura crítica un elemento, sistema o parte de este que sea esencial para el mantenimiento de funciones vitales de la sociedad, la salud, la seguridad, la protección y el bienestar económico y social de la población cuya perturbación o destrucción tendría un impacto significativo al no poder mantener sus funciones.
5.ª El delito se haya cometido utilizando alguno de los medios a que se refiere el artículo 264 ter CP.

c.- Art. 264 bis CP: Se introducen en este precepto unas conductas específicas castigando al que, sin estar autorizado y de manera grave, obstaculizara o interrumpiera el funcionamiento de un sistema informático ajeno:

-realizando alguna de las conductas a que se refiere el artículo anterior;
- introduciendo o transmitiendo datos; o
- destruyendo, dañando, inutilizando, eliminando o sustituyendo un sistema informático, telemático o de almacenamiento de información electrónica.

d.- Art. 264 ter CP: este precepto sanciona a quien produzca, adquiera para su uso, importe o, de cualquier modo, facilite a terceros, con la intención de facilitar la comisión de alguno de los delitos a que se refieren los dos artículos anteriores:

- un programa informático, concebido o adaptado principalmente para cometer alguno de los delitos a que se refieren los dos artículos anteriores;
- una contraseña de ordenador, un código de acceso o datos similares que permitan acceder a la totalidad o a una parte de un sistema de información.

d.- Art. 264 quater CP: sanciona cuando el delito se cometa en el seno de una persona jurídica y por su responsabilidad.

El presente caso puede ubicarse en el art. 264.2 CP. Se configurar como un tipo agravado más del delito de daños, tratando de dar respuesta al problema introducido a raíz del desarrollo de las nuevas tecnologías por los conocidos como piratas o hackers a través de la difusión de virus informáticos, es decir programas cuya finalidad es producir un deterioro o destrucción del software de los terminales que infectan, o sencillamente una alteración de su sistema operativo, que determina un funcionamiento anómalo o deficiente, problema para el que no daba respuesta el tipo básico ordinario, pensando más en la afectación de un bien, de un objeto material tangible.

El delito de daños constituye una figura concretada en la destrucción o menoscabo material o funcional de la propiedad ajena, de manera que el objeto de ajeno dominio sobre el que se lleva a cabo la acción resulte destruido o menoscabado, sea en su entidad física sea en la funcionalidad que le es propia.

La acción de destruir, alterar, inutilizar, dañar de cualquier otro modo datos programas o documentos electrónicos contenidos en un soporte informático, venía a comportar un daño patrimonial por reparación o sustitución del objeto material sobre el que habían operado dichas acciones.

Por ello se introdujo el tipo del que por cualquier medio destruya, altere, inutilice o de cualquier otro modo dañe los datos, programas o documentos electrónicos ajenos contenidos en redes, soportes o documentos informáticos y tras la reforma operada por LO 5/2010 de 22 de junio se amplió su ámbito de un lado dándole carta de naturaleza propia al dejar de contemplarlo junto a las circunstancias cualificadoras de los daños, dotándole de autonomía sistemática y de otro lado recogiendo un elenco de conductas más amplio para solventar así todo debate en relación a su alcance, a que manipulaciones debían valorarse, pasando a contemplar prácticamente cualquier injerencia en un programa ajeno, con tal de que esta pueda tacharse de grave, ya que en su apartado primero como elenco de conductas punibles se alude a borrar, dañar, deteriorar, alterar, suprimir o hacer inaccesibles datos, programas o documentos y en su apartado segundo a obstaculizar o interrumpir el funcionamiento de un sistema informático ajeno introduciendo transmitiendo, dañando, borrando, deteriorando, alterando, suprimiendo o haciendo inaccesibles datos.

Entre los procedimientos informáticos de ataque a los elementos lógicos de un sistema informático o vandalismo electrónico, se vienen citando los crash o programas de destrucción progresiva, las bombas lógicas de actuación retardada, virus programs, caballo de Troya, etc y entre los que se dirigen a la alteración u obstaculización del funcionamiento informático el mail bomber o las bombas ANSI y la denegación de servicio de ataques DDoS.

En ambos casos la conducta se ha de realizar sin autorización y de forma grave y el resultado ocasionado ha de ser igualmente grave.

El tipo no concreta los criterios para determinar la gravedad de la conducta, lo que plantea el problema de delimitar los ataques que puedan resultar realmente perturbadores o molestos, pero penalmente insignificantes y distinguirlos de los que por su mayor gravedad revisten relevancia penal. (SJP Gijón 224/2016 de 6 de julio, Rec. 385/2015).

(3) Es importante instar ya ambos la petición de suspensión de ejecución de la pena con el apoyo de la fiscalía para garantizarla y evitar el ingreso en prisión.

En este caso podría pactarse la conformidad por debajo de los dos años de prisión para conseguir la suspensión de la ejecución de la pena.

================================================================================
