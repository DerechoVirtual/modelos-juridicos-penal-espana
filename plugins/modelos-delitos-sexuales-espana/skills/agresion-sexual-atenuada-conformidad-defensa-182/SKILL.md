---
name: agresion-sexual-atenuada-conformidad-defensa-182
description: "Redacta el escrito «Agresión sexual atenuada: conformidad de la defensa» (formulario 182 de delitos sexuales, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Agresión sexual atenuada: conformidad de la defensa

> Formulario 0182 del plugin **Delitos sexuales** · revisado el 17-11-2026.

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

- Formulario en la versión de la LO 10/2022 (existe versión «LO 4/2023»). Desde el 29-4-2023 el tipo atenuado es el art. 178.4 CP (mitad inferior o multa de 18 a 24 meses) y no se aplica con violencia, intimidación o voluntad anulada, que el art. 178.3 castiga con uno a cinco años.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] Nº DE PROCEDIMIENTO (2 veces)
- [ ] COLEGIO
- [ ] LOCALIDAD
- [ ] PENA
- [ ] LUGAR
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «…, en representación del/de la acusado/a»

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (1)

Inclúyelos solo si encajan en los hechos:

- (Si la pena con la que se conforma es de prisión igual o inferior a 2 años)…

## Correcciones de la revisión (2)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 178.3 CP
- art. 784.3 LECRIM
- art. 787 ter LECRIM
- art. 80 CP

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

### Formulario 0182 · Agresión sexual atenuada: conformidad de la defensa

- Año del modelo: 2022
- Revisión 17-11-2026: 2 citas normativas corregidas tras comprobarlas en el BOE; 1 puntualizaciones normativas añadidas en el texto; 5 llamadas a nota sin texto retiradas; 1 bloques de alternativas señalados; 1 párrafos opcionales señalados; 11 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 1 notas de revisión repetidas retiradas
- Avisos de la revisión: Formulario en la versión de la LO 10/2022 (existe versión «LO 4/2023»). Desde el 29-4-2023 el tipo atenuado es el art. 178.4 CP (mitad inferior o multa de 18 a 24 meses) y no se aplica con violencia, intimidación o voluntad anulada, que el art. 178.3 castiga con uno a cinco años.

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales en la representación que tiene acreditada de D./Dña. [NOMBRE Y APELLIDOS], acusado/a en las diligencias previas número [Nº DE PROCEDIMIENTO], por el supuesto delito de agresión sexual del art. 178.3 CP [NOTA DE REVISIÓN: Numeración de la LO 10/2022 (hechos del 7-10-2022 al 28-4-2023). Para hechos posteriores el tipo atenuado es el art. 178.4 CP (LO 4/2023): mitad inferior de la pena o multa de 18 a 24 meses, excluido si hay violencia, intimidación, voluntad anulada o circunstancias del art. 180. Fuente: Código Penal, BOE-A-1995-25444, art. 178 (redacción LO 4/2023, BOE-A-2023-10213).], comparezco ante este órgano judicial y, como mejor proceda en derecho,

D./Dña. [NOMBRE Y APELLIDOS], Letrado/a del Ilustre Colegio de Abogados de [COLEGIO], con nº de colegiado y con despacho profesional abierto en [LOCALIDAD], en representación del/de la acusado/a [COMPLETAR], en las diligencias previas número [Nº DE PROCEDIMIENTO] por el supuesto delito de agresión sexual del art. 178.3 CP, comparezco ante este órgano judicial y, como mejor proceda en derecho,

DIGO:

Que, conforme al Protocolo de conformidades suscrito entre la Fiscalía General del Estado y el Consejo General de la Abogacía de fecha 1 de abril de 2009 y el art. 784.3 LECRIM, en relación con el art. 787 ter LECRIM, se formula [NOTA DE REVISIÓN: Desde el 3-4-2025 la conformidad en el procedimiento abreviado se regula en el art. 787 ter LECrim, introducido por la LO 1/2025. Fuente: LO 1/2025, BOE-A-2025-76 (art. 787 ter LECrim).] escrito de conformidad con los hechos calificados como delito del art. 178.3 CP.

En este sentido, la defensa se conforma con la petición formulada por la Fiscalía, en los términos del art. 787 ter LECRIM, para D./Dña. [NOMBRE Y APELLIDOS], a la pena de [PENA].

[OPCIONAL — incluir si procede]

(Si la pena con la que se conforma es de prisión igual o inferior a 2 años)

Al haberse satisfecho las responsabilidades civiles y no existir antecedentes penales, se interesa se conceda la suspensión de la ejecución de la pena del art. 80 CP y ss que por la defensa se solicita con ocasión del presente escrito, por concurrir los requisitos legales.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita, tenga por evacuado el trámite por la conformidad de la defensa y por interesada la medida de suspensión de la ejecución de la pena.

Es de Justicia que pido en [LUGAR]

Firma de Abogado/a	Firma de el/la acusado/a

================================================================================
