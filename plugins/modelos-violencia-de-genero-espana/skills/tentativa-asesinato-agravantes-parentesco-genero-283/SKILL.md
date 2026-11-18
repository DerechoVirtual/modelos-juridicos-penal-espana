---
name: tentativa-asesinato-agravantes-parentesco-genero-283
description: "Redacta el escrito «Tentativa de asesinato con agravantes de parentesco y de género: calificación de la acusación» (formulario 283 de violencia de género y delitos en la familia, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Tentativa de asesinato con agravantes de parentesco y de género: calificación de la acusación

> Formulario 0283 del plugin **Violencia de género y delitos en la familia** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (6 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] SEDE
- [ ] NÚMERO
- [ ] FECHA (2 veces)
- [ ] NOMBRE DEL REPRESENTADO/A
- [ ] Nº (2 veces)
- [ ] PENA
- [ ] IMPORTE (2 veces)
- [ ] LUGAR
- [ ] Otros 5 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…entes: CONCLUSIONES PRIMERA.- El acusado»; «…ra hacer nada para evitarlo y defenderse»; «…re de un vecino, donde salió en su ayuda»; «…como secuelas las de»; «….- Testifical: -Declaración de»

## Elecciones que hay que hacer

- casado / convivendo

## Párrafos opcionales (3)

Inclúyelos solo si encajan en los hechos:

- 1.- Interrogatorio del acusado que declarará en último lugar, tras la práctica de la prueba.…
- .- Testifical:…
- .-Pericial de D./Dña [NOMBRE Y APELLIDOS] y D./Dña. sobre las lesiones sufridas e intención de matar.…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 651 LECr
- artículo 16 CP
- art. 23 CP
- art. 22.4 CP
- art. 544 bis LECRIM
- art. 57 CP

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

### Formulario 0283 · Tentativa de asesinato con agravantes de parentesco y de género: calificación de la acusación

- Año del modelo: 2021
- Revisión 17-11-2026: 2 llamadas a nota sin texto retiradas; 1 desplegables y casillas convertidos en elección en blanco; 3 párrafos opcionales señalados; 22 campos de relleno marcados en blanco; 1 huecos del original que se habían perdido sin marca, marcados (NOMBRE Y APELLIDOS)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la Audiencia Provincial de [LOCALIDAD]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales, actuando en representación de D./Dña. [NOMBRE Y APELLIDOS], acusador particular, según consta acreditado en el Procedimiento sumario ordinario nº [Nº DE PROCEDIMIENTO] procedente de la Sección de Instrucción del Tribunal de Instancia de [SEDE] plaza nº [NÚMERO], comparezco ante la sala y como proceda en Derecho DIGO:

En aplicación del artículo 651 LECr y concordantes formulo escrito de calificación, con base en las siguientes:

CONCLUSIONES

PRIMERA.- El acusado [COMPLETAR], el día [FECHA] estaba esperando a que llegara a casa de trabajar mi representada [NOMBRE DEL REPRESENTADO/A], con la que lleva [ELEGIR: casado / convivendo] años, cuando sobre las [Nº] horas apareció y, de modo sorpresivo, sin que pudiera hacer nada para evitarlo y defenderse [COMPLETAR] le asestó una puñalada en el cuello con un cuchillo de cocina de 15 cm y acto seguido otra en el estómago, todo ello con la intención de causarle la muerte, porque lo hizo en órganos y zonas donde sabía que acabaría con su vida, al tiempo que le decía:

"¡Te dije que no quería verte con tu compañero de trabajo! ¡Eres una zorra porque me engañas! ¡Eres solo mía y de nadie más y, como no quieres quedarte en casa para atenderme y obdecerme, es por lo que te mato!"

Sin embargo, mi representada le dio un fuerte empujón al acusado, abrió rápidamente la puerta de la calle y bajó como pudo las escaleras. Tocó el timbre de un vecino, donde salió en su ayuda [COMPLETAR], quien llamó a una ambulancia que, a los pocos minutos, le llevó al hospital, aún con vida, donde pudieron salvarle la vida.

De tales hechos le han quedado a Dña. [NOMBRE Y APELLIDOS] como secuelas las de [COMPLETAR], estando incapacitada [Nº]. días.

SEGUNDA.- Tales hechos son constitutivos de un delito de asesinato del artículo 139.1.1º CP, en grado de tentativa conforme al artículo 16 CP.

TERCERA.- Es responsable del delito en concepto de autor el acusado.

CUARTA.- Concurren las circunstancias agravantes de parentesco del art. 23 CP y de género del art. 22.4 CP.

QUINTA.- Procede imponer al acusado por el delito del art. 139.1.1º CP en grado de tentativa la pena de [PENA]

Se impondrá, además, la pena de alejamiento a la víctima y sus familiares con prohibición de acercarse a menos de 500 metros y de comunicación por cualquier medio incluidos los tecnológicos.

SEXTA.- Como responsabilidad civil a indemnizar a mi mandante se postula se abone por los perjuicios causados por daño físico [IMPORTE] euros y moral de [IMPORTE] euros.

Las costas deberán ser satisfechas por el acusado.

Por lo expuesto,

SUPLICO A LA SALA:

Que tenga por presentado este escrito, lo admita y tenga por realizado el trámite de calificación.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que para el juicio oral intereso la práctica de los siguientes:

MEDIOS DE PRUEBA

[OPCIONAL — incluir si procede]

1.- Interrogatorio del acusado que declarará en último lugar, tras la práctica de la prueba.

[OPCIONAL — incluir si procede]

.- Testifical:

-Declaración de [COMPLETAR] vecino que auxilió a la querellante.
-D./Dña [NOMBRE Y APELLIDOS] y D./Dña. [NOMBRE Y APELLIDOS] agentes de las Fuerzas y Cuerpos de Seguridad del Estado que comparecieron en los hechos requerida su presencia por el/la vecino/a que ayudó.

[OPCIONAL — incluir si procede]

.-Pericial de D./Dña [NOMBRE Y APELLIDOS] y D./Dña. sobre las lesiones sufridas e intención de matar.

Por lo expuesto.

SUPLICO A LA SALA: que declare pertinentes las pruebas interesadas y acuerde su práctica.

SEGUNDO OTROSÍ DIGO: se interesa que, en base al art. 544 bis LECRIM, dado que el delito denunciado está entre los incluidos en el art. 57 CP, se dicte una orden de alejamiento que le impida acercarse a la víctima y sus familiares a menos de 500 metros, así como, sobre todo, una orden de prohibición de comunicación por cualquier tipo de medio, y que se adopten las medidas cautelares necesarias para asegurar las responsabilidades civiles y las costas.

SUPLICO A LA SALA: que adopte las medidas cautelares interesadas.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a	Firma de Procurador/a

================================================================================
