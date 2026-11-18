---
name: narcotrafico-defensa-conformidad-juicio-rapido-792
description: "Redacta el escrito «Narcotráfico: defensa con conformidad en juicio rápido» (formulario 792 de salud pública y maltrato animal, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Narcotráfico: defensa con conformidad en juicio rápido

> Formulario 0792 del plugin **Salud pública y maltrato animal** · revisado el 17-11-2026.

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
- [ ] COLEGIO
- [ ] Nº DE COLEGIADO/A
- [ ] LOCALIDAD
- [ ] PENA
- [ ] LUGAR
- [ ] FECHA

## Párrafos opcionales (1)

Inclúyelos solo si encajan en los hechos:

- (Si la pena con la que se conforma es igual o inferior a 2 años)…

## Correcciones de la revisión (2)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 368 CP
- artículo 801 de la Ley de Enjuiciamiento Criminal
- art. 801.2 LECrim
- art. 80 CP
- art. 795.1.2.g) LECRIM

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

### Formulario 0792 · Narcotráfico: defensa con conformidad en juicio rápido

- Año del modelo: 2016
- Revisión 17-11-2026: 2 puntualizaciones normativas añadidas en el texto; restos de formato retirados; notas del formulario agrupadas al final (4); 1 párrafos opcionales señalados; 7 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito de la defensa en juicio rápido conformándose con la pena solicitada por la acusación por delito contra la salud pública del art. 368 CP y solicitando al mismo tiempo la suspensión de la ejecución de la pena.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Letrado/a (1) del Ilustre Colegio de Abogados de [COLEGIO], con nº de colegiado/a [Nº DE COLEGIADO/A] y con despacho profesional abierto en [LOCALIDAD], en representación del/de la acusado/a D./Dña. [NOMBRE Y APELLIDOS], en el procedimiento / por el supuesto delito contra la salud pública del art. 368 CP, comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

Que, conforme al artículo 801 de la Ley de Enjuiciamiento Criminal, formulo escrito de defensa manifestando la conformidad con el escrito de acusación presentado por el Ministerio Fiscal, que solicita la pena de [PENA] de prisión, firmando también el/la acusado/a en prueba de conformidad al concurrir los supuestos previstos en el inciso segundo del art. 368 CP en relación al art. 795.1.2º g) LECRIM. (2) (3)

[OPCIONAL — incluir si procede]

(Si la pena con la que se conforma es igual o inferior a 2 años)

Al mismo tiempo, y en base al art. 801.2 LECrim, intereso le sea concedida la suspensión de la ejecución de la pena al concurrir los presupuestos del art. 80 CP y ss, habida cuenta que el/la juez/a a la vista de la conformidad podrá declarar oralmente la sentencia y resolver sobre la suspensión interesada. (4)

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita, tenga por evacuado el trámite por la defensa, manifestada la conformidad con el escrito de acusación del Fiscal y por interesada la medida de suspensión de la ejecución de la pena.

Es de Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a:	Firma de acusado/a:

NOTAS DEL FORMULARIO

(1) El abogado designado para la defensa tendrá también habilitación legal para la representación de su defendido en todas las actuaciones ante el juez de guardia. (Art. 797.3 LECrim).

(2) Puede acudirse a la vía del juicio rápido en la guardia porque lo permite el art. 795.1.2.g) LECRIM cuando se aleguen las circunstancias del inciso segundo del art. 368 CP.

(3) Solo puede prestarse conformidad por la vía del art. 801.1.2º LECrim en el caso de calificación por delito castigado con pena de hasta tres años de prisión en juicio rápido en el que está admitido el de salud pública del art. 368 CP si se le aplica la rebaja en un tercio de la pena.

(4) Para acordar, en su caso, la suspensión de la pena privativa de libertad bastará, a los efectos de lo dispuesto en el artículo 81.3.ª del Código Penal [NOTA DE REVISIÓN (comprobar): Cita literal del art. 801.3 LECrim, no actualizada: tras la LO 1/2015 el requisito de satisfacer la responsabilidad civil está en el art. 80.2.3.ª CP. Fuente: Código Penal, BOE-A-1995-25444, art. 80.2.3.ª; LECrim, BOE-A-1882-6036, art. 801.3.], con el compromiso del acusado de satisfacer las responsabilidades civiles que se hubiesen originado en el plazo prudencial que el juez de guardia fije. Asimismo, en los casos en que de conformidad con el artículo 87.1.1.ª del Código Penal [NOTA DE REVISIÓN (comprobar): La suspensión para penados drogodependientes está hoy en el art. 80.5 CP (el art. 87 fue reformado por la LO 1/2015). Fuente: Código Penal, BOE-A-1995-25444, art. 80.5.] sea necesaria una certificación suficiente por centro o servicio público o privado debidamente acreditado u homologado de que el acusado se encuentra deshabituado o sometido a tratamiento para tal fin, bastará para aceptar la conformidad y acordar la suspensión de la pena privativa de libertad el compromiso del acusado de obtener dicha certificación en el plazo prudencial que el juez de guardia fije. (Art. 801.3 LECrim).

================================================================================
