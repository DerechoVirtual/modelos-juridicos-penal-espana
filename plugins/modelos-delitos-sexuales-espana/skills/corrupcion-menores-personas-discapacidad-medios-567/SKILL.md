---
name: corrupcion-menores-personas-discapacidad-medios-567
description: "Redacta el escrito «Corrupción de menores o personas con discapacidad por medios tecnológicos: defensa con conformidad» (formulario 567 de delitos sexuales, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Corrupción de menores o personas con discapacidad por medios tecnológicos: defensa con conformidad

> Formulario 0567 del plugin **Delitos sexuales** · revisado el 17-11-2026.

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

- [ ] SEDE (3 veces)
- [ ] Nº (3 veces)
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] PENA
- [ ] IMPORTE
- [ ] LUGAR

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (1)

Inclúyelos solo si encajan en los hechos:

- (Si la pena con la que se conforma es de prisión de 2 años)…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 188 CP
- art. 784.3 LECRIM
- art. 787 LECRIM
- art. 787 ter LECRIM
- art. 785 LECRIM
- art. 80 CP
- art. 14.6 LECRIM
- art. 14.5 LECRIM
- art. 89.5 LOPJ
- artículos 14.7 LECrim
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

### Formulario 0567 · Corrupción de menores o personas con discapacidad por medios tecnológicos: defensa con conformidad

- Año del modelo: 2018
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (4); 1 bloques de alternativas señalados; 1 párrafos opcionales señalados; 6 campos de relleno marcados en blanco; 3 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que el acusado se conforma con la calificación de los hechos como delito de corrupción de menores del art. 188 CP, al obligar a un menor de edad o discapacitado a mantener relaciones sexuales con adultos a cambio de precio, para hacer videos y fotografías y luego colgarlos en un blog de acceso bajo pago. Si se pacta la pena de prisión más baja posible para este delito, la de 2 años, se solicitará también la suspensión de la ejecución de la pena.

Actualizado conforme a la LO 1/2025, de Eficiencia de la Justicia.

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

A la Sección de Violencia sobre la Mujer del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

A la Sección de Violencia contra la Infancia y la Adolescencia del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales en la representación que tiene acreditada de D./Dña. [NOMBRE Y APELLIDOS], acusado/a en las diligencias previas número [Nº DE PROCEDIMIENTO], por el supuesto delito del art. 188 CP, comparezco ante este órgano judicial (1) y, como mejor proceda en derecho, DIGO:

Que, conforme al Protocolo de conformidades suscrito entre la Fiscalía General del Estado y el Consejo General de la Abogacía de fecha 1 de abril de 2009 (2) y el art. 784.3 LECRIM, en relación con el art. 787 LECRIM (hasta el 2/4/2025) art. 787 ter LECRIM (desde el 3/4/2025), se formula escrito de conformidad con la calificación de los hechos como corrupción de menores del art. 188 CP.

En este sentido, la defensa se conforma con la petición formulada por la Fiscalía a la pena de [PENA] (3) y al pago de [IMPORTE] euros de indemnización al querellante, a ratificar en la audiencia preliminar del art. 785 LECRIM (desde el 3/4/2025)..

[OPCIONAL — incluir si procede]

(Si la pena con la que se conforma es de prisión de 2 años)

Se interesa se conceda la suspensión de la ejecución de la pena del art. 80 CP y ss que por la defensa se solicita con ocasión del presente escrito, por concurrir los requisitos legales. (4)

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita, tenga por evacuado el trámite por la conformidad de la defensa y por interesada la medida de suspensión de la ejecución de la pena.

Es de Justicia que pido en [LUGAR]

Firma de Abogado/a:	Firma del acusado/a:

NOTAS DEL FORMULARIO

(1) Cuando la víctima sea un niño, niña o adolescente la competencia para la instrucción es de la Sección de Violencia contra la Infancia y la Adolescencia, si la hay (art. 14.6 LECRIM y art. 89 bis 5 LOPJ). Pero lo es la Sección de Violencia sobre la Mujer del Tribunal de Instancia cuando la víctima sea o haya sido su esposa, o mujer que esté o haya estado ligada al autor por análoga relación de afectividad, aun sin convivencia, así como de los cometidos sobre los descendientes, propios o de la esposa o conviviente, o sobre los menores o personas con discapacidad que con él convivan o que se hallen sujetos a la potestad, tutela, curatela, acogimiento o guarda de hecho de la esposa o conviviente, cuando también se haya producido un acto de violencia de género y, desde el 3 de octubre de 2025, tras la reforma operada por la LO 1/2025, de Eficiencia de la Justicia, también instruye estos delitos cuando la víctima sea una mujer (art. 14.5 LECRIM y art. 89.5 LOPJ). Los artículos 14.7 LECrim y art. 89 bis 7 LOPJ disponen que "en caso de que los hechos objeto de instrucción por la Sección de Violencia contra la Infancia y Adolescencia también pudieran ser conocidos por la Sección de Violencia sobre la Mujer, la competencia corresponderá, en todo caso, a la segunda". Entonces, si la víctima fuera niña o chica correspondería a las Secciones de Violencia sobre la Mujer, pero el grupo de expertos del Observatorio de Violencia Doméstica y de Género del CGPJ interpreta que solo irá a la Sección de Violencia sobre la Mujer en los siguientes casos: (I) En los supuestos de violencia vicaria, cuando los niños, niñas o adolescentes son víctimas de la violencia ejercida sobre la madre; (II) Cuando la violencia sobre la menor es ejercida por su pareja o ex pareja.

(2) En base al protocolo de conformidades suscrito entre la Fiscalía General del Estado y el Consejo General de la Abogacía de fecha 1 de abril de 2009 se puede presentar escrito del abogado defensor antes del señalamiento de juicio oral incluso después de evacuado el trámite de calificación.

(3) En este caso podría pactarse la conformidad en los dos años de prisión para conseguir la suspensión de la ejecución de la pena,

Además, procede imponer la pena de prohibición de comunicación con la víctima, o con aquellos de sus familiares u otras personas que determine el juez, prevista en el art. 48.3 CP, la pena de prohibición de aproximarse a la víctima o familiares u otras personas que determine el juez, prevista en el art. 48.2 CP y la de prohibición de acceso a internet, en atención a la prohibición de regreso al lugar del delito del art. 48.1 y 57 CP, que en este caso ha sido la red de internet en cualquiera de sus modalidades.

(4) Es importante instar ya ambos la petición de suspensión de ejecución de la pena con el apoyo de la fiscalía para garantizarla y evitar el ingreso en prisión.

================================================================================
