---
name: ciberbullying-alegaciones-defensa-menor-672
description: "Redacta el escrito «Ciberbullying: alegaciones de la defensa del menor» (formulario 672 de honor, intimidad y delitos de odio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Ciberbullying: alegaciones de la defensa del menor

> Formulario 0672 del plugin **Honor, intimidad y delitos de odio** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (5 veces)
- [ ] Nº DE EXPEDIENTE
- [ ] NÚMERO
- [ ] COLEGIO
- [ ] LUGAR
- [ ] FECHA
- [ ] Otros 3 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…s Tribunales y del/de la menor acusado/a»; «… alguna. En virtud de ello, SE INTERESA:»; «…, Director/a del centro escolar»

## Párrafos opcionales (5)

Inclúyelos solo si encajan en los hechos:

- 1.- Examen del/de la menor encausado/a.…
- .- Testifical, debiendo ser citadas a través de la oficina judicial las siguientes personas:…
- - D./Dña. [NOMBRE Y APELLIDOS]…
- .- Pericial, debiendo ser citado/a a través de la oficina judicial el/la siguiente perito:…
- .- Documental mediante la lectura de los siguientes folios de expediente:…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 169 CP
- artículo 31 de la LO 5/2000
- artículo 31 de la Ley Orgánica 5/2000
- art. 35.2 de la LO 5/2000

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

### Formulario 0672 · Ciberbullying: alegaciones de la defensa del menor

- Año del modelo: 2017
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (3); 1 párrafos repetibles señalados; 4 párrafos opcionales señalados; 11 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la defensa del menor acusado en un proceso de menores presenta sus alegaciones concluyendo que no hay ciberbullying ni delito de amenazas del art. 169 CP, sino que se trata de una diferencia de opiniones entre dos menores en redes sociales.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Menores del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales y del/de la menor acusado/a [COMPLETAR], en el expediente nº [Nº DE EXPEDIENTE] comparezco ante este órgano judicial y, como mejor proceda en Derecho, DIGO:

Que, de conformidad con lo previsto en el artículo 31 de la LO 5/2000 Reguladora de la Responsabilidad Penal de los Menores, vengo a presentar (1) las siguientes

CONCLUSIONES

PRIMERA.- De las actuaciones practicadas no resulta la comisión de ilícito penal alguno (2), ya que, como puede verse en las respuestas enviadas por el/la denunciante, que constan en el expediente incoado por la Fiscalía de menores y se adjuntan como documental, todo se reduce a un intercambio de opiniones de dos menores por diferencias escolares, sin que pueda entenderse que exceden de ese umbral para entrar en el terreno del derecho penal de menores, ya que estas diferencias deben ser resueltas por los equipos de mediación del propio centro escolar y no por la Sección de Menores del Tribunal de Instancia.

SEGUNDA.- Los hechos relatados no son constitutivos de delito alguno, sino que se debe resolver en el equipo de mediación del centro escolar.

TERCERA.- Mi representado/a no es el/la autor/a del delito por el que se procede ni de ningún otro.

CUARTA.- Al no ser autor/a de ningún delito no pueden existir circunstancias modificativas de la responsabilidad inexistente.

QUINTA.- Por ello no procede adoptar medida alguna de seguridad.

SEXTA.- No procede indemnización alguna.

En virtud de ello,

SE INTERESA: [COMPLETAR]

Se acuerde la apertura de la correspondiente audiencia para la que se propone los siguientes

MEDIOS DE PRUEBA

[OPCIONAL — incluir si procede]

1.- Examen del/de la menor encausado/a.

[OPCIONAL — incluir si procede]

.- Testifical, debiendo ser citadas a través de la oficina judicial las siguientes personas:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS]

- D./Dña. [NOMBRE Y APELLIDOS], Director/a del centro escolar [COMPLETAR].

[OPCIONAL — incluir si procede]

.- Pericial, debiendo ser citado/a a través de la oficina judicial el/la siguiente perito:

- D./Dña. [NOMBRE Y APELLIDOS].

-Equipo de Asesoramiento Técnico, a través de los responsables del informe que aparece en los folios nº [NÚMERO] del expediente y con el objeto de ratificar el contenido del mismo.

[OPCIONAL — incluir si procede]

.- Documental mediante la lectura de los siguientes folios de expediente:

 donde constan los correos electrónicos con las respuestas enviadas por el/la denunciante.

- Acta notarial del/de la notario/a D./Dña. [NOMBRE Y APELLIDOS] del Ilustre Colegio de [COLEGIO], donde puede comprobarse el contenido de los correos electrónicos adverado por el/la citado/a notario/a. (3)

Y hace suya la prueba propuesta por las demás partes, con derecho de intervenirla aun cuando fuese renunciada.

OTROSÍ DICE: Que, en interés del/de la menor, y de conformidad con lo establecido en el artículo 31 de la Ley Orgánica 5/2000 Reguladora de la Responsabilidad Penal de los Menores, se presenta este escrito y se propone la participación en el acto de la audiencia del/de la letrado/a del/de la menor para que se formulen sus alegaciones y pruebas.

OTROSÍ SEGUNDO DICE: Que, en interés del/de la menor, y de conformidad con lo establecido en el art. 35.2 de la LO 5/2000, se solicita se acuerde la no publicidad de los/as menores.

En [LUGAR], a [FECHA].

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Plazo para presentar este escrito: 5 días a contar desde que se recibe el escrito de alegaciones del Fiscal y el testimonio del expediente.

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

(3) El correo electrónico se aporta impreso donde consta la dirección de email del remitente y destinatario a fin de acreditar la referencia de origen y destino del envío. Es conveniente su adveración por notario o por Letrado de la Administración de Justicia.

Solo si existiese un medio impugnatorio de la parte a quien perjudique estaría obligado la parte que lo aportó a proponer para el acto del plenario una pericial informática que valide su existencia.

================================================================================
