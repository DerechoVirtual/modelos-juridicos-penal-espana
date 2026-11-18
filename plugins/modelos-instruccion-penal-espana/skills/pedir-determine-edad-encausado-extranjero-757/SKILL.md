---
name: pedir-determine-edad-encausado-extranjero-757
description: "Redacta el escrito «Pedir que se determine la edad del encausado extranjero» (formulario 757 de instrucción y procedimiento penal, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Pedir que se determine la edad del encausado extranjero

> Formulario 0757 del plugin **Instrucción y procedimiento penal** · revisado el 17-11-2026.

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

- [ ] NOMBRE Y APELLIDOS
- [ ] NOMBRE DEL REPRESENTADO/A
- [ ] Nº DE PROCEDIMIENTO
- [ ] LOCALIDAD
- [ ] LUGAR
- [ ] DÍA
- [ ] MES
- [ ] AÑO
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «… solicitará de la Fiscalía Provincial de»; «… 478 LECRIM y arts. 762.7ª y 778 LECRIM,»

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 311 LECRIM
- art. 166 RD 1155/2024
- artículo 311 de la Ley de Enjuiciamiento Criminal
- art. 166 del Real Decreto 1155/2024
- artículo 35 de la Ley Orgánica 4/2000
- artículos 339, 399, 478 LECRIM

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

### Formulario 0757 · Pedir que se determine la edad del encausado extranjero

- Año del modelo: 2016
- Revisión 17-11-2026: 1 puntualizaciones normativas añadidas en el texto; 7 campos de relleno marcados en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que se solicita que se practiquen las diligencias necesarias para determinar la edad de una persona extranjera encausada, conforme al art. 311 LECRIM y al art. 166 RD 1155/2024, de 19 de noviembre, reglamento de extranjería.

Actualizado conforme a la LO 1/2025, de Eficiencia de la Justicia.

A la Sección de Instrucción del Tribunal de Instancia deplazanº

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, actuando en nombre y representación de [NOMBRE DEL REPRESENTADO/A], según consta acreditado en autos, comparezco en el Procedimiento nº [Nº DE PROCEDIMIENTO] que se tramita en ese órgano judicial y, como mejor proceda en Derecho, DIGO:

Que, a la vista de los actos de investigación llevados a cabo hasta la fecha y cuya resultancia obra en autos, y de conformidad con lo dispuesto en el artículo 311 de la Ley de Enjuiciamiento Criminal, esta representación, existiendo indicios de que mi representado/a es menor de edad, interesa la práctica de las siguientes

DILIGENCIAS

a) Al amparo de lo dispuesto en el art. 166 del Real Decreto 1155/2024 [NOTA DE REVISIÓN: Precepto vigente. La STS de 8-7-2026 (BOE-A-2026-19632) anuló un inciso del párrafo segundo del apartado 1: la atención inmediata del art. 35.3 LOEX es obligatoria desde que se comunica la localización del extranjero de edad incierta. Fuente: RD 1155/2024, BOE-A-2024-24099, art. 166.], de 19 de noviembre, por el que se aprueba el Reglamento de la Ley Orgánica 4/2000, de 11 de enero, sobre derechos y libertades de los extranjeros en España y su integración social, deberá solicitarse de la Brigada de Extranjería del Cuerpo Nacional de Policía una certificación relativa a si la persona que se halla inculpada en el presente procedimiento figura como menor de edad en el Registro de Menores Extranjeros No Acompañados (MENA).

b) En el supuesto de que la diligencia anterior arroje resultado negativo por no hallarse mi representado/a inscrito en el Registro de Menores Extranjeros No Acompañados, se solicitará de la Fiscalía Provincial de [COMPLETAR] información relativa a si al/a la encausado/a le ha sido practicada la prueba de determinación de la edad a que se refiere el artículo 35 de la Ley Orgánica 4/2000 de 11 de enero, sobre Derechos y Libertades de los Extranjeros en España y su Integración Social, y, en caso de respuesta afirmativa, que se aporte a esta causa una copia del Decreto del Ministerio Fiscal en el que se determina dicha edad.

c) En el supuesto de que la diligencia indicada en el apartado anterior arroje resultado negativo y de conformidad con lo dispuesto en los artículos 339, 399, 478 LECRIM y arts. 762.7ª y 778 LECRIM, [COMPLETAR] se deberá citar a mi representado/a en la Clínica Médico Forense, al objeto de que le sea practicada la prueba médica para la determinación de la edad.

En el caso de que cualesquiera de las diligencias antes mencionadas acredite que el encausado es menor de edad, esta representación interesa que, por el Juez de instrucción se acuerde la inhibición o se remita testimonio de particulares a favor de la Sección de Menores de la Fiscalía Provincial de [LOCALIDAD].

En su virtud,

SUPLICO A LA SECCIÓN:

Tener por hechas las manifestaciones contenidas en el presente escrito y en las copias que se acompañan, y, previa audiencia del Ministerio Fiscal, acordar la práctica de las diligencias interesadas, dándose al procedimiento el curso legal que corresponda.

En [LUGAR], a [DÍA] de [MES] de [AÑO].

Firma de Abogado/a	Firma de Procurador/a

================================================================================
