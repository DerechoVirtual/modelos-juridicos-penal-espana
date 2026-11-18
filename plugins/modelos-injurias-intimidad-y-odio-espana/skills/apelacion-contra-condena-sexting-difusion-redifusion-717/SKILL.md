---
name: apelacion-contra-condena-sexting-difusion-redifusion-717
description: "Redacta el escrito «Apelación contra la condena por sexting (difusión o redifusión inconsentida de imágenes)» (formulario 717 de honor, intimidad y delitos de odio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Apelación contra la condena por sexting (difusión o redifusión inconsentida de imágenes)

> Formulario 0717 del plugin **Honor, intimidad y delitos de odio** · revisado el 17-11-2026.

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
- [ ] NÚMERO (2 veces)
- [ ] FECHA (3 veces)
- [ ] LUGAR
- [ ] DÍA
- [ ] MES
- [ ] AÑO
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «… autorización, del art. 197.7 CP pfo. 2º»; «…y»

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Para el condenado por el delito del art. 197.7 CP pfo. 1º / Para el condenado por el delito del art. 197.7 CP pfo. 2º — el texto de cada opción no venía en el formulario original

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 197.7 CP
- artículo 790 de la Ley de Enjuiciamiento Criminal
- artículo 790.2 de la Ley de Enjuiciamiento Criminal
- art. 197.1 y 3 CP

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

### Formulario 0717 · Apelación contra la condena por sexting (difusión o redifusión inconsentida de imágenes)

- Año del modelo: 2017
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (5); 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 10 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Recurso del condenado contra sentencia condenatoria dictada en procedimiento abreviado por delito de difusión inconsentida de imágenes obtenidas con anuencia (sexting) del art. 197.7 CP, pfo. 1º o del delito de redifusión de esas imágenes sin autorización, del art. 197.7 CP pfo. 2º [COMPLETAR].

Actualizado conforme a la LO 10/2022, de garantía integral de la libertad sexual, con entrada en vigor el 7 de octubre de 2022.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de lo Penal del Tribunal de Instancia de [SEDE] – plaza n.º [Nº] (1)

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales, actuando en nombre y representación de D./Dña. [NOMBRE Y APELLIDOS] condenado/a en el juicio oral número [NÚMERO] por delito de sexting del art. 197.7 CP (2), ante este órgano judicial comparezco y, como más procedente sea en derecho, DIGO:

Que con fecha de [FECHA] se le ha notificado a esta parte la sentencia recaída en fecha de [FECHA], y por no considerarla ajustada a derecho, dicho con todo respeto y en términos de estricta defensa, dentro del término legal (3) interpongo contra la misma recurso de apelación en ambos efectos, conforme a lo prevenido en el artículo 790 de la Ley de Enjuiciamiento Criminal, para ante la Audiencia Provincial, en base a las siguientes

ALEGACIONES (4)

ÚNICA.-

[ELEGIR UNA OPCIÓN Y REDACTARLA: Para el condenado por el delito del art. 197.7 CP pfo. 1º / Para el condenado por el delito del art. 197.7 CP pfo. 2º — el texto de cada opción no venía en el formulario original]

De igual modo, así lo declararon en el juicio oral los agentes policiales nº [NÚMERO] y [COMPLETAR]

En su virtud,

SUPLICO A LA SECCIÓN:

Se sirva tener por interpuesto en tiempo y forma recurso de apelación en ambos efectos contra la sentencia de fecha [FECHA] recaída en los precitados autos, lo admita a trámite, acordando la remisión de lo actuado a la Audiencia Provincial a fin de que se dicte sentencia en la que se revoque la recurrida y se absuelva a mi representado de la condena impuesta.

OTROSÍ DIGO: Que conforme a lo establecido en el artículo 790.2 de la Ley de Enjuiciamiento Criminal, designo como domicilio para notificaciones la sala del Colegio de Procuradores sita en el mismo edificio de la Audiencia Provincial.

SUPLICO A LA SECCIÓN: Que tenga por efectuada la anterior designación.

Es justicia que pido en [LUGAR], a [DÍA] de [MES] de [AÑO].

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este recurso se presenta ante el Juez de lo Penal que dictó la resolución impugnada.

(2) El delito de sexting ha sido introducido en el CP por la LO 1/2015, vigente a partir del 1-7-2015.

El art. 197.7 CP castiga como delito de "sexting" al que, sin autorización de la persona afectada, difunda, revele o ceda a terceros imágenes o grabaciones audiovisuales de aquélla que hubiera obtenido con su anuencia en un domicilio o en cualquier otro lugar fuera del alcance de la mirada de terceros, cuando la divulgación menoscabe gravemente la intimidad personal de esa persona.

Ahora bien, si la grabación se hubiera llevado a cabo sin consentimiento de la víctima se aplicaría una agravación de la pena y sería el art. 197.1 y 3 CP el de aplicación, con una penalidad de entre 2 y 5 años de prisión frente a la pena de prisión de tres meses a un año o multa de seis a doce meses del art. 197.7 CP.

Los elementos básicos del delito se centran en:

1.- El hecho se comete sin autorización de la difusión de la persona afectada.

En este caso la carga de esta prueba de la existencia del consentimiento de la afectada en difundir las imágenes correspondería, obviamente, al acusado al efectuar el descargo de que la víctima fue la que prestó su consentimiento a que el video o las imágenes se trasladaran a terceros y/o difundieran, ya que de lo contrario se trataría de una prueba diabólica al no poder obligarse a la víctima a que ella probara que «no prestó el consentimiento a que el video se difundiera». En cualquier caso, resultará obvio pensar que determinados videos o imágenes no están autorizadas normalmente a que se difundan, de ahí que se tenga que exigir la prueba del consentimiento al acusado si así lo alega.

2.- La conducta que se sanciona es la de difundir, revelar o ceder a terceros imágenes o grabaciones audiovisuales de aquélla que hubiera obtenido con su anuencia en un domicilio o en cualquier otro lugar fuera del alcance de la mirada de terceros.

Las imágenes se obtendrán normalmente en un lugar cerrado sin intervención de terceros. Precisamente por eso se trata de proteger la intimidad de la víctima y que lo que ella graba no sea objeto de difusión a terceros, ya que esta opta por que se quede en el ámbito de lo privado. Pero hay una referencia que se puede entender hasta como superflua y es la mención de que las imágenes se obtengan en su domicilio o lugar fuera del alcance de la mirada de terceros, ya que entendemos que lo importante es la vulneración efectiva del derecho a la intimidad, y no tanto el lugar donde se hayan captado las imágenes, ya que resulta irrelevante a los efectos penales el lugar, porque lo sancionable es la difusión de esas imágenes privadas.

3.- Que la divulgación menoscabe gravemente la intimidad personal de esa persona.

Esta exigencia debe resultar obvia según los contenidos que sean objeto de difusión y ello quedará a la valoración del juez en cada caso al exigirse que menoscabe gravemente la intimidad personal de esa persona. Esto puede dar lugar a problemas al entender en algunos casos algunas denunciantes que determinadas imágenes menoscaban su intimidad, pero no debe perderse de vista que esta exigencia es un elemento del tipo, por lo que, si se efectúa una difusión de imágenes, pero no llega a considerarse que ello supone una afectación o menoscabo a su intimidad el hecho no será delito. Pero es que el bien jurídico protegido por este delito es, precisamente, la intimidad, y en conjunción con la propia imagen. Pero se exige no una mera afectación a ambas, sino que esta sea grave, de lo que se debe concluir que no se podrá derivar al ámbito de la persecución penal cualquier hecho de divulgación de imágenes o videos, sino aquellos que menoscaben de forma grave esa intimidad personal de la víctima, por lo que deberán ser imágenes o videos con unos determinados contenidos por ejemplo de naturaleza sexual o similares para entender afectada gravemente la intimidad, es decir, como en el caso antes expuesto que fue, precisamente, el que dio lugar a esta tipificación.

(3) Plazo para presentar el recurso: de 10 días a partir del siguiente al de la notificación de la sentencia.

(4) Deben exponerse de forma ordenada las alegaciones que quepan contra la sentencia sobre quebrantamiento de normas y garantías procesales, error en la apreciación de la prueba o infracción de normas del ordenamiento jurídico.

(5) Puede pedirse la práctica de pruebas que no se pudieron proponer en el procedimiento abreviado o que se denegaron indebidamente si se formuló protesta y las admitidas y no practicadas por causas no imputables al apelante. Véanse STC 22/2013 de 31 de enero y STS 32/2012 de 25 de enero, Rec. 932/2011.

================================================================================
