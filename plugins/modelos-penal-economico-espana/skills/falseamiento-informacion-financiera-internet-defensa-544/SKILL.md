---
name: falseamiento-informacion-financiera-internet-defensa-544
description: "Redacta el escrito «Falseamiento de información financiera por internet: defensa» (formulario 544 de delitos económicos y de empresa, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Falseamiento de información financiera por internet: defensa

> Formulario 0544 del plugin **Delitos económicos y de empresa** · revisado el 17-11-2026.

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

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] LUGAR
- [ ] FECHA
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «…dministrador, ya de derecho, ya de hecho»

## Elecciones que hay que hacer

- a continuación / en escrito aparte
- judicialmente / mediante exhorto

## Párrafos opcionales (3)

Inclúyelos solo si encajan en los hechos:

- 1.- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y…
- - D./Dña. [NOMBRE Y APELLIDOS].…
- .- Pericial técnica contradictoria con la de la acusación sobre la falsedad de la información financiera, a cu…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 282 bis CP
- artículo 784.1 de la Ley de Enjuiciamiento Criminal
- art. 784 LECRIM
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

### Formulario 0544 · Falseamiento de información financiera por internet: defensa

- Año del modelo: 2018
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (3); 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 1 desplegables convertidos en elección en blanco; 2 párrafos opcionales señalados; 7 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la defensa presenta sus conclusiones provisionales en un procedimiento abreviado por delito contra el mercado y los consumidores del art. 282 bis CP, alegando la inexistencia de falseamiento en la información financiera publicitada.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales en la representación que tiene acreditada de D./Dña. [NOMBRE Y APELLIDOS], acusado/a en las diligencias previas número [Nº DE PROCEDIMIENTO] por el supuesto delito de falseamiento de información financiera del art. 282 bis CP, comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

Que, conforme a lo preceptuado en el artículo 784.1 de la Ley de Enjuiciamiento Criminal, manifiesto mi disconformidad con los escritos de acusación y formulo escrito de defensa (1)

en base a las siguientes:

CONCLUSIONES

PRIMERA.- Disconforme con la correlativa del Ministerio Fiscal y de los acusadores particulares. Mi representado/a no hizo lo que se le imputa ya que no existe en primer lugar el perjuicio que se alega en base al informe pericial que consta aportado a la presente.

No negamos que el resultado final de la inversión no fuera el esperado, pero no ha habido ninguna falsedad de la información económico-financiera expuesta por internet y en otros medios de publicidad, sino que fue el devenir de la situación económica el que provocó que la inversión no fuera positiva finalmente, por lo que los inversionistas también corren el riesgo con su inversión que no pueden trasladar a la empresa, ya que lo asumen cuando realizan la inversión.

Siendo la clave del tipo penal el falseamiento se aporta dictamen pericial contradictorio con el de la querella interpuesta que desmonta ese dictamen determinante de la inexistencia del falseamiento denunciado.

No hay por ello ilícito penal alguno.

SEGUNDA.- Los hechos no son constitutivos de un delito contra el mercado y los consumidores del art. 282 bis CP. (2)

TERCERA.- Niego las correlativas. Mi representado/a no es autor/a del delito por el que se procede ni de ningún otro.

CUARTA.- Disconforme con las correlativas. Al no ser autor/a de ningún delito no pueden existir circunstancias modificativas de la responsabilidad inexistente.

QUINTA.- Disconforme con las correlativas. Procede absolver a mi representado/a con todos los pronunciamientos favorables.

SEXTA.- Disconforme con las correlativas. No puede existir responsabilidad civil cuando no existe delito. Y por lo mismo procede declarar las costas de oficio.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito con sus copias, los admita y por realizada la calificación.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que para el acto del juicio oral propongo los siguientes

MEDIOS DE PRUEBA (3)

Todos los propuestos por el Ministerio fiscal y el acusador particular y además los siguientes:

[OPCIONAL — incluir si procede]

1.- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados/as [ELEGIR: judicialmente / mediante exhorto], que son compradores del depósito y que conocían el riesgo.

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS].

[OPCIONAL — incluir si procede]

.- Pericial técnica contradictoria con la de la acusación sobre la falsedad de la información financiera, a cuyo fin deberá ser citado/a a través de la oficina judicial el/la siguiente perito:

- D./Dña. [NOMBRE Y APELLIDOS].

Por lo expuesto,

SUPLICO A LA SECCIÓN: Que declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 10 días desde el traslado del art. 784 LECRIM por el letrado de la administración de Justicia.

(2) Se trata de un delito que se comete por personas que tengan cargo de administrador, ya de derecho, ya de hecho [COMPLETAR], admitiendo en esta segunda modalidad a cualquier persona que tenga cargo de representación societaria, como puede ser director general,. Apoderado, etc. Se refiere a este cargo respecto a entidades que sean emisoras de valores negociados en mercado de valores y que lleven a cabo conductas de falsedad en la información económica de la publicidad. El objetivo, que se exige como elemento del tipo, es la de captar inversores o depositantes para colocar productos financieros u obtener financiación.

La mera falsedad ya conlleva la comisión del delito, ya que si se causa el perjuicio se agrava la pena, ya que la pena básica del apartado 1º es de 1 a 4 años, pero de 2 años y 6 meses a 4 años en el caso del párrafo 2º de que se cause el perjuicio. Y si hay grave perjuicio la pena va en un arco de 1 a seis años.

(3) En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos al comienzo del juicio oral pueden aportarse más pruebas.

También debe pedirse que se reproduzca la grabación o lectura literal de la prueba practicada anticipadamente en la fase de diligencias previas (art. 777.2 LECr.).

================================================================================
