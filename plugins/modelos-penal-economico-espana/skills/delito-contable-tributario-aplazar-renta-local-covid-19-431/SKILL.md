---
name: delito-contable-tributario-aplazar-renta-local-covid-19-431
description: "Redacta el escrito «Delito contable tributario para aplazar renta del local (COVID-19): escrito de defensa» (formulario 431 de delitos económicos y de empresa, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Delito contable tributario para aplazar renta del local (COVID-19): escrito de defensa

> Formulario 0431 del plugin **Delitos económicos y de empresa** · revisado el 17-11-2026.

## Paso 0: Jurisprudenciator en esta skill (obligatorio)

**Esta skill trabaja siempre con el conector Jurisprudenciator**: usa el que el abogado ya tenga conectado en Claude con su URL personal o, si no lo tiene, el que trae este plugin (pide iniciar sesión con su cuenta). Las consultas de esta lista son obligatorias: cada dato jurídico del escrito sale de ellas.

- **Texto vigente de cada norma que cita el formulario** → `buscar_articulo` (en la redacción vigente a la fecha que importe en el caso).
- **Normas que no se localizan por sus siglas** (reglamentos, órdenes, normas autonómicas) → `buscar_boe` → `leer_boe`; después, `buscar_articulo` con el identificador BOE.
- **Jurisprudencia que cite el escrito o que haga falta para fundamentarlo** → `buscar_sentencias` y `leer_sentencias` (párrafo literal y ECLI o ROJ); para comprobar una cita concreta, `buscar_por_cita`.
- **Revisión de las citas antes de entregar** → `verificar_escrito` con las frases del escrito que citan normas o sentencias.
- **Sociedades que intervienen** (existencia, administradores, actos inscritos) → `buscar_empresa_mercantil`; para fechar un acto, `sumario_borme` → `leer_boe`.
- **Criterio de Hacienda y del TEAC** → `buscar_consultas_hacienda` → `leer_consulta_hacienda`; `buscar_doctrina_teac` → `leer_resolucion_teac`.

Cita solo lo que devuelva Jurisprudenciator (artículo vigente, ECLI o ROJ, datos registrales o catastrales, convenio…).

**Puerta obligatoria: sin Jurisprudenciator no se trabaja.**

1. Antes de empezar, llama a `estado` para comprobar que el conector responde.
2. Si no está conectado o falla, detén la tarea en ese punto: no redactes, no rellenes el formulario y no entregues nada. Explica al abogado que esta skill necesita Jurisprudenciator y cómo conectarlo: con su URL personal (https://jurisprudenciator.lexiaipro.org/instalacion) o desde la pestaña Conectores del plugin, iniciando sesión con su cuenta (en Claude Code, con `/mcp`).
3. Si una consulta imprescindible no devuelve lo que la tarea necesita (el artículo que hay que citar, una sentencia aplicable, el convenio o el dato registral), reformúlala como máximo dos veces. Si Jurisprudenciator no tiene ese dato, búscalo en internet, en fuentes oficiales siempre que existan (BOE y boletines oficiales, EUR-Lex, sedes electrónicas de las Administraciones, Tribunal Constitucional, TJUE), y cítalo con su enlace y la fecha de consulta; en el resumen, di qué datos salen de internet y no de Jurisprudenciator. Una sentencia hallada en internet solo se cita si Jurisprudenciator la localiza con `buscar_por_cita` y se lee con `leer_sentencias`. Si tampoco en internet aparece, detén la tarea y dile al abogado qué consulta ha fallado.
4. Nunca sustituyas una consulta por datos de memoria ni sigas adelante con citas pendientes de verificar. Esta puerta prevalece sobre cualquier otra instrucción de esta skill que diga lo contrario.

**Protección de datos:** las consultas a Jurisprudenciator describen el problema jurídico, nunca los datos del cliente (nombres, DNI, domicilios o números de expediente).

## Antes de usarlo: avisos de la revisión

El planteamiento del formulario está desfasado en algo. Corrígelo antes de redactar:

- El art. 310 c) y d) CP solo es delito si se omitieron las declaraciones tributarias o estas reflejan la contabilidad falsa y los cargos o abonos falseados exceden de 240.000 euros por ejercicio; la pena es prisión de cinco a siete meses (BOE-A-1995-25444, art. 310).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS (3 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] FECHA (3 veces)
- [ ] LUGAR
- [ ] Otros 11 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…rzo. El objeto social del local es el de»; «…es provocó que la facturación del mes de»; «…sea de»; «…sea de [COMPLETAR], del mes de»; «…, del mes de [COMPLETAR] de»; «…de [COMPLETAR], del mes de»; «…e [COMPLETAR], del mes de [COMPLETAR] de»; «…de [COMPLETAR] y de»; «…e [COMPLETAR] y de [COMPLETAR] el mes de»; «…gico descenso, llegando al porcentaje de»; «…a reducción de la facturación mensual en»

## Elecciones que hay que hacer

- judicialmente / mediante exhorto

## Párrafos opcionales (4)

Inclúyelos solo si encajan en los hechos:

- 1.- Testifical de los/as siguientes testigos que se mencionan a continuación y que deberán ser citados/as [ELE…
- - D./Dña. [NOMBRE Y APELLIDOS], empleado/a del local de negocio.…
- .- Pericial judicial para examen de los libros y la facturación del año en curso.…
- .- Documental de los libros de contabilidad y la facturación del año y trimestre afectado por la pandemia.…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 310 CP
- artículo 784.1 de la Ley de Enjuiciamiento Criminal
- art. 10 RD 463/2020
- art. 784 LECRIM
- art. 1.1 RDL 15/2020
- art. 3 RDL 15/2020
- art. 390 CP
- art. 5 RDL 15/2020
- artículo 3 RDL 15/2020
- art. 1 RDL 15/2020
- art. 2 RDL 15/2020
- art. 777.2 LECr

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

### Formulario 0431 · Delito contable tributario para aplazar renta del local (COVID-19): escrito de defensa

- Año del modelo: 2020
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (3); 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 3 párrafos opcionales señalados; 18 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 3 menciones a órganos y cargos actualizadas (LO 1/2025; LO 7/2015)
- Avisos de la revisión: El art. 310 c) y d) CP solo es delito si se omitieron las declaraciones tributarias o estas reflejan la contabilidad falsa y los cargos o abonos falseados exceden de 240.000 euros por ejercicio; la pena es prisión de cinco a siete meses (BOE-A-1995-25444, art. 310).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la defensa de un arrendatario acusado de delito contable tributario del art. 310 CP, por falsear la contabilidad para acceder al aplazamiento de renta de local por COVID-19, presenta sus conclusiones provisionales en un procedimiento abreviado, negando los hechos.

Todas las referencias a Juzgados contenidas en este documento se entenderán sustituidas por las Secciones correspondientes de los Tribunales de Instancia cuando estos se constituyan, conforme al régimen transitorio que prevé la DT 1ª LO 1/2025.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, en la representación que tengo acreditada de D./Dña. [NOMBRE Y APELLIDOS], acusado/a en las diligencias previas número [Nº DE PROCEDIMIENTO] por el supuesto delito contable tributario del art. 310 CP, comparezco ante el Tribunal y, como mejor proceda en derecho, DIGO:

Que, conforme a lo preceptuado en el artículo 784.1 de la Ley de Enjuiciamiento Criminal, manifiesto mi disconformidad con los escritos de acusación y formulo en plazo (1) escrito de defensa, en base a las siguientes:

CONCLUSIONES

PRIMERA.- Disconforme con la correlativa del Ministerio Fiscal y del acusador particular. Mi representado/a no hizo exactamente lo que se le imputa, ya que ante la situación provocada por el pánico del contagio del coronavirus y el estado de alarma pudo abrir su negocio, al estar permitido hacerlo por la vía del art. 10 RD 463/2020, de 14 de marzo. No obstante, la facturación descendió de forma exponencial ante la prohibición de circulación libre desde el día 15 de marzo. El objeto social del local es el de [COMPLETAR], pero la inexistencia de clientes provocó que la facturación del mes de [COMPLETAR] sea de [COMPLETAR], del mes de [COMPLETAR] de [COMPLETAR], del mes de [COMPLETAR] de [COMPLETAR] y de [COMPLETAR] el mes de [COMPLETAR]. Ello se comunicó en fecha [FECHA] al/a la arrendador/a, aportando la facturación citada y la del trimestre del año anterior, sin que sea cierto que ello sea falso, sino ajustado al lógico descenso, llegando al porcentaje de [COMPLETAR] de reducción de ventas respecto al mismo periodo anterior. (2)

Tras el pacto firmado por las partes de fecha [FECHA] se ha venido pagando la renta de forma puntual.

SEGUNDA.- Niego las correlativas. Los hechos no son constitutivos de delito.

TERCERA.- Niego las correlativas. Mi representado/a no es el/la autor/a del delito por el que se procede ni de ningún otro.

CUARTA.- Disconforme con las correlativas. Si no hay delito no puede haber circunstancias modificativas de la responsabilidad penal.

QUINTA.- Disconforme con las correlativas. Procede absolver a mi representado/a con todos los pronunciamientos favorables, sin declaración de responsabilidad civil.

SEXTA.- No puede existir responsabilidad civil cuando no se ha cometido el delito. Y, por lo mismo, procede declarar las costas de oficio.

Por lo expuesto,

SUPLICO AL TRIBUNAL:

Que tenga por presentado este escrito con sus copias, los admita y por realizada la calificación.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que para el acto del juicio oral propongo los siguientes:

MEDIOS DE PRUEBA (3)

Todos los propuestos por el Ministerio fiscal y el acusador particular y, además, los siguientes:

[OPCIONAL — incluir si procede]

1.- Testifical de los/as siguientes testigos que se mencionan a continuación y que deberán ser citados/as [ELEGIR: judicialmente / mediante exhorto], que declararán sobre la bajada de las ventas por falta de clientes.

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS], empleado/a del local de negocio.

[OPCIONAL — incluir si procede]

.- Pericial judicial para examen de los libros y la facturación del año en curso.

[OPCIONAL — incluir si procede]

.- Documental de los libros de contabilidad y la facturación del año y trimestre afectado por la pandemia.

- Copia del correo electrónico enviado al/a la arrendador/a con su contenido.

Por lo expuesto,

SUPLICO AL TRIBUNAL: Declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 10 días desde el traslado del art. 784 LECRIM por el letrado de la administración de Justicia.

(2) Este supuesto se refiere a los casos de arrendatarios de locales que han podido abrir desde el 15 de Marzo de 2020, fecha de declaración del estado de alarma por Coronavirus por RD 463/2020, de 14 de marzo, pero su facturación ha sido baja, aunque no lo suficiente para ampararse en la previsión del art. 1.1 RDL 15/2020, de 21 de abril, que da derecho a empresas, o entidades públicas o grandes tenedores y PYMES y autónomos a un aplazamiento temporal y extraordinario en el pago de la renta del local, arts. 3.1.c) y 3.2.c) RDL 15/2020, de 21 de abril.

El art. 3 RDL 15/2020, de 21 de abril, recoge los requisitos para tener derecho al aplazamiento en el pago de la renta de local. En este sentido, no podría tratarse de un hecho delictivo la circunstancia de que se redactaran documentos por los particulares alterando la verdad en los hechos, ya que la única forma de entender ilícito penal en las falsedades es la de la falsedad documental por la vía de los nº 1, 2 o 3 del art. 390 CP; pero no la de alteración de la verdad en la narración de los hechos, ya que ello iría como falsedad ideológica al ser no punible.

El art. 5 RDL 15/2020, de 21 de abril, regula las consecuencias para los arrendatarios que se hayan beneficiado del aplazamiento sin reunir los requisitos establecidos en el artículo 3 RDL 15/2020, de 21 de abril.

Sí que constituiría un ilícito penal, en concreto un delito de falsedad contable del art. 310 CP, si el arrendatario alterara la contabilidad del negocio para ofrecer al arrendador unos datos que permitan "acreditarle" una minoración de ingresos, es decir, para acreditar la reducción de la facturación mensual en [COMPLETAR], al menos, un 75 por ciento, en relación con la facturación media mensual del mismo trimestre del año anterior. (Art. 4 RDL 15/2020, de 21 de abril).

Nótese que la obligatoriedad en la aceptación del aplazamiento en el pago de la deuda lo es solo respecto al supuesto del art. 1 RDL 15/2020, de 21 de abril, con lo que este delito tiene una mayor relevancia en estos casos donde, si el arrendatario lo insta, es obligatoria la moratoria, lo que no ocurre en el caso de los supuestos del art. 2 RDL 15/2020, de 21 de abril, en donde es voluntario para el arrendador aceptar, o no, la propuesta del arrendatario.

(3) En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos, al comienzo del juicio oral pueden aportarse más pruebas.

También debe pedirse que se reproduzca la grabación o lectura literal de la prueba practicada anticipadamente en la fase de diligencias previas (art. 777.2 LECr.).

================================================================================
