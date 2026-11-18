---
name: prueba-preconstituida-menor-discapacitado-acusacion-pide-418
description: "Redacta el escrito «Prueba preconstituida de menor o discapacitado: la acusación pide reproducirla en juicio» (formulario 418 de víctimas y justicia restaurativa, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Prueba preconstituida de menor o discapacitado: la acusación pide reproducirla en juicio

> Formulario 0418 del plugin **Víctimas y justicia restaurativa** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (5 veces)
- [ ] COLEGIO
- [ ] LOCALIDAD
- [ ] ACTO O RESOLUCIÓN
- [ ] DELITO (3 veces)
- [ ] PENA
- [ ] IMPORTE
- [ ] LUGAR
- [ ] FECHA
- [ ] Otros 5 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…n las siguientes: CONCLUSIONES PRIMERA.-»; «…Es responsable del delito en concepto de»; «…INTA.- Procede imponer a el/la acusado/a»; «…del/de la menor/discapacitado/a»; «…cial. Informe de los psicólogos forenses»

## Elecciones que hay que hacer

- la madre / el padre

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 780.1 de la Ley de Enjuiciamiento Criminal
- art. 781 LECRIM
- art. 780 LECRIM
- art. 650 LECRIM
- art. 20 y 21 CP
- art. 703 bis, 730.2 y 788 LECRIM
- art. 449 ter LECRIM
- art. 777.2 LECRIM

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

### Formulario 0418 · Prueba preconstituida de menor o discapacitado: la acusación pide reproducirla en juicio

- Año del modelo: 2020
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (1); 1 desplegables y casillas convertidos en elección en blanco; 20 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la acusación particular presenta sus conclusiones provisionales y solicita pruebas para practicar en el juicio oral, entre ellas que se reproduzca en el juicio oral la declaración de un menor de 14 años, hecha en la instrucción como prueba preconstituida, para evitar la victimización secundaria, conforme a los arts. 449 ter, 703 bis y 730 LECRIM.

Actualizado conforme a la LO 8/2021, con entrada en vigor a partir del 25 de junio de 2021.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los tribunales del Ilustre colegio de procuradores de [COLEGIO] y con despacho profesional abierto en [LOCALIDAD], en representación del acusador particular D./Dña. [NOMBRE Y APELLIDOS], comparezco ante este órgano judicial y como mejor proceda en derecho, DIGO:

En aplicación del artículo 780.1 de la Ley de Enjuiciamiento Criminal, mediante el presente escrito formulo solicitud en plazo de apertura de juicio oral ante la Sección de lo Penal del Tribunal de Instancia por la vía del art. 781 LECRIM y de acusación por la vía del art. 780 LECRIM, en relación con el art. 650 LECRIM, contra [ACTO O RESOLUCIÓN] con base en las siguientes:

CONCLUSIONES

PRIMERA.- [COMPLETAR]

SEGUNDA.- Tales hechos son constitutivos del delito de [DELITO] del art. CP

TERCERA.- Es responsable del delito en concepto de [COMPLETAR] el/la acusado/a.

CUARTA.- No concurre con respecto a el/la acusado/a circunstancias agravantes ni atenuantes genéricas del art. 20 y 21 CP.

QUINTA.- Procede imponer a el/la acusado/a [COMPLETAR] por el delito del art. CP la pena de [PENA].

Como responsabilidad civil se postula se abone la suma de [IMPORTE] euros por los daños morales y perjuicios sufridos.

Las costas deberán ser satisfechas por el/la acusado/a.

Por lo expuesto,

SUPLICO A LA SECCIÓN

Que tenga por presentado este escrito, lo admita y tenga por realizado el trámite de traslado para acusación.

Es de Justicia que pido en [LUGAR]

OTROSÍ DIGO: Que para el juicio oral intereso la práctica de los siguientes:

MEDIOS DE PRUEBA

Los propuestos por el Ministerio Fiscal y además los siguientes:

1.- Interrogatorio de el/la acusado/a.
2.- Testifical:

Testifical de [ELEGIR: la madre / el padre] del/de la menor/discapacitado/a [COMPLETAR],

D./Dña. [NOMBRE Y APELLIDOS]

3.- Documental: Informe elaborado por médico y psicólogo en relación a la afectación del/de la menor/discapacitado/a por los hechos de los que ha sido víctima que evidenció la necesidad de que en fecha [FECHA] se procediera a la declaración del/de la menor/discapacitado/a en fase de instrucción como prueba preconstituida ante expertos y garantizando la debida contradicción, y la grabación de esta declaración para la reproducción en el juicio oral como desarrollo de la práctica de la prueba en el plenario.

Documental: Reproducción en el plenario de la grabación efectuada de la declaración del/de la menor de 14 años/discapacitado/a garantizando la contradicción.

La "victimización secundaria" que conllevan los delitos [DELITO] de los menores determina que exigen y requieren de la adopción de medidas excepcionales, como la que en este escrito se interesa y que no atentan en ninguna medida contra los principios de concentración de pruebas en el juicio oral, ya que la prueba realizada con todas las garantías se reproduce en el plenario y se respetan igualmente los principios de inmediación, contradicción y publicidad. (1)

No se debe exigir en modo alguno la comparecencia del/de la menor/discapacitado/a en el juicio oral para el caso de que lo proponga la defensa.

Conforme me permite el art. 703 bis, 730.2 y 788 LECRIM, solicito que la declaración del/de la menor/discapacitado/a que fue grabada como prueba preconstituida y se guardó para su conservación conforme a los arts. 449 bis y 449 ter LECRIM, sea reproducida en sede de plenario, sin que sea necesaria la presencia del testigo en la vista. Todo ello al tratarse de un delito de [DELITO] contemplado en el art. 449 ter LECRIM cuya víctima es un menor de 14 años/discapacitado/a.

4.- Pericial judicial. Informe de los psicólogos forenses [COMPLETAR] sobre credibilidad de el/la menor.

Por todo lo expuesto,

SUPLICO A LA SECCIÓN: que declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a	Firma de Procurador/a
D./Dña. [NOMBRE Y APELLIDOS] 	D./Dña. [NOMBRE Y APELLIDOS]

NOTAS DEL FORMULARIO

(1) La STS 579/2019 de 26 de noviembre de 2019, Rec. 2104/2018 recoge los criterios o principios para que se pueda proceder a la reproducción en juicio oral de la prueba preconstituida de las declaraciones de los menores en el juicio oral.

Lo mismo se reitera en la STS 321/2020 de 17 de junio y se incide en que el Tribunal valorará, a la vista de los informes sobre el estado de la víctima, si la exigencia de que asista al juicio oral puede ser perjudicial para ella procediéndose a la reproducción de la declaración efectuada como prueba preconstituida (art. 777.2 LECRIM)

================================================================================
