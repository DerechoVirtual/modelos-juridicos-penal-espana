---
name: amenazas-informaticas-defensa-conformidad-535
description: "Redacta el escrito «Amenazas informáticas: defensa con conformidad» (formulario 535 de delitos contra las personas, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Amenazas informáticas: defensa con conformidad

> Formulario 0535 del plugin **Delitos contra las personas** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] PENA
- [ ] IMPORTE
- [ ] LUGAR
- [ ] FECHA

## Párrafos opcionales (1)

Inclúyelos solo si encajan en los hechos:

- (Si la pena con la que se conforma es de prisión igual o inferior a 2 años)…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 80 CP
- art. 169 CP
- art. 48.3 CP
- art. 48.2 CP
- art. 48.1 y 57 CP

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

### Formulario 0535 · Amenazas informáticas: defensa con conformidad

- Año del modelo: 2018
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (4); 1 párrafos opcionales señalados; 6 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que el acusado se conforma con la calificación de los hechos como delito de amenazas condicionales del art. 169 1º pfo 2º CP, al enviar un mensaje a la víctima amenazando con quitarle la vida si no pagaba una suma de dinero determinada.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales en la representación que tiene acreditada de D./Dña. [NOMBRE Y APELLIDOS], acusado/a en el procedimiento número [Nº DE PROCEDIMIENTO],por el supuesto delito de amenazas informáticas del art. 169. 1º CP párrafo 2º, comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

Que, conforme al Protocolo de conformidades suscrito entre la Fiscalía General del Estado y el Consejo General de la Abogacía de fecha 1 de abril de 2009 (1), se formula escrito de conformidad de los hechos considerados de amenazas del art. 169.1º CP párrafo 2º. (2)

En este sentido, la defensa se conforma con la petición formulada por la Fiscalía a la pena de [PENA] (3) y al pago de [IMPORTE] euros de indemnización al/a la querellante.

[OPCIONAL — incluir si procede]

(Si la pena con la que se conforma es de prisión igual o inferior a 2 años)

Al haberse indemnizado al querellante y no existir antecedentes penales, se interesa se conceda la suspensión de la ejecución de la pena del art. 80 CP y ss que por la defensa se solicita con ocasión del presente escrito, por concurrir los requisitos legales. (4)

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita y tenga por evacuado el trámite por la conformidad de la defensa.

Es de Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a:	Firma del acusado/a:

NOTAS DEL FORMULARIO

(1) En base al protocolo de conformidades suscrito entre la Fiscalía General del Estado y el Consejo General de la Abogacía de fecha 1 de abril de 2009 se puede presentar escrito del abogado defensor antes del señalamiento de juicio oral incluso después de evacuado el trámite de calificación.

(2) La modalidad comisiva del art. 169 CP puede cometerse por medios informáticos, pudiendo llevarse a cabo por Whatsapp, correo electrónico, o los medios previstos en redes sociales mediante comunicación directa por uno de los sistemas de comunicación informática direccional entre partes y no público.

La modalidad de la amenaza informática está prevista de forma expresa, pero solo en el supuesto de amenazas condicionales del art. 169.1º pfo 2 CP, en cuyo caso supone una agravaciónel método utilizado para realizar la amenaza, distinguiendo la pena a imponer según se consiga o no el propósito, no existiendo una previsión especial de agravación para la amenaza informática no condicional.

En cualquier caso, la agravación existe cuando con ese método de llevar a cabo la amenaza se busque el anonimato, no cuando el receptor de la amenaza lo puede identificar con facilidad. Así lo señala el Tribunal Supremo, en STS 838/2016 de 4 de Noviembre, Rec. 537/2016.

(3) Además, procede imponer la pena prevista en el art. 48.3 CP de prohibición de comunicación con la víctima, o con aquellos de sus familiares u otras personas que determine el juez, la pena prevista en el art. 48.2 CP de prohibición de aproximarse a la víctima o familiares u otras personas que determine el juez y la de prohibición de acceso a internet, en atención a la prohibición de regreso al lugar del delito del art. 48.1 y 57 CP, que en este caso ha sido la red de internet en cualquiera de sus modalidades.

(4) Es importante instar ya ambos la petición de suspensión de ejecución de la pena con el apoyo de la fiscalía para garantizarla y evitar el ingreso en prisión.

================================================================================
