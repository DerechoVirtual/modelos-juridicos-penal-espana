---
name: apelacion-contra-condena-falsedad-documento-privado-852
description: "Redacta el escrito «Apelación contra la condena por falsedad en documento privado y estafa» (formulario 852 de delitos contra el patrimonio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Apelación contra la condena por falsedad en documento privado y estafa

> Formulario 0852 del plugin **Delitos contra el patrimonio** · revisado el 17-11-2026.

## Paso 0: Jurisprudenciator en esta skill (obligatorio)

**Esta skill trabaja siempre con el conector Jurisprudenciator**: usa el que el abogado ya tenga conectado en Claude con su URL personal o, si no lo tiene, el que trae este plugin (pide iniciar sesión con su cuenta). Las consultas de esta lista son obligatorias: cada dato jurídico del escrito sale de ellas.

- **Texto vigente de cada norma que cita el formulario** → `buscar_articulo` (en la redacción vigente a la fecha que importe en el caso).
- **Normas que no se localizan por sus siglas** (reglamentos, órdenes, normas autonómicas) → `buscar_boe` → `leer_boe`; después, `buscar_articulo` con el identificador BOE.
- **Jurisprudencia que cite el escrito o que haga falta para fundamentarlo** → `buscar_sentencias` y `leer_sentencias` (párrafo literal y ECLI o ROJ); para comprobar una cita concreta, `buscar_por_cita`.
- **Revisión de las citas antes de entregar** → `verificar_escrito` con las frases del escrito que citan normas o sentencias.
- **Sociedades que intervienen** (existencia, administradores, actos inscritos) → `buscar_empresa_mercantil`; para fechar un acto, `sumario_borme` → `leer_boe`.
- **Inmuebles** (referencia catastral, superficie, uso) → `consultar_catastro` (y `callejero_catastro` para localizar la dirección).

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

- [ ] SEDE (2 veces)
- [ ] Nº (2 veces)
- [ ] NOMBRE Y APELLIDOS (3 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] NÚMERO
- [ ] FECHA (3 veces)
- [ ] LOCALIDAD
- [ ] PENA
- [ ] IMPORTE
- [ ] LUGAR
- [ ] Otros 4 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «… Policía Local de este municipio llamado»; «…a entidad bancaria y del Excmo. Ayto. de»; «…oncurso medial, a una pena de prisión de»; «…icilio para notificaciones el situado en»

## Párrafos opcionales (2)

Inclúyelos solo si encajan en los hechos:

- 1.- Interrogatorio del/de la acusado/a…
- .- .- Testifical: del/de la empleado/a de la sucursal bancaria, D./Dña. [NOMBRE Y APELLIDOS], y del funcionari…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 392.1 CP
- art. 21.4 CP
- art. 790 de la Ley de Enjuiciamiento Criminal
- artículos 66 y 77.3 del CP
- arts. 248, 390.1 y 392.1 del Código Penal
- artículo 77.3 del Código Penal
- art. 790.3 LECrim
- art. 847 LECrim
- artículo 849.1 de la LECrim

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

### Formulario 0852 · Apelación contra la condena por falsedad en documento privado y estafa

- Año del modelo: 2016
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (5); 2 párrafos opcionales señalados; 19 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Recurso de apelación presentado por el condenado en sentencia en procedimiento abreviado por delito de falsedad en documento privado del art. 392.1 CP, basado en infracción de normas del ordenamiento jurídico, por no haberse valorado debidamente la circunstancia de haber confesado la infracción del art. 21.4 CP.

Actualizado conforme a la LO 14/2022, con entrada en vigor el 12 de enero de 2023.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de lo Penal del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

Sección de lo Penal del Tribunal Central de Instancia

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales y del/de la acusado/a D./Dña. [NOMBRE Y APELLIDOS], según tengo ya acreditado en el Procedimiento abreviado número [Nº DE PROCEDIMIENTO], seguido en la Sección de Instrucción del Tribunal de Instancia de [SEDE] plaza nº [NÚMERO], por el delito de falsedad en documento privado y estafa, ante este órgano judicial, como mejor proceda en derecho, DIGO:

Con fecha [FECHA], le ha sido notificada a esta parte la sentencia dictada el día [FECHA] y estimándola perjudicial y gravosa para mi representado/a, dicho sea con los debidos respetos y en términos de defensa, dentro del plazo legalmente fijado (1) interpongo en tiempo y forma recurso de apelación para ante la Audiencia Provincial de [LOCALIDAD] (2), al amparo de lo establecido en el art. 790 de la Ley de Enjuiciamiento Criminal, con base en las siguientes:

ALEGACIONES (3)

ÚNICA.- Sobre infracción de normas del ordenamiento jurídico

La sentencia recurrida impone a mi representado/a una pena de [PENA] de prisión y multa de [Nº] meses, a razón de [IMPORTE] euros por día, e inhabilitación especial para el derecho de sufragio pasivo durante el tiempo de la condena, por la comisión de un delito de falsedad en documento mercantil y estafa en concurso medial, sin la concurrencia de circunstancias modificativas de la responsabilidad criminal.

Sin embargo, esta parte considera que no se ha valorado debidamente la circunstancia de haberse procedido a confesar la infracción por el/la acusado/a, conforme al artículo 21.4ª del CP, en relación con los artículos 66 y 77.3 del CP, respecto a las conductas tipificadas en los arts. 248, 390.1 y 392.1 del Código Penal.

Se ha de admitir, como se relata y queda acreditado en la sentencia recurrida, que mi representado/a falsificó un pagaré de la empresa en la que prestaba sus servicios y lo presentó para su descuento en la sucursal de la entidad bancaria, apropiándose, tras el abono en cuenta de los 9.000 euros correspondientes, de dicha cantidad, por ser autorizado/a para disponer de los saldos de esta cuenta.

No obstante, en un momento posterior, mi representad/a admitió los hechos ante el/la apoderado/a de la sucursal bancaria en la propia agencia, ante la presencia de un funcionario de la Policía Local del municipio, sin que de dicha declaración haya quedado constancia documental, pues ese mismo día se produjo su detención.

La sentencia recurrida ha rechazado el anterior alegato, por considerar que esta circunstancia atenuante modificativa de la responsabilidad criminal no ha quedado acreditada suficientemente.

En consecuencia, de admitirse esta atenuante, de acuerdo con el artículo 77.3 del Código Penal, por tratarse de un delito para cometer otro (el subrayado es nuestro): "se impondrá una pena superior a la que habría correspondido, en el caso concreto, por la infracción más grave, y que no podrá exceder de la suma de las penas concretas que hubieran sido impuestas separadamente por cada uno de los delitos. Dentro de estos límites, el juez o tribunal individualizará la pena conforme a los criterios expresados en el artículo 66. En todo caso, la pena impuesta no podrá exceder del límite de duración previsto en el artículo anterior".

MEDIOS DE PRUEBA

En aplicación del art. 790.3 LECrim., por no haberse podido practicar en la primera instancia por causa no imputable al recurrente, que insistió en su necesidad en el acto del juicio, se solicitan las siguientes (4):

[OPCIONAL — incluir si procede]

1.- Interrogatorio del/de la acusado/a

[OPCIONAL — incluir si procede]

.- .- Testifical: del/de la empleado/a de la sucursal bancaria, D./Dña. [NOMBRE Y APELLIDOS], y del funcionario de la Policía Local de este municipio llamado [COMPLETAR], para cuya localización se solicita la colaboración, respectivamente, de la entidad bancaria y del Excmo. Ayto. de [COMPLETAR].

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita, y tenga por interpuesto recurso de apelación contra la sentencia recaída en estos autos, se admita en ambos efectos, dando traslado del mismo a las demás partes para que presenten sus escritos de alegaciones, y remita las actuaciones a la Audiencia Provincial para que admita las pruebas propuestas y dicte sentencia (5) en la que, estimando el recurso, revoque la apelada, dictando otra por la que se condene a mi representado/a, por la comisión de un delito de falsedad en documento mercantil y estafa en concurso medial, a una pena de prisión de [COMPLETAR], y demás penas accesorias.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que, cumpliendo el art. 790.2 LECrimin fine, designo como domicilio para notificaciones el situado en [COMPLETAR].

Por lo expuesto,

SUPLICO A LA SECCIÓN: Que tenga por realizada la anterior manifestación.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este recurso se presenta en el plazo de 10 días a partir del siguiente al de la notificación de la sentencia.

(2) Debe interponerse ante el Juez de lo Penal o Central de lo Penal que dictó la resolución impugnada.

(3) Deben exponerse de forma ordenada las alegaciones que quepan contra la sentencia sobre quebrantamiento de normas y garantías procesales, error en la apreciación de la prueba o infracción de normas del ordenamiento jurídico.

Si en el recurso se pidiera la declaración de nulidad del juicio por infracción de normas o garantías procesales que causaren la indefensión del recurrente, en términos tales que no pueda ser subsanada en la segunda instancia, se citarán las normas legales o constitucionales que se consideren infringidas y se expresarán las razones de la indefensión.

(4) Puede pedirse la práctica de pruebas que no se pudieron proponer en el procedimiento o que se denegaron indebidamente si se formuló protesta y las admitidas y no practicadas por causas no imputables al apelante. Véanse STC 22/2013 de 31 de enero y STS 32/2012, de 25 de enero, rec 932/2011.

(5) A partir del 6 de diciembre de 2015, fecha de entrada en vigor de la L 41/2015, de 5 de octubre, de reforma de la LECrim., contra las sentencias dictadas por las Audiencias Provinciales en grado de apelación ante las dictadas por la Sección de de lo Penal del Tribunal de Instancia cabe según el art. 847 LECrim. recurso de casación por infracción de ley del motivo previsto en el artículo 849.1 de la LECrim. Son las dictadas por los jueces de lo penal recurridas en apelación y resueltas por la Audiencia "Cuando, dados los hechos que se declaren probados en las resoluciones comprendidas en los dos artículos anteriores, se hubiere infringido un precepto penal de carácter sustantivo u otra norma jurídica del mismo carácter que deba ser observada en la aplicación de ley penal." Ahora bien, el recurrente deberá citar el precepto penal o la norma jurídica infringida, es decir se trata de un claro error de norma, no una diferente valoración de la prueba.

================================================================================
