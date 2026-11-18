---
name: prueba-defensa-denegada-procedimiento-abreviado-queja-556
description: "Redacta el escrito «Prueba de la defensa denegada en el procedimiento abreviado: queja (hasta el 2 de abril de 2025)» (formulario 556 de recursos penales, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Prueba de la defensa denegada en el procedimiento abreviado: queja (hasta el 2 de abril de 2025)

> Formulario 0556 del plugin **Recursos penales** · revisado el 17-11-2026.

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

- Planteamiento anterior a la LO 1/2025: desde el 3-4-2025 la prueba denegada se reproduce en la audiencia preliminar (art. 785.1 LECrim); lo resuelto no es recurrible, salvo protesta y reproducción en el recurso contra la sentencia (art. 785.3), y al inicio del juicio solo cabe aportar documentos o prueba desconocida al tiempo de la audiencia (art. 787.3).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS (5 veces)
- [ ] COLEGIO
- [ ] Nº DE COLEGIADO/A
- [ ] LOCALIDAD
- [ ] NÚMERO (2 veces)
- [ ] FECHA (5 veces)
- [ ] LUGAR
- [ ] Otros 3 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…. 1.-»; «…, a [FECHA]. Firma de Abogado/a:»; «…Firma de Procurador/a:»

## Correcciones de la revisión (2)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículos 785.1 y 786.2 de la LECRIM
- artículo 656 de la Ley de Enjuiciamiento Criminal
- artículos 790.5 y 791.2 LECRIM
- artículos 790.5 y 791 de la Ley de Enjuiciamiento Criminal

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

### Formulario 0556 · Prueba de la defensa denegada en el procedimiento abreviado: queja (hasta el 2 de abril de 2025)

- Año del modelo: 2018
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; 1 puntualizaciones normativas añadidas en el texto; restos de formato retirados; notas del formulario agrupadas al final (1); 16 campos de relleno marcados en blanco; 2 etiquetas sin dato marcadas en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 1 menciones a juzgados penales actualizadas (LO 1/2025); 2 menciones a órganos y cargos actualizadas (LO 1/2025; LO 7/2015); 1 huecos del original que se habían perdido sin marca, marcados (FECHA)
- Avisos de la revisión: Planteamiento anterior a la LO 1/2025: desde el 3-4-2025 la prueba denegada se reproduce en la audiencia preliminar (art. 785.1 LECrim); lo resuelto no es recurrible, salvo protesta y reproducción en el recurso contra la sentencia (art. 785.3), y al inicio del juicio solo cabe aportar documentos o prueba desconocida al tiempo de la audiencia (art. 787.3).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la defensa del acusado anticipa ante el juzgado de lo penal que al inicio del juicio oral propondrá, como cuestión previa, la prueba que ya solicitó en su escrito de defensa y que le fue denegada, conforme al art. 785.1 y 786, según redacción vigente hasta el 2 de abril de 2025 [NOTA DE REVISIÓN: La LO 1/2025 entró en vigor el 3-4-2025 (DF 38.1): la redacción anterior de los arts. 785 y 786 LECrim estuvo vigente hasta el 2-4-2025 inclusive. Fuente: LO 1/2025, BOE-A-2025-76, art. 20.10 y 20.11 y DF 38.1.], antes de la entrada en vigor de la reforma de la LO 1/2025.

A la Sección de lo Penal del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales del Ilustre Colegio de [COLEGIO], con nº de colegiado [Nº DE COLEGIADO/A] y con despacho profesional abierto en [LOCALIDAD], en representación del/de la acusado/a D./Dña. [NOMBRE Y APELLIDOS] en el J.O. nº [NÚMERO] del Tribunal de Instancia (Sección de lo Penal), comparezco ante el Tribunal y, como mejor proceda en derecho, DIGO:

Que conforme a lo establecido en los artículos 785.1 y 786.2 de la LECRIM [NOTA DE REVISIÓN: Régimen sustituido desde el 3-4-2025: la prueba denegada se reproduce ahora en la audiencia preliminar (art. 785.1 LECrim), lo resuelto no es recurrible salvo protesta (art. 785.3) y al inicio del juicio solo caben documentos o prueba desconocida al tiempo de la audiencia (art. 787.3). Fuente: LECrim, BOE-A-1882-6036, arts. 785 y 787.3 (redacción LO 1/2025, BOE-A-2025-76).] (según redacción anterior al 3 de abril de 2025, fecha de entrada en vigor de la LO 1/2025), presento las siguientes

ALEGACIONES

PRIMERA

Con fecha [FECHA] presenté escrito de defensa en representación de mi defendido/a D./Dña. [NOMBRE Y APELLIDOS] donde expuse la siguiente prueba para el acto del juicio oral señalado para el día [FECHA].

1.- [COMPLETAR].

Con respecto a la petición de prueba referida se nos ha denegado la citada a los nº [NÚMERO] que es absolutamente necesaria para defender los legítimos intereses de nuestro/a defendido/a.

SEGUNDA

La denegación de prueba supone una limitación de nuestro derecho a la tutela judicial efectiva, ya que con ella queremos probar los siguientes extremos de nuestro escrito de defensa y, del mismo modo, oponernos a las alegaciones de la acusación en los siguientes extremos:

TERCERA

La prueba interesada anteriormente es pertinente y necesaria, según se ha razonado con respecto a los hechos sometidos a debate.

Como presupuestos de la admisibilidad de la prueba interesada que reproduciremos como cuestión previa al inicio del juicio oral (1) señalado para el día [FECHA], citamos los siguientes:

A) La diligencia probatoria ha de haber sido solicitada en tiempo y forma, en los términos exigidos por el artículo 656 de la Ley de Enjuiciamiento Criminal, respecto al Procedimiento Ordinario, y con cuyas previsiones coinciden con los artículos 790.5 y 791.2 LECRIM respecto al Procedimiento Abreviado.
B) Que el órgano judicial haya denegado la diligencia de prueba no obstante merecer la calificación de "pertinente":

Dos elementos han de ser valorados a este respecto:

1.- La pertinencia

Pertinencia es la relación entre las pruebas propuestas con lo que es objeto del juicio y constituye "thema decidendi" (vid. STC 51/1981, de 10 de abril).

2.- La relevancia de la prueba propuesta.

En cuanto a la relevancia del medio probatorio ha de distinguirse entre la relevancia formal y la material -que es la verdaderamente trascendente- y que debe apreciarse cuando la no realización de tal prueba, por su relación con los hechos, puede alterar la sentencia en favor del proponente, pero no cuando dicha omisión no haya influido en el contenido de ésta (vid. STC. 116/1983, de 7 de diciembre, STC 51/1985, de 10 de abril; y STC 45/1990, de 15 de marzo).

En la relevancia deben destacarse dos aspectos:

a.- El primero funcional relativo a los requisitos formales necesarios para la práctica y desarrollo de la prueba y su impugnación.
b.- De carácter material relativo a la potencialidad de la prueba denegada con relación a una alteración del fallo de la sentencia.
c.- Que la prueba sea además "necesaria", es decir, tenga utilidad para los intereses de defensa de quien la propone (STS de 7 de febrero de 1995), de modo que su omisión le cause indefensión.

A diferencia de la pertinencia que se mueve en el ámbito de la admisibilidad como facultad del Tribunal para determinar inicialmente la prueba que genéricamente es pertinente por admisible (STS 2ª de 17 de enero de 1991), la "necesidad" de su ejecución se desenvuelve en el terreno de la práctica, de manera que medios probatorios inicialmente admitidos como pertinentes pueden lícitamente no realizarse, por muy diversas circunstancias (STS de 21 de marzo de 1995, Rec. 995/1994) que eliminen de manera sobrevenida su condición de indispensable y forzosa, como cualidades distintas de la oportunidad y adecuación propias de la idea de pertinencia.

La ausencia del medio de prueba en cuestión se puede traducir en una indefensión material para la parte, lo que significa que la prueba denegada es decisiva en términos de defensa, esto es, que puede tener una influencia decisiva en la resolución del pleito, potencialmente trascendental para el sentido de la resolución.

d.- Que sea "posible" la práctica de la prueba propuesta, como exige la STS 2ª de 23 de abril de 1992, y como reitera la STS de 21 de marzo de 1995, Rec. 995/1994 "en el sentido de que el Tribunal debe agotar razonablemente las posibilidades de su realización sin incidir en la violación del derecho constitucional a un juicio sin dilaciones indebidas".
e.- Que ante la denegación de la prueba formule el proponente la correspondiente "protesta".
f.- Que en el caso del Procedimiento Abreviado la proposición de la prueba que, formulada en los escritos de acusación y de defensa (artículos 790.5 y 791 de la Ley de Enjuiciamiento Criminal), no haya sido admitida por el Tribunal se reitere al inicio de las sesiones del Juicio Oral, donde puede reproducirse la petición.

En este caso concurren todos los elementos antes expuestos, ya que las pruebas denegadas son pertinentes y necesarias y pueden ser llevadas a cabo el día del juicio.

Por lo expuesto,

SUPLICO AL TRIBUNAL

Que tenga por presentado este escrito, lo admita y tenga por realizado el trámite interesando que cuando se planteen las cuestiones previas el día del juicio señalado para el día [FECHA] se admita la prueba propuesta y denegada que se reiterará al inicio del juicio.

Es de Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a: [COMPLETAR]

Firma de Procurador/a: [COMPLETAR]

D./Dña. [NOMBRE Y APELLIDOS] 	D./Dña. [NOMBRE Y APELLIDOS]

NOTAS DEL FORMULARIO

(1) El requisito de la protesta formal al inicio del juicio oral frente a la denegación de la prueba es imprescindible para la queja impugnativa posterior, ya que está exigida legalmente. Significa que debe plantearse ante el juez que acordó tal medida denegatoria que se replantee la decisión a la vista de la proporcionalidad de la decisión y poner de manifiesto que la parte no se aquieta a la denegación de la prueba.

================================================================================
