---
name: promover-internet-suicidio-menores-discapacitados-314
description: "Redacta el escrito «Promover por internet el suicidio de menores o discapacitados: escrito de acusación» (formulario 314 de delitos contra las personas, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Promover por internet el suicidio de menores o discapacitados: escrito de acusación

> Formulario 0314 del plugin **Delitos contra las personas** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] COLEGIO
- [ ] LOCALIDAD
- [ ] CIRCUNSTANCIA
- [ ] PENA
- [ ] IMPORTE
- [ ] LUGAR
- [ ] Otros 4 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…página web que ha creado el/la acusado/a»; «…siguientes expresiones que transcribimos»; «…de mis mandantes visita con frecuencia»; «… objeto de acusación y los contenidos de»

## Elecciones que hay que hacer

- menor de edad / discapacitado/a
- menor / discapacitado/a

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS
- ELEGIR UNA OPCIÓN Y REDACTARLA: Si se adoptaron medidas cautelares / Si se reitera la petición de medidas cautelares no acordadas — el texto de cada opción no venía en el formulario original

## Párrafos opcionales (5)

Inclúyelos solo si encajan en los hechos:

- 1.- Declaración del/de la acusado/a.…
- .- Declaración de los denunciantes.…
- .- Testifical:…
- .- Pericial…
- .- Documental:…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 780.1 de la Ley de Enjuiciamiento Criminal
- art. 781 LECRIM
- art. 780 LECRIM
- art. 650 LECRIM
- art. 143 bis CP
- art. 22 del CP
- art. 189 bis CP

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

### Formulario 0314 · Promover por internet el suicidio de menores o discapacitados: escrito de acusación

- Año del modelo: 2021
- Revisión 17-11-2026: 2 llamadas a nota sin texto retiradas; 2 desplegables y casillas convertidos en elección en blanco; 1 desplegables convertidos en elección en blanco; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 1 bloques de alternativas señalados; 5 párrafos opcionales señalados; 13 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 1 huecos del original que se habían perdido sin marca, marcados (NOMBRE Y APELLIDOS)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los tribunales del Ilustre colegio de procuradores de [COLEGIO] y con despacho profesional abierto en [LOCALIDAD], en representación de los acusadores particulares D. y Dña. [NOMBRE Y APELLIDOS], comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

En aplicación del artículo 780.1 de la Ley de Enjuiciamiento Criminal, mediante el presente escrito formulo en plazo solicitud de apertura de juicio oral ante la Sección de lo Penal del Tribunal de Instancia por la vía del art. 781 LECRIM y escrito de acusación por la vía del art. 780 LECRIM, en relación con el art. 650 LECRIM, contra D./Dña. [NOMBRE Y APELLIDOS], con base en las siguientes:

CONCLUSIONES

PRIMERA.- En la página web que ha creado el/la acusado/a [COMPLETAR] ha subido contenidos claros y tendenciosos dirigidos a fomentar o incitar al suicidio de personas menores de edad o con discapacidad necesitadas de especial protección, como consta en las siguientes expresiones que transcribimos [COMPLETAR].

Este método conlleva un grave peligro al dirigirse a personas con problemas de autoestima y con claros déficits personales que pueden llevar a que quien los lea pueda aceptar las instrucciones, consejos o directrices que se indican y acabar con su vida.

En el caso del/de la hijo/a [ELEGIR: menor de edad / discapacitado/a] de mis mandantes visita con frecuencia [COMPLETAR] e incluso de las conversaciones existentes se detecta el riesgo de que pueda cometer el acto del suicidio, que es el que promueve e incita el/la acusado/a por la alta influencia que está ejerciendo sobre el/la [ELEGIR: menor / discapacitado/a] y el elevado riesgo de que pueda llevar a cabo dicha conducta.

SEGUNDA.- Tales hechos son constitutivos del delito del art. 143 bis CP.

TERCERA.- Es responsable del delito en concepto de autor/a el/la acusado/a.

CUARTA.-

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

No concurren en el/la acusado/a circunstancias agravantes.

Concurre en el/la acusado/a la circunstancia agravante de [CIRCUNSTANCIA] del art. 22 del CP.

QUINTA.- Procede imponer al/a la acusado/a por el delito del art. 143 bis CP la pena de [PENA].

Se impondrá, además, la pena de alejamiento de la víctima y de sus familiares con prohibición de acercarse a menos de 500 metros y de prohibición de comunicación por cualquier medio, incluidos los tecnológicos.

Asimismo, se impondrá, en base al párrafo 2º del art. 189 bis CP, la retirada de los contenidos distribuidos por internet y redes sociales por el/la acusado/a, la interrupción de los servicios que ofrezcan predominantemente dichos contenidos o el bloqueo de unos y otros cuando radiquen en el extranjero.

SEXTA.- El importe de la responsabilidad civil por daño moral es de [IMPORTE] euros.

Las costas deberán ser satisfechas por el/la acusado/a.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita y tenga por realizado el trámite de traslado para acusación.

Es de Justicia que pido en [LUGAR]

OTROSÍ DIGO: Que para el juicio oral intereso la práctica de los siguientes:

MEDIOS DE PRUEBA

Los propuestos por el Ministerio Fiscal y además los siguientes:

[OPCIONAL — incluir si procede]

1.- Declaración del/de la acusado/a.

[OPCIONAL — incluir si procede]

.- Declaración de los denunciantes.

[OPCIONAL — incluir si procede]

.- Testifical:

-Declaración del/de la [ELEGIR: menor / discapacitado/a] que será grabada como prueba preconstituida para ser reproducida el día del juicio oral por la vía de los arts. 449 bis, 449 ter, 703 bis y 777.3 LECRIM, así como de los siguientes menores que también han seguido los comentarios del/de la acusado/a.
-Testifical de los agentes de las Fuerzas y cuerpos de seguridad que llevaron a cabo la investigación respecto al ordenador desde el que accedió el acusado:
-Testifical de los siguientes testigos mayores de edad que han visualizado los mensajes tendentes a llevar a cabo las víctimas las conductas descritas en el art. 143 bis CP.

[OPCIONAL — incluir si procede]

.- Pericial

-Pericial psicológica de la situación de ansiedad y depresión provocada en el/la menor por visualizar los contenidos de internet.

[OPCIONAL — incluir si procede]

.- Documental:

Acta notarial del Notario D./Dña. [NOMBRE Y APELLIDOS] del Ilustre colegio de que ha redactado la misma en atención a haber comprobado personalmente los hechos que son objeto de acusación y los contenidos de [COMPLETAR], durante los siguientes días.

Por todo lo expuesto,

SUPLICO A LA SECCIÓN: que declare pertinentes las pruebas interesadas y acuerde su práctica

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si se adoptaron medidas cautelares / Si se reitera la petición de medidas cautelares no acordadas — el texto de cada opción no venía en el formulario original]

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a	Firma de Procurador/a

================================================================================
