---
name: promover-internet-autolesion-menores-discapacitados-307
description: "Redacta el escrito «Promover por internet la autolesión de menores o discapacitados: escrito de defensa» (formulario 307 de delitos contra las personas, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Promover por internet la autolesión de menores o discapacitados: escrito de defensa

> Formulario 0307 del plugin **Delitos contra las personas** · revisado el 17-11-2026.

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
- [ ] LUGAR

## Elecciones que hay que hacer

- menores / discapacitados
- menor / discapacitado

## Párrafos opcionales (3)

Inclúyelos solo si encajan en los hechos:

- 1.-La declaración del/de la acusado/a será en último lugar tras la práctica de la prueba.…
- .- Testifical de los siguientes testigos menores de edad,que se practicó como prueba preconstituida y se ruega…
- D/Dña [NOMBRE Y APELLIDOS]…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 156 ter CP
- artículo 784.1 de la Ley de Enjuiciamiento Criminal

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

### Formulario 0307 · Promover por internet la autolesión de menores o discapacitados: escrito de defensa

- Año del modelo: 2021
- Revisión 17-11-2026: 3 llamadas a nota sin texto retiradas; 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 1 desplegables convertidos en elección en blanco; 2 párrafos opcionales señalados; 7 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D/Dña [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales en la representación que tiene acreditada de D/Dña [NOMBRE Y APELLIDOS], acusado/a en las diligencias previas número [Nº DE PROCEDIMIENTO] por el supuesto delito del art. 156 ter CP, comparezco ante el órgano judicial y, como mejor proceda en derecho, DIGO:

Que, conforme a lo preceptuado en el artículo 784.1 de la Ley de Enjuiciamiento Criminal, manifiesto mi disconformidad con los escritos de acusación y formulo escrito de defensa en base a las siguientes:

CONCLUSIONES

PRIMERA.- Disconforme con la correlativa del Ministerio Fiscal y del acusador particular.

Mi representado/a no hizo exactamente lo que se le imputa, ya que los contenidos que se difunden en internet se refieren a un juego on line, pero que no se dirige a fomentar la autolesión. Sí es cierto que hay algunos miembros del juego que caen en algunos lugares o se lesionan, pero sin que ello promueva la autolesión de los jugadores.

La circunstancia de que el/la hijo/a de los denunciantes se haya autolesionado no puede pasarse al "debe" nuestro, por cuanto se trata de una reacción anómala y anormal de esta persona que estará basada en algunos problemas personales que pueda padecer, pero que no pueden achacarse a quienes hemos puesto en marcha este juego on line.

De hecho, la culpa puede estar en los padres por permitir a sus hijos el acceso libre a internet cuando los [ELEGIR: menores / discapacitados] pueden sufrir algún problema personal antecedente que les lleve a realizar conductas como la que en este caso ha llevado a cabo el/la [ELEGIR: menor / discapacitado], pero sin que sea por causa nuestra, de tal manera que si los padres hubieran tenido más control sobre él/ella o le/la hubieran llevado antes a un especialista, los hechos no hubieran ocurrido. Así, no puede trasladarse la responsabilidad a los autores de este juego on line. No hay en el juego ningún dato que pruebe que existe promoción de la autolesión, aunque sí que es cierto que se ha "desatado" una campaña promovida por representantes de otros video juegos que se consideran afectados por el éxito entre los jóvenes del nuestro.

Por ello, no existe evidencia objetiva de que este juego consista en contenidos específicamente destinados a promover, fomentar o incitar a la autolesión de personas menores de edad o personas con discapacidad necesitadas de especial protección.

SEGUNDA.- Los hechos no son constitutivos de un delito del art. 156 ter CP.

TERCERA.- Niego las correlativas. Mi representado/a no es el/la autor/a del delito por el que se procede ni de ningún otro.

CUARTA.- Disconforme con las correlativas. Procede absolver a mi representado/a con todos los pronunciamientos favorables, sin declaración de responsabilidad civil.

Por lo expuesto,

SUPLICO A LA SECCIÓN

Que tenga por presentado este escrito con sus copias, los admita y por realizada la calificación.

Es de Justicia que pido en [LUGAR]

PRIMER OTROSÍ DIGO: Que para el acto del juicio oral propongo los siguientes:

MEDIOS DE PRUEBA

[OPCIONAL — incluir si procede]

1.-La declaración del/de la acusado/a será en último lugar tras la práctica de la prueba.

[OPCIONAL — incluir si procede]

.- Testifical de los siguientes testigos menores de edad,que se practicó como prueba preconstituida y se ruega se reproduzca el día del juicio oral por la vía de los arts. 449 bis, 449 ter, 703 bis y 777.3 LECRIM, que han accedido a este juego y no se han autolesionado:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

D/Dña [NOMBRE Y APELLIDOS]

.- Pericial:

-Pericial de experto en estos videos acerca de la inexistencia de riesgo alguno para la salud de los menores o personas con discapacidad y que se trata de un mero juego on line.
-Pericial de trastornos conductuales de menores hoy en día.

Pericial médica de examen de la menor para acreditar su predisposición a la autolesión.

.- Documental de la puesta en marcha de la distribución del juego on line mediante la aportación de un video del juego que se interesa sea reproducido en el juicio oral.

Por lo expuesto,

SUPLICO A LA SECCIÓN: declare pertinentes las pruebas interesadas y acuerde su práctica.

SEGUNDO OTROSÍ DIGO: Se interesa se alce con urgencia la medida cautelar de cierre de la difusión de los productos por el grave daño que está haciendo a la empresa.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a	Firma de Procurador/a

================================================================================
