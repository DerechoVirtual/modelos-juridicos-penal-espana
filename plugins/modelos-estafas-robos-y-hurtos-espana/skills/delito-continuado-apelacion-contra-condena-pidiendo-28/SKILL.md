---
name: delito-continuado-apelacion-contra-condena-pidiendo-28
description: "Redacta el escrito «Delito continuado: apelación contra la condena pidiendo la unidad natural de acción» (formulario 28 de delitos contra el patrimonio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Delito continuado: apelación contra la condena pidiendo la unidad natural de acción

> Formulario 0028 del plugin **Delitos contra el patrimonio** · revisado el 17-11-2026.

## Paso 0: Jurisprudenciator en esta skill (obligatorio)

**Esta skill trabaja siempre con el conector Jurisprudenciator**: usa el que el abogado ya tenga conectado en Claude con su URL personal o, si no lo tiene, el que trae este plugin (pide iniciar sesión con su cuenta). Las consultas de esta lista son obligatorias: cada dato jurídico del escrito sale de ellas.

- **Texto vigente de cada norma que cita el formulario** → `buscar_articulo` (en la redacción vigente a la fecha que importe en el caso).
- **Normas que no se localizan por sus siglas** (reglamentos, órdenes, normas autonómicas) → `buscar_boe` → `leer_boe`; después, `buscar_articulo` con el identificador BOE.
- **Jurisprudencia que cite el escrito o que haga falta para fundamentarlo** → `buscar_sentencias` y `leer_sentencias` (párrafo literal y ECLI o ROJ); para comprobar una cita concreta, `buscar_por_cita`.
- **Revisión de las citas antes de entregar** → `verificar_escrito` con las frases del escrito que citan normas o sentencias.
- **Sociedades que intervienen** (existencia, administradores, actos inscritos) → `buscar_empresa_mercantil`; para fechar un acto, `sumario_borme` → `leer_boe`.
- **Inmuebles** (referencia catastral, superficie, uso) → `consultar_catastro` (y `callejero_catastro` para localizar la dirección).

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
- [ ] NÚMERO
- [ ] FECHA (4 veces)
- [ ] DELITO
- [ ] LUGAR
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «…ad natural de acción son las siguientes:»

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 790 de la Ley de Enjuiciamiento Criminal
- art. 74 CP
- art. 74 del Código Penal
- art. 8 CP
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

### Formulario 0028 · Delito continuado: apelación contra la condena pidiendo la unidad natural de acción

- Año del modelo: 2026
- Revisión 17-11-2026: 9 campos de relleno marcados en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la Sección de lo Penal del Tribunal de Instancia deplazanº

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, actuando en nombre y representación del/de la recurrente D./Dña. [NOMBRE Y APELLIDOS] en el juicio oral número [NÚMERO] sobre el delito del art. CP, ante este órgano judicial comparezco y, como más procedente sea en derecho, DIGO:

Que, con fecha [FECHA] se le ha notificado a esta parte la sentencia recaída en fecha [FECHA] y, por no considerarla ajustada a derecho, dicho con todo respeto y en términos de estricta defensa, dentro del término legal interpongo contra la misma recurso de apelación, en ambos efectos, conforme a lo prevenido en el artículo 790 de la Ley de Enjuiciamiento Criminal, para ante la Audiencia Provincial, en base a las siguientes

ALEGACIONES

ÚNICA.-

La resolución que se recurre padece errores en la apreciación de la prueba como se explica:

Mi representado/a ha sido condenado/a como autor/a del delito continuado de [DELITO] del art. del CP y del art. 74 CP, lo que ha llevado a imponer la pena prevista en su mitad superior.

Los hechos deberían haberse incardinado bajo la tesis de la unidad natural de acción, dado que concurren las siguientes circunstancias que habilitan para considerar que se trata de un solo delito, en base al criterio de la STS 887/2025 de 29 de octubre, Rec. 1767/2023, que diferencia el delito continuado y la unidad natural de acción:

"Se habla de unidad de acción en sentido natural cuando el autor del hecho realiza un solo acto entendido en un sentido puramente ontológico o naturalístico (propinar un solo puñetazo). En cambio, se habla de unidad natural de acción cuando, aunque ontológicamente concurren varios actos, desde una perspectiva socio-normativa se consideran como una sola acción (propinar una paliza integrada por varios puñetazos, que integra un solo delito de lesiones).

De esta forma se aplica el concepto de la unidad natural de acción cuando los actos que ejecuta un sujeto presentan una unidad espacial y una estrechez o inmediatez temporal tal que, desde una dimensión socio-normativa, permiten apreciar un único supuesto fáctico subsumible en un solo tipo penal (especialmente en ciertos casos de delitos de falsedad documental y también contra la libertad sexual)

En cambio, concurre una unidad típica de acción cuando la norma penal engarza o ensambla varios actos o varias unidades naturales de acción en un único tipo penal (tráfico de drogas, delitos contra el medio ambiente y de intrusismo, entre otros). Pues la unidad típica de acción se da cuando varios actos son unificados como objeto único de valoración jurídica por el tipo penal. De forma que varios actos que contemplados aisladamente colman las exigencias de un tipo de injusto se valoran por el derecho desde un punto de vista unitario.

Por último, el delito continuado se encuentra formado por varias unidades típicas de acción que, al darse ciertos supuestos objetivos y subjetivos previstos en el art. 74 del Código Penal, se integran en una unidad jurídica de acción. Aparece constituido, por tanto, el delito continuado por varias realizaciones típicas individuales que acaban siendo abrazadas en una unidad jurídica a la que, por su intensificación del injusto, se aplica una pena agravada con respecto al delito único propio de la unidad típica de acción. Para ello tiene en cuenta el legislador que las acciones obedezcan a un plan preconcebido o al aprovechamiento de idéntica ocasión, así como a la homogeneidad de la infracción de la misma norma penal o a preceptos de igual o semejante naturaleza. De no darse tales condiciones, las acciones habrían de subsumirse en un concurso real de delitos."

En el presente caso concurre un solo hecho con una intensidad en la acción que no se prolonga en días distintos, sino en el mismo día, aunque integrando varias conductas en un mismo espacio temporal, lo que implica unidad natural de acción y no continuidad delictiva.

Las pruebas que avalan que no concurre un delito continuado, sino un solo delito bajo la tesis de la unidad natural de acción son las siguientes: [COMPLETAR].

Las tesis que abogan por esta teoría son las siguientes:

1.- A tenor de la continuidad delictiva, la distancia temporal entre las distintas acciones ha de ser la suficiente para no poder apreciar unidad natural de acción, pero tampoco debe ser demasiado grande hasta el punto de que suponga una ruptura de los elementos valorativos que justifican el tratamiento jurídicamente unitario.

La doctrina de la unidad natural de acción o unidad típica podría entenderse como «la concurrencia (simultánea o sucesiva) de varias acciones u omisiones que se hallan en estrecha conexión espacial y temporal, que puedan reconocerse objetivamente como unidad fáctica, pero que además poseen una vinculación de significado, de manera tal que se las puede considerar como unidad de valoración jurídica y ser juzgadas como una sola acción»

2.- La interpretación de la unidad de acción depende más de la normativa que de una valoración prejurídica, considerando factores como la voluntad única, la vinculación espacial y temporal, y la tipología delictiva.
3.- Requisitos para la unidad natural de acción:
a.- Conexión espacio-temporal muy estrecha.
b.- Unidad de sujeto pasivo.
c.- Unidad de bien jurídico.
d.- Unidad de propósito o designio inmediato.
e.- Percepción social del hecho como una sola acción.
f.- Desde el punto de vista subjetivo, que concurra un único acto de voluntad encaminado a la realización de toda la dinámica delictiva.
g.- Como elementos o condicionamientos objetivos de esta actividad, que todos los actos estén vinculados espacial y temporalmente, pues la disgregación de la dinámica delictiva en uno y otro sentido pueden romper la identidad que reclama la voluntad única.
h.- Desde la óptica normativa, que se dé la identificación en la tipología delictiva.
4.- A nivel penológico habrá una sola pena, sin acudir al art. 74 CP. No hay concurso ni agravación específica, pero será posible considerar que la pluralidad de hechos puede ser determinante a la hora de individualizar la pena dentro del marco establecido.

Si ocurren varios hechos en un mismo espacio temporal para aplicar la debida proporcionalidad de la pena se impondría la misma atendiendo a la «conjunta gravedad del hecho». Así, la motivación de la pena iría en este caso por argumentar por la vía del art. 66.1.6º CP la que corresponda atendiendo a la mayor gravedad que supone la existencia de varios delitos en el mismo lugar con la misma persona. Se trataría de un solo delito, pero en el marco de la pena a sancionar de forma más grave por la pluralidad de hechos cometidos al mismo tiempo.

A la unidad natural de acción le es aplicable el concurso aparente de normas penales del art. 8 CP, en aplicación de los criterios de la especialidad, absorción o consunción y alternatividad.

5.- El modo de proceder para determinar la respuesta ante si hay unidad natural de acción, continuidad delictiva o concurso real primero se determina si hay un solo hecho (unidad natural). Solo si se descarta, se analiza: la continuidad delictiva o el concurso real o ideal.
6.- Existe unidad natural de acción cuando se dan dos o más actos delictivos del mismo tipo si el hecho se produce entre las mismas personas y en un mismo ámbito espacio temporal, por ser todo ello realizado en una misma situación y consecuencia de un mismo dolo.

Se ha concebido el injusto como un todo unitario por aplicación de la doctrina de la unidad natural de acción.

Existirá un único delito siempre que las sucesivas acciones delictivas singulares, subsumibles en el mismo tipo legal, no supongan sino una simple intensificación del contenido material de injusto del hecho total.

7.- Existirá, también, unidad de acción y no una pluralidad de acciones, entendidas ambas en el sentido de relevancia penal, cuando la pluralidad de actuaciones sea percibida por un tercero no interviniente como una unidad por su realización conforme a una única resolución delictiva y por encontrarse vinculadas en el tiempo y en el espacio. La ley penal no atiende estrictamente a la naturalidad de las acciones, sino a sus componentes jurídicos.
8.- El concepto de unidad natural de acción concurre cuando los mismos movimientos corporales típicos se reiteran en un mismo espacio y de manera temporalmente próxima (varios puñetazos seguidos configuran un único delito de lesiones y varias penetraciones seguidas un único delito de violación) de manera que para un observador imparcial el hecho puede ser considerado como una misma acción natural, careciendo de sentido alguno descomponerlo en varios actos delictivos.
9.- Estaríamos ante una unidad natural de acción y un solo delito, no uno continuado, cuando puedan aplicarse a los hechos expresiones tales como «secuencias ininterrumpidas», «ataques progresivos», «encadenamiento sucesivo de agresiones» o «iteración inmediata», por designar algunas. Ello lleva a asumir la doctrina de la «unidad natural de acción», o mejor como la ha designado algún sector doctrinal «unidad típica» de acción.

En su virtud,

SUPLICO A LA SECCIÓN:

Se sirva tener por interpuesto en tiempo y forma recurso de apelación en ambos efectos contra la sentencia de fecha [FECHA] recaída en los precitados autos, lo admita a trámite, acordando la remisión de lo actuado a la Audiencia Provincial, a fin de que se dicte sentencia en la que se revoque la recurrida y se condene por un solo delito, suprimiendo la continuidad delictiva en la condena.

OTROSÍ DIGO: Que, conforme a lo establecido en el artículo 790.2 de la Ley de Enjuiciamiento Criminal, designo como domicilio para notificaciones la sala del Colegio de Procuradores sita en el mismo edificio de la Audiencia Provincial.

SUPLICO A LA SECCIÓN: Que tenga por efectuada la anterior designación.

Es Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a

================================================================================
