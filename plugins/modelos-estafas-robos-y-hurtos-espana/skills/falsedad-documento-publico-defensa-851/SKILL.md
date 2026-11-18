---
name: falsedad-documento-publico-defensa-851
description: "Redacta el escrito «Falsedad en documento público: defensa» (formulario 851 de delitos contra el patrimonio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Falsedad en documento público: defensa

> Formulario 0851 del plugin **Delitos contra el patrimonio** · revisado el 17-11-2026.

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

- [ ] SEDE
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS (32 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] AÑO
- [ ] FECHA (3 veces)
- [ ] NÚMERO
- [ ] ...
- [ ] LUGAR
- [ ] Otros 11 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…rador/a único/a de la sociedad mercantil»; «…rador/a único/a de la sociedad mercantil»; «…, del Registro de la Propiedad de»; «… representación de la sociedad mercantil»; «…scrito en el Registro de la Propiedad de»; «…a único/a de la de la sociedad mercantil»; «… administrador/a único/a de la mercantil»; «…rador/a único/a de la sociedad mercantil»; «…miento, y, en un momento posterior, para»; «…timo administrador único de la mercantil»; «…ión, con el fin de privar a la mercantil»

## Párrafos opcionales (2)

Inclúyelos solo si encajan en los hechos:

- 1.- Interrogatorio del/de la acusado/a…
- .- .- Testifical. Declaración de los/as siguientes testigos, que deberán ser citados/as judicialmente:…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 392.1 CP
- artículo 784.1 de la Ley de Enjuiciamiento Criminal
- art. 28 del Código Penal
- art. 392 CP

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

### Formulario 0851 · Falsedad en documento público: defensa

- Año del modelo: 2016
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (2); 2 párrafos opcionales señalados; 49 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito del acusado en procedimiento abreviado presentando sus conclusiones provisionales sobre la acusacón del delito de falsedad en documento público del art. 392.1 CP.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales en la representación que tiene acreditada de D./Dña. [NOMBRE Y APELLIDOS], acusado/a en las diligencias previas número [Nº DE PROCEDIMIENTO] del año [AÑO] por el supuesto delito de falsedad en documento público, comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

Que, conforme a lo preceptuado en el artículo 784.1 de la Ley de Enjuiciamiento Criminal, manifiesto mi disconformidad con los escritos de acusación y formulo en plazo (1) escrito de defensa, con base en las siguientes:

CONCLUSIONES

PRIMERA.- Disconforme con la correlativa del Ministerio Fiscal y del acusador particular. Los hechos que realmente sucedieron fueron los que se enuncian seguidamente.

En la tarde del día [FECHA], se presentó en la notaría de mi representado el/la acusado/a D./Dña. [NOMBRE Y APELLIDOS]. Era la primera ocasión en que comparecía en la misma, sin que, al margen de su actividad como notario/a, tuviera con él ningún tipo de relación personal o profesional.

El/La acusado/a fue presentado por un/a cliente, D./Dña. [NOMBRE Y APELLIDOS], administrador/a de varias empresas dedicadas al negocio inmobiliario, cuya presencia en el despacho, en relación con su actividad empresarial, sí era frecuente, al efecto de realizar operaciones de índole societaria y bancaria, sin que en ningún momento se produjera incidencia alguna o motivo para sospechar de la existencia de una operativa subyacente irregular, en general o en relación con actos jurídicos concretos.

El/La acusado/a D./Dña. [NOMBRE Y APELLIDOS], acompañado/a de D./Dña. [NOMBRE Y APELLIDOS], se presentó en la notaría en aquella fecha junto con otra persona, D./Dña. [NOMBRE Y APELLIDOS] que se identificó como administrador/a único/a de la sociedad mercantil [COMPLETAR].

D./Dña. [NOMBRE Y APELLIDOS], en su referida condición de administrador/a único/a de la sociedad mercantil [COMPLETAR], otorgó "poder tan amplio y bastante como en derecho se requiera y sea necesario a favor de D./Dña. [NOMBRE Y APELLIDOS] " (el/la acusado/a) para que aquél/aquella, en nombre y representación de la sociedad poderdante, pudiera vender la finca registral nº [NÚMERO], del Registro de la Propiedad de [COMPLETAR], de la titularidad, al cien por cien, de esta mercantil.

En virtud de dicho poder, seis meses más tarde, en otra notaría de la misma ciudad, se otorgó escritura de compraventa por el/la acusado/a D./Dña. [NOMBRE Y APELLIDOS], en nombre y representación de la sociedad mercantil [COMPLETAR], resultando ser la parte adquirente D./Dña. [NOMBRE Y APELLIDOS], según consta inscrito en el Registro de la Propiedad de [COMPLETAR], en el asiento registral correspondiente a esta finca.

Retomando el hilo de los hechos, en lo que ahora interesa a esta defensa, D./Dña. [NOMBRE Y APELLIDOS] afirmó ser el/la administrador/a único/a de la de la sociedad mercantil [COMPLETAR], identificándose con un documento nacional de identidad de apariencia externa correcta, que permitía colegir, de forma razonable, que resultaba ser la persona que afirmaba que era. En cambio, no aportó escritura de poder o de elevación a público de acuerdos sociales para acreditar la condición de administrador/a único/a de la mercantil [COMPLETAR]. Sin embargo, con el apoyo del/de la acusado/a D./Dña. [NOMBRE Y APELLIDOS], D./Dña. [NOMBRE Y APELLIDOS] fue capaz de facilitar todos los datos necesarios, tanto de la propia sociedad como los registrales de la finca objeto del otorgamiento, lo que permitía concluir, asimismo, que se trataba efectivamente del/de la administrador/a único/a de la mercantil.

Ciertamente, como después se ha puesto de manifiesto, D./Dña. [NOMBRE Y APELLIDOS] no era el/la administrador/a único/a de la sociedad mercantil [COMPLETAR], y, posiblemente, el documento nacional de identidad con el que se identificó era un documento falso.

Lo cierto es que la intervención de mi representado/a en el otorgamiento de la escritura de poder respondió a las maniobras del/de la acusado/a D./Dña. [NOMBRE Y APELLIDOS], que se valió de D./Dña. [NOMBRE Y APELLIDOS] y de la confianza de mi representado/a con éste/a para rebajar las cautelas relacionadas con el otorgamiento, y, en un momento posterior, para [COMPLETAR], como medio, consumar la privación al legítimo propietario —la sociedad mercantil — de la finca transmitida. Aunque el nuevo titular de la finca, una vez ejercido el poder, seis meses más tarde, fue D./Dña. [NOMBRE Y APELLIDOS], el dominio de la situación era ejercido, realmente, por el/la acusado/a D./Dña. [NOMBRE Y APELLIDOS].

En cuanto a D./Dña. [NOMBRE Y APELLIDOS], de quien tampoco se han vuelto a tener noticias, según resulta de la documentación procesal, parece, asimismo, que no era más que un instrumento del/de la acusado/a D./Dña. [NOMBRE Y APELLIDOS].

Todo esto nos permite colegir que el/la acusado/a D./Dña. [NOMBRE Y APELLIDOS] era conocedor/a de todos los datos que permitieron plasmar la intervención de una persona que no era el legítimo administrador único de la mercantil [COMPLETAR], que actúo fingiendo serlo, y que aquel era el/la único/a beneficiario/a, con la posterior apariencia de la intervención como comprador de la finca de D./Dña. [NOMBRE Y APELLIDOS], de dicho apoderamiento ilegítimo.

Estos hechos nos conducen a concluir en la falsedad del propio poder de representación otorgado, al ser provocada la intervención en el apoderamiento de una persona que nunca intervino (D./Dña. [NOMBRE Y APELLIDOS]), lo que determina la concurrencia de un delito de falsedad documental del que es responsable en exclusiva, en concepto de autor/a el/la acusado/a D./Dña. [NOMBRE Y APELLIDOS], quien, conociendo que la persona que comparecía como poderdante (D./Dña. [NOMBRE Y APELLIDOS]) no era el verdadero administrador único, se valió de esta tercera persona, y de D./Dña. [NOMBRE Y APELLIDOS] como posterior adquirente en la compraventa de la finca en cuestión, con el fin de privar a la mercantil [COMPLETAR] de este elemento patrimonial.

Autoría que así debe establecerse por ser el/la acusado/a D./Dña. [NOMBRE Y APELLIDOS] la única persona beneficiaria de dicha falsedad, quien tenía el dominio funcional del hecho conociendo la falsedad concurrente en la identidad de la persona otorgante del poder, pues se aprovechó de las consecuencias del ilícito penal.

Conforme a la STS 770/2008, de 18 de noviembre, rec. 376/2008, "en los supuestos en los que no pueda determinarse quien sea el autor de la falsedad, podrá tenerse por tal a quien tenga el dominio funcional del hecho conociendo la falsedad del documento. Esta construcción tiene su amparo legal en el art. 28 del Código Penal, que refiere que son autores no sólo quienes realizan por sí solos el hecho, sino también quienes lo realizan por medio de otro del que se sirven de instrumento [...] el delito de falsedad puede cometerlo quien tiene el dominio funcional del hecho, siendo indiferente la realización material de la falsedad, pues si existe una decisión conjunta de realizar el hecho, resulta irrelevante la materialización de los rasgos falsarios, ya que esa connivencia convierte en autores a todos los posibles participantes".

Estos hechos nos situarían ante un posible delito de falsedad documental en la escritura de apoderamiento de fecha [FECHA], que se subsume en el art. 392 CP, apartado 1, en relación con el art. 390.1.3º del Código Penal, imputable, al menos, a D./Dña. [NOMBRE Y APELLIDOS], pero que, en ningún caso, acarrearía reproche penal alguno para el/la notario autorizante de dicho poder, que no ha sido más que un elemento instrumental en los propósitos criminales del/de la acusado/a D./Dña. [NOMBRE Y APELLIDOS].

SEGUNDA.- Se niega la correlativa. Sin delito no puede hablarse de responsabilidad criminal de ninguna clase.

TERCERA.- Disconforme con las correlativas. Sin delito y sin responsable no pueden existir circunstancias modificativas de la responsabilidad.

CUARTA.- Disconforme con la correlativa. Procede absolver a mi representado/a con todos los pronunciamientos favorables.

QUINTA.- Disconforme con la correlativa. No puede existir responsabilidad civil cuando no existe delito. Y por lo mismo procede declarar las costas de oficio.

Por todo lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito con sus copias, los admita y por realizada la calificación.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que para el acto del juicio oral propongo los siguientes,

MEDIOS DE PRUEBA (2)

Todos los propuestos por el Ministerio Fiscal en su escrito de calificación y la Acusación Particular y además los siguientes:

[OPCIONAL — incluir si procede]

1.- Interrogatorio del/de la acusado/a

[OPCIONAL — incluir si procede]

.- .- Testifical. Declaración de los/as siguientes testigos, que deberán ser citados/as judicialmente:

— D./Dña. [NOMBRE Y APELLIDOS], oficial de la notaría de mi representado/a en la fecha en que ocurrieron los hechos.
— D./Dña. [NOMBRE Y APELLIDOS], notario que, en base al poder controvertido, autorizó la compraventa del inmueble con posterioridad.

Por lo expuesto,

SUPLICO A LA SECCIÓN: declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 10 días hábiles desde que se recibe traslado de la causa.

(2) En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos al comienzo del juicio oral pueden aportarse más pruebas.

================================================================================
