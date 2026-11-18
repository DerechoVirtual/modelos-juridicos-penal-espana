---
name: apelacion-contra-condena-coacciones-mensajes-whatsapp-700
description: "Redacta el escrito «Apelación contra la condena por coacciones por mensajes de WhatsApp» (formulario 700 de delitos contra las personas, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Apelación contra la condena por coacciones por mensajes de WhatsApp

> Formulario 0700 del plugin **Delitos contra las personas** · revisado el 17-11-2026.

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
- [ ] FECHA (4 veces)
- [ ] LUGAR

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 172 CP
- artículo 790 de la Ley de Enjuiciamiento Criminal
- artículo 790.2 de la Ley de Enjuiciamiento Criminal

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

### Formulario 0700 · Apelación contra la condena por coacciones por mensajes de WhatsApp

- Año del modelo: 2017
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (1); 7 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Recurso de apelación contra sentencia condenatoria por delito de coacciones del art. 172 CP llevada a cabo a través de mensajes de WhatsApp, basado en error en la apreciación de la prueba por no haberse acreditado suficientemente la procedencia de esos mensajes, mediante pericial informática.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de lo Penal del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, actuando en nombre y representación del/de la condenado/a D./Dña [NOMBRE Y APELLIDOS] en el juicio oral número [NÚMERO] por delito de coacciones del art. 172.1 ó 2 CP, ante este órgano judicial comparezco y, como más procedente sea en derecho, DIGO:

Que, con fecha [FECHA] se le ha notificado a esta parte la sentencia recaída en fecha [FECHA], y por no considerarla ajustada a derecho, dicho con todo respeto y en términos de estricta defensa, dentro del término legal interpongo contra la misma recurso de apelación en ambos efectos, conforme a lo prevenido en el artículo 790 de la Ley de Enjuiciamiento Criminal, ante la Audiencia Provincial, en base a las siguientes

ALEGACIONES

PRIMERA.- La resolución que se recurre padece errores en la apreciación de la prueba como se explica a continuación:

Mi representado/a ha sido condenado/a exclusivamente por el envío de unos mensajes de un teléfono móvil que no le pertenece. Además, la prueba aportada ha consistido tan solo en la adveración por el/la Letrado/a de la Administración de Justicia de los mensajes de WhatsApp que se alegaba que habían sido enviados por mi representado/a, pero sin que se haya propuesto por la acusación la prueba pericial informática, al haber impugnado esta parte el contenido de los mensajes de WhatsApp bajo el alegato de que no salieron del teléfono móvil de mi representado/a y que podían haberse debido a una alteración o manipulación informática de su terminal para hacer entender que esos mensajes salían de su teléfono móvil. (1)

La ausencia de la práctica de la pericial informática no puede sino que conllevar el dictado de una sentencia absolutoria, habida cuenta de que, como afirma la STS 300/2015, de 19 de mayo, Rec. 2387/2014:

«la impugnación de la autenticidad de cualquiera de esas conversaciones, cuando son aportadas a la causa mediante archivos de impresión, desplaza la carga de la prueba hacia quien pretende aprovechar su idoneidad probatoria. Será indispensable en tal caso la práctica de una prueba pericial que identifique el verdadero origen de esa comunicación, la identidad de los interlocutores y, en fin, la integridad de su contenido».

Si se impugnan los mensajes de WhatsApp por la defensa debe proponerse pericial informática por la acusación sobre la veracidad de su contenido y su origen del teléfono del/de la acusado/a.

En este caso no se llevó a cabo esta prueba y hace inhábil la adveración del contenido de los mensajes de WhatsApp, que el único efecto que produce es la constatación de que en un mensaje de WhatsApp pone determinada aseveración, pero no acreditan que ese mensaje ha salido desde el teléfono móvil de mi representado/a, que alega haber sufrido una manipulación informática que ha dado lugar a que en el presente juicio no exista prueba bastante para el dictado de la sentencia condenatoria emitida, que carece de la necesaria prueba de cargo.

SEGUNDA.- Conforme a una reiterada doctrina del TS (entre otras STS 28/2016 de 28 de enero, Rec. 1137/2015, la invocación del derecho fundamental a la presunción de inocencia permite al tribunal de apelación constatar si la sentencia de instancia se fundamenta en:

a) una prueba de cargo suficiente, referida a todos los elementos esenciales del delito;
b) una prueba constitucionalmente obtenida, es decir que no sea lesiva de otros derechos fundamentales, requisito que nos permite analizar aquellas impugnaciones que cuestionan la validez de las pruebas obtenidas directa o indirectamente mediante vulneraciones constitucionales y la cuestión de la conexión de antijuridicidad entre ellas,
c) una prueba legalmente practicada, lo que implica analizar si se ha respetado el derecho al proceso con todas las garantías en la práctica de la prueba, y
d) una prueba racionalmente valorada, lo que implica que de la prueba practicada debe inferirse racionalmente la comisión del hecho y la participación del acusado, sin que pueda calificarse de ilógico, irrazonable o insuficiente el iter discursivo que conduce desde la prueba al hecho probado.

Estos parámetros, analizados en profundidad, permiten una revisión integral de la sentencia de instancia, garantizando al condenado el ejercicio de su derecho internacionalmente reconocido a la revisión de la sentencia condenatoria por un Tribunal Superior (Art. 14.5º del Pacto Internacional de Derechos Civiles y Políticos, de 19 de diciembre de 1966) por entenderse que la prueba practicada no enerva la presunción de inocencia y sustentarse la condena en meros indicios o presunciones no determinantes de una condena.

En este caso, la prueba de cargo de la acusación es la pericial informática que no se ha llevado a juicio, lo que debe conllevar la absolución que se interesa en el presente recurso de apelación con todos los pronunciamientos favorables en la revocación de la sentencia condenatoria dictada.

En su virtud,

SUPLICO A LA SECCIÓN:

Se sirva tener por interpuesto en tiempo y forma recurso de apelación en ambos efectos contra la sentencia de fecha [FECHA] recaída en los precitados autos, lo admita a trámite, acordando la remisión de lo actuado a la Audiencia Provincial, a fin de que se dicte sentencia en la que se revoque la recurrida y se absuelva a mi representado/a de la condena impuesta.

OTROSÍ DIGO: Que, conforme a lo establecido en el artículo 790.2 de la Ley de Enjuiciamiento Criminal, designo como domicilio para notificaciones la sala del Colegio de Procuradores sita en el mismo edificio de la Audiencia Provincial.

SUPLICO A LA SECCIÓN: Que tenga por efectuada la anterior designación.

Es justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Señala JOAQUIN DELGADO que la existencia de alegaciones impugnatorias con suficiente seriedad pueden producir en la práctica un efecto similar a un desplazamiento de la carga de la prueba. De esta forma, la carga recaerá sobre la parte que pretenda la validez probatoria del medio impugnado, quien deberá aportar medios probatorios para acreditar la integridad y/o autenticidad del documento impugnado, frecuentemente mediante pericial.

Este «desplazamiento» será más probable en los supuestos en los que el medio probatorio utilizado por la parte sea únicamente la aportación de la transcripción o reproducción en soporte papel del contenido de los datos (especialmente en casos de conversaciones por mensajería instantánea o por redes sociales), porque en estos casos existe un mayor riesgo de manipulación.

================================================================================
