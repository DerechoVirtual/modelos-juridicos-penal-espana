---
name: libertad-conciencia-sentimientos-religiosos-defensa-643
description: "Redacta el escrito «Libertad de conciencia y sentimientos religiosos: defensa» (formulario 643 de honor, intimidad y delitos de odio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Libertad de conciencia y sentimientos religiosos: defensa

> Formulario 0643 del plugin **Honor, intimidad y delitos de odio** · revisado el 17-11-2026.

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
- [ ] Nº (2 veces)
- [ ] NOMBRE Y APELLIDOS (3 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] LOCALIDAD
- [ ] LUGAR
- [ ] FECHA (2 veces)
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «…terio de Justicia, porque, de no hacerlo»

## Elecciones que hay que hacer

- judicialmente / mediante exhorto

## Párrafos opcionales (3)

Inclúyelos solo si encajan en los hechos:

- 1.- Declaración del/de la acusado/a.…
- .- Testifical: declaración de los/as testigos que se mencionan a continuación y que deberán ser citados/as [EL…
- .- Documental: Cintas de grabación del lugar de culto que grabaron la secuencia ocurrida el día [FECHA] a las …

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 523 CP
- artículo 784.1 de la Ley de Enjuiciamiento Criminal
- art. 20.2 CP
- art. 784 LECrim
- artículo 523 CP
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

### Formulario 0643 · Libertad de conciencia y sentimientos religiosos: defensa

- Año del modelo: 2017
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (3); 1 desplegables y casillas convertidos en elección en blanco; 3 párrafos opcionales señalados; 9 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la defensa presenta sus conclusiones provisionales alegando que no cometió el delito del art. 523 CP que se le atribuye porque no realizó acto alguno de violencia, amenaza tumulto o una vía de hecho

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, en la representación que tengo acreditada de D./Dña. [NOMBRE Y APELLIDOS], acusado/a en las diligencias previas número [Nº DE PROCEDIMIENTO] por el supuesto delito del art. 523 CP comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

Que, conforme a lo preceptuado en el artículo 784.1 de la Ley de Enjuiciamiento Criminal, manifiesto mi disconformidad con los escritos de acusación y formulo en plazo (1) escrito de defensa en base a las siguientes:

CONCLUSIONES

PRIMERA.- Disconforme con la correlativa del Ministerio Fiscal y del acusador particular. Mi representado/a simplemente accedió a la iglesia sita en [LOCALIDAD] y profirió algunas expresiones desafortunadas, pero sin exigir la suspensión de la ceremonia religiosa, ni realizar acto alguno de violencia, amenaza, tumulto o una vía de hecho, ya que se limitó a entrar y decir "Pero ¿qué hacéis aquí perdiendo el tiempo?, pero sin querer afectar los derechos fundamentales de nadie ni la libertad de conciencia. Además, ese día había ingerido bebidas alcohólicas y no era consciente de sus actos.

SEGUNDA.- Los hechos no son constitutivos de un delito del art 523 CP. (2)

TERCERA.- Niego las correlativas. Mi representado/a no es el/la autor/a del delito por el que se procede ni de ningún otro.

CUARTA.- Disconforme con las correlativas. En cualquier caso, y en el supuesto de que se entendiera cometido el hecho se debería aplicar la eximente del art. 20.2 CP por el excesivo consumo de alcohol ingerido.

QUINTA.- Disconforme con las correlativas. Procede absolver a mi representado/a con todos los pronunciamientos favorables, por no ser el/la autor/a.

SEXTA.- No existiendo delito no ha lugar a realizar pronunciamiento alguno en torno a la responsabilidad civil.

Las costas serán declaradas de oficio.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito con sus copias, los admita y por realizada la calificación.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que para el acto del juicio oral propongo los siguientes:

MEDIOS DE PRUEBA (3)

Todos los propuestos por el Ministerio fiscal y el acusador particular y además los siguientes:

[OPCIONAL — incluir si procede]

1.- Declaración del/de la acusado/a.

[OPCIONAL — incluir si procede]

.- Testifical: declaración de los/as testigos que se mencionan a continuación y que deberán ser citados/as [ELEGIR: judicialmente / mediante exhorto]

- D/Dña [NOMBRE Y APELLIDOS], que acompañaba al/a la acusado/a ese día y se quedó en la puerta de entrada.

[OPCIONAL — incluir si procede]

.- Documental: Cintas de grabación del lugar de culto que grabaron la secuencia ocurrida el día [FECHA] a las [Nº] horas.

Por lo expuesto,

SUPLICO A LA SECCIÓN: Que declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 10 días desde el traslado del art. 784 LECrim por el/la Letrado/a de la Administración de Justicia.

(2) En este tipo penal se exige la concurrencia de cualquiera de las vías de acción que constan en el tipo, es decir, violencia, amenaza, tumulto o vías de hecho y la acción consiste en impedir, interrumpir o perturbar actos, funciones, ceremonias o manifestaciones de confesiones religiosas, pero se exigen que consten inscritas en el Registro del Ministerio de Justicia, porque, de no hacerlo [COMPLETAR], no estaría incluido en el tipo y solo se sancionarían las conductas realizadas que fueran delictivas, pero fuera de este artículo 523 CP.

Si, además de los hechos descritos en el art. 523 CP se realizaran otros consistentes en daños en bienes muebles o lesiones a las personas presentes en el lugar, se aplicarían las reglas del concurso con el tipo del art. 523 CP.

La STS 835/2017, de 19 de diciembre, rec. 47/2017, por un lado, recuerda que la ley exige que se actué con violencia, amenaza, tumulto o vías de hecho, de manera que el impedimento, la interrupción o la perturbación ocasionada de cualquier otra forma no sería delictiva. Por otro, que la doctrina exige que cualquiera de esos resultados presente cierta relevancia, teniendo en cuenta el tiempo de duración, la forma en la que se ha causado y la forma en la que cesó.

En cuanto a la penalidad se impone la de 6 meses a 6 años si los actos se realizan en lugar de culto y la de multa de 4 a 10 meses si se hacen en otro lugar, es decir fuera del lugar de culto, tales como los templos religiosos.

(3) En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos, al comienzo del juicio oral pueden aportarse más pruebas.

También debe pedirse que se reproduzca la grabación o lectura literal de la prueba practicada anticipadamente en la fase de diligencias previas (art. 777.2 LECr.).

================================================================================
