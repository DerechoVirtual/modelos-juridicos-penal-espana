---
name: mediacion-penal-acuerdo-hurto-familiar-731
description: "Redacta el escrito «Mediación penal: acuerdo por hurto a un familiar» (formulario 731 de víctimas y justicia restaurativa, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Mediación penal: acuerdo por hurto a un familiar

> Formulario 0731 del plugin **Víctimas y justicia restaurativa** · revisado el 17-11-2026.

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
- [ ] SEDE (5 veces)
- [ ] NÚMERO (6 veces)
- [ ] NOMBRE Y APELLIDOS (16 veces)
- [ ] DNI/NIE (2 veces)
- [ ] CALLE
- [ ] IMPORTE (5 veces)
- [ ] Nº
- [ ] NÚMERO DE LA CALLE
- [ ] LUGAR
- [ ] FECHA
- [ ] Otros 9 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…nte ACUERDO 1º) Que, a partir del mes de»; «…de»; «…tiene en la entidad bancaria»; «…nº [NÚMERO], de la localidad de»; «…iliar con el/la denunciante, de quien es»; «…o de pensión 1.- Que a partir del mes de»; «…de cuenta»; «…ro tipo como resultado del procedimiento»; «…A la vista del ACUERDO conseguido:»

## Párrafos opcionales (1)

Inclúyelos solo si encajan en los hechos:

- Opción en caso de impago de pensión…

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

### Formulario 0731 · Mediación penal: acuerdo por hurto a un familiar

- Año del modelo: 2017
- Revisión 17-11-2026: 1 párrafos opcionales señalados; 45 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco; 3 huecos del original que se habían perdido sin marca, marcados (Nº DE PROCEDIMIENTO, NÚMERO DE LA CALLE)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Acuerdo de mediación penal al que se llega entre la acusación y la defensa en un procedimiento penal por delito de hurto a un familiar, suspendido mientras se tramita el expediente de mediación.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

Reunidos en el Servicio de Mediación Penal, los interesados en el presente Expediente de Mediación Nº [Nº DE PROCEDIMIENTO]/[AÑO], derivado del Juicio Oral Nº [Nº DE PROCEDIMIENTO]/[AÑO] de la Sección de lo Penal del Tribunal de Instancia de [SEDE] plaza nº [NÚMERO], por una parte la parte denunciante D./Dña. [NOMBRE Y APELLIDOS], con DNI [DNI/NIE], y por la otra la parte denunciada D./Dña. [NOMBRE Y APELLIDOS], con DNI [DNI/NIE], con carácter previo a la concreción del Acuerdo al que han llegado en este proceso de mediación, en base a la Disposición Adicional 9.8 LECRIM, ambas partes afirman expresamente que son ciertos los siguientes

EXTREMOS

1º) Que en el presente procedimiento de mediación han podido expresarse libremente, transmitiendo a los mediadores sus pretensiones, sobre los hechos objeto del procedimiento, y sobre el trámite judicial seguido hasta el momento.

2º) Que han sido informados de la sistemática del proceso de mediación, de los derechos que les asisten y de las consecuencias que podrían tener lugar en el supuesto de llegar a un acuerdo, como de no poder llevarse el mismo a cabo.

3º) Que la intervención del mediador les ha facilitado la libre expresión de sus emociones y sentimientos, con referencia a la globalidad de la situación procesal y personal compartida, que, en cada caso, han experimentado respecto de los hechos objeto del procedimiento, y sobre el trámite judicial seguido hasta el momento.

4º) Que los mediadores se han conducido con imparcialidad, neutralidad y objetividad, señalando los puntos en conflicto, y procurando acercar las distintas sensibilidades y posturas respecto de la discrepancia que les ha llevado al marco de un proceso penal, con la finalidad primordial de lograr un acuerdo reparador que satisfaga las pretensiones conjuntas de las partes.

5º) Que los mediadores les han indicado la posibilidad de consultar el contenido del presente acuerdo con sus respectivos letrados acreditados en el procedimiento de origen, ofreciéndose a comunicar directamente con ellos para aclarar cualquier duda o aspecto relacionado con el mismo.

Verificado lo cual, por mutuo consenso, manifiestan haber llegado libre y voluntariamente, al siguiente

ACUERDO

1º) Que, a partir del mes de [COMPLETAR] de [COMPLETAR], durante los cinco primeros días de cada uno de los tres primeros meses del año en curso, D./Dña. [NOMBRE Y APELLIDOS], deberá proceder a ingresar, en la cuenta nº [NÚMERO], que D./Dña. [NOMBRE Y APELLIDOS] tiene en la entidad bancaria [COMPLETAR], sita en la Calle [CALLE] nº [NÚMERO], de la localidad de [COMPLETAR], la suma de [IMPORTE] €, hasta satisfacer la cantidad final de [IMPORTE] € que el mediado denunciado ha admitido haber sustraído al mediado denunciante.

2º) Que en caso de existir cualquier eventualidad a la hora de proceder a materializar el ingreso al que se hace referencia en el punto anterior, por parte de D./Dña. [NOMBRE Y APELLIDOS], se deberá comunicar, de forma directa y personal, con anterioridad al vencimiento del plazo de ingreso acordado, a D./Dña. [NOMBRE Y APELLIDOS], dicha eventualidad.

3º) Que, en caso de impago total o parcial de alguna de las cantidades mensuales establecidas, D./Dña. [NOMBRE Y APELLIDOS] deberá proceder a la regularización inmediata de dicha cantidad, atendiendo al criterio de flexibilidad responsable que se acuerda entre las partes, asumiendo al firmar el presente acuerdo, que la reiteración del impago podrá ser motivo de que por D./Dña. [NOMBRE Y APELLIDOS] se proceda a hacer uso de las acciones civiles y/o penales que estime convenientes para hacer valer su derecho a recuperar la parte de la suma defraudada y reconocida.

4º) Que D./Dña. [NOMBRE Y APELLIDOS] se muestra, respecto del contenido del presente acuerdo, satisfecho y moralmente reparado, no deseando que a D./Dña. [NOMBRE Y APELLIDOS] le deriven otras consecuencias penales como resultado del procedimiento seguido en la Sección de lo Penal del Tribunal de Instancia de [SEDE] plaza nº [NÚMERO] contra el mismo y, como manifestación de buena voluntad, expresamente renuncia a los intereses legales que, por la cantidad reclamada, le pudieran corresponder, así como a cualquier incremento en concepto del IPC que se pudiera aplicar.

5º) Que D./Dña. [NOMBRE Y APELLIDOS] manifiesta que, de forma expresa, asume la responsabilidad personal y penal que le corresponde como consecuencia de su acción ilícita, manifestando su deseo de recuperar afectivamente su relación familiar con el/la denunciante, de quien es [COMPLETAR]), mediante la demostración efectiva de su capacidad para restituir la suma defraudada y para pedir perdón por su acción.

[OPCIONAL — incluir si procede]

Opción en caso de impago de pensión

1.- Que a partir del mes de [COMPLETAR] actual por D. se abonará, en concepto de pago por la responsabilidad civil que corresponde, a D.ª [NOMBRE Y APELLIDOS] la suma de [IMPORTE] € mensuales durante los primeros 5 días de cada mes, con las actualizaciones de IPC por años, salvo que viniera a mejor fortuna, en el nº [Nº] de cuenta [COMPLETAR].

2.- Que cualquier eventualidad que surgiera a la hora de realizar los ingresos se deberá comunicar, con anterioridad al vencimiento del plazo mensual establecido, para proceder al ingreso en cuenta de la cantidad acordada. Deberá procederse a la regularización inmediata de las cantidades que se adeuden atendiendo al criterio de flexibilidad responsable que se acuerda entre las partes

3.- Que, coincidiendo con los meses de junio y diciembre, cada año, D. deberá incrementar en [IMPORTE] € la cantidad establecida, igualmente con el incremento de IPC correspondiente por años sucesivos, la cifra establecida en el apartado 1 de este Acuerdo, lo que significa que esos meses se deberá abonar a D.ª [NOMBRE Y APELLIDOS] la suma de [IMPORTE] €.

4.- Ambas partes acuerdan asimismo ejercer de manera responsable y solidaria las obligaciones respecto de la coeducación y coparticipación en la adopción conjunta de las decisiones que se deban establecer respecto de la educación y desarrollo evolutivo de los hijos menores, procurando que éstos se desarrollen de manera positiva y dentro de un margen de interacción corresponsable y bidireccional entre ambos progenitores.

5.- D.ª [NOMBRE Y APELLIDOS] se muestra, respecto del contenido del presente Acuerdo, satisfecha y reparada, no teniendo especial interés en que a D. le deriven consecuencias penales o de otro tipo como resultado del procedimiento [COMPLETAR] seguido en la Sección de lo Penal del Tribunal de Instancia de [SEDE] plaza nº [NÚMERO] contra él mismo, sin renunciar a las acciones que le correspondan.

6.- D. manifiesta expresamente que asume la responsabilidad personal y penal que pudiera corresponderle, siendo informado por los Mediadores de las posibles consecuencias legales y las fases procesales que en adelante han de tramitarse en la Sección de lo Penal del Tribunal de Instancia de [SEDE] plaza nº [NÚMERO DE LA CALLE]

A la vista del ACUERDO conseguido: [COMPLETAR]

El Equipo de Mediación hace una valoración global muy positiva de la actitud de los mediados y del acuerdo al que, de forma libre y consciente, han llegado, no solo por ser un medio que facilita la reparación material del denunciante, sino porque, además, puede posibilitar la resolución pacífica del conflicto interpersonal que separa y enfrenta a los mediados como consecuencia del hecho denunciado.

Dicha valoración, no obstante, es también cauta, pues si bien la actitud mostrada por ambos mediados es, sin lugar a dudas, no solo positiva, sino también sincera, y ambas partes quieren recuperar la relación familiar preexistente a la denuncia, la viabilidad del fortalecimiento de dicho vínculo queda condicionada al cumplimiento de las obligaciones que se determinan por las partes en el presente ACUERDO.

Por todo ello, el Equipo de Mediación pone en conocimiento del Ministerio Fiscal y de la Sección de lo Penal del Tribunal de Instancia de [SEDE] plaza nº [NÚMERO] que D./Dña. [NOMBRE Y APELLIDOS] ha sido informado/a de la posibilidad de que puedan serle aplicados, conforme a la legalidad vigente y bajo superior criterio de la autoridad competente, los beneficios legales asociados, en la ejecutoria penal correspondiente, de los mecanismos de suspensión o sustitución de la pena; en cuya virtud, el funcionario mediador, comunica que D./Dña. [NOMBRE Y APELLIDOS] muestra preferencia por que la responsabilidad penal que le correspondiera en sentencia, pudiera dejarse en suspenso, conforme a los artículos 80 y ss. del CP, valorándose, a tal fin, la regularidad en el abono de los pagos a los que se compromete en el presente ACUERDO.

En prueba de su conformidad con todo lo reseñado, firman ambas partes el presente acuerdo, en [LUGAR], a [FECHA].

Firma de los mediados	Firma del mediador

================================================================================
