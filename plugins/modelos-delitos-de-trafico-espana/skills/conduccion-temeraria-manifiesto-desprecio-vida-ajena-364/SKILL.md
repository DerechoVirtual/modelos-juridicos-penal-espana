---
name: conduccion-temeraria-manifiesto-desprecio-vida-ajena-364
description: "Redacta el escrito «Conducción temeraria con manifiesto desprecio por la vida ajena: escrito de defensa» (formulario 364 de seguridad vial, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Conducción temeraria con manifiesto desprecio por la vida ajena: escrito de defensa

> Formulario 0364 del plugin **Seguridad vial** · revisado el 17-11-2026.

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
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS (3 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] AÑO
- [ ] LUGAR
- [ ] FECHA

## Elecciones que hay que hacer

- judicialmente / mediante exhorto

## Párrafos opcionales (4)

Inclúyelos solo si encajan en los hechos:

- 1.- Interrogatorio del/de la acusado/a.…
- .- Testifical de los siguientes testigos que serán citados [ELEGIR: judicialmente / mediante exhorto] que decl…
- D./Dña. [NOMBRE Y APELLIDOS]…
- . Informe biomecánico respecto al escenario del accidente que evidencia que fue la conducta del/de la denuncia…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 381 y 382 CP
- art. 152 CP
- artículo 784.1 de la Ley de Enjuiciamiento Criminal
- art. 381 CP

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

### Formulario 0364 · Conducción temeraria con manifiesto desprecio por la vida ajena: escrito de defensa

- Año del modelo: 2021
- Revisión 17-11-2026: 3 llamadas a nota sin texto retiradas; 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 3 párrafos opcionales señalados; 6 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales en la representación que tengo acreditada de D./Dña. [NOMBRE Y APELLIDOS], acusado/a en el procedimiento abreviado número [Nº DE PROCEDIMIENTO] del año [AÑO] por el supuesto delito de conducción temeraria con manifiesto desprecio a la vida de los demás del art. 381 y 382 CP y de lesiones del art. 152 CP, comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

Que, conforme a lo preceptuado en el artículo 784.1 de la Ley de Enjuiciamiento Criminal, manifiesto mi disconformidad con los escritos de acusación y formulo escrito de defensa en base a las siguientes:

CONCLUSIONES

PRIMERA.- Disconforme con la correlativa del Ministerio Fiscal y del acusador particular. Mi representado/a no hizo exactamente lo que se le imputa ya que no conducía en la forma expuesta, sino que fue el/la denunciante quien colisionó con el vehículo de mi representado/a y no como se recoge en la denuncia.

No ha existido, pues, conducción temeraria con manifiesto desprecio de la vida de los demás en la conducta del/de la denunciado/a, sino que fue la conducción imprudente del/de la denunciante la que determinó que se saliera de la vía y colisionara sin que hubiera causa eficiente alguna en que ello lo causara el/la denunciado/a y no existiendo prueba alguna que evidencia lo contrario.

En cualquier caso, se trató de un mero accidente y no de un delito de conducción temeraria del art. 381 CP, ya que el denunciante ha tergiversado la forma de ocurrir los hechos ocultando su propia responsabilidad, ya que en todo caso sería un accidente con culpas recíprocas, pero nunca un delito contra la seguridad vial.

SEGUNDA.- Disconforme con las correlativas. Los hechos descritos no constituyen infracción penal alguna.

TERCERA.- Disconforme con las correlativas. Sin delito no puede hablarse de responsabilidad criminal de ninguna clase.

CUARTA.- Disconforme con las correlativas. Sin delito y sin responsable no pueden existir circunstancias modificativas de la responsabilidad.

QUINTA.- Disconforme con las correlativas. Procede absolver a mi representado/a con todos los pronunciamientos favorables.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito con sus copias, los admita y por realizada la calificación.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que para el acto del juicio oral propongo los siguientes:

MEDIOS DE PRUEBA

Todos los propuestos por el Ministerio Fiscal y el acusador particular y además, los siguientes:

[OPCIONAL — incluir si procede]

1.- Interrogatorio del/de la acusado/a.

[OPCIONAL — incluir si procede]

.- Testifical de los siguientes testigos que serán citados [ELEGIR: judicialmente / mediante exhorto] que declararán sobre la inexistencia de responsabilidad en el accidente.

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

D./Dña. [NOMBRE Y APELLIDOS]

[OPCIONAL — incluir si procede]

. Informe biomecánico respecto al escenario del accidente que evidencia que fue la conducta del/de la denunciante la que determina que se salga de la vía y colisione, sin que hubiera causa eficiente en la conducción del/de la denunciado/a, que circulaba de forma correcta.

Por lo expuesto,

SUPLICO A LA SECCIÓN: que declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a	Firma de Procurador/a

================================================================================
