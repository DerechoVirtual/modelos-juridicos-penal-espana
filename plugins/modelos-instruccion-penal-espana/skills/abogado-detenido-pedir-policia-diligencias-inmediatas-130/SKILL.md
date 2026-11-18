---
name: abogado-detenido-pedir-policia-diligencias-inmediatas-130
description: "Redacta el escrito «Abogado del detenido: pedir a la policía diligencias inmediatas» (formulario 130 de instrucción y procedimiento penal, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Abogado del detenido: pedir a la policía diligencias inmediatas

> Formulario 0130 del plugin **Instrucción y procedimiento penal** · revisado el 17-11-2026.

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

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión. Empieza con una nota explicativa (para qué sirve el escrito y cuándo se usa), revisada en el BOE: léela antes de redactar, pero no la copies en el escrito.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] NOMBRE Y APELLIDOS (3 veces)
- [ ] COLEGIO
- [ ] Nº
- [ ] Otros 6 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…A la comisaría de policía de»; «…a evaluar su situación física y psíquica»; «…a las dependencias del Hospital»; «…traídos pueden encontrarse escondidos en»; «…racticar las diligencias solicitadas. En»; «…, siendo las [Nº] horas, del»

## Párrafos opcionales (2)

Inclúyelos solo si encajan en los hechos:

- Que, al amparo de lo dispuesto en el art. 520.6 a) de la LECrim, solicito que le sea practicado reconocimiento…
- Que, a la vista de la declaración de mi defendido/a, los objetos sustraídos pueden encontrarse escondidos en […

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 520.6 a) de la LECrim

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

### Formulario 0130 · Abogado del detenido: pedir a la policía diligencias inmediatas

- Año del modelo: 2023
- Revisión 17-11-2026: 2 párrafos opcionales señalados; 11 campos de relleno marcados en blanco
- Nota explicativa incorporada desde la colección Procesal (formulario 116) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Escrito del abogado del detenido solicitando a la policía judicial que proceda a practicar diligencias inaplazables, como el reconocimiento médico del detenido o su personación para ocupar efectos sustraídos.

---

A la comisaría de policía de [COMPLETAR]

D./Dña. [NOMBRE Y APELLIDOS], Abogado/a del Iltre. Colegio de Abogados de [COLEGIO], designado/a para la defensa del/de la detenido/a D./Dña. [NOMBRE Y APELLIDOS] en estas diligencias policiales, por medio del presente escrito, EXPONGO:

[OPCIONAL — incluir si procede]

Que, al amparo de lo dispuesto en el art. 520.6 a) de la LECrim, solicito que le sea practicado reconocimiento médico de forma inmediata, en atención a que he tenido conocimiento de que se halla en un estado de intoxicación etílica agudo desde el momento de su detención, por ser imprescindible dicho reconocimiento para evaluar su situación física y psíquica [COMPLETAR].

Por este motivo, considero que, de forma inaplazable, debe procederser al traslado inmediato del/de la detenido/a D./Dña. [NOMBRE Y APELLIDOS] a las dependencias del Hospital [COMPLETAR] para que se le practique reconocimiento médico.

[OPCIONAL — incluir si procede]

Que, a la vista de la declaración de mi defendido/a, los objetos sustraídos pueden encontrarse escondidos en [COMPLETAR], puesto que allí se dirigió la persona que vio el detenido cuando se encontraba en el lugar de los hechos, siendo absolutamente inaplazable comprobar si, efectivamente, dichos objetos pueden encontrarse en dicho lugar, puesto que, de no actuar de forma inmediata, los verdaderos autores del robo pueden hacer disponer de los objetos, trasladándolos a otro lugar o vendiéndolos.

Que por estos motivos considero que, de forma inaplazable, deben personarse agente o agentes de esa Comisaría en el citado lugar a fin de buscar y, en su caso, ocupar los efectos sustraídos.

Por lo expuesto,

SOLICITO A LA POLICÍA JUDICIAL:

Que proceda a practicar las diligencias solicitadas.

En [COMPLETAR], siendo las [Nº] horas, del [COMPLETAR]

Firma de Abogado/a

================================================================================
