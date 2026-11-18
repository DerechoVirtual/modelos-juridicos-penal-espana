---
name: suspension-pena-denegada-apelacion-pidiendo-excepcional-100
description: "Redacta el escrito «Suspensión de pena denegada: apelación pidiendo la excepcional (hasta el 2 de abril de 2025)» (formulario 100 de ejecución penal, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Suspensión de pena denegada: apelación pidiendo la excepcional (hasta el 2 de abril de 2025)

> Formulario 0100 del plugin **Ejecución penal** · revisado el 17-11-2026.

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

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] FECHA (7 veces)
- [ ] PENA
- [ ] Nº DE DOCUMENTO
- [ ] LUGAR
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «… el auto de este Tribunal con referencia»

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE ESTAS ALTERNATIVAS Y SUPRIMIR LAS DEMÁS:

## Párrafos opcionales (1)

Inclúyelos solo si encajan en los hechos:

- Frente a dicho auto esta parte presentó recurso de reforma de fecha [FECHA] resuelto por auto de fecha [FECHA]…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 766.1, 2 y 3 de la Ley de Enjuiciamiento Criminal
- art. 80 CP
- art. 80.2 CP
- art. 80.3 CP
- art. 80.5 CP

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

### Formulario 0100 · Suspensión de pena denegada: apelación pidiendo la excepcional (hasta el 2 de abril de 2025)

- Año del modelo: 2023
- Revisión 17-11-2026: 1 bloques de alternativas señalados; 1 párrafos opcionales señalados; 14 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 1 menciones a juzgados penales actualizadas (LO 1/2025); 3 menciones a órganos y cargos actualizadas (LO 1/2025; LO 7/2015); 1 huecos del original que se habían perdido sin marca, marcados (FECHA)
- Avisos de la revisión: La regla 1.ª del art. 80.2 CP cambió con la LO 1/2026 (desde el 10-4-2026): computan las condenas anteriores por delitos leves que integren un tipo agravado por multirreincidencia; deben revisarse los antecedentes del penado antes de pedir u oponerse a la suspensión.

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la Sección de lo Penal del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales, en nombre y representación de D./Dña [NOMBRE Y APELLIDOS], tal y como tengo acreditado en los autos del procedimiento abreviado nº juicio oral y con ejecutoria número [Nº DE PROCEDIMIENTO], ante este Tribunal comparezco y, como mejor en Derecho proceda, DIGO

Que, mediante el presente escrito, y en virtud del artículo 766.1, 2 y 3 de la Ley de Enjuiciamiento Criminal, formulo RECURSO APELACIÓN contra el auto de este Tribunal de Instancia (Sección de lo Penal) de fecha [FECHA] que deniega la suspensión de la pena a la que fue condenado mi patrocinado; recurso que se basa en las siguientes

ALEGACIONES

PRIMERA.- Este Juzgado, en la sentencia dictada en fecha condenó a mi representado/a a una pena de [PENA]

Se adjunta como documento número [Nº DE DOCUMENTO] copia de la referida sentencia.

SEGUNDA.- Al no haberse resuelto en sentencia sobre la suspensión de la pena que, de modo subsidiario a la absolución, ya instó esta parte en la calificación provisional de la defensa y en vía de informe, esta parte presentó escrito en fecha solicitando la suspensión de la pena a la que había sido condenado/a D./Dña. [NOMBRE Y APELLIDOS].

TERCERA.- Este Juzgado dictó auto de fecha [FECHA] denegando la suspensión de la ejecución de la pena instada, aunque concurrían los presupuestos del art. 80 CP.

[OPCIONAL — incluir si procede]

Frente a dicho auto esta parte presentó recurso de reforma de fecha [FECHA] resuelto por auto de fecha [FECHA], denegando nuevamente la suspensión.

CUARTA.- Se formula el presente recurso, por cuanto concurren las condiciones necesarias para suspender la pena impuesta:

[ELEGIR UNA DE ESTAS ALTERNATIVAS Y SUPRIMIR LAS DEMÁS:]
— (Supuesto de suspensión del art. 80.2 CP)
— (Supuesto de suspensión excepcional del art. 80.3 CP)
— (Supuesto de suspensión especial del art. 80.5 CP: para el caso de que el condenado haya sido condenado a una pena de prisión de hasta cinco años, pero cometiera el delito a consecuencia de su drogodependencia, y ahora se haya deshabituado o esté sometido a tratamiento.)

Por todo lo expuesto,

SUPLICO AL TRIBUNAL:

Que, teniendo por presentado este escrito con todas las copias y documentos que le acompañan, tenga por formulado RECURSO DE APELACION contra el auto de este Tribunal con referencia [COMPLETAR] de fecha [FECHA] y por la superioridad que resuelva este recurso se acuerde la suspensión de la pena privativa de libertad que fue impuesta a D./Dña. [NOMBRE Y APELLIDOS] en la sentencia de fecha [FECHA].

Es de Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a

================================================================================
