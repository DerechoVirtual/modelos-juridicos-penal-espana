---
name: robo-uso-vehiculo-motor-querella-873
description: "Redacta el escrito «Robo de uso de vehículo de motor: querella» (formulario 873 de delitos contra el patrimonio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Robo de uso de vehículo de motor: querella

> Formulario 0873 del plugin **Delitos contra el patrimonio** · revisado el 17-11-2026.

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

- [ ] SEDE
- [ ] Nº (2 veces)
- [ ] NOMBRE Y APELLIDOS (8 veces)
- [ ] Nº DE COLEGIADO
- [ ] COLEGIO
- [ ] ESTADO CIVIL (2 veces)
- [ ] PROFESIÓN (2 veces)
- [ ] LOCALIDAD (3 veces)
- [ ] CALLE (2 veces)
- [ ] NÚMERO
- [ ] FECHA (2 veces)
- [ ] MATRÍCULA
- [ ] IMPORTE (2 veces)
- [ ] LUGAR
- [ ] Otros 6 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…, con domicilio en [LOCALIDAD],»; «…, [COMPLETAR],»; «…. horas, el/la querellado/a»; «…que se encontraba estacionado en»; «… querella y que manifieste en particular»; «…al de valoración de daños que asciende a»

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original

## Párrafos opcionales (4)

Inclúyelos solo si encajan en los hechos:

- .- DECLARACIÓN del/de la querellado/a sobre los hechos de la querella y que manifieste en particular [COMPLETA…
- .- TESTIFICAL: A cuyo fin deberá ser citado a través de la oficina judicial la siguiente persona, que localizó…
- .- DOCUMENTAL: teniendo por reproducidos los documentos que se acompañan a la querella:…
- D./Dña. [NOMBRE Y APELLIDOS]…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 244.2 CP
- art. 77 RDL 6/2023
- art. 24.1 LEC
- artículos 270 de la Ley de Enjuiciamiento Criminal
- artículos 277 LECrim
- artículos 14 y 272 de la Ley de Enjuiciamiento Criminal
- art. 281 de la Ley de Enjuiciamiento Criminal
- art. 4 LEC
- art. 24.2 LEC
- art. 244 CP
- art. 244.1 CP
- art. 244.3 CP
- art. 244.4 CP
- art. 244 del CP
- art. 242 CP

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

### Formulario 0873 · Robo de uso de vehículo de motor: querella

- Año del modelo: 2016
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (3); 1 párrafos repetibles señalados; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 3 párrafos opcionales señalados; 33 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 1 huecos del original que se habían perdido sin marca, marcados (Nº DE COLEGIADO)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito poniendo en conocimiento del juez unos hechos que presentan los caracteres de un delito de robo de uso de vehículo de motor del art. 244.2 CP por haber sido sustraído su vehículo, rompiendo el cristal de una ventana y entrando por ella, dejándolo después abandonado en la vía pública.

Encabezamiento actualizado conforme al art. 77 RDL 6/2023, vigente desde 9-1-2024 y art. 24.1 LEC, vigente desde 20-3-2024.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales y de D./Dña. [NOMBRE Y APELLIDOS], según consta en escritura de poder especial otorgado a mi favor (1),

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si el poder se otorga a través de la sede judicial electrónica / Si el poder se otorga mediante comparecencia apud acta / Si el poder se otorga ante Notario — el texto de cada opción no venía en el formulario original]

bajo la dirección letrada de D./Dña [NOMBRE Y APELLIDOS], abogado/a en ejercicio, con despacho profesional abierto en colegiado nº [Nº DE COLEGIADO] del Ilustre Colegio de la Abogacía de [COLEGIO], ante este órgano judicial comparezco y como mejor en Derecho proceda, DIGO:

Que, siguiendo las instrucciones de mi mandante, formulo querella en ejercicio del derecho reconocido en los artículos 270 de la Ley de Enjuiciamiento Criminal y siguientes contra D./Dña. [NOMBRE Y APELLIDOS] por el delito de robo de uso de vehículo de motor con fuerza en las cosas del art. 244.2 CP, a cuyo efecto, dando cumplimiento a lo que determinan los artículos 277 LECrim y concordantes de dicha ley,

EXPONGO

PRIMERO.- Se presenta ante la Sección de Instrucción del Tribunal de Instancia de esta ciudad que por turno de reparto corresponda por ser el competente para su instrucción, a tenor de los artículos 14 y 272 de la Ley de Enjuiciamiento Criminal, al haber ocurrido los hechos dentro de este partido, concretamente en

SEGUNDO.- El/La querellante es D./Dña. [NOMBRE Y APELLIDOS] como queda dicho, mayor de edad, de estado civil [ESTADO CIVIL], de profesión [PROFESIÓN], vecino/a de [LOCALIDAD], con domicilio en la calle [CALLE] número [NÚMERO].

TERCERO.- El/La querellado/a es D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, de estado civil [ESTADO CIVIL], de profesión [PROFESIÓN], vecino/a de [LOCALIDAD], con domicilio en [LOCALIDAD], [COMPLETAR], [COMPLETAR] (2).

CUARTO.- Los hechos que motivan la querella, y que presentan caracteres delictivos, son los siguientes:

El día [FECHA] siendo, aproximadamente, las [Nº]. horas, el/la querellado/a [COMPLETAR] esperó a que saliera del aparcamiento sito en la calle [CALLE] el dueño del vehículo matrícula [MATRÍCULA] que se encontraba estacionado en [COMPLETAR] y, aprovechando que el titular de este vehículo salió del parking, entró el/la querellado/a en el mismo por la puerta que estaba abierta. El aparcamiento no disponía de vigilancia alguna, lo que provocó que el/la querellado/a se acercara al vehículo por la puerta del conductor y golpeara el cristal del mismo, rompiéndolo e introduciéndose por la misma ventana en el interior del vehículo hasta colocarse en el asiento del piloto. A continuación, hizo un "puente" para encenderlo, llevándose el vehículo del aparcamiento para utilizarlo, aunque sin intención de apropiárselo, ya que el vehículo fue recuperado aparcado en la calle al día siguiente, al darse cuenta un amigo del querellante de su presencia, al conocerlo, una vez tuvo conocimiento de que había sido sustraído. El vehículo tenía daños por valor de [IMPORTE] euros, tanto al haber hecho el puente como a resultas de un accidente que tuvo el/la querellado/a, como consta en el informe pericial que se adjunta a la querella.

La autoría del querellado/querellada consta en el informe de huellas de los agentes intervinientes en los hechos.

Los hechos expuestos revisten los caracteres de un delito de robo de uso de vehículo que define el artículo 244.2 del Código penal (3), del que presuntamente es culpable el querellado/la querellada.

QUINTO.- Como diligencias de investigación a practicar para la comprobación del hecho señalamos las siguientes:

[OPCIONAL — incluir si procede]

.- DECLARACIÓN del/de la querellado/a sobre los hechos de la querella y que manifieste en particular [COMPLETAR]

[OPCIONAL — incluir si procede]

.- TESTIFICAL: A cuyo fin deberá ser citado a través de la oficina judicial la siguiente persona, que localizó el vehículo al día siguiente:

D./Dña. [NOMBRE Y APELLIDOS]

[OPCIONAL — incluir si procede]

.- DOCUMENTAL: teniendo por reproducidos los documentos que se acompañan a la querella:

— Documento acreditativo de la titularidad del vehículo de el/la querellante.
— Informe pericial de valoración de daños que asciende a [COMPLETAR].
— Informe de huellas dactilares encontradas en el vehículo elaborado por los agentes de policía:
[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

D./Dña. [NOMBRE Y APELLIDOS]

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito de querella con la escritura de poder especial que acompaña y documentos, me tenga por parte en la representación con que comparezco, se admita, se practiquen las diligencias interesadas y se tomen las pertinentes medidas cautelares sobre los bienes de el/la querellado/a, disponiendo se le exija fianza para cubrir las responsabilidades civiles y, en su defecto, se decrete el embargo de sus bienes suficientes para atender dichas responsabilidades, que esta parte valora en [IMPORTE] euros.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que, conforme a lo dispuesto en el art. 281 de la Ley de Enjuiciamiento Criminal, esta parte considera que está exenta de prestar fianza.

Por ello,

SUPLICO A LA SECCIÓN: Que tenga por hecha esta manifestación.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a	Firma de Procurador/a

NOTAS DEL FORMULARIO

(1) En el modelo se hacen constar las tres posibilidades para otorgar el apoderamiento al Procurador de los Tribunales, conforme dispone el art. 24.1 LEC, aplicable al procedimiento penal de manera supletoria, según el art. 4 LEC. En todo caso, para la interposición de la querella es necesario poder especial y se presenta siempre por medio de Procurador y suscrita por Abogado. Cuando el Procurador no tenga poder especial, es necesaria la firma del querellante o la de otra persona a su ruego, si no sabe o no puede, y debe ratificarse ante la Sección de Instrucción del Tribunal de Instancia. Todos los poderes deben estar inscritos en el Registro Electrónico de Apoderamientos Judiciales (REAJ). Para su acreditación, basta con la consulta (de dicho Registro) automatizada orientada al dato, a disposición de cualquier Letrado de la Administración de Justicia. Sin embargo, dado que el art. 24.2 LEC configura la certificación de dicha inscripción como vía subsidiaria de acreditación, para el caso de que el sistema no permita aquella consulta automatizada, se señala en el modelo que se acompaña certificación electrónica. El sistema permite emitir dicha certificación para quien inscribe el poder. En todos los casos, quien asuma la representación procesal indicará el número asignado a la inscripción en dicho Registro (art. 77 RDL 6/2023).

El ofendido o perjudicado puede mostrarse parte en la causa sin necesidad de formular querella.

(2) Si se ignora el nombre, apellidos y vecindad del querellado, se hará la designación del mismo por las señas que mejor puedan darle a conocer.

(3) En los casos de sustracción de vehículos caben en el art. 244 CP varias opciones:

a.- Que lo restituyera, directa o indirectamente, en un plazo no superior a cuarenta y ocho horas (art. 244.1 CP) Hurto de uso.

b.- Empleando fuerza en las cosas (art. 244.2 CP) robo de uso.

c.- Que no se efectúe la devolución (art. 244.3 CP) Hurto o robo.

d.- Que se emplee en la comisión violencia o intimidación en las personas. (art. 244.4 CP) Robo de uso.

En el art. 244 del CP se aprecia una doble remisión. Después de describir los hechos susceptibles de ser estimados como hurto de uso y robo de uso con fuerza en las cosas y fijar sus penas, se especifica en su apartado 3 que «de no efectuarse la restitución en el plazo señalado —-no superior a cuarenta y ocho horas—-, se castigará el hecho como hurto o robo en sus respectivos casos».

Se exige que no concurra el ánimo de apropiación y que ésta no se lleve a cabo porque, si así se hiciera, serían delitos de robo o hurto, según la modalidad.

Si, además de empleo de fuerza como en este caso, se utilizase violencia o intimidación en las personas, se aplica el art. 244.4 CP que remite a las penas de prisión de 2 a 5 años del art. 242 CP.

================================================================================
