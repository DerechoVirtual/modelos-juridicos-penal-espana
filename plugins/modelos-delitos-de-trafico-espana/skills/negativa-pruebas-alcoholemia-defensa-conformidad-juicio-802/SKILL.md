---
name: negativa-pruebas-alcoholemia-defensa-conformidad-juicio-802
description: "Redacta el escrito «Negativa a las pruebas de alcoholemia: defensa con conformidad en juicio rápido» (formulario 802 de seguridad vial, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Negativa a las pruebas de alcoholemia: defensa con conformidad en juicio rápido

> Formulario 0802 del plugin **Seguridad vial** · revisado el 17-11-2026.

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
- [ ] LUGAR
- [ ] FECHA
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…,»; «…, [COMPLETAR],»

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 383 CP
- artículo 801 de la Ley de Enjuiciamiento Criminal
- art. 801.2 LECrim
- art. 80 CP
- artículo 787 ter LECrim
- artículo 789 LECrim

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

### Formulario 0802 · Negativa a las pruebas de alcoholemia: defensa con conformidad en juicio rápido

- Año del modelo: 2016
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (3); 8 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la defensa en un juicio rápido se conforma con la pena solicitada por el fiscal por delito de negativa a someterse a las pruebas de alcoholemia del art. 383 CP y así verá reducida la pena en un tercio y puede solicitar, además, la suspensión de la ejecución de la pena.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Letrado/a del Ilustre Colegio de Abogados de [COLEGIO], con nº de colegiado [Nº DE COLEGIADO/A] y con despacho profesional abierto en [LOCALIDAD], [COMPLETAR], [COMPLETAR] (1) en representación del acusado/a D./Dña. [NOMBRE Y APELLIDOS], en el procedimiento / por el supuesto delito de negativa a someterse a la prueba de alcoholemia del art. 383 CP, comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

Que, conforme al artículo 801 de la Ley de Enjuiciamiento Criminal, formulo escrito de defensa manifestando la conformidad con el escrito de acusación presentado por el Ministerio Fiscal, que solicita la pena (2) de cuatro meses de prisión y privación del derecho a conducir vehículos a motor y ciclomotores por tiempo de ocho meses, firmando también el acusado en prueba de conformidad.

Al mismo tiempo y en base al art. 801.2 LECrim intereso le sea concedida la suspensión de la ejecución de la pena, al concurrir los presupuestos del art. 80 CP y ss, habida cuenta que el juez a la vista de la conformidad podrá declarar oralmente la sentencia y resolver sobre la suspensión interesada. (3)

Por lo expuesto,

SUPLICO A LA SECCIÓN:

que tenga por presentado este escrito, lo admita, tenga por evacuado el trámite por la defensa y manifestada la conformidad con el escrito de acusación del Fiscal.

Por ser de Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de acusado/a

NOTAS DEL FORMULARIO

(1) El abogado designado para la defensa tendrá también habilitación legal para la representación de su defendido en todas las actuaciones ante el juez de guardia. (Art. 797.3 LECrim).

(2) En juicio rápido solo puede prestarse conformidad por la vía del art. 801.1.2º LECrim en el caso de calificación por delito castigado con pena de hasta tres años de prisión o pena de multa, cualquiera que sea su cuantía, u otra pena de distinta naturaleza de duración no superior a 10 años, en el que está incluido el de negativa a someterse a la prueba de alcoholemia del art. 383 CP.

El juez de guardia realizará el control de la conformidad prestada en los términos previstos en el artículo 787 ter LECrim y, en su caso, dictará oralmente sentencia de conformidad que se documentará con arreglo a lo previsto en el apartado 2 del artículo 789 LECrim, en la que impondrá la pena solicitada reducida en un tercio, aun cuando suponga la imposición de una pena inferior al límite mínimo previsto en el Código Penal. Si el fiscal y las partes personadas expresasen su decisión de no recurrir, el juez, en el mismo acto, declarará oralmente la firmeza de la sentencia y, si la pena impuesta fuera privativa de libertad, resolverá lo procedente sobre su suspensión (Art. 801.2 LECrim).

(3) Para acordar, en su caso, la suspensión de la pena privativa de libertad bastará, a los efectos de lo dispuesto en el artículo 80.2. 3.ª del Código Penal, con el compromiso del acusado de satisfacer las responsabilidades civiles que se hubiesen originado en el plazo prudencial que el juez de guardia fije. (Art. 801.3 LECrim)

Conforme al art. 83.1.7º CP el juez podrá anudar también la suspensión de la ejecución de la pena a participar en programas de deshabituación al consumo de alcohol, drogas tóxicas o sustancias estupefacientes, o de tratamiento de otros comportamientos adictivos.]

================================================================================
