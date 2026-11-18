---
name: victima-pedir-reglas-conducta-penado-libertad-779
description: "Redacta el escrito «Víctima: pedir reglas de conducta para el penado en libertad condicional» (formulario 779 de víctimas y justicia restaurativa, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Víctima: pedir reglas de conducta para el penado en libertad condicional

> Formulario 0779 del plugin **Víctimas y justicia restaurativa** · revisado el 17-11-2026.

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

- [ ] SEDE (2 veces)
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] AÑO
- [ ] NÚMERO
- [ ] DELITO
- [ ] FECHA (2 veces)
- [ ] DISTANCIA EN METROS
- [ ] LUGAR
- [ ] Otros 5 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…Prohibición de aproximarse a mí o a»; «…Prohibición de comunicarse conmigo o con»; «…Prohibición de establecer contacto con»; «…Mantener su lugar de residencia en»; «…Prohibición de residir en»

## Párrafos opcionales (9)

Inclúyelos solo si encajan en los hechos:

- Prohibición de aproximarse a mí o a [COMPLETAR], a menos de [DISTANCIA EN METROS] metros de distancia…
- Prohibición de comunicarse conmigo o con [COMPLETAR] por cualquier medio.…
- Prohibición de establecer contacto con [COMPLETAR], puesto que existen indicios que permiten suponer fundadame…
- Mantener su lugar de residencia en [COMPLETAR] con prohibición de abandonarlo o ausentarse temporalmente sin a…
- Prohibición de residir en [COMPLETAR] o de acudir al mismo, cuando en ellos pueda encontrar la ocasión o motiv…
- Comparecer personalmente cada 15 días ante el juez o tribunal (o dependencias policiales o servicio de la admi…
- Participar en programas formativos, laborales, culturales, de educación vial, sexual, de defensa del medio amb…
- Participar en programas de deshabituación al consumo de alcohol, drogas tóxicas o sustancias estupefacientes, …
- Prohibición de conducir vehículos de motor que no dispongan de dispositivos tecnológicos que condicionen su en…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- arts. 83, 86 y 87 CP
- artículo 13.2 a) Ley 4/2015
- artículo 90.5 CP
- artículo 83 CP

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

### Formulario 0779 · Víctima: pedir reglas de conducta para el penado en libertad condicional

- Año del modelo: 2016
- Revisión 17-11-2026: 9 párrafos opcionales señalados; 13 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 1 huecos del original que se habían perdido sin marca, marcados (Nº DE PROCEDIMIENTO)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la víctima interesa que se le impongan al penado al que se le concede la libertad condicional algunas medidas o reglas de conducta de las enumeradas en los arts. 83, 86 y 87 CP, en virtud de la posibilidad que le otorga en artículo 13.2 a) de la L 4/2015, del Estatuto de la víctima del delito.

Actualizado conforme a la LO 10/2022, de garantía integral de la libertad sexual, con entrada en vigor el 7 de octubre de 2022.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Vigilancia Penitenciaria del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] víctima en expediente nº [Nº DE PROCEDIMIENTO]/[AÑO] de la Sección de Violencia sobre la Mujer del Tribunal de Instancia de [SEDE] plaza nº [NÚMERO] sobre delito de [DELITO] ante este órgano judicial comparezco y, como más procedente sea en derecho, y a tenor de lo dispuesto en el artículo 13.2 a) Ley 4/2015, de 27 de abril, del Estatuto de la víctima del delito, DIGO:

Con fecha [FECHA] la Sección de Vigilancia Penitenciaria del Tribunal de Instancia ha dictado auto concediendo al penado la libertad condicional.

Preceptúa el artículo 13.2 a) Ley 4/2015 de 27 de abril, del Estatuto de la víctima del delito que:

2. Las víctimas estarán también legitimadas para:

a) Interesar que se impongan al liberado condicional las medidas o reglas de conducta previstas por la ley que consideren necesarias para garantizar su seguridad, cuando aquél hubiera sido condenado por hechos de los que pueda derivarse razonablemente una situación de peligro para la víctima;

Por su parte, el artículo 90.5 CP se recoge que:

"En los casos de suspensión de la ejecución del resto de la pena y concesión de la libertad condicional, resultarán aplicables las normas contenidas en los artículos 83, 86 y 87.

El juez de vigilancia penitenciaria, a la vista de la posible modificación de las circunstancias valoradas, podrá modificar la decisión que anteriormente hubiera adoptado conforme al artículo 83, y acordar la imposición de nuevas prohibiciones, deberes o prestaciones, la modificación de las que ya hubieran sido acordadas o el alzamiento de las mismas."

En consecuencia, y dadas las características del delito del que fui víctima, y en virtud de la posibilidad que me otorga el artículo 13.2 a) Ley 4/2015, de 27 de abril, intereso se proceda a imponer al condenado sujeto ahora a libertad condicional las siguientes medidas de las contempladas en el artículo 83 CP:

[OPCIONAL — incluir si procede]

Prohibición de aproximarse a mí o a [COMPLETAR], a menos de [DISTANCIA EN METROS] metros de distancia

[OPCIONAL — incluir si procede]

Prohibición de comunicarse conmigo o con [COMPLETAR] por cualquier medio.

[OPCIONAL — incluir si procede]

Prohibición de establecer contacto con [COMPLETAR], puesto que existen indicios que permiten suponer fundadamente que tales sujetos pueden facilitarle la ocasión para cometer nuevos delitos o incitarle a hacerlo.

[OPCIONAL — incluir si procede]

Mantener su lugar de residencia en [COMPLETAR] con prohibición de abandonarlo o ausentarse temporalmente sin autorización del juez o tribunal.

[OPCIONAL — incluir si procede]

Prohibición de residir en [COMPLETAR] o de acudir al mismo, cuando en ellos pueda encontrar la ocasión o motivo para cometer nuevos delitos.

[OPCIONAL — incluir si procede]

Comparecer personalmente cada 15 días ante el juez o tribunal (o dependencias policiales o servicio de la administración que se determine), para informar de sus actividades y justificarlas.

[OPCIONAL — incluir si procede]

Participar en programas formativos, laborales, culturales, de educación vial, sexual, de defensa del medio ambiente, de protección de los animales, de igualdad de trato y no discriminación, resolución pacífica de conflictos, parentalidad positiva y otros similares.

[OPCIONAL — incluir si procede]

Participar en programas de deshabituación al consumo de alcohol, drogas tóxicas o sustancias estupefacientes, o de tratamiento de otros comportamientos adictivos.

[OPCIONAL — incluir si procede]

Prohibición de conducir vehículos de motor que no dispongan de dispositivos tecnológicos que condicionen su encendido o funcionamiento a la comprobación previa de las condiciones físicas del conductor

Por todo ello,

SUPLICO A LA SECCIÓN

Se admita el presente escrito y se adopten las medidas antes recogidas sobre la persona del penado.

En [LUGAR], a [FECHA].

Firma de la víctima

D./Dña. [NOMBRE Y APELLIDOS]

================================================================================
