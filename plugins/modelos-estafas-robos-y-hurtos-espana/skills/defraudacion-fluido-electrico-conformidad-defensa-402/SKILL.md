---
name: defraudacion-fluido-electrico-conformidad-defensa-402
description: "Redacta el escrito «Defraudación de fluido eléctrico: conformidad de la defensa» (formulario 402 de delitos contra el patrimonio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Defraudación de fluido eléctrico: conformidad de la defensa

> Formulario 0402 del plugin **Delitos contra el patrimonio** · revisado el 17-11-2026.

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

## Antes de usarlo: avisos de la revisión

El planteamiento del formulario está desfasado en algo. Corrígelo antes de redactar:

- La LO 1/2026 añadió el art. 255.3 CP: si la defraudación, cualquiera que sea su cuantía, sirve para abastecer instalaciones de cultivo o tráfico de drogas (art. 368), la pena es prisión de seis a dieciocho meses o multa de doce a veinticuatro meses (BOE-A-2026-7966).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] Nº (2 veces)
- [ ] NOMBRE Y APELLIDOS (3 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] IMPORTE
- [ ] LUGAR
- [ ] FECHA

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 255 CP
- art. 255 CP
- art. 784.3 LECRIM
- art. 787 LECRIM
- art. 787 ter LECRIM
- art. 785 LECRIM

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

### Formulario 0402 · Defraudación de fluido eléctrico: conformidad de la defensa

- Año del modelo: 2020
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (2); 7 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)
- Avisos de la revisión: La LO 1/2026 añadió el art. 255.3 CP: si la defraudación, cualquiera que sea su cuantía, sirve para abastecer instalaciones de cultivo o tráfico de drogas (art. 368), la pena es prisión de seis a dieciocho meses o multa de doce a veinticuatro meses (BOE-A-2026-7966).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que el acusado en procedimiento abreviado se conforma con la calificación jurídica de los hechos como delito de defraudación del fluido eléctrico del artículo 255 CP realizada por la fiscalía y con la pena solicitada.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales en la representación que tiene acreditada de D./Dña. [NOMBRE Y APELLIDOS], acusado/a en las diligencias previas número [Nº DE PROCEDIMIENTO], por el supuesto delito de defraudación del fluido eléctrico del art. 255 CP, comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

Que, conforme al Protocolo de conformidades suscrito entre la Fiscalía General del Estado y el Consejo General de la Abogacía de fecha 1 de abril de 2009 (1) y el art. 784.3 LECRIM, en relación con el art. 787 LECRIM (hasta el 2/4/2025) art. 787 ter LECRIM (desde el 3/4/2025), se formula escrito de conformidad de los hechos considerados como delito de defraudación del fluido eléctrico del art. 255 CP. (2).

En este sentido, la defensa se conforma con la petición formulada por la Fiscalía para D./Dña. [NOMBRE Y APELLIDOS], a la pena de [Nº] meses de multa a razón de [IMPORTE] euros/día y con responsabilidad personal subsidiaria de 1 día por cada dos cuotas impagadas, a ratificar en la audiencia preliminar del art. 785 LECRIM (desde el 3/4/2025).

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita y tenga por evacuado el trámite por la conformidad de la defensa.

Es de Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a:	Firma de el/la acusado/a:

NOTAS DEL FORMULARIO

(1) En base al protocolo de conformidades suscrito entre la Fiscalía General del Estado y el Consejo General de la Abogacía de fecha 1 de abril de 2009 se puede presentar escrito del abogado defensor antes del señalamiento de juicio oral incluso después de evacuado el trámite de calificación.

(2) En el delito del art. 255 CP deberían ser los técnicos de la empresa suministradora los que, cuando van a comprobar la lectura de contadores, detecten la existencia del enganche y den cuenta a la mercantil del hecho producido para ejercitar esta las acciones penales frente al infractor, pero no llevar a cabo un cargo al vecino que ha sufrido en su toma el enganche de aquél, o dejar que sea el vecino o la comunidad los que tengan que ejercitar las acciones civiles y/o penales frente al infractor, bien para evitar que lo siga haciendo al interesar medidas cautelares penales o la ejecución de la responsabilidad personal subsidiaria en caso de impago de la multa que se le imponga e ingreso corolario en prisión, bien para tratar de recuperar por la vía civil lo que al titular perjudicado se le ha defraudado, cuando en realidad el concepto de «perjudicado» debe atribuírsele a la empresa suministradora de la luz, no al propietario al que se le hace el enganche ilegal.

Por ello, el concepto de perjudicado en el delito de defraudación de fluido eléctrico debe ser atribuible a la compañía que es la suministradora de la luz, no el vecino a quien se engancha la toma de luz llevada a cabo de forma irregular, ya que las posibilidades de detectar la acción ilícita no son del vecino, sino de la empresa que tiene en su haber y disposición la posibilidad de saber y conocer quien ha efectuado la maniobra ilegal.

Por lo tanto, junto a la denuncia que debería presentar la empresa suministradora de la luz, se aportaría la fotografía de la acción ejecutada con la fecha, copia de los recibos de consumo de luz del vecino y un informe pericial de parte de la compañía con el cálculo estimado de la correspondencia del consumo defraudado. Pero, por ello, no se le debería cargar a este vecino al que se le practicó el enganche el cargo de la totalidad del recibo, sino efectuar un cálculo del consumo estimado y aplicarle el mismo, vigilando en lo sucesivo de forma más periódica el acceso a los cuadros de contadores, o bien que las propias comunidades de propietarios se esmeren en cerrar estos compartimentos para que solo y exclusivamente pueda entrar en ellos la empresa suministradora de la luz.

En todo caso, si es el vecino defraudado al que la empresa le ha pasado el cargo el que presenta la denuncia podría plantearle luego a la empresa la existencia de la prejudicialidad penal del caso, por haber presentado la denuncia contra el infractor, si la empresa decidiera proceder judicialmente contra él por la vía civil, dado que suscitaría en el pleito civil la paralización de la reclamación y que no le corresponde a él el control y vigilancia del cuadro de contadores, resultando evidente que se ha realizado la defraudación de fluido eléctrico, a fin de que se proceda a efectuar las investigaciones que fueran necesarias para ello.

Si cabe, el vecino en estos casos podría interesar la colaboración de la comunidad para acceder al cuadro de contadores y poder obtener pruebas acerca de quién es el inmueble que recibe la luz que es cargada en su contador de luz para que la acción penal se dirija contra el titular del inmueble o sus ocupantes.

Sería en este procedimiento donde podría personarse, en todo caso, la compañía de la luz para reclamar frente al o los denunciados la suma del importe de las cantidades que resulten de realizar el cálculo antes expuesto. No hay que olvidar que el lugar donde se encuentra el cuadro de contadores no es de libre acceso al propietario, sino que pertenece a la empresa suministradora de luz su control. Los vecinos son responsables de lo que ocurre de puertas hacia adentro de su inmueble, pero no de lo que ocurra fuera de él, y si hay una alteración de su cuadro de contadores no es su responsabilidad.

Por otro lado, la comunidad de propietarios también podría intervenir directamente presentando la denuncia acerca de que alguien ha accedido al cuadro de contadores que no es zona privada de nadie, ni común de la propia comunidad, sino un elemento al que solo puede acceder personal de la compañía que suministra la luz. Por ello, la comunidad de propietarios, si recibe la queja en este sentido de un vecino, comunicaría con la empresa suministradora de la luz para que se acceda al cuarto de contadores y que, con la presencia del presidente, el administrador de fincas o un empleado de la comunidad se pudieran obtener las pruebas tendentes a identificar al autor o autores de la defraudación.

En este tipo de casos suele alegarse que se trata de una cuestión civil por el montante económico defraudado y no penal. No obstante, nos encontramos ante un ilícito penal, como lo destaca la jurisprudencia. Y así, la SAP Guadalajara 39/2009, de 3 de marzo, rec. 73/2009.

Interesante también resulta en estos casos el supuesto en el que, a raíz de una entrada y registro por un delito distinto, por ejemplo, contra la salud pública, se detecta la existencia de estos enganches ilegales, y la cuestión a resolver es si tiene validez el auto habilitante para la entrada y registro a raíz de un caso de tráfico de drogas para de ahí depurar responsabilidades también por otro del que ahora estamos analizando. Y sobre esta validez se pronuncia la SAP Balears 170/2013, de 3 de julio, rec. 175/2013.

================================================================================
