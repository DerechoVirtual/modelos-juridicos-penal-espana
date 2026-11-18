---
name: ejecutoria-penal-reforma-subsidiario-apelacion-contra-56
description: "Redacta el escrito «Ejecutoria penal: reforma y subsidiario de apelación contra el auto que resuelve alegaciones» (formulario 56 de ejecución penal, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Ejecutoria penal: reforma y subsidiario de apelación contra el auto que resuelve alegaciones

> Formulario 0056 del plugin **Ejecución penal** · revisado el 17-11-2026.

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

- La regla 1.ª del art. 80.2 CP cambió con la LO 1/2026 (desde el 10-4-2026): computan las condenas anteriores por delitos leves que integren un tipo agravado por multirreincidencia; deben revisarse los antecedentes del penado antes de pedir u oponerse a la suspensión.

## Nota explicativa: puntualizaciones de la revisión

La nota explicativa de este formulario se ha revisado en el BOE. Tenlo en cuenta al redactar:

- Los Juzgados de lo Penal son Secciones de lo Penal desde el 31-12-2025 (DT 1ª LO 1/2025). La reforma se interpone en 3 días (art. 211 LECrim) y la apelación, en 5 días (art. 766.3 LECrim).
- La LO 1/2026 (BOE-A-2026-7966), vigente desde el 10-4-2026, cambió la regla 1.ª del art. 80.2 CP. Las condenas por delitos leves ya cuentan como antecedente cuando forman parte de un tipo agravado por multirreincidencia de delitos leves. El inciso final que cita la nota no ha cambiado.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión. Empieza con una nota explicativa (para qué sirve el escrito y cuándo se usa) y acaba con sus notas al pie, revisadas en el BOE: léela antes de redactar, pero no la copies en el escrito.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] FECHA DEL AUTO
- [ ] FECHA (2 veces)
- [ ] IMPORTE (3 veces)
- [ ] DESCRIBIR
- [ ] LUGAR
- [ ] Otros 3 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…utoria penal. Señala el citado artículo:»; «…Añade el art. 80 CP que:»; «…sitos legales para su aceptación, ya que»

## Elecciones que hay que hacer

- la sección / tribunal
- A LA SECCIÓN / TRIBUNAL

## Párrafos opcionales (11)

Inclúyelos solo si encajan en los hechos:

- La suspensión de la pena impuesta a mi representado/a de años de prisión como autor de un delito de del art. d…
- La petición relativa al aplazamiento del pago de responsabilidades pecuniarias.…
- La solicitud de [FECHA].…
- Añade el art. 80 CP que: [COMPLETAR]…
- SEGUNDA.- En el auto que se recurre se ha denegado el aplazamiento de las responsabilidades pecuniarias fijada…
- TERCERA.- Una vez estimada la suspensión de la ejecución de la pena, se interesa que se fijen las siguientes c…
- CUARTA.- En el auto que ahora se recurre se denegó la solicitud de cuando se cumplen todos los requisitos lega…
- la suspensión de la ejecución de la pena por plazo de cinco años del art. 81 CP.…
- se fijen las siguientes condiciones del art. 83 y 84 CP.…
- las peticiones relativas al aplazamiento del pago de responsabilidades pecuniarias.…
- la solicitud relativa a para la ejecución de los pronunciamientos de la sentencia.…

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículos 211 y 766.1 de la LECrim
- art. 988 bis.2 LECRIM
- art. 80 CP
- art. 83 y 84 CP
- art. 81 CP
- art. 766.4 LECrim
- art. 766.3 LECrim

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

### Formulario 0056 · Ejecutoria penal: reforma y subsidiario de apelación contra el auto que resuelve alegaciones

- Año del modelo: 2025
- Revisión 17-11-2026: 1 puntualizaciones normativas añadidas en el texto; 2 llamadas a nota sin texto retiradas; 2 desplegables y casillas convertidos en elección en blanco; 1 desplegables convertidos en elección en blanco; 11 párrafos opcionales señalados; 8 campos de relleno marcados en blanco; 2 etiquetas sin dato marcadas en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 4 huecos del original que se habían perdido sin marca, marcados (FECHA DEL AUTO, IMPORTE)
- Avisos de la revisión: La regla 1.ª del art. 80.2 CP cambió con la LO 1/2026 (desde el 10-4-2026): computan las condenas anteriores por delitos leves que integren un tipo agravado por multirreincidencia; deben revisarse los antecedentes del penado antes de pedir u oponerse a la suspensión.
- Nota explicativa incorporada desde la colección Procesal (formulario 51) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Recurso de reforma presentado por el condenado contra auto dictado en ejecutoria penal por la Sección de lo Penal del Tribunal de Instancia (antes, Juzgado de lo Penal) que deniega cualquier solicitud relativa a la ejecución de los pronunciamientos de la sentencia del art. 988 bis 1 LECRIM, según redacción dada por LO 1/2025, vigente desde el 3 de abril de 2025, que sigue los trámites del art. 211 y 766.1 LECRIM.

---

A la Sección de lo Penal del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales, en nombre y representación de D./Dña. [NOMBRE Y APELLIDOS], según tengo debidamente acreditado en la Ejecutoria nº [Nº DE PROCEDIMIENTO], ante este órgano judicial comparezco y, como mejor proceda en derecho, DIGO:

Que, con el presente escrito y según permiten los artículos 211 y 766.1 de la LECrim., interpongo RECURSO DE REFORMA Y SUBSIDIARIO DE APELACIÓN, contra el auto de fecha [FECHA DEL AUTO] por el que se deniega:

[OPCIONAL — incluir si procede]

La suspensión de la pena impuesta a mi representado/a de años de prisión como autor de un delito de del art. del CP.

[OPCIONAL — incluir si procede]

La petición relativa al aplazamiento del pago de responsabilidades pecuniarias.

[OPCIONAL — incluir si procede]

La solicitud de [FECHA].

Ello con base en las siguientes,

ALEGACIONES

PRIMERA.- Conforme al art. 988 bis.2 LECRIM (según redacción dada por LO 1/2025), se dictó por [ELEGIR: la sección / tribunal] auto resolviendo sobre las peticiones de las partes en la presente ejecutoria penal.

Señala el citado artículo: [COMPLETAR]

"2. Presentado el escrito, al que deberán acompañarse los informes o la documentación en que se funden las peticiones, el juez o tribunal realizará, en su caso, las comprobaciones necesarias sobre la concurrencia de los requisitos de la suspensión y del resto de peticiones realizadas, tras lo cual dará traslado de la solicitud y de lo practicado al Ministerio Fiscal, a las partes acusadoras personadas y víctimas, directamente afectadas por la decisión, para que, en el plazo de diez días, formulen alegaciones. Transcurrido el plazo, en el término de cinco días el juez, la jueza o el tribunal resolverán mediante auto sobre todas las peticiones."

[OPCIONAL — incluir si procede]

Añade el art. 80 CP que: [COMPLETAR]

"1. Los jueces o tribunales, mediante resolución motivada, podrán dejar en suspenso la ejecución de las penas privativas de libertad no superiores a dos años cuando sea razonable esperar que la ejecución de la pena no sea necesaria para evitar la comisión futura por el penado de nuevos delitos.

Para adoptar esta resolución el juez o tribunal valorará las circunstancias del delito cometido, las circunstancias personales del penado, sus antecedentes, su conducta posterior al hecho, en particular su esfuerzo para reparar el daño causado, sus circunstancias familiares y sociales, y los efectos que quepa esperar de la propia suspensión de la ejecución y del cumplimiento de las medidas que fueren impuestas.

2. Serán condiciones necesarias para dejar en suspenso la ejecución de la pena, las siguientes:
1.ª Que el condenado haya delinquido por primera vez. A tal efecto no se tendrán en cuenta las anteriores condenas por delitos imprudentes o por delitos leves, ni los antecedentes penales [NOTA DE REVISIÓN: Desde el 10-4-2026 la LO 1/2026 añadió a la regla 1.ª del art. 80.2 CP, tras «delitos leves», el inciso «salvo que estos integren un tipo agravado por multirreincidencia de delitos leves»; la cita literal debe actualizarse. Fuente: CP, BOE-A-1995-25444, art. 80.2.1.ª (redacción LO 1/2026, BOE-A-2026-7966).] que hayan sido cancelados, o debieran serlo con arreglo a lo dispuesto en el artículo 136. Tampoco se tendrán en cuenta los antecedentes penales correspondientes a delitos que, por su naturaleza o circunstancias, carezcan de relevancia para valorar la probabilidad de comisión de delitos futuros.
2.ª Que la pena o la suma de las impuestas no sea superior a dos años, sin incluir en tal cómputo la derivada del impago de la multa.
3.ª Que se hayan satisfecho las responsabilidades civiles que se hubieren originado y se haya hecho efectivo el decomiso acordado en sentencia conforme al artículo 127.

Este requisito se entenderá cumplido cuando el penado asuma el compromiso de satisfacer las responsabilidades civiles de acuerdo a su capacidad económica y de facilitar el decomiso acordado, y sea razonable esperar que el mismo será cumplido en el plazo prudencial que el juez o tribunal determine. El juez o tribunal, en atención al alcance de la responsabilidad civil y al impacto social del delito, podrá solicitar las garantías que considere convenientes para asegurar su cumplimiento."

La pena impuesta al recurrente es la de años de prisión, por lo que procede que se conceda la suspensión de la ejecución de la pena denegada en el auto que se recurre, y, además, se ha realizado una oferta seria de pago del resto de la responsabilidad civil fijada en sentencia una vez se consignó para entrega la suma de [IMPORTE] euros, que es la que se podría abonar con arreglo a las circunstancias económicas de esta parte, comprometiendo el resto aplazado conforme se admite por el párrafo 2º de la regla 3ª antes citado.

[OPCIONAL — incluir si procede]

SEGUNDA.- En el auto que se recurre se ha denegado el aplazamiento de las responsabilidades pecuniarias fijadas en sentencia por importe de [IMPORTE] euros, a fin de poder satisfacerlas en plazos mensuales por importe de [IMPORTE] euros, cuando se ha demostrado, mediante la documentación aportada, la imposibilidad de satisfacerlas de una sola vez. Esta solicitud es, además, una prueba de buena voluntad del pago de la responsabilidad civil fijada en sentencia.

[OPCIONAL — incluir si procede]

TERCERA.- Una vez estimada la suspensión de la ejecución de la pena, se interesa que se fijen las siguientes condiciones recogidas en los art. 83 y 84 CP relativas a [DESCRIBIR], que esta parte se compromete a cumplir.

[OPCIONAL — incluir si procede]

CUARTA.- En el auto que ahora se recurre se denegó la solicitud de cuando se cumplen todos los requisitos legales para su aceptación, ya que [COMPLETAR].

Por lo expuesto,

SUPLICO [ELEGIR: A LA SECCIÓN / TRIBUNAL]:

Que tenga por presentado este escrito y documentos que se acompañan, lo admita, tenga por interpuesto recurso de reforma contra el auto de fecha [FECHA] y acuerde conceder a mi representado/a:

[OPCIONAL — incluir si procede]

la suspensión de la ejecución de la pena por plazo de cinco años del art. 81 CP.

[OPCIONAL — incluir si procede]

se fijen las siguientes condiciones del art. 83 y 84 CP.

[OPCIONAL — incluir si procede]

las peticiones relativas al aplazamiento del pago de responsabilidades pecuniarias.

[OPCIONAL — incluir si procede]

la solicitud relativa a para la ejecución de los pronunciamientos de la sentencia.

Para el caso de que no se estimen las peticiones deducidas, se declare por presentado de forma subsidiaria recurso de apelación.

Es Justicia que pido en [LUGAR]

PRIMER OTROSÍ DIGO: Que, en caso de desestimarse total o parcialmente el recurso de reforma, solicito que se conceda nuevo traslado a esta parte por plazo de cinco días a los efectos prevenidos en el art. 766.4 LECrim.

Por lo expuesto,

SUPLICO [ELEGIR: A LA SECCIÓN / TRIBUNAL]: que tenga por hecha la anterior manifestación.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

SEGUNDO OTROSÍ DIGO: que, en caso de tramitarse la apelación interpuesta con carácter subsidiario, designo los siguientes particulares para que sean remitidos a la Audiencia Provincial para la resolución del recurso, de acuerdo con lo establecido en el art. 766.3 LECrim:

Por lo expuesto,

SUPLICO A LA SECCIÓN
TRIBUNAL
 : que remita a la Audiencia Provincial los anteriores particulares.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a	Firma de Procurador/a

================================================================================

---

#### Notas al pie

(1) Hay que tener en cuenta los supuestos contemplados en los apartados 3, 4 y 5 del art. 80 CP y las condiciones que en cada caso permiten la suspensión. Podría ser impugnada la negativa a concederla si se dan dichas condiciones

(2) Hay que tener en cuenta que la regla 1ª del art. 80.2 CP recoge que: "Tampoco se tendrán en cuenta los antecedentes penales correspondientes a delitos que, por su naturaleza o circunstancias, carezcan de relevancia para valorar la probabilidad de comisión de delitos futuros." En el caso de que se deniegue la suspensión en base a que existen antecedentes penales, se podrá apelar al citado inciso final de la regla 1ª, ya que cabría admitir la posibilidad de que, incluso, con antecedentes penales se pudiera conceder la suspensión de la ejecución de la pena si se puede entender que por la naturaleza del delito cometido y los antecedentes penales existentes no hay riesgo de reincidencia, o de comisión de otro nuevo hecho delictivo similar a aquel por el que se le ha condenado

[NOTA DE REVISIÓN: Los Juzgados de lo Penal son Secciones de lo Penal desde el 31-12-2025 (DT 1ª LO 1/2025). La reforma se interpone en 3 días (art. 211 LECrim) y la apelación, en 5 días (art. 766.3 LECrim).]

[NOTA DE REVISIÓN: La LO 1/2026 (BOE-A-2026-7966), vigente desde el 10-4-2026, cambió la regla 1.ª del art. 80.2 CP. Las condenas por delitos leves ya cuentan como antecedente cuando forman parte de un tipo agravado por multirreincidencia de delitos leves. El inciso final que cita la nota no ha cambiado.]
