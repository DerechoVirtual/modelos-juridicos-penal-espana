---
name: tentativa-asesinato-agravantes-parentesco-genero-284
description: "Redacta el escrito «Tentativa de asesinato con agravantes de parentesco y de género: calificación de la defensa» (formulario 284 de violencia de género y delitos en la familia, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Tentativa de asesinato con agravantes de parentesco y de género: calificación de la defensa

> Formulario 0284 del plugin **Violencia de género y delitos en la familia** · revisado el 17-11-2026.

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

- [ ] LOCALIDAD
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] AÑO
- [ ] SEDE
- [ ] NÚMERO
- [ ] LUGAR
- [ ] FECHA
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «…epresentación que tengo acreditada de D.»

## Párrafos opcionales (3)

Inclúyelos solo si encajan en los hechos:

- 1.- La declaración del acusado, que será en último lugar tras la práctica de la prueba.…
- .- Testifical de los siguientes testigos:…
- -D./Dña [NOMBRE Y APELLIDOS]…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 652 de la Ley de Enjuiciamiento Criminal
- art. 22.4 CP
- art. 23 CP
- art. 147.1 CP

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

### Formulario 0284 · Tentativa de asesinato con agravantes de parentesco y de género: calificación de la defensa

- Año del modelo: 2021
- Revisión 17-11-2026: 3 llamadas a nota sin texto retiradas; 1 párrafos repetibles señalados; 2 párrafos opcionales señalados; 9 campos de relleno marcados en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la Audiencia Provincial de [LOCALIDAD]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales, en la representación que tengo acreditada de D. [COMPLETAR], acusado en el procedimiento de sumario ordinario número [Nº DE PROCEDIMIENTO] del año [AÑO] procedente de la Sección de Instrucción del Tribunal de Instancia de [SEDE] plaza nº [NÚMERO] por el supuesto delito del art. 139.1. 1º CP, comparezco ante el órgano judicial y, como mejor proceda en derecho, DIGO:

Que, conforme a lo preceptuado en el artículo 652 de la Ley de Enjuiciamiento Criminal, manifiesto mi disconformidad con los escritos de calificación provisional del Fiscal y de la acusación particular y formulo escrito de calificación con base en las siguientes:

CONCLUSIONES

PRIMERA.- Disconforme con la correlativa del Ministerio Fiscal y del acusador particular.

En primer lugar, mi representado no hizo exactamente lo que se le imputa ya que fue la querellante la que intentó agredir con el mismo cuchillo que se cita en la acusación, que fue arrebatado por el acusado y, en el forcejeo, se clavó en el cuerpo de la víctima en dos ocasiones hasta que ella cedió, al sufrir las heridas. No hubo, pues, un acto inicial de acometimiento doloso con ánimo de matar, sino una legítima defensa.

En segundo lugar, son inciertas las expresiones manifestadas por la acusación en cuanto a que se trataba de un acto de dominación o machismo posesorio del acusado sobre la querellante.

Todo se debió a un arranque inicial agresivo de la querellante, cuando llegó a la casa, por diferencias personales entre ellos, debido al deterioro de la relación, no existiendo ningún ánimo de matar. El hecho de que el cuchillo se haya clavado en las partes del cuerpo que certifican los médicos forenses es circunstancial y derivado del forcejeo, pero no hay acto inicial de agresión ilegítima por el acusado, sino todo lo contrario.

SEGUNDA.- Los hechos no son constitutivos de un delito de asesinato del art. 139.1.1º CP.

TERCERA.- Niego las correlativas. Mi representado no es el autor del delito por el que se procede.

CUARTA.- Disconforme con las correlativas. No concurre agravante alguna, pero en el caso de que se entendiera por el Tribunal que concurre la condena no puede aplicarse la agravante de género, ya que no existe ninguna connotación de carácter subjetivo de dominación o machismo que haga aplicable la agravante del art. 22.4 CP. Si se aplica la de parentesco del art. 23 CP, esta es objetiva y no puede aplicarse también la de género por el mero hecho de tratarse de pareja, ya que vulnera el non bis in idem.

Procede absolver a mi representado con todos los pronunciamientos favorables, sin declaración de responsabilidad civil y, en su defecto, aplicar un delito de lesiones del art. 147.1 CP, sin la agravante de género del art. 22.4 CP.

Por lo expuesto,

SUPLICO A LA SALA:

Que tenga por presentado este escrito con sus copias, los admita y por realizada la calificación.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que para el acto del juicio oral propongo los siguientes:

MEDIOS DE PRUEBA

[OPCIONAL — incluir si procede]

1.- La declaración del acusado, que será en último lugar tras la práctica de la prueba.

[OPCIONAL — incluir si procede]

.- Testifical de los siguientes testigos:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

-D./Dña [NOMBRE Y APELLIDOS]

Por lo expuesto,

SUPLICO A LA SALA: declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a	Firma de Procurador/a

================================================================================
