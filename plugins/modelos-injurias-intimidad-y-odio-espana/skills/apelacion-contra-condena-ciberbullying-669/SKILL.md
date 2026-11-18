---
name: apelacion-contra-condena-ciberbullying-669
description: "Redacta el escrito «Apelación contra la condena por ciberbullying» (formulario 669 de honor, intimidad y delitos de odio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Apelación contra la condena por ciberbullying

> Formulario 0669 del plugin **Honor, intimidad y delitos de odio** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (3 veces)
- [ ] Nº DE EXPEDIENTE
- [ ] FECHA (4 veces)
- [ ] LUGAR
- [ ] DESCRIBIR
- [ ] Otros 7 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…, letrado/a del/de la menor»; «…, que condena al/a la menor»; «…a la medida de»; «…cnicos de mediación en el centro escolar»; «…del centro»; «…del centro [COMPLETAR] que manifestó que»; «…ión de un ilícito penal. Y el/la testigo»

## Párrafos opcionales (3)

Inclúyelos solo si encajan en los hechos:

- -Testifical de D./Dña. [NOMBRE Y APELLIDOS] que deberá ser citado/a judicialmente.…
- -Documental consistente en [DESCRIBIR].…
- -…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 169 CP
- art. 169 CP
- artículo 41.1 de la LO 5/2000
- art. 169 del Código Penal
- art. 790.3 de la LECrim

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

### Formulario 0669 · Apelación contra la condena por ciberbullying

- Año del modelo: 2017
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (2); 3 párrafos opcionales señalados; 16 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que un menor condenado por delito de amenazas del artículo 169 CP por ciberbullying recurre su condena alegando que no hay delito, sino que es un enfrentamiento mutuo en redes sociales que no debe entrar en la esfera penal. Solicita pruebas admitidas pero no practicadas en el proceso de menores.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Menores del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], letrado/a del/de la menor [COMPLETAR] en expediente nº [Nº DE EXPEDIENTE] por presunto delito de amenazas del art. 169 CP, como mejor proceda en derecho, DIGO:

Que, al amparo del artículo 41.1 de la LO 5/2000 reguladora de la Responsabilidad Penal de los Menores, interpongo recurso de apelación (1) contra la sentencia de fecha [FECHA], que se me notificó el día [FECHA], que condena al/a la menor [COMPLETAR] a la medida de [COMPLETAR] como autor/a de un delito de amenazas por ciberbullying del art. 169 del Código Penal; por suponer para mi representado/a un grave perjuicio, dicho sea con el debido respeto y en términos de defensa y ser susceptible de apelación, con base en las siguientes:

RAZONES

ÚNICA.-

El delito objeto de condena es el de amenazas del art. 169 CP en su modalidad de Ciberbullying. Pero, como ya es expuso en el acto del juicio oral, no estamos ante un ilícito penal, sino simplemente ante problemas de menores de edad que sufren en el colegio por enfrentamientos entre ellos por redes sociales pero que no constituyen un ilícito penal y que podrían tener otras vías de solución de conflictos intraescolares y no en el campo del derecho penal.

Es sabido que estamos ante un caso de ciberbullying cuando un/a menor atormenta, amenaza, hostiga, humilla o molesta a otro/a mediante Internet, teléfonos móviles, consolas de juegos u otras tecnologías telemáticas. Según el Estudio sobre hábitos seguros en el uso de las TIC por los menores publicado por el INTECO en Marzo de 2009 el ciberbullying se define como acoso entre iguales en el entorno TIC, e incluye actuaciones de chantaje, vejaciones e insultos de niños a otros niños. (2)

Pero lo que aquí ha ocurrido no son actos de acoso y hostigamiento como se refleja en la sentencia, sino tan solo unas discrepancias entre dos menores de edad sobre su comportamiento en clase que podrían tener cabida en el ámbito de los equipos técnicos de mediación en el centro escolar [COMPLETAR] y no en este terreno del derecho penal.

Nótese que nos movemos en el marco del principio de intervención mínima del derecho penal y es por ello, por lo que no puede elevarse a la calificación de delito la conducta del/de la ahora recurrente, sino que fueron diferencias que se manifestaron ambos recurrentes por las redes sociales. Si se comprueba la redacción del contenido de los mensajes, aunque no son ciertamente afortunados los emitidos por esta parte, tampoco deben merecer un reproche penal. De suyo, de la testifical practicada con el/la profesor/a D./Dña. [NOMBRE Y APELLIDOS] del centro [COMPLETAR] que manifestó que [COMPLETAR], no se desprende la comisión de un ilícito penal. Y el/la testigo [COMPLETAR] profesor/a de ambos/as menores también manifestó que siempre estaban discutiendo en clase y tenían una mala relación, por lo que también puede suponer una cierta venganza la denuncia presentada en su día.

Es por ello por lo que se solicita se revoque la sentencia condenatoria y se absuelva a esta parte de los hechos objeto de acusación.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito con sus copias y por interpuesto en tiempo y forma el presente RECURSO DE APELACIÓN contra la sentencia de fecha [FECHA], lo admita, y tras los trámites procesales correspondientes, remita las actuaciones a la Audiencia Provincial para que, tras la celebración de la vista, resuelva con arreglo a las pretensiones de esta parte.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que, de conformidad con lo establecido en el art. 790.3 de la LECrim., propongo para el acto de la vista la práctica de las pruebas que, propuestas por esta parte y admitidas por auto de la Sección de Menores del Tribunal de Instancia de plaza nº no pudieron practicarse en su día por causas de fuerza mayor no imputables al/a la menor ni a este/a Letrado/a, y que se concretan en las siguientes:

[OPCIONAL — incluir si procede]

-Testifical de D./Dña. [NOMBRE Y APELLIDOS] que deberá ser citado/a judicialmente.

[OPCIONAL — incluir si procede]

-Documental consistente en [DESCRIBIR].

[OPCIONAL — incluir si procede]

-

Por ello,

SUPLICO A LA AUDIENCIA: Tenga por hecha la precedente solicitud de prueba y en su momento la admita y acuerde su práctica en el acto de la vista.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Plazo para interponer el recurso: 5 días desde la notificación de la sentencia.

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

================================================================================
