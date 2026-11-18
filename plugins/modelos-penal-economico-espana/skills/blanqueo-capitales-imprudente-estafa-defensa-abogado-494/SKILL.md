---
name: blanqueo-capitales-imprudente-estafa-defensa-abogado-494
description: "Redacta el escrito «Blanqueo de capitales imprudente y estafa: defensa del abogado acusado» (formulario 494 de delitos económicos y de empresa, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Blanqueo de capitales imprudente y estafa: defensa del abogado acusado

> Formulario 0494 del plugin **Delitos económicos y de empresa** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (3 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] LUGAR
- [ ] FECHA

## Elecciones que hay que hacer

- judicialmente / mediante exhorto
- - / D. / Dña.

## Párrafos opcionales (3)

Inclúyelos solo si encajan en los hechos:

- 1. Testifical: declaración de los testigos que se mencionan a continuación y que deberán ser citados [ELEGIR: …
- [ELEGIR: - / D. / Dña.].…
- 2. Se impugna de forma expresa la documental aportada por la acusación.…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 301.3 CP
- art. 248 CP
- artículo 248 y 301.3 CP
- artículo 784.1 de la Ley de Enjuiciamiento Criminal
- art. 784 LECRIM
- art. 2 ñ) Ley 10/2010
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

### Formulario 0494 · Blanqueo de capitales imprudente y estafa: defensa del abogado acusado

- Año del modelo: 2019
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (3); 2 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 2 párrafos opcionales señalados; 5 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que un abogado acusado de blanqueo de capitales por imprudencia grave del art. 301.3 CP y de estafa del art. 248 CP en un procedimiento abreviado presenta sus conclusiones provisionales alegando que sus actos no son delictivos, no existiendo sospecha alguna de actividades de su cliente que exijan que se dé cuenta al SEPBLAC.

Actualizado conforme a la LO 14/2022, con entrada en vigor el 12 de enero de 2023.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales en la representación que tiene acreditada de D./Dña. [NOMBRE Y APELLIDOS], acusado/a en las diligencias previas número [Nº DE PROCEDIMIENTO] por el supuesto delito del artículo 248 y 301.3 CP, comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

Que, conforme a lo preceptuado en el artículo 784.1 de la Ley de Enjuiciamiento Criminal, manifiesto mi disconformidad con los escritos de acusación y formulo escrito de defensa (1) en base a las siguientes:

CONCLUSIONES

PRIMERA.- Disconforme con la correlativa del Ministerio Fiscal y del acusador particular. Mi representado/a no hizo exactamente lo que se le imputa, ya que no es cierto que haya participado en las relaciones comerciales entre el/la querellante y el/la empresario/a que sí es cierto que era su cliente, no existiendo sospecha alguna de actividad que exija que se dé cuenta al SEPBLAC. La circunstancia de que en las relaciones profesionales habidas entre el/la empresario/a y el/la querellante existan problemas queda al margen de la obligación y marco de responsabilidad del/de la letrado/a, existiendo obligación de dar cuenta al SEPBLAC solo cuando existan claros indicios de operaciones de blanqueo de capitales. Que en este caso haya concurrido una operación comercial entre el/la querellado/a D./Dña. [NOMBRE Y APELLIDOS] y el/la querellante queda en el marco de su exclusiva relación y responsabilidades mutuas, quedando al margen el/la letrado/a.

SEGUNDA.- Los hechos no son constitutivos de un delito de estafa del art. 248 CP ni de blanqueo de capitales por imprudencia grave del art. 301.3 CP (2).

TERCERA.- Niego las correlativas. Mi representado/a no es el/la autor/a del delito por el que se procede ni de ningún otro.

CUARTA.- Disconforme con las correlativas. Al no ser autor/a de ningún delito no pueden existir circunstancias modificativas de la responsabilidad inexistente.

QUINTA.- Disconforme con las correlativas. Procede absolver a mi representado/a con todos los pronunciamientos favorables, por no ser el/la autor/a.

SEXTA.- No existiendo delito no ha lugar a realizar pronunciamiento alguno en torno a la responsabilidad civil.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito con sus copias, los admita y por realizada la calificación.

OTROSÍ DIGO: Que para el acto del juicio oral propongo los siguientes:

MEDIOS DE PRUEBA (3)

Todos los propuestos por el Ministerio fiscal y el acusador particular y además los siguientes:

[OPCIONAL — incluir si procede]

1. Testifical: declaración de los testigos que se mencionan a continuación y que deberán ser citados [ELEGIR: judicialmente / mediante exhorto], que declararán sobre la inexistencia de la conducta de la que se le acusa por su conocimiento personal

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

[ELEGIR: - / D. / Dña.].

[OPCIONAL — incluir si procede]

2. Se impugna de forma expresa la documental aportada por la acusación.

Por lo expuesto,

SUPLICO A LA SECCIÓN: declare pertinentes las pruebas interesadas y acuerde su práctica.

Por ser de Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 10 días desde el traslado del art. 784 LECRIM por el letrado de la administración de Justicia.

(2) En los casos de delito de blanqueo por imprudencia grave del art. 301.3 CP se sanciona a los profesionales que cometan el delito por imprudencia, que solo puede ser grave o temeraria, no menos grave.

Esta imprudencia grave se suele cometer por profesionales precisamente por no dar cumplimiento a lo previsto en la Ley 10/2010, de 28 de abril, de prevención del blanqueo de capitales y de la financiación del terrorismo acerca del control de la actividad de sus clientes. (STS 997/2013, de 19 de diciembre, rec. 854/2013)

Sobre la obligación del letrado de dar cuenta al SEPBLAC de operaciones sospechosas de clientes señala el art. 2 ñ) Ley 10/2010, de 28 de abril, de prevención del blanqueo de capitales y de la financiación del terrorismo que son sujetos obligados los abogados.

El Servicio Ejecutivo de la Comisión de Prevención del Blanqueo de Capitales e Infracciones Monetarias (Sepblac) es la Unidad de Inteligencia Financiera de España, siendo único en todo el territorio nacional. El Sepblac es, asimismo, Autoridad Supervisora en materia de prevención del blanqueo de capitales y de la financiación del terrorismo.

(3) En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos al comienzo del juicio oral pueden aportarse más pruebas.

También debe pedirse que se reproduzca la grabación o lectura literal de la prueba practicada anticipadamente en la fase de diligencias previas (art. 777.2 LECrim.)

================================================================================
