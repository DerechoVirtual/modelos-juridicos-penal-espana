---
name: promover-internet-autolesion-menores-discapacitados-304
description: "Redacta el escrito «Promover por internet la autolesión de menores o discapacitados: escrito de acusación» (formulario 304 de delitos contra las personas, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Promover por internet la autolesión de menores o discapacitados: escrito de acusación

> Formulario 0304 del plugin **Delitos contra las personas** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (6 veces)
- [ ] COLEGIO
- [ ] LOCALIDAD
- [ ] CIRCUNSTANCIA
- [ ] PENA
- [ ] IMPORTE (2 veces)
- [ ] LUGAR
- [ ] Otros 8 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…y Dª»; «…n tiempo está accediendo a la página web»; «…del "jugador" on line, concretamente por»; «…que promueven ha tenido resultado porque»; «…ondene, de igual modo, al/a la acusado/a»; «…e comunicación con respecto a la víctima»; «…s mayores de edad que conocen los hechos»; «…mprobado personalmente los contenidos de»

## Elecciones que hay que hacer

- menor de edad / discapacitado/a
- menor / discapacitado/a

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS
- ELEGIR UNA OPCIÓN Y REDACTARLA: Si se adoptaron medidas cautelares / Si se reitera la petición de medidas cautelares no acordadas — el texto de cada opción no venía en el formulario original

## Párrafos opcionales (4)

Inclúyelos solo si encajan en los hechos:

- 1.- Interrogatorio de los/las acusados/as, que declararán en último lugar tras la práctica de la prueba.…
- .- Testifical:…
- .- Pericial…
- .- Documental:…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 780.1 de la Ley de Enjuiciamiento Criminal
- art. 781 LECRIM
- art. 780 LECRIM
- art. 650 LECRIM
- art. 156 ter CP
- art. 22 del CP

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

### Formulario 0304 · Promover por internet la autolesión de menores o discapacitados: escrito de acusación

- Año del modelo: 2021
- Revisión 17-11-2026: 2 llamadas a nota sin texto retiradas; 2 desplegables y casillas convertidos en elección en blanco; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 1 bloques de alternativas señalados; 4 párrafos opcionales señalados; 22 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 1 huecos del original que se habían perdido sin marca, marcados (NOMBRE Y APELLIDOS)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los tribunales del Ilustre colegio de procuradores de [COLEGIO] y con despacho profesional abierto en [LOCALIDAD], en representación de los acusadores particulares D. y Dña. [NOMBRE Y APELLIDOS], comparezco ante el órgano judicial y, como mejor proceda en derecho, DIGO:

En aplicación del artículo 780.1 de la Ley de Enjuiciamiento Criminal, mediante el presente escrito formulo en plazo solicitud de apertura de juicio oral ante la Sección de lo Penal del Tribunal de Instancia por la vía del art. 781 LECRIM y escrito de acusación por la vía del art. 780 LECRIM, en relación con el art. 650 LECRIM, contra D./Dña. [NOMBRE Y APELLIDOS], con base en las siguientes:

CONCLUSIONES

PRIMERA.- D.. [NOMBRE Y APELLIDOS] y Dª [COMPLETAR] son los padres de [ELEGIR: menor de edad / discapacitado/a], la cual desde hace un tiempo está accediendo a la página web [COMPLETAR], con amplia difusión, en la que se publicitan contenidos dirigidos a incitar la autolesión de menores y/o personas en situación de sufrir alguna discapacidad y que no tengan el conocimiento suficiente para evitar acceder a llevar a cabo lo que se fomenta en los videos. Estos contenidos aparecen como un juego en virtud del cual se consiguen puntos por realizar autolesiones en el cuerpo del "jugador" on line, concretamente por [COMPLETAR]. De hecho, la eficacia del juego que promueven ha tenido resultado porque [COMPLETAR] se ha provocado ya lesiones por las que tuvo que acudir al hospital, reconociendo a su madre que se las había hecho él/ella misma participando en el juego descrito.

SEGUNDA.- Tales hechos son constitutivos del delito del art. 156 ter CP.

TERCERA.- Es responsable del delito en concepto de autor/a el/la acusado/a.

CUARTA.-

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

No concurren en el/la acusado/a circunstancias agravantes.

Concurre en el/la acusado/a la circunstancia agravante de [CIRCUNSTANCIA] del art. 22 del CP.

QUINTA.- Procede imponer al/a la acusado/a por el delito del art. 156 ter CP la pena de [PENA].

Se condene, de igual modo, al/a la acusado/a [COMPLETAR] a la pena de alejamiento para no acercarse a menos de 500 metros y prohibición de comunicación con respecto a la víctima [COMPLETAR] y sus familiares.

También que se acuerde en sentencia la retirada definitiva de los contenidos difundidos, la interrupción de los servicios que ofrezcan predominantemente dichos contenidos o el bloqueo de unos y otros cuando radiquen en el extranjero, conforme al art. 156 ter CP, párrafo 2º.

SEXTA.- El importe de la responsabilidad civil por daño físico es de [IMPORTE] euros y por daño moral es de [IMPORTE] euros.

Las costas deberán ser satisfechas por el/la acusado/a.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita y tenga por realizado el trámite de traslado para acusación.

Es de Justicia que pido en [LUGAR]

OTROSÍ DIGO: Que para el juicio oral intereso la práctica de los siguientes:

MEDIOS DE PRUEBA

Los propuestos por el Ministerio Fiscal y además los siguientes:

[OPCIONAL — incluir si procede]

1.- Interrogatorio de los/las acusados/as, que declararán en último lugar tras la práctica de la prueba.

[OPCIONAL — incluir si procede]

.- Testifical:

-Reproducción en el plenario de la grabación de la prueba preconstituida de la declaración del/de la [ELEGIR: menor / discapacitado/a] víctima y de los testigos menores conocedores de los hechos:
-Testifical de los agentes de las Fuerzas y Cuerpos de seguridad que llevaron a cabo la investigación respecto al ordenador desde el que el acusado envió las informaciones:
-Testifical de los siguientes testigos mayores de edad que conocen los hechos [COMPLETAR]

[OPCIONAL — incluir si procede]

.- Pericial

- Pericial psicológica de la situación de ansiedad y depresión provocada en la víctima por el visionado de estos contenidos.

-Pericial del médico forense D/Dña. [NOMBRE Y APELLIDOS] acerca de las lesiones causadas.

[OPCIONAL — incluir si procede]

.- Documental:

Acta notarial del Notario D/Dña. [NOMBRE Y APELLIDOS] del Ilustre colegio de que ha redactado la misma en atención a haber comprobado personalmente los contenidos de [COMPLETAR], durante los siguientes días.

Por todo lo expuesto,

SUPLICO A LA SECCIÓN: que declare pertinentes las pruebas interesadas y acuerde su práctica.

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si se adoptaron medidas cautelares / Si se reitera la petición de medidas cautelares no acordadas — el texto de cada opción no venía en el formulario original]

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a	Firma de Procurador/a

================================================================================
