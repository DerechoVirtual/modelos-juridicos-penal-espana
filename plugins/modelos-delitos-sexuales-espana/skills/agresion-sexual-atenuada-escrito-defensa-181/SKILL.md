---
name: agresion-sexual-atenuada-escrito-defensa-181
description: "Redacta el escrito «Agresión sexual atenuada: escrito de defensa» (formulario 181 de delitos sexuales, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Agresión sexual atenuada: escrito de defensa

> Formulario 0181 del plugin **Delitos sexuales** · revisado el 17-11-2026.

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

## Antes de usarlo: avisos de la revisión

El planteamiento del formulario está desfasado en algo. Corrígelo antes de redactar:

- Formulario en la versión de la LO 10/2022 (existe versión «LO 4/2023»). Desde el 29-4-2023 el tipo atenuado es el art. 178.4 CP (mitad inferior o multa de 18 a 24 meses) y no se aplica con violencia, intimidación o voluntad anulada, que el art. 178.3 castiga con uno a cinco años.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] Nº DE PROCEDIMIENTO (2 veces)
- [ ] COLEGIO
- [ ] LOCALIDAD
- [ ] IMPORTE
- [ ] LUGAR
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «…, en representación del/de la acusado/a»

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (6)

Inclúyelos solo si encajan en los hechos:

- Subsidiariamente, los hechos pueden ser constitutivos de un delito del art. 178.3 CP, en atención a la menor e…
- Subsidiariamente, mi representado es autor del delito de agresión sexual atenuada en atención a la menor entid…
- Subsidiariamente, procede condenar a mi representado a la pena de multa de [IMPORTE], sin declaración de respo…
- 1.-La declaración del acusado será en último lugar tras la práctica de la prueba.…
- .-Testifical:…
- D./Dña. [NOMBRE Y APELLIDOS]…

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 784.1 de la Ley de Enjuiciamiento Criminal
- art. 178.1 CP
- art. 178.3 CP

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

### Formulario 0181 · Agresión sexual atenuada: escrito de defensa

- Año del modelo: 2022
- Revisión 17-11-2026: 1 puntualizaciones normativas añadidas en el texto; 5 llamadas a nota sin texto retiradas; 1 párrafos repetibles señalados; 1 bloques de alternativas señalados; 5 párrafos opcionales señalados; 11 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)
- Avisos de la revisión: Formulario en la versión de la LO 10/2022 (existe versión «LO 4/2023»). Desde el 29-4-2023 el tipo atenuado es el art. 178.4 CP (mitad inferior o multa de 18 a 24 meses) y no se aplica con violencia, intimidación o voluntad anulada, que el art. 178.3 castiga con uno a cinco años.

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales en la representación que tiene acreditada de D./Dña. [NOMBRE Y APELLIDOS], acusado/a en las diligencias previas número [Nº DE PROCEDIMIENTO], por el supuesto delito de agresión sexual del art. 178.1 o 3 CP [NOTA DE REVISIÓN: Numeración de la LO 10/2022 (hechos del 7-10-2022 al 28-4-2023). Para hechos posteriores el tipo atenuado es el art. 178.4 CP (LO 4/2023): mitad inferior de la pena o multa de 18 a 24 meses, excluido si hay violencia, intimidación, voluntad anulada o circunstancias del art. 180. Fuente: Código Penal, BOE-A-1995-25444, art. 178 (redacción LO 4/2023, BOE-A-2023-10213).], comparezco ante este órgano judicial y, como mejor proceda en derecho,

D./Dña. [NOMBRE Y APELLIDOS], Letrado/a del Ilustre Colegio de Abogados de [COLEGIO], con nº de colegiado y con despacho profesional abierto en [LOCALIDAD], en representación del/de la acusado/a [COMPLETAR], en las diligencias previas número [Nº DE PROCEDIMIENTO] por el supuesto delito de agresión sexual del art. 178.1 o 3 CP, comparezco ante este órgano judicial y, como mejor proceda en derecho,

Que, conforme a lo preceptuado en el artículo 784.1 de la Ley de Enjuiciamiento Criminal, manifiesto mi disconformidad con los escritos de acusación y formulo escrito de defensa en base a las siguientes:

CONCLUSIONES

PRIMERA.- Disconforme con la correlativa del Ministerio Fiscal y del acusador particular. Mi representado no hizo exactamente lo que se le imputa, ya que la realidad es que simplemente se cruzó con ella e intercambió unas palabras nada más, pero no es cierto que él le tocara en modo alguno. De suyo nadie vio esos hechos, y todo parte de una invención de la querellante. Lo único que ocurrió es que al salir ella y entrar él chocaron de frente y este fue el único contacto que tuvo, pero que fue totalmente fortuito.

SEGUNDA.- Niego las correlativas. Los hechos no son constitutivos de un delito del art. 178.1 CP.

[OPCIONAL — incluir si procede]

Subsidiariamente, los hechos pueden ser constitutivos de un delito del art. 178.3 CP, en atención a la menor entidad del hecho.

TERCERA.- Niego las correlativas. Mi representado no es el autor del delito por el que se procede.

[OPCIONAL — incluir si procede]

Subsidiariamente, mi representado es autor del delito de agresión sexual atenuada en atención a la menor entidad del hecho.

CUARTA.- Disconforme con las correlativas. Procede absolver a mi representado con todos los pronunciamientos favorables, sin declaración de responsabilidad civil.

[OPCIONAL — incluir si procede]

Subsidiariamente, procede condenar a mi representado a la pena de multa de [IMPORTE], sin declaración de responsabilidad civil.

Por lo expuesto,

SUPLICO A LA SECCIÓN

Que tenga por presentado este escrito con sus copias, los admita y por realizada la calificación.

Es de Justicia que pido en [LUGAR]

OTROSÍ DIGO: Que para el acto del juicio oral propongo los siguientes:

MEDIOS DE PRUEBA

[OPCIONAL — incluir si procede]

1.-La declaración del acusado será en último lugar tras la práctica de la prueba.

[OPCIONAL — incluir si procede]

.-Testifical:

-Declaración de los siguientes testigos acerca de que no vieron nada extraño en la reacción del acusado al volver a la mesa donde estaban cenando con él.

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

D./Dña. [NOMBRE Y APELLIDOS]

Por lo expuesto,

SUPLICO A LA SECCIÓN: declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a	Firma de Procurador/a

================================================================================
