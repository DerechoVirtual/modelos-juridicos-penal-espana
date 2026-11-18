---
name: abandono-lugar-accidente-lesiones-imprudentes-trafico-503
description: "Redacta el escrito «Abandono del lugar del accidente y lesiones imprudentes de tráfico: defensa» (formulario 503 de seguridad vial, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Abandono del lugar del accidente y lesiones imprudentes de tráfico: defensa

> Formulario 0503 del plugin **Seguridad vial** · revisado el 17-11-2026.

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

- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] LUGAR
- [ ] ORDINAL QUE CORRESPONDA (2 veces)
- [ ] DATOS IDENTIFICATIVOS DEL TESTIGO (2 veces)
- [ ] Otros 3 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…e acusación y formulo escrito de defensa»; «…er citados judicialmentemediante exhorto»; «…Firma de Abogado/a Firma de Procurador/a»

## Párrafos opcionales (3)

Inclúyelos solo si encajan en los hechos:

- [ORDINAL QUE CORRESPONDA].- Declaración de los testigos que se mencionan a continuaciónen escrito aparte y que…
- -D/Dña. [DATOS IDENTIFICATIVOS DEL TESTIGO]: nombre, apellidos, domicilio.…
- [ORDINAL QUE CORRESPONDA].- Pericial de los servicios médicos de la aseguradora al objeto de que se valore el …

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 382 bis CP
- art. 152 CP
- arts. 382 bis y 152 CP
- artículo 784.1 de la Ley de Enjuiciamiento Criminal
- art. 784 LECRIM
- art. 152.2 CP
- arts. 147.1, 149 y 150 CP
- artículo 382 bis CP
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

### Formulario 0503 · Abandono del lugar del accidente y lesiones imprudentes de tráfico: defensa

- Año del modelo: 2019
- Revisión 17-11-2026: saltos de párrafo recuperados (texto venía pegado); restos de formato retirados; 8 llamadas a nota sin texto retiradas; 1 párrafos repetibles señalados; 2 párrafos opcionales señalados; 6 campos de relleno marcados en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que el acusado presenta sus conclusiones provisionales en un procedimiento abreviado por delito de abandono del lugar del accidente del art. 382 bis CP y por lesiones imprudentes del art. 152 CP alegando que no se produjo ningún accidente de tráfico.

Actualizado conforme a la LO 11/2022, con entrada en vigor desde el 15 de septiembre de 2022.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia. A la Sección de Instrucción del Tribunal de Instancia deplaza nºD./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales en la representación que tiene acreditada de D./Dña. [NOMBRE Y APELLIDOS], acusado/a en las diligencias previas número [Nº DE PROCEDIMIENTO] por los supuestos delitos de los arts. 382 bis y 152 CP, comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:Que, conforme a lo preceptuado en el artículo 784.1 de la Ley de Enjuiciamiento Criminal, manifiesto mi disconformidad con los escritos de acusación y formulo escrito de defensa [COMPLETAR] en base a las siguientes:CONCLUSIONESPRIMERA.- Disconforme con la correlativa del Ministerio Fiscal y del acusador particular. Mi representado/a no hizo exactamente lo que se le imputa ya que no existió fuga alguna, ya que no llegó a colisionar el vehículo, sino que dio un frenazo y bajó a ver si había pasado algo, y al ver que el otro conductor le dijo que estaba bien se subió al vehículo y se marchó. No existió en realidad un accidente, ya que no colisionó.SEGUNDA.- Los hechos no son constitutivos de un delito de fuga del lugar del accidente del art. 382 bis CP ni de un delito de lesiones imprudentes del art. 152 CP. TERCERA.- Niego las correlativas. Mi representado/a no es el/la autor/a del delito por el que se procede ni de ningún otro.CUARTA.- Disconforme con las correlativas. Al no ser autor/a de ningún delito no pueden existir circunstancias modificativas de la responsabilidad inexistente.QUINTA.- Disconforme con las correlativas. Procede absolver a mi representado/a con todos los pronunciamientos favorables, por no existir responsabilidad penal.SEXTA.- No existiendo delito no ha lugar a realizar pronunciamiento alguno en torno a la responsabilidad civil.

Por lo expuesto,

SUPLICO A LA SECCIÓN:Que tenga por presentado este escrito con sus copias, los admita y por realizada la calificación.

Es de Justicia que pido en [LUGAR], día, mes, año

OTROSÍ DIGO: que para el acto del juicio oral propongo los siguientes:MEDIOS DE PRUEBA Todos los propuestos por el Ministerio fiscal y el acusador particular y además los siguientes:

[OPCIONAL — incluir si procede]

[ORDINAL QUE CORRESPONDA].- Declaración de los testigos que se mencionan a continuaciónen escrito aparte y que deberán ser citados judicialmentemediante exhorto [COMPLETAR], que declararán sobre la inexistencia de la conducta de la que se le acusa por su conocimiento personal.D/Dña. [DATOS IDENTIFICATIVOS DEL TESTIGO]: nombre, apellidos, domicilio ocupante del vehículo del acusado.
[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]
-D/Dña. [DATOS IDENTIFICATIVOS DEL TESTIGO]: nombre, apellidos, domicilio.

[OPCIONAL — incluir si procede]

[ORDINAL QUE CORRESPONDA].- Pericial de los servicios médicos de la aseguradora al objeto de que se valore el resultado lesional, siendo citados por la parte para el día del juicio. Por lo expuesto,

SUPLICO A LA SECCIÓN: que declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a

Firma de Procurador/a [COMPLETAR] Este escrito debe presentarse en el plazo de 10 días desde el traslado del art. 784 LECRIM por el letrado de la administración de Justicia.
 Existirá delito de fuga del art. 382 bis CP tanto si el accidente se produce por imprudencia grave, menos grave o leve del conductor, o, incluso, por caso fortuito sin culpa de éste y no se baja del vehículo para auxiliar al herido., eso sí, debe causarse un siniestro del que se derivan muertes o lesiones de los arts. 147.1, 149 o 150 CP.La LO 11/2022, vigente desde el 15 de septiembre de 2022, modifica la redacción del delito de abandono del lugar del accidente del art. 382 bis CP. En vez de remitirse a las lesiones del art. 152.2 CP que, a su vez, reenviaba a las de los arts. 147.1, 149 y 150 CP, el propio artículo 382 bis CP se refiere concretamente a estos 3 últimos artículos. La diferencia es que esas lesiones ya no tienen que producirse sólo por imprudencia menos grave, requisito que prevé el art. 152.2 CP, al que ya no hay remisión.
 En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos al comienzo del juicio oral pueden aportarse más pruebas.

También debe pedirse que se reproduzca la grabación o lectura literal de la prueba practicada anticipadamente en la fase de diligencias previas (art. 777.2 LECrim.)
 Se puede presentar esta pericial para contrarrestar la presentada por la acusación, o la pericial del forense.

================================================================================
