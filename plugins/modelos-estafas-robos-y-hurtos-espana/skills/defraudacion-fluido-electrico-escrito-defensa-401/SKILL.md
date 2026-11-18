---
name: defraudacion-fluido-electrico-escrito-defensa-401
description: "Redacta el escrito «Defraudación de fluido eléctrico: escrito de defensa» (formulario 401 de delitos contra el patrimonio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Defraudación de fluido eléctrico: escrito de defensa

> Formulario 0401 del plugin **Delitos contra el patrimonio** · revisado el 17-11-2026.

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
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS (3 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] FECHA (2 veces)
- [ ] IMPORTE (2 veces)
- [ ] LUGAR
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «…euros de los meses»

## Elecciones que hay que hacer

- arrendó / ocupó
- judicialmente / mediante exhorto

## Párrafos opcionales (3)

Inclúyelos solo si encajan en los hechos:

- 1.- Testifical: de los/as siguientes testigos que se mencionan a continuación y que deberán ser citados/as [EL…
- - D./Dña. [NOMBRE Y APELLIDOS], que declarará sobre la existencia del contrato verbal de arrendamiento.…
- .- Documental siguiente:…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 255 CP
- artículo 255 CP
- artículo 784.1 de la Ley de Enjuiciamiento Criminal
- art. 784 LECRIM
- art. 777.2 LECrim

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

### Formulario 0401 · Defraudación de fluido eléctrico: escrito de defensa

- Año del modelo: 2020
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (3); 2 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 2 párrafos opcionales señalados; 9 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)
- Avisos de la revisión: La LO 1/2026 añadió el art. 255.3 CP: si la defraudación, cualquiera que sea su cuantía, sirve para abastecer instalaciones de cultivo o tráfico de drogas (art. 368), la pena es prisión de seis a dieciocho meses o multa de doce a veinticuatro meses (BOE-A-2026-7966).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que el acusado por un delito defraudación de fluido eléctrico del art. 255 CP en un procedimiento abreviado presenta sus conclusiones provisionales alegando que no hay pruebas de que haya sido el autor del enganche al contador de la luz de otro.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales en la representación que tiene acreditada de D./Dña. [NOMBRE Y APELLIDOS], acusado/a en las diligencias previas número [Nº DE PROCEDIMIENTO] por el supuesto delito del artículo 255 CP, comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

Que, conforme a lo preceptuado en el artículo 784.1 de la Ley de Enjuiciamiento Criminal, manifiesto mi disconformidad con los escritos de acusación y formulo escrito de defensa (1) en base a las siguientes:

CONCLUSIONES

PRIMERA.- Disconforme con la correlativa del Ministerio Fiscal y del acusador particular. Mi representado/a no hizo exactamente lo que se le imputa, ya que cuando [ELEGIR: arrendó / ocupó] la casa el enganche de luz ya estaba realizado y no hay prueba alguna de que lo haya realizado él/ella.
El contrato de arrendamiento
La ocupación
 data de fecha [FECHA] y nada se ha manipulado ni alterado en relación a la electricidad. De suyo, se le comentó al/a la propietario/a si pagaba él/ella el consumo de luz, lo que acredita la inexistencia de intención alguna de alterar los contadores y evitar la constancia del consumo propio y llevar a cabo un enganche en el del vecino.

Aunque conste la alteración, esta maniobra puede haber sido realizada por cualquier persona que haya ocupado esta vivienda, no pudiendo existir una presunción de culpabilidad por el hecho de residir actualmente en el inmueble.

El informe de la compañía de electricidad no acredita la autoría del/de la acusado/a.

Consta el pago de los recibos de agua por importe de [IMPORTE] euros de los meses [COMPLETAR], en tanto en cuanto se nos pasaron estos recibos al cobro, pero no los de luz.

SEGUNDA.- Niego las correlativas. Los hechos no son constitutivos de un delito de defraudación de fluido eléctrico del art. 255 CP. (2)

TERCERA.- Niego las correlativas. Mi representado/a no es el/la autor/a del delito por el que se procede ni de ningún otro.

CUARTA.- Disconforme con las correlativas. Al no ser autor/a de ningún delito no pueden existir circunstancias modificativas de la responsabilidad inexistente.

QUINTA.- Disconforme con las correlativas. Procede absolver a mi representado/a con todos los pronunciamientos favorables, por no existir responsabilidad penal.

SEXTA.- Disconforme con las correlativas. Al no existir responsabilidad penal no hay tampoco responsabilidad civil.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito con sus copias, los admita y por realizada la calificación.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que para el acto del juicio oral propongo los siguientes:

MEDIOS DE PRUEBA (3)

Todos los propuestos por el Ministerio fiscal y el acusador particular y además los siguientes:

[OPCIONAL — incluir si procede]

1.- Testifical: de los/as siguientes testigos que se mencionan a continuación y que deberán ser citados/as [ELEGIR: judicialmente / mediante exhorto]:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS], que declarará sobre la existencia del contrato verbal de arrendamiento.

[OPCIONAL — incluir si procede]

.- Documental siguiente:

— Recibos de pago del importe de los muebles adquiridos.
— Contrato de arrendamiento.
— Pago del servicio de agua, por importe de [IMPORTE] euros.

Por lo expuesto,

SUPLICO A LA SECCIÓN: Declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 10 días desde el traslado del art. 784 LECRIM por el letrado de la administración de Justicia.

(2) En el delito del art. 255 CP deberían ser los técnicos de la empresa suministradora los que, cuando van a comprobar la lectura de contadores, detecten la existencia del enganche y den cuenta a la mercantil del hecho producido para ejercitar esta las acciones penales frente al infractor, pero no llevar a cabo un cargo al vecino que ha sufrido en su toma el enganche de aquél, o dejar que sea el vecino o la comunidad los que tengan que ejercitar las acciones civiles y/o penales frente al infractor, bien para evitar que lo siga haciendo al interesar medidas cautelares penales o la ejecución de la responsabilidad personal subsidiaria en caso de impago de la multa que se le imponga e ingreso corolario en prisión, bien para tratar de recuperar por la vía civil lo que al titular perjudicado se le ha defraudado, cuando en realidad el concepto de «perjudicado» debe atribuírsele a la empresa suministradora de la luz, no al propietario al que se le hace el enganche ilegal.

Por ello, el concepto de perjudicado en el delito de defraudación de fluido eléctrico debe ser atribuible a la compañía que es la suministradora de la luz, no el vecino a quien se engancha la toma de luz llevada a cabo de forma irregular, ya que las posibilidades de detectar la acción ilícita no son del vecino, sino de la empresa que tiene en su haber y disposición la posibilidad de saber y conocer quien ha efectuado la maniobra ilegal.

Por lo tanto, junto a la denuncia que debería presentar la empresa suministradora de la luz, se aportaría la fotografía de la acción ejecutada con la fecha, copia de los recibos de consumo de luz del vecino y un informe pericial de parte de la compañía con el cálculo estimado de la correspondencia del consumo defraudado. Pero, por ello, no se le debería cargar a este vecino al que se le practicó el enganche el cargo de la totalidad del recibo, sino efectuar un cálculo del consumo estimado y aplicarle el mismo, vigilando en lo sucesivo de forma más periódica el acceso a los cuadros de contadores, o bien que las propias comunidades de propietarios se esmeren en cerrar estos compartimentos para que solo y exclusivamente pueda entrar en ellos la empresa suministradora de la luz.

En todo caso, si es el vecino defraudado al que la empresa le ha pasado el cargo el que presenta la denuncia podría plantearle luego a la empresa la existencia de la prejudicialidad penal del caso, por haber presentado la denuncia contra el infractor, si la empresa decidiera proceder judicialmente contra él por la vía civil, dado que suscitaría en el pleito civil la paralización de la reclamación y que no le corresponde a él el control y vigilancia del cuadro de contadores, resultando evidente que se ha realizado la defraudación de fluido eléctrico, a fin de que se proceda a efectuar las investigaciones que fueran necesarias para ello.

Si cabe, el vecino en estos casos podría interesar la colaboración de la comunidad para acceder al cuadro de contadores y poder obtener pruebas acerca de quién es el inmueble que recibe la luz que es cargada en su contador de luz para que la acción penal se dirija contra el titular del inmueble o sus ocupantes.

Sería en este procedimiento donde podría personarse, en todo caso, la compañía de la luz para reclamar frente al o los denunciados la suma del importe de las cantidades que resulten de realizar el cálculo antes expuesto. No hay que olvidar que el lugar donde se encuentra el cuadro de contadores no es de libre acceso al propietario, sino que pertenece a la empresa suministradora de luz su control. Los vecinos son responsables de lo que ocurre de puertas hacia adentro de su inmueble, pero no de lo que ocurra fuera de él, y si hay una alteración de su cuadro de contadores no es su responsabilidad.

Por otro lado, la comunidad de propietarios también podría intervenir directamente presentando la denuncia acerca de que alguien ha accedido al cuadro de contadores que no es zona privada de nadie, ni común de la propia comunidad, sino un elemento al que solo puede acceder personal de la compañía que suministra la luz. Por ello, la comunidad de propietarios, si recibe la queja en este sentido de un vecino, comunicaría con la empresa suministradora de la luz para que se acceda al cuarto de contadores y que, con la presencia del presidente, el administrador de fincas o un empleado de la comunidad se pudieran obtener las pruebas tendentes a identificar al autor o autores de la defraudación.

En este tipo de casos suele alegarse que se trata de una cuestión civil por el montante económico defraudado y no penal. No obstante, nos encontramos ante un ilícito penal, como lo destaca la jurisprudencia. Y así, la SAP Guadalajara 39/2009, de 3 de marzo, rec. 73/2009.

Interesante también resulta en estos casos el supuesto en el que, a raíz de una entrada y registro por un delito distinto, por ejemplo, contra la salud pública, se detecta la existencia de estos enganches ilegales, y la cuestión a resolver es si tiene validez el auto habilitante para la entrada y registro a raíz de un caso de tráfico de drogas para de ahí depurar responsabilidades también por otro del que ahora estamos analizando. Y sobre esta validez se pronuncia la SAP Balears 170/2013, de 3 de julio, rec. 175/2013.

(3) En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos, al comienzo del juicio oral pueden aportarse más pruebas.

También debe pedirse que se reproduzca la grabación o lectura literal de la prueba practicada anticipadamente en la fase de diligencias previas (art. 777.2 LECrim.).

================================================================================
