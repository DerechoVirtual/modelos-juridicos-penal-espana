---
name: fiscalia-europea-querella-acusacion-particular-326
description: "Redacta el escrito «Fiscalía Europea: querella de la acusación particular» (formulario 326 de procedimiento de la fiscalía europea, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Fiscalía Europea: querella de la acusación particular

> Formulario 0326 del plugin **Procedimiento de la Fiscalía Europea** · revisado el 17-11-2026.

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

- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] DNI/NIE (3 veces)
- [ ] LOCALIDAD (2 veces)
- [ ] Nº
- [ ] FECHA (2 veces)
- [ ] IMPORTE
- [ ] LUGAR
- [ ] Otros 3 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…os Tribunales, actuando en nombre de Don»; «…, a [FECHA]. Firma del Procurador»; «…Firma del Abogado»

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículos 18.1 y 36 de la Ley Orgánica 9/2021
- artículo 83 de la Ley Orgánica 9/2021
- artículo 81 de la Ley Orgánica 9/2021

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

### Formulario 0326 · Fiscalía Europea: querella de la acusación particular

- Año del modelo: 2021
- Revisión 17-11-2026: 16 campos de relleno marcados en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

AL FISCAL EUROPEO DELEGADO

Don/Doña [NOMBRE Y APELLIDOS], Procurador de los Tribunales, actuando en nombre de Don [COMPLETAR], con DNI [DNI/NIE], cuyo mandato y representación acredito mediante la copia adjunta de poder especial para la interposición de querellas, comparezco y, como mejor proceda en derecho, digo:

Que al amparo de lo dispuesto en los artículos 18.1 y 36 de la Ley Orgánica 9/2021, de 1 de julio, de la Fiscalía Europea, así como 270 y 277 de la Ley de Enjuiciamiento Criminal, y en el ejercicio de la acción penal que compete a mi representado, interpongo querella en los siguientes términos:

1.- La querella se interpone ante el Fiscal Europeo Delegado, por ser éste competente, al tratarse de delitos que perjudican los intereses financieros de la Unión Europea, de conformidad con lo dispuesto en los artículos 4, 22, 23 y 25 del Reglamento (UE) 2017/1939 del Consejo, de 12 de octubre de 2017.

2.- Es querellante D./Dª [NOMBRE Y APELLIDOS], con DNI [DNI/NIE], y con domicilio en [LOCALIDAD]

3.- Es querellado D./Dª [NOMBRE Y APELLIDOS], con DNI [DNI/NIE], y con domicilio en [LOCALIDAD]

4.- Los hechos que motivan esta querella son los siguientes:

Sobre las [Nº] horas del día [FECHA],

5.- En averiguación de los hechos relatados y de las personas criminalmente responsables, esta parte interesa la práctica de las siguientes diligencias:

a) Que se reciba declaración, en calidad de investigada, a la persona del querellado.

b) Que se recabe su Hoja Histórico Penal.

c) Que se recabe de los organismos oficiales competentes la información necesaria para acreditar la situación patrimonial del querellado.

d) Que se reciba declaración, en calidad de testigos, a las personas que a continuación se indica:

e) Que se admitan los documentos que esta parte adjunta a la presente querella.

f) Las diligencias derivadas que sean pertinentes.

6.- Por todo ello, esta parte interesa del Fiscal Europeo Delegado que tenga por presentado este escrito, junto con los documentos que se adjuntan, y por interpuesta querella criminal contra D./Dª [NOMBRE Y APELLIDOS], admitiéndose la personación de mi mandante en concepto de Acusación Particular, dando traslado inmediato de la querella al querellado.

Al objeto de garantizar que la persona querellada no se sustraerá a la acción de la justicia, se solicita del Fiscal Europeo Delegado que, de conformidad con lo dispuesto en el artículo 83 de la Ley Orgánica 9/2021, de 1 de julio, de la Fiscalía Europea, interese del Juez de Garantías la celebración de la audiencia prevista en el artículo 81 de la Ley Orgánica 9/2021, con el fin de reclamar la aplicación de medidas cautelares de carácter personal.

Asimismo, para satisfacer las responsabilidades pecuniarias de toda índole que pudieran corresponder a la persona querellada, de conformidad con lo dispuesto en los artículos 52 y siguientes de la Ley Orgánica 9/2021, de 1 de julio, así como 589 y 764 de la Ley de Enjuiciamiento Criminal (LEG 1882, 16), se le requerirá para que preste fianza por importe de [IMPORTE] euros, decretándose el embargo de bienes bastantes para cubrir esta responsabilidad pecuniaria si la persona querellada no prestare la fianza exigida.

En su virtud, se interesa del Fiscal Europeo Delegado que tenga por interpuesta la presente querella, y por solicitada la personación de mi mandante en concepto de Acusación Particular.

En [LUGAR], a [FECHA].

Firma del Procurador [COMPLETAR]

Firma del Abogado [COMPLETAR]

Firma del querellante

================================================================================
