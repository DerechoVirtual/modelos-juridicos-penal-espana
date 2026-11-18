---
name: declinatoria-falta-competencia-objetiva-razon-materia-231
description: "Redacta el escrito «Declinatoria por falta de competencia objetiva por razón de la materia» (formulario 231 de instrucción y procedimiento penal, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Declinatoria por falta de competencia objetiva por razón de la materia

> Formulario 0231 del plugin **Instrucción y procedimiento penal** · revisado el 17-11-2026.

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

## Nota explicativa: puntualizaciones de la revisión

La nota explicativa de este formulario se ha revisado en el BOE. Tenlo en cuenta al redactar:

- El art. 65 LOPJ fija la competencia de la Sala de lo Penal de la Audiencia Nacional para el enjuiciamiento. La de la Sección de Instrucción del Tribunal Central de Instancia está en el art. 95.a) LOPJ: instruye las causas que juzga la Sala de lo Penal de la Audiencia Nacional o la Sección de lo Penal del propio Tribunal Central (ambos en la redacción de la LO 1/2025, vigentes desde el 23-1-2025).
- Los antiguos Juzgados Centrales de Instrucción se transformaron en esa Sección el 31-12-2025, con la fase de «los restantes Juzgados» (DT 1.ª, ordinal 3.º, LO 1/2025). Para asuntos anteriores a esa fecha, el destinatario era el Juzgado Central de Instrucción.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión. Empieza con una nota explicativa (para qué sirve el escrito y cuándo se usa), revisada en el BOE: léela antes de redactar, pero no la copies en el escrito.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] NOMBRE DEL REPRESENTADO/A (2 veces)
- [ ] NÚMERO
- [ ] Nº DE DOCUMENTO
- [ ] LOCALIDAD
- [ ] Nº DE COLEGIADO
- [ ] COLEGIO
- [ ] Nº DE PROCEDIMIENTO
- [ ] ACTO O RESOLUCIÓN
- [ ] NÚMERO DE LA CALLE
- [ ] Otros 3 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «… maniobras defraudatorias realizadas por»; «…de Administrador Único de la Aseguradora»; «…ón del Tribunal Central de Instancia. En»

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 26 de la LECRIM
- art. 65.1 c) de la LOPJ

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

### Formulario 0231 · Declinatoria por falta de competencia objetiva por razón de la materia

- Año del modelo: 2022
- Revisión 17-11-2026: 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 12 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 3 huecos del original que se habían perdido sin marca, marcados (Nº DE COLEGIADO, Nº DE DOCUMENTO, NÚMERO DE LA CALLE)
- Nota explicativa incorporada desde la colección Procesal (formulario 135) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Escrito por el que la acusación particular se persona en la instrucción y plantea una declinatoria por falta de competencia objetiva por razón de la materia de una Sección de Instrucción de un Tribunal de Instancia, solicitando que se inhiba en favor de la Sección de Instrucción del Tribunal Central de Instancia, por ser de su competencia, conforme a los arts. 65 y 95.a) de la LOPJ y en base al art. 26 LECRIM. Recuerde que....

---

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dª. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, actuando en representación de [NOMBRE DEL REPRESENTADO/A], parte perjudicada en este procedimiento, según consta en escritura de poder especial otorgado a mi favor, mediante

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original]

e inscrito en el Registro Electrónico de Apoderamientos Judiciales con el número [NÚMERO] y que se acredita mediante consulta automatizada orientada al dato, por parte del órgano judicial al cual tengo el honor de dirigirme. Se acompaña certificación electrónica del Registro Electrónico de Apoderamientos Judiciales como Documento nº [Nº DE DOCUMENTO] por si no es posible la consulta automatizada.

Actuando bajo la dirección letrada de D./Dña. [NOMBRE Y APELLIDOS], abogado/a en ejercicio, con despacho profesional abierto en [LOCALIDAD] colegiado nº [Nº DE COLEGIADO] del Ilustre Colegio de la Abogacía de [COLEGIO], ante este órgano judicial comparezco y, como mejor en Derecho proceda, DIGO:

Que mediante el presente escrito me PERSONO en el procedimiento número [Nº DE PROCEDIMIENTO] seguido ante ese órgano judicial por delito de estafa contra [ACTO O RESOLUCIÓN], en la representación que acredito y, como parte perjudicada, en ejercicio de la acusación particular.

Que, asimismo, mediante el presente escrito promuevo DECLINATORIA por falta de competencia objetiva, conforme al art. 26 de la LECRIM, al corresponder la instrucción de esta causa a la de Sección de Instrucción del Tribunal Central de Instancia, conforme al art. 65.1 c) de la LOPJ, al amparo de los siguientes,

MOTIVOS

PRIMERO.- Las presentes actuaciones se siguen por delito de estafa por las maniobras defraudatorias realizadas por [COMPLETAR] en su calidad de Administrador Único de la Aseguradora [COMPLETAR], a consecuencia de las cuales fue intervenida y sometida a liquidación forzosa.

SEGUNDO.- Esta parte entiende que la competencia para la instrucción de la causa corresponde a la Sección de Instrucción del Tribunal Central de Instancia al tratarse de un delito de defraudación que afecta a una generalidad de personas en el territorio de más de una Audiencia, conforme a lo establecido en el art. 65.1 c) de la LOPJ.

En fundamento de la pretensión, debe indicarse que la aseguradora intervenida operaba en todo el territorio nacional, con una cartera de clientes en número de 7.000, y con 150 empleados en plantilla, además de más de 200 agentes libres, tal como se desprende del informe realizado por la Comisión de Liquidación obrante en folio 23 a 45 de las actuaciones.

Por tanto, existe una generalidad de personas afectadas por la defraudación en todo el territorio nacional. En este sentido, no puede circunscribirse el perjuicio sólo a la propia aseguradora intervenida, sino que el mismo se extiende a la masa de asegurados, beneficiarios y trabajadores de la aseguradora, que debe ser considerada como una generalidad de personas y que están dispersas por el territorio de más de una Audiencia.

Este criterio interpretativo resulta claro a la vista de la doctrina del Tribunal Supremo, recogida entre otras en Auto de 25 de octubre de 1999, que viene señalando que hay que valorar la transcendencia económica de la defraudación, en este caso enorme al superar los diez millones de euros, en una primera estimación, y la posibilidad de instrucción sin dilaciones indebidas fuera de la jurisdicción única de la Audiencia Nacional, la cual en este caso cabe considerar como inviable, ya que la instrucción por parte del Juez al que nos dirigimos se dilataría necesariamente por la multitud de perjudicados dispersos por todo el territorio nacional.

TERCERO.- Por lo anterior, instamos de la Sección de Instrucción del Tribunal de Instancia de plaza nº [NÚMERO DE LA CALLE] que se inhiba del conocimiento del asunto a favor de la Sección de Instrucción del Tribunal Central de Instancia de la Audiencia Nacional, por corresponderle la competencia, conforme al art. 65.1 c) de la LOPJ, y de acuerdo a lo establecido en el art. 26 de la LECrim.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito con los documentos que se acompañan, me tenga por personado y parte como acusación particular en la representación de [NOMBRE DEL REPRESENTADO/A], y tenga por promovida la declinatoria por falta de competencia objetiva y, previos los trámites legales, dicte auto inhibiéndose del conocimiento del asunto a favor de la Sección de Instrucción del Tribunal Central de Instancia.

En [COMPLETAR]

Firma de Abogado/a	Firma de Procurador/a

================================================================================

---

#### Notas al pie

[NOTA DE REVISIÓN: El art. 65 LOPJ fija la competencia de la Sala de lo Penal de la Audiencia Nacional para el enjuiciamiento. La de la Sección de Instrucción del Tribunal Central de Instancia está en el art. 95.a) LOPJ: instruye las causas que juzga la Sala de lo Penal de la Audiencia Nacional o la Sección de lo Penal del propio Tribunal Central (ambos en la redacción de la LO 1/2025, vigentes desde el 23-1-2025).]

[NOTA DE REVISIÓN: Los antiguos Juzgados Centrales de Instrucción se transformaron en esa Sección el 31-12-2025, con la fase de «los restantes Juzgados» (DT 1.ª, ordinal 3.º, LO 1/2025). Para asuntos anteriores a esa fecha, el destinatario era el Juzgado Central de Instrucción.]
