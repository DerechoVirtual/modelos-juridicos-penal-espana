---
name: mediacion-penal-acuerdo-cambio-calificacion-juridica-732
description: "Redacta el escrito «Mediación penal: acuerdo con cambio de calificación jurídica de los hechos» (formulario 732 de víctimas y justicia restaurativa, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Mediación penal: acuerdo con cambio de calificación jurídica de los hechos

> Formulario 0732 del plugin **Víctimas y justicia restaurativa** · revisado el 17-11-2026.

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

- [ ] Nº DE PROCEDIMIENTO (2 veces)
- [ ] AÑO (2 veces)
- [ ] SEDE (3 veces)
- [ ] NÚMERO (3 veces)
- [ ] NOMBRE Y APELLIDOS (11 veces)
- [ ] DNI/NIE (2 veces)
- [ ] IMPORTE
- [ ] DELITO
- [ ] LUGAR
- [ ] FECHA
- [ ] Otros 4 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…, del artículo»; «…adas, por el Servicio de Mediación Penal»; «…al distinto del contenido en el artículo»; «…mediados Firma del mediador LOS MEDIADOS»

## Normas que cita el formulario

No cita artículos concretos. Si añades alguno, compruébalo con `buscar_articulo`.

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

### Formulario 0732 · Mediación penal: acuerdo con cambio de calificación jurídica de los hechos

- Año del modelo: 2017
- Revisión 17-11-2026: 26 campos de relleno marcados en blanco; 2 huecos del original que se habían perdido sin marca, marcados (Nº DE PROCEDIMIENTO)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Acuerdo de mediación penal al que se llega por parte de la acusación y la defensa y en el que la acusación accede a modificar la calificación jurídica de los hechos objeto de procedimiento penal, que ha quedado en suspenso mientras se sigue el trámite de la mediación.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

Reunidos en el Servicio de Mediación Penal, los interesados en el presente Expediente de Mediación Nº [Nº DE PROCEDIMIENTO]/[AÑO], derivado del Juicio Oral Nº [Nº DE PROCEDIMIENTO]/[AÑO] de la Sección de lo Penal del Tribunal de Instancia de [SEDE] plaza nº [NÚMERO], por una parte la parte denunciante D./Dña. [NOMBRE Y APELLIDOS], con DNI [DNI/NIE], y por la otra la parte denunciada D./Dña. [NOMBRE Y APELLIDOS], con DNI [DNI/NIE], con carácter previo a la concreción del Acuerdo al que han llegado en este proceso de mediación, ambas partes afirman expresamente que son ciertos los siguientes

EXTREMOS

1º) Que en el presente procedimiento de mediación han podido expresarse libremente, transmitiendo a los mediadores sus pretensiones, sobre los hechos objeto del procedimiento, y sobre el trámite judicial seguido hasta el momento.

2º) Que han sido informados de la sistemática del proceso de mediación, de los derechos que les asisten y de las consecuencias que podrían tener lugar en el supuesto de llegar a un acuerdo, como de no poder llevarse el mismo a cabo.

3º) Que la intervención del mediador les ha facilitado la libre expresión de sus emociones y sentimientos, con referencia a la globalidad de la situación procesal y personal compartida, que, en cada caso, han experimentado respecto de los hechos objeto del procedimiento, y sobre el trámite judicial seguido hasta el momento.

4º) Que los mediadores se han conducido con imparcialidad, neutralidad y objetividad, señalando los puntos en conflicto, y procurando acercar las distintas sensibilidades y posturas respecto de la discrepancia que les ha llevado al marco de un proceso penal, con la finalidad primordial de lograr un acuerdo reparador que satisfaga las pretensiones conjuntas de las partes.

5º) Que los mediadores les han indicado la posibilidad de consultar el contenido del presente acuerdo con sus respectivos letrados acreditados en el procedimiento de origen, ofreciéndose a comunicar directamente con ellos para aclarar cualquier duda o aspecto relacionado con el mismo.

Verificado lo cual, por mutuo consenso, manifiestan haber llegado libre y voluntariamente, al siguiente

ACUERDO

1º) Que D./Dña. [NOMBRE Y APELLIDOS] se muestra, respecto del contenido del presente acuerdo, satisfecha y moralmente reparada, no deseando que a D./Dña. [NOMBRE Y APELLIDOS] se le deriven más consecuencias penales como resultado del procedimiento seguido en la Sección de lo Penal del Tribunal de Instancia de [SEDE] plaza nº [NÚMERO] contra el mismo.

2º) Que D./Dña. [NOMBRE Y APELLIDOS] manifiesta expresamente que asume la responsabilidad personal y penal que le pueda corresponder como consecuencia de sus acciones, lamentando los perjuicios ocasionados a la denunciante, y accediendo con ello a reparar moralmente a

D./Dña. [NOMBRE Y APELLIDOS], y del mismo modo a reparar económicamente, en concepto de responsabilidad civil, a la denunciante.

3º) Que, por ello, y en concepto de responsabilidad civil derivada del procedimiento penal de origen, con renuncia a cualquier otro concepto, las partes acuerdan expresamente que D./Dña. [NOMBRE Y APELLIDOS] abone a D./Dña. [NOMBRE Y APELLIDOS] la cantidad de [IMPORTE] euros, más el importe de las costas procesales correspondientes a la representación y defensa en este procedimiento del denunciante.

4º) Que por la Acusación Particular ejercida por la representación de D./Dña. [NOMBRE Y APELLIDOS] se accede a modificar la calificación jurídica de los hechos objeto del procedimiento penal, entendiendo que los mismos, de forma alternativa pueden ser calificados como un delito de [DELITO], del artículo [COMPLETAR] del CP.

A la vista del ACUERDO conseguido, en base a la Disposición adicional 9.8 LECRIM el Equipo de Mediación hace una valoración global muy positiva de la actitud de los mediados y del Acuerdo al que, de forma libre y consciente, han llegado, no solo por ser un medio que facilita la reparación material de la denunciante, sino porque, además, puede posibilitar la resolución pacífica del conflicto interpersonal que separa a los mediados como consecuencia de los hechos denunciados.

Dado el Acuerdo alcanzado entre las partes en el presente procedimiento de Mediación, así como las pretensiones aducidas por las respectivas letradas, por el Servicio de Mediación Penal [COMPLETAR] se sugiere que por el/la Ilustrísimo/a Sr./Sra. Fiscal y por el/la propio/a Ilmo/a Sr./Sra. Magistrado/a-Juez de lo Penal, con los/las Sres./Sras. Letrados/as de la defensa y de la acusación particular, se estudie la posibilidad de calificar jurídicamente, de forma alternativa, los hechos objeto de Acusación en el procedimiento penal, con un tipo penal distinto del contenido en el artículo [COMPLETAR] CP.

Por todo ello, el Equipo de Mediación pone en conocimiento del Ministerio Fiscal y de la Sección de lo Penal del Tribunal de Instancia de [SEDE] plaza nº [NÚMERO] que D./Dña. [NOMBRE Y APELLIDOS] ha sido informado de la posibilidad de que puedan serle aplicados, conforme a la legalidad vigente y bajo superior criterio de la autoridad competente, los beneficios legales asociados a la apreciación en sentencia de la aplicación, en la ejecutoria penal correspondiente, de los mecanismos de suspensión o sustitución de la pena; en cuya virtud, el mediador, comunica que D./Dña. [NOMBRE Y APELLIDOS] muestra preferencia por que la responsabilidad penal que le pudiera corresponder en Sentencia, quedara en suspenso, conforme a los artículos 80 y ss. del CP, valorándose a tal fin el abono del pago de la responsabilidad civil a la que se compromete en el presente ACUERDO, a la firma del mismo.

En prueba de su conformidad con todo lo reseñado, firman ambas partes el presente acuerdo en [LUGAR], a [FECHA].

Firma de los mediados	Firma del mediador

LOS MEDIADOS [COMPLETAR]

EL MEDIADOR

================================================================================
