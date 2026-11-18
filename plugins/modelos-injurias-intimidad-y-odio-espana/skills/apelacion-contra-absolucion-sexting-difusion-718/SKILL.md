---
name: apelacion-contra-absolucion-sexting-difusion-718
description: "Redacta el escrito «Apelación contra la absolución por sexting (difusión inconsentida de imágenes por internet)» (formulario 718 de honor, intimidad y delitos de odio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Apelación contra la absolución por sexting (difusión inconsentida de imágenes por internet)

> Formulario 0718 del plugin **Honor, intimidad y delitos de odio** · revisado el 17-11-2026.

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
- [ ] NÚMERO
- [ ] FECHA (3 veces)
- [ ] LUGAR
- [ ] DÍA
- [ ] MES
- [ ] AÑO
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «… torno a la figura del delito de sexting»

## Elecciones que hay que hacer

- Procurador / Procuradora

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 197.7 CP
- artículo 790 de la Ley de Enjuiciamiento Criminal
- art. 790.2 LECRIM
- art. 792.2 LECRIM
- artículo 790.2 de la Ley de Enjuiciamiento Criminal
- art. 197.1 y 3 CP
- art. 197.3 CP

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

### Formulario 0718 · Apelación contra la absolución por sexting (difusión inconsentida de imágenes por internet)

- Año del modelo: 2017
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (5); 1 desplegables y casillas convertidos en elección en blanco; 8 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Recurso de apelación de la acusación contra sentencia dictada en procedimiento abreviado que absuelve por delito de difusión inconsentida de imágenes grabadas con anuencia (sexting), del art. 197.7 CP. No se interesa la revocación de la sentencia sino la anulación para que se vuelva a celebrar el juicio.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de lo Penal del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [ELEGIR: Procurador / Procuradora] de los Tribunales, actuando en nombre y representación de la acusación particular D./Dña. [NOMBRE Y APELLIDOS] en el juicio oral número [NÚMERO] por delito del art. 197.7 CP ante este órgano judicial (1) comparezco y, como más procedente sea en derecho, DIGO:

Que con fecha de [FECHA] se le ha notificado a esta parte la sentencia recaída en fecha de [FECHA], y por no considerarla ajustada a derecho, dicho con todo respeto y en términos de estricta defensa, dentro del término legal (2) interpongo contra la misma recurso de apelación en ambos efectos, conforme a lo prevenido en el artículo 790 de la Ley de Enjuiciamiento Criminal, para ante la Audiencia Provincial, en base a las siguientes

ALEGACIONES (3)

ÚNICA.-

La resolución que se recurre padece errores en la apreciación de la prueba como se explica:

El/La acusado/a divulgó un video que había grabado previamente con consentimiento de la ahora recurrente (4) como venganza por haberle comunicado la ruptura de la relación. Se ha aportado al procedimiento penal en sede de plenario copia del acta notarial donde consta la reproducción por el Notario D./Dña. [NOMBRE Y APELLIDOS] de la grabación del contenido que afecta a la intimidad del recurrente al haber sido tomado en la privacidad de su hogar y sin autorización para ser difundido. (5)

La sentencia debe ser anulada por falta de motivación de la absolución y el apartamiento manifiesto de las máximas de experiencia y la omisión de todo razonamiento sobre alguna o algunas de las pruebas practicadas en el plenario que acreditan la difusión por diversos servidores de la grabación efectuada por el acusado y que afecta a la intimidad e imagen de la recurrente.

La viabilidad de la anulación de la sentencia se basa en el art. 790.2 LECRIM que señala que:

"Cuando la acusación alegue error en la valoración de la prueba para pedir la anulación de la sentencia absolutoria o el agravamiento de la condenatoria, será preciso que se justifique la insuficiencia o la falta de racionalidad en la motivación fáctica, el apartamiento manifiesto de las máximas de experiencia o la omisión de todo razonamiento sobre alguna o algunas de las pruebas practicadas que pudieran tener relevancia o cuya nulidad haya sido improcedentemente declarada."

Además, el art. 792.2 LECRIM añade que:

"2. La sentencia de apelación no podrá condenar al encausado que resultó absuelto en primera instancia ni agravar la sentencia condenatoria que le hubiera sido impuesta por error en la apreciación de las pruebas en los términos previstos en el tercer párrafo del artículo 790.2.

No obstante, la sentencia, absolutoria o condenatoria, podrá ser anulada y, en tal caso, se devolverán las actuaciones al órgano que dictó la resolución recurrida. La sentencia de apelación concretará si la nulidad ha de extenderse al juicio oral y si el principio de imparcialidad exige una nueva composición del órgano de primera instancia en orden al nuevo enjuiciamiento de la causa."

Por ello, no se interesa la revocación, sino la anulación para que se vuelva a celebrar el juicio y que un nuevo juez con nueva valoración de prueba efectúe una adecuada motivación de los extremos alegados por esta parte en el plenario en torno a la figura del delito de sexting [COMPLETAR].

En su virtud,

SUPLICO A LA SECCIÓN:

Se sirva tener por interpuesto en tiempo y forma recurso de apelación en ambos efectos contra la sentencia de fecha [FECHA] recaída en los precitados autos, lo admita a trámite, acordando la remisión de lo actuado a la Audiencia Provincial a fin de que se dicte sentencia en la que se anule la recurrida y se celebre nuevo juicio conforme a lo interesado.

OTROSÍ DIGO: Que conforme a lo establecido en el artículo 790.2 de la Ley de Enjuiciamiento Criminal, designo como domicilio para notificaciones la sala del Colegio de Procuradores sita en el mismo edificio de la Audiencia Provincial.

SUPLICO A LA SECCIÓN: Que tenga por efectuada la anterior designación.

Es justicia que pido en [LUGAR], a [DÍA] de [MES] de [AÑO].

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este recurso se presenta ante el Juez de lo Penal que dictó la resolución impugnada.

(2) Plazo para presentar el recurso: de 10 días a partir del siguiente al de la notificación de la sentencia.

(3) Deben exponerse de forma ordenada las alegaciones que quepan contra la sentencia sobre quebrantamiento de normas y garantías procesales, error en la apreciación de la prueba o infracción de normas del ordenamiento jurídico.

(4) El delito de sexting ha sido introducido en el CP por la LO 1/2015, vigente a partir del 1-7-2015.

El art. 197.7 CP castiga como delito de "sexting" al que, sin autorización de la persona afectada, difunda, revele o ceda a terceros imágenes o grabaciones audiovisuales de aquélla que hubiera obtenido con su anuencia en un domicilio o en cualquier otro lugar fuera del alcance de la mirada de terceros, cuando la divulgación menoscabe gravemente la intimidad personal de esa persona.

Ahora bien, si la grabación se hubiera llevado a cabo sin consentimiento de la víctima se aplicaría una agravación de la pena y sería el art. 197.1 y 3 CP el de aplicación, con una penalidad de entre 2 y 5 años de prisión frente a la pena de prisión de tres meses a un año o multa de seis a doce meses del art. 197.7 CP.

Los elementos básicos del delito se centran en:

1.- El hecho se comete sin autorización de la difusión de la persona afectada.

En este caso la carga de esta prueba de la existencia del consentimiento de la afectada en difundir las imágenes correspondería, obviamente, al acusado al efectuar el descargo de que la víctima fue la que prestó su consentimiento a que el video o las imágenes se trasladaran a terceros y/o difundieran, ya que de lo contrario se trataría de una prueba diabólica al no poder obligarse a la víctima a que ella probara que «no prestó el consentimiento a que el video se difundiera». En cualquier caso, resultará obvio pensar que determinados videos o imágenes no están autorizadas normalmente a que se difundan, de ahí que se tenga que exigir la prueba del consentimiento al acusado si así lo alega.

2.- La conducta que se sanciona es la de difundir, revelar o ceder a terceros imágenes o grabaciones audiovisuales de aquélla que hubiera obtenido con su anuencia en un domicilio o en cualquier otro lugar fuera del alcance de la mirada de terceros.

Las imágenes se obtendrán normalmente en un lugar cerrado sin intervención de terceros. Precisamente por eso se trata de proteger la intimidad de la víctima y que lo que ella graba no sea objeto de difusión a terceros, ya que esta opta por que se quede en el ámbito de lo privado. Pero hay una referencia que se puede entender hasta como superflua y es la mención de que las imágenes se obtengan en su domicilio o lugar fuera del alcance de la mirada de terceros, ya que entendemos que lo importante es la vulneración efectiva del derecho a la intimidad, y no tanto el lugar donde se hayan captado las imágenes, ya que resulta irrelevante a los efectos penales el lugar, porque lo sancionable es la difusión de esas imágenes privadas.

3.- Que la divulgación menoscabe gravemente la intimidad personal de esa persona.

Esta exigencia debe resultar obvia según los contenidos que sean objeto de difusión y ello quedará a la valoración del juez en cada caso al exigirse que menoscabe gravemente la intimidad personal de esa persona. Esto puede dar lugar a problemas al entender en algunos casos algunas denunciantes que determinadas imágenes menoscaban su intimidad, pero no debe perderse de vista que esta exigencia es un elemento del tipo, por lo que, si se efectúa una difusión de imágenes, pero no llega a considerarse que ello supone una afectación o menoscabo a su intimidad el hecho no será delito. Pero es que el bien jurídico protegido por este delito es, precisamente, la intimidad, y en conjunción con la propia imagen. Pero se exige no una mera afectación a ambas, sino que esta sea grave, de lo que se debe concluir que no se podrá derivar al ámbito de la persecución penal cualquier hecho de divulgación de imágenes o videos, sino aquellos que menoscaben de forma grave esa intimidad personal de la víctima, por lo que deberán ser imágenes o videos con unos determinados contenidos por ejemplo de naturaleza sexual o similares para entender afectada gravemente la intimidad, es decir, como en el caso antes expuesto que fue, precisamente, el que dio lugar a esta tipificación.

Hasta la reforma operada por LO 10/2022, de garantía integral de la libertad sexual, vigente desde el 7 de octubre de 2022, no estaba sancionado nada más que el primer envío, pero no los reenvíos sucesivos, habida cuenta que el art. 197.7 CP no se remitía al art. 197.3 CP que sí lo sancionaba, lo que se resuelve con el párrafo 2º del art. 197.7 CP que sí sanciona el segundo reenvío de quien ha recibido esa imagen sin autorización, tampoco, de la persona afectada.

(5) Puede pedirse la práctica de pruebas que no se pudieron proponer en el procedimiento abreviado o que se denegaron indebidamente si se formuló protesta y las admitidas y no practicadas por causas no imputables al apelante. Véanse STC 22/2013 de 31 de enero y STS 32/2012 de 25 de enero, Rec. 932/2011.

================================================================================
