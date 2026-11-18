---
name: fiscalia-europea-reclamacion-civil-actor-civil-324
description: "Redacta el escrito «Fiscalía Europea: reclamación civil del actor civil» (formulario 324 de procedimiento de la fiscalía europea, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Fiscalía Europea: reclamación civil del actor civil

> Formulario 0324 del plugin **Procedimiento de la Fiscalía Europea** · revisado el 17-11-2026.

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
- [ ] NÚMERO
- [ ] ÓRGANO
- [ ] Nº
- [ ] FECHA (2 veces)
- [ ] DELITO
- [ ] IMPORTE
- [ ] LUGAR
- [ ] Otros 18 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…dad española y sin antecedentes penales,»; «…, tipificado y penado en los artículos»; «… delito son responsables, en concepto de»; «…ales. Asimismo, se acordará el comiso de»; «…bienes decomisados el siguiente destino:»; «…n, los cuales deberán ser testimoniados:»; «…rar las siguientes fuentes de prueba: a)»; «…b)»; «…as fuentes de prueba son los siguientes:»; «… de utilizarse para el aseguramiento son»; «…se justifican por los siguientes hechos:»; «…. 2.- Testifical de»; …

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículos 114 a 116 de la Ley Orgánica 9/2021
- artículo 116.1 de la Ley Orgánica 9/2021

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

### Formulario 0324 · Fiscalía Europea: reclamación civil del actor civil

- Año del modelo: 2021
- Revisión 17-11-2026: 1 rangos de artículos despegados («25 a31» → «25 a 31»); 29 campos de relleno marcados en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

AL JUEZ DE GARANTÍAS

D./Dª [NOMBRE Y APELLIDOS], Procurador de los Tribunales, actuando en nombre y representación del actor civil de D./Dª [NOMBRE Y APELLIDOS], según consta en el apoderamiento que obra en autos, comparezco en el Procedimiento de Investigación de la Fiscalía Europea número [NÚMERO], y, como mejor proceda en derecho, digo:

Que, de conformidad con lo dispuesto en los artículos 114 a 116 de la Ley Orgánica 9/2021, de 1 de julio, de la Fiscalía Europea, esta representación formula escrito de reclamación civil contra D./Dª [NOMBRE Y APELLIDOS], y solicita la apertura del juicio oral ante [ÓRGANO], formulando las siguientes

Conclusiones provisionales

PRIMERA.- Sobre las [Nº] horas del día [FECHA], las personas acusadas D./Dª [NOMBRE Y APELLIDOS], de nacionalidad española y sin antecedentes penales, [COMPLETAR]

SEGUNDA.- Los hechos descritos son constitutivos de un delito de [DELITO], tipificado y penado en los artículos [COMPLETAR] del Código Penal.

TERCERA.- Del mencionado delito son responsables, en concepto de [COMPLETAR], las personas acusadas.

CUARTA.- No concurren circunstancias modificativas de la responsabilidad criminal.

QUINTA.- Los acusados, como responsables civiles directos y solidarios, quedan obligados a indemnizar a mi mandante, con la cantidad de [IMPORTE] euros, más los intereses legales. Asimismo, se acordará el comiso de [COMPLETAR], debiendo aplicarse a estos bienes decomisados el siguiente destino: [COMPLETAR].

OTROSÍ I.- Se interesa el mantenimiento de las siguientes medidas cautelares:

OTROSÍ II.- Para el caso de que se disponga la apertura del juicio oral, se designan los siguientes particulares del procedimiento de investigación, los cuales deberán ser testimoniados: [COMPLETAR].

OTROSÍ III.- De conformidad con lo dispuesto en los artículos 116.3, así como 96 y siguientes de la Ley Orgánica 9/2021, de 1 de julio, de la Fiscalía Europea, esta representación promueve incidente para asegurar las siguientes fuentes de prueba:

a) [COMPLETAR]

b) [COMPLETAR]

Los hechos y motivos que justifican el aseguramiento de estas fuentes de prueba son los siguientes: [COMPLETAR].

Los particulares del procedimiento que habrán de utilizarse para el aseguramiento son [COMPLETAR].

Para el acto del juicio oral, se interesa la práctica de las siguientes pruebas:

1.- Interrogatorio de las personas acusadas. La pertinencia y utilidad de esta prueba se justifican por los siguientes hechos: [COMPLETAR].

2.- Testifical de [COMPLETAR]. La pertinencia y utilidad de esta prueba se justifican por los siguientes hechos: [COMPLETAR].

3.- Pericial de [COMPLETAR]. La pertinencia y utilidad de esta prueba se justifican por los siguientes hechos: [COMPLETAR].

4.- Documental contraída a la lectura de los siguientes documentos de las actuaciones: [COMPLETAR]. La pertinencia y utilidad de esta prueba se justifican por los siguientes hechos: [COMPLETAR].

De conformidad con lo establecido en el artículo 116.1 de la Ley Orgánica 9/2021, de 1 de julio, de la Fiscalía Europea, la reclamación de los documentos, así como las citaciones de los peritos y los testigos deberán realizarse por medio de la oficina judicial.

En su virtud, puede servirse el Juez de Garantías tener por formulada la reclamación civil, y dar a las diligencias el curso legal correspondiente.

En [LUGAR], a [FECHA].

Firma del Procurador [COMPLETAR]

Firma del Abogado

================================================================================
