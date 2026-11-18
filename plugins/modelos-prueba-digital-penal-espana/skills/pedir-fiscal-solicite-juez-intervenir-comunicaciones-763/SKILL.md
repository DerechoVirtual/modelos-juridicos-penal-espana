---
name: pedir-fiscal-solicite-juez-intervenir-comunicaciones-763
description: "Redacta el escrito «Pedir al fiscal que solicite al juez intervenir las comunicaciones» (formulario 763 de investigación tecnológica y prueba digital, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Pedir al fiscal que solicite al juez intervenir las comunicaciones

> Formulario 0763 del plugin **Investigación tecnológica y prueba digital** · revisado el 17-11-2026.

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

- [ ] NOMBRE Y APELLIDOS (3 veces)
- [ ] COLEGIO
- [ ] Nº DE COLEGIADO/A
- [ ] LOCALIDAD
- [ ] Nº DE PROCEDIMIENTO
- [ ] SEDE
- [ ] NÚMERO
- [ ] Nº
- [ ] DESCRIBIR
- [ ] LUGAR
- [ ] FECHA
- [ ] Otros 6 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…ibunales de Instancia. AL FISCAL JEFE DE»; «…efónicas y telemáticas del investigado/a»; «…años de prisión del artículo»; «…edida. La identidad del investigado/a es»; «…esentes diligencias y sus teléfonos son:»; «…castigados con pena con límite máximo de»

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 579.1 LECRIM
- artículo 588 bis a 4 LECRIM
- artículo 579 LECRIM

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

### Formulario 0763 · Pedir al fiscal que solicite al juez intervenir las comunicaciones

- Año del modelo: 2016
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (1); 18 campos de relleno marcados en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la acusación en un proceso penal solicita al fiscal que interese autorización judicial para la intervención de las comunicaciones telefónicas y/o telemáticas del investigado por un delito de terrorismo o cometido a través de instrumentos informáticos o de cualquier otra tecnología de la información o la comunicación.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

AL FISCAL JEFE DE [COMPLETAR]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los tribunales del Ilustre Colegio de procuradores de [COLEGIO], con nº de colegiado [Nº DE COLEGIADO/A] y con despacho profesional abierto en [LOCALIDAD], en representación de D./Dña. [NOMBRE Y APELLIDOS], parte personada como acusación particular en el procedimiento penal nº [Nº DE PROCEDIMIENTO] que se tramita ante la Sección de Instrucción del Tribunal de Instancia de [SEDE] plaza nº [NÚMERO], comparezco ante este órgano judicial y como mejor proceda en derecho, DIGO:

Mediante el presente escrito formulo solicitud al Fiscal para que, en aplicación del artículo 588 bis b de la Ley de Enjuiciamiento Criminal, se interese la intervención e interceptación de las comunicaciones telefónicas y telemáticas del investigado/a [COMPLETAR] con base en las siguientes:

CONCLUSIONES

PRIMERA.- El resultado de las diligencias practicadas ofrece fundadas sospechas de la comisión de un hecho delictivo castigado con pena de [Nº] años de prisión del artículo [COMPLETAR] del CP (1)

Se cumple el presupuesto fijado en el artículo 588 ter a LECRIM ya que: la autorización para la interceptación de las comunicaciones telefónicas y telemáticas solo podrá ser concedida cuando la investigación tenga por objeto alguno de los delitos a que se refiere el artículo 579.1 LECRIM o delitos cometidos a través de instrumentos informáticos o de cualquier otra tecnología de la información o la comunicación o servicio de comunicación.

SEGUNDA.- Se cumple el presupuesto del art 588 bis a LECRIM dado que:

El principio de especialidad exige que una medida esté relacionada con la investigación de un delito concreto. No podrán autorizarse medidas de investigación tecnológica que tengan por objeto prevenir o descubrir delitos o despejar sospechas sin base objetiva.

El principio de idoneidad servirá para definir el ámbito objetivo y subjetivo y la duración de la medida en virtud de su utilidad.

En este caso no se trata de una medida prospectiva, sino que existen ya serios indicios de la comisión de un delito que pueden ser complementados por la medida de interceptación de las comunicaciones.

Además, en base al artículo 588 bis a 4 LECRIM no existen medidas menos gravosas para los derechos fundamentales del investigado o encausado e igualmente útiles para el esclarecimiento del hecho, y el descubrimiento o la comprobación del hecho investigado, la determinación de su autor o autores, la averiguación de su paradero, o la localización de los efectos del delito se vería gravemente dificultada sin el recurso a esta medida.

Se ha valorado también la proporcionalidad de la medida que no es excesivamente gravosa, dada la identidad del delito cometido y su gravedad y la necesidad de ajustar la investigación al objetivo y posible eficacia de esta medida.

TERCERA.- En base al artículo 588 bis b LECRIM la petición del Fiscal contendrá:

1.º La descripción del hecho objeto de investigación y la identidad del investigado/a o de cualquier otro afectado por la medida, siempre que tales datos resulten conocidos.

Este hecho objeto de investigación se refiere a [DESCRIBIR]

2.º La exposición detallada de las razones que justifiquen la necesidad de la medida de acuerdo a los principios rectores establecidos en el artículo 588 bis a LECRIM, así como los indicios de criminalidad que se hayan puesto de manifiesto durante la investigación previa a la solicitud de autorización del acto de injerencia.

Se cumplen estos requisitos como antes se ha expuesto.

3.º Los datos de identificación del investigado/a o encausado/a y, en su caso, de los medios de comunicación empleados que permitan la ejecución de la medida.
La identidad del investigado/a es [COMPLETAR] conforme está siéndolo en las presentes diligencias y sus teléfonos son: [COMPLETAR].
4.º La extensión de la medida con especificación de su contenido.
5.º La unidad investigadora de la Policía Judicial que se hará cargo de la intervención.
6.º La forma de ejecución de la medida.
7.º La duración de la medida que se solicita.
8.º El sujeto obligado que llevará a cabo la medida, en caso de conocerse.

Todo ello más el contenido del artículo 588 ter d LECRIM relativo a la solicitud de autorización judicial.

CUARTA.- En base al artículo 588 bis d LECRIM"La solicitud y las actuaciones posteriores relativas a la medida solicitada se sustanciarán en una pieza separada y secreta, sin necesidad de que se acuerde expresamente el secreto de la causa". Se interesa se traslade al juez que se tramite la presente en pieza separada.

Por lo expuesto,

SOLICITO AL FISCAL

que tenga por presentado este escrito, lo admita y tenga por realizada la petición de solicitud de autorización judicial en los términos expuestos.

Es Justicia que pido en [LUGAR], a [FECHA].

Firma del procurador/a

D./Dña. [NOMBRE Y APELLIDOS]

NOTAS DEL FORMULARIO

(1) Solo puede acordarse esta medida cumpliéndose el presupuesto del artículo 579 LECRIM, es decir, que se trate de delitos dolosos castigados con pena con límite máximo de [COMPLETAR], al menos, tres años de prisión.

================================================================================
