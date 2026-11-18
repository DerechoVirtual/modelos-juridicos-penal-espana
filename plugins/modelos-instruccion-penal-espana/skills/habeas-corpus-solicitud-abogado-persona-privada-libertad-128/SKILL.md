---
name: habeas-corpus-solicitud-abogado-persona-privada-libertad-128
description: "Redacta el escrito «Habeas corpus: solicitud del abogado de la persona privada de libertad» (formulario 128 de instrucción y procedimiento penal, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Habeas corpus: solicitud del abogado de la persona privada de libertad

> Formulario 0128 del plugin **Instrucción y procedimiento penal** · revisado el 17-11-2026.

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
- [ ] Nº (3 veces)
- [ ] NOMBRE Y APELLIDOS (6 veces)
- [ ] COLEGIO
- [ ] DNI/NIE
- [ ] FECHA (2 veces)
- [ ] Otros 5 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…con el número de colegiación»; «…l fue detenido por agentes de la Policía»; «… declaración prestada en la Comisaría de»; «…o en las dependencias de la Comisaría de»; «…, de conformidad al art. 7 LO 6/1984. En»

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 3.d) de la LO 6/1984
- art. 1.c) de la LO 6/1984
- art. 7 LO 6/1984

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

### Formulario 0128 · Habeas corpus: solicitud del abogado de la persona privada de libertad

- Año del modelo: 2023
- Revisión 17-11-2026: 17 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, Abogado en ejercicio del Iltre. Colegio de Abogados de [COLEGIO] con el número de colegiación [COMPLETAR], actuando en representación de mi defendido D./Dña. [NOMBRE Y APELLIDOS], mediante el presente escrito, conforme al art. 3.d) de la LO 6/1984, formulo solicitud de incoación de procedimiento de «Habeas Corpus» en base a los siguientes

MOTIVOS:

PRIMERO. Nombre y circunstancias personales del solicitante y del privado de libertad

El solicitante actúa en representación de D./Dña. [NOMBRE Y APELLIDOS], con DNI [DNI/NIE], el cual fue detenido por agentes de la Policía [COMPLETAR] el pasado día [FECHA] a las [Nº] horas, habiendo sido asistido por el Letrado que suscribe en la declaración prestada en la Comisaría de [COMPLETAR] el pasado día [FECHA] a las [Nº] horas.

SEGUNDO. Lugar de privación de libertad y circunstancias relevantes

Tras haber asistido a mi defendido en la citada diligencia, éste permaneció detenido en las dependencias de la Comisaría de [COMPLETAR], habiendo sido informado quien suscribe por parte de los funcionarios que practicaron la declaración que mi defendido pasaría a disposición judicial en la mañana de ayer, sin que ello se haya producido y sin que haya tenido noticias sobre su paradero.

TERCERO. Motivo de solicitud

De acuerdo con lo relatado, han transcurrido más de setenta y dos horas desde la detención policial de D./Dña. [NOMBRE Y APELLIDOS] por lo que me veo en la obligación de instar en su representación la incoación del procedimiento de «habeas corpus», por concurrir la causa del art. 1.c) de la LO 6/1984, al haberse rebasado el plazo de detención, sin que mi defendido haya sido puesto en libertad ni tampoco entregado al Juez de Instrucción.

Por lo expuesto, SUPLICO A LA SECCIÓN que proceda a la incoación de procedimiento de «habeas corpus» en relación a la privación de libertad de D./Dña. [NOMBRE Y APELLIDOS] y, previos los trámites legales, se dicte auto declarando ilegal la detención, con los pronunciamientos inherentes, y acordando la inmediata puesta a disposición judicial de D./Dña. [NOMBRE Y APELLIDOS].

OTROSÍ DIGO que a los efectos de acreditar lo anterior aporto con este escrito copia de las diligencias policiales entregadas al que suscribe en el momento de la asistencia al detenido, donde constan la fecha y motivos de la detención, y demás circunstancias identificativas.

Por lo que SUPLICO A LA SECCIÓN admita este documento, de conformidad al art. 7 LO 6/1984.

En [COMPLETAR]

Firma Abogado

================================================================================
