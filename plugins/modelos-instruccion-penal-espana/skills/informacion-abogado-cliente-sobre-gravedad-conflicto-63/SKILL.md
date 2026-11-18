---
name: informacion-abogado-cliente-sobre-gravedad-conflicto-63
description: "Redacta el escrito «Información del abogado al cliente sobre la gravedad del conflicto y estrategia (art. 6 LO 5/2024)» (formulario 63 de instrucción y procedimiento penal, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Información del abogado al cliente sobre la gravedad del conflicto y estrategia (art. 6 LO 5/2024)

> Formulario 0063 del plugin **Instrucción y procedimiento penal** · revisado el 17-11-2026.

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

- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] LOCALIDAD
- [ ] FECHA

## Elecciones que hay que hacer

- b) La estrategia procesal más adecuada es la siguiente. / c) El asunto se encuentra en la fase de. / d) Los costos generales del proceso serán .

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículos 27, 28, 48.4 y 49 del RD 135/2021
- art. 6 de la Ley Orgánica 5/2024

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

### Formulario 0063 · Información del abogado al cliente sobre la gravedad del conflicto y estrategia (art. 6 LO 5/2024)

- Año del modelo: 2024
- Revisión 17-11-2026: 1 llamadas a nota sin texto retiradas; 1 desplegables y casillas convertidos en elección en blanco; 4 campos de relleno marcados en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Para D/Dña [NOMBRE Y APELLIDOS]

D/Dña [NOMBRE Y APELLIDOS] con DNI con domicilio profesional en [LOCALIDAD], letrado/a en ejercicio del Ilustre Colegio de Abogados de con número de colegiado y actuando profesionalmente por encargo de la persona a la que se dirige el presente escrito, por medio del mismo,

DIGO:

Con fecha [FECHA] se firmó por el/la letrado/a firmante de la presente comunicación una hoja de encargo profesional con Ud respecto al ejercicio de acción judicial consistente en.

La nota de encargo está regulada en los artículos 27, 28, 48.4 y 49 del RD 135/2021, de 2 de marzo por el que se aprueba el Estatuto General de la Abogacía Española y en el artículo 15 del Código Deontológico de la Abogacía Española.

La razón de la presente comunicación profesional tiene por base, sin embargo, informarle de los aspectos recogidos en el art. 6 de la Ley Orgánica 5/2024, de 11 de noviembre, del Derecho de Defensa.

Es por ello por lo que se le da cumplida información sobre los siguientes extremos:

a) Sus intereses y derechos pueden verse afectados de la siguiente manera
Su petición es viable de la siguiente manera: [ELEGIR: b) La estrategia procesal más adecuada es la siguiente. / c) El asunto se encuentra en la fase de. / d) Los costos generales del proceso serán .]

Los honorarios profesionales se han fijado de la siguiente manera.

Debe tener en cuenta que, si se le condena en costas deberá hacerse cargo también del coste de los honorarios de la parte contraria que podrán ascender a, en base a los criterios orientativos publicados por el Colegio de Abogados de.

f) Además, deberá tener en cuenta los siguientes aspectos:
g) Puede solicitar el reconocimiento del derecho a la asistencia jurídica gratuita del siguiente modo

Por lo expuesto,

Sirva por dado cumplimiento a lo dispuesto en el art. 6 de la LEY ORGÁNICA 5/2024, DE 11 DE NOVIEMBRE, DEL DERECHO DE DEFENSA.

Firma de letrado/a

================================================================================
