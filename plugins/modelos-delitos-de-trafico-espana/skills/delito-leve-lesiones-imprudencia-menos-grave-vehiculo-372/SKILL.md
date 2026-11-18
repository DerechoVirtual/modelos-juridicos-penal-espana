---
name: delito-leve-lesiones-imprudencia-menos-grave-vehiculo-372
description: "Redacta el escrito «Delito leve de lesiones por imprudencia menos grave con vehículo a motor: denuncia» (formulario 372 de seguridad vial, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Delito leve de lesiones por imprudencia menos grave con vehículo a motor: denuncia

> Formulario 0372 del plugin **Seguridad vial** · revisado el 17-11-2026.

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

- [ ] SEDE (2 veces)
- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] Nº
- [ ] MATRÍCULA (2 veces)
- [ ] CALLE
- [ ] IMPORTE
- [ ] NÚMERO
- [ ] LUGAR
- [ ] FECHA
- [ ] ÓRGANO
- [ ] Otros 8 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…PRIMERO.- Con fecha circulaba por la AV/»; «…so y asegurado en la compañía de seguros»; «…, cuando el/la conductor/a denunciado/a»; «…y asegurado en la compañía de seguros»; «…a la denunciante las siguientes lesiones»; «…uida en el art. 147.1 CP al consistir en»; «…a/s denunciada /s que se conocen son: 1.»; «….»

## Elecciones que hay que hacer

- se aporta oferta motivada remitida por la aseguradora / b.- Partes médicos respecto de las lesiones sufridas y que se incardinan, al menos, en el art. 147.1 CP. / c.- Presupuesto o factura de los daños del vehículo. / d.- Copia de la póliza de seguro del vehículo denunciante y la referencia de la aseguradora del denunciado que es

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si se aporta perito de parte / Si se solicita reconocimiento de médico forense — el texto de cada opción no venía en el formulario original
- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS
- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (3)

Inclúyelos solo si encajan en los hechos:

- . [COMPLETAR].…
- D./Dña. [NOMBRE Y APELLIDOS]…
- (Si se designa abogado y procurador ya en la denuncia)…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 152.2 CP
- art. 966 LECRIM
- arts. 9.3 y 24.1 CE
- artículos 1, 100, 111 LECRIM
- artículos 112 y 259 a 269 LECRIM
- artículo 964.2 de la LECRIM
- art. 76 l) del Real Decreto Legislativo 6/2015
- art. 13.3 y 4 CP
- arts. 962 LECRIM
- art. 147.1 CP
- art. 88.1 c) LOPJ
- art. 14.1 de la LECRIM
- art. 964.3 LECRIM
- arts. 265 y 266 LECRIM
- artículo 10 de la Ley 39/2015
- art. 152.1 CP
- art. 147.2 CP
- art. 76 del RDLeg. 6/2015
- art. 967.1 LECRIM
- art. 149 CP
- art. 150 CP
- Ley Orgánica 1/2015

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

### Formulario 0372 · Delito leve de lesiones por imprudencia menos grave con vehículo a motor: denuncia

- Año del modelo: 2021
- Revisión 17-11-2026: restos de formato retirados; 1 rangos de artículos despegados («25 a31» → «25 a 31»); notas del formulario agrupadas al final (3); 1 desplegables y casillas convertidos en elección en blanco; 2 párrafos repetibles señalados; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 2 bloques de alternativas señalados; 1 párrafos opcionales señalados; 21 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Denuncia presentada por el perjudicado en unos hechos de la circulación que presentan los caracteres de un posible delito leve de lesiones del art. 152.2 CP por imprudencia menos grave. Se especifican los extremos que deben hacerse constar en ella para que se incoe proceso por delito leve y evitar su archivo de plano.

Actualizado conforme al RDL 6/2023, vigente desde el 20 de marzo de 2024.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción que por turno de reparto corresponda del Tribunal de Instancia de [SEDE]

D./Dña. [NOMBRE Y APELLIDOS], con Documento Nacional de Identidad núm. [Nº], correo electrónicoy teléfono, a los efectos de notificaciones conforme previsiones del art. 966 LECRIM, en su propio nombre y derecho, y al amparo y conforme a las previsiones de los arts. 9.3 y 24.1 CE, y artículos 1, 100, 111 LECRIM., artículos 112 y 259 a 269 LECRIM. y ss y artículo 964.2 de la LECRIM., mediante el presente escrito interpone DENUNCIA (1) por delito leve del art. 152.2 CP por los siguientes,

HECHOS

PRIMERO.- Con fecha circulaba por la AV/ [COMPLETAR] con el vehículo matrícula [MATRÍCULA] con preferencia de paso y asegurado en la compañía de seguros [COMPLETAR], cuando el/la conductor/a denunciado/a [COMPLETAR] lo hacía con el vehículo matrícula [MATRÍCULA] y asegurado en la compañía de seguros [COMPLETAR] quien lo hacía por la calle [CALLE], teniendo una señal de ceda el paso que le exigía observar la diligencia debida y cautela dando preferencia de paso al/a la denunciante. El/La denunciado/a se saltó dicho ceda el paso y colisionó con el vehículo de el/la denunciante infringiendo así el art. 76 l) del Real Decreto Legislativo 6/2015, de 30 de octubre, por el que se aprueba el texto refundido de la Ley sobre Tráfico, Circulación de Vehículos a Motor y Seguridad.

SEGUNDO.- Se han causado al/a la denunciante las siguientes lesiones [COMPLETAR]

TERCERO.- Los daños han ascendido a la suma de [IMPORTE] euros.

A los anteriores hechos le son aplicables los siguientes,

FUNDAMENTOS DE DERECHO

PREVIO.-

Los hechos objeto de denuncia son indiciariamente constitutivos de un delito del art. 152.2 CP

De acuerdo con las previsiones del art. 13.3 y 4 CP, el anterior delito posee la calificación de leve y le son aplicables las previsiones del Libro IV de la LECRIM (arts. 962 LECRIM y ss).

Señala el art. 152.2 CP, según redacción dada por LO 11/2022:

" El que por imprudencia menos grave causare alguna de las lesiones a que se refiere el artículo 147.1, será castigado con la pena de multa de uno a dos meses, y si se causaren las lesiones a que se refieren los artículos 149 y 150, será castigado con la pena de multa de tres meses a doce meses.

Si los hechos se hubieran cometido utilizando un vehículo a motor o un ciclomotor, se impondrá también la pena de privación del derecho a conducir vehículos a motor y ciclomotores de tres a dieciocho meses. A los efectos de este apartado, se reputará en todo caso como imprudencia menos grave aquella no calificada como grave en la que para la producción del hecho haya sido determinante la comisión de alguna de las infracciones graves de las normas de tráfico, circulación de vehículos y seguridad vial. La valoración sobre la existencia o no de la determinación deberá apreciarse en resolución motivada."

En el presente caso se ha cometido por el/la denunciado/a una infracción grave de tráfico del art. 76 l) del Real Decreto Legislativo 6/2015, de 30 de octubre, por el que se aprueba el texto refundido de la Ley sobre Tráfico, Circulación de Vehículos a Motor y Seguridad y la lesión sufrida, a falta de corroboración por el médico forense, está incluida en el art. 147.1 CP al consistir en [COMPLETAR]. (2)

La presencia de una infracción grave de tráfico, según la catalogación administrativa, empuja a que la imprudencia deba se catalogada por el juez como mínimo de menos grave y no de imprudencia leve, que no sería punible.

PRIMERO.- Es competente para el conocimiento del procedimiento para el juicio sobre el delito leve que nos ocupa, a materializar conforme las previsiones del Libro IV de los arts. 962 y ss de la LECRIM, la Sección de Instrucción del Tribunal de Instancia de [SEDE] plaza nº [NÚMERO], de acuerdo con las previsiones del art. 88.1 c) LOPJ, la DA 2ª de la Ley Orgánica 1/2015 de 30 de marzo, y el art. 14.1 de la LECRIM, al ser el partido judicial en el que se desarrollaron los hechos objeto de denuncia indiciariamente constitutivos de un delito leve.

SEGUNDO.- Los datos de la/s persona/s denunciada /s que se conocen son:

1. [COMPLETAR].

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

. [COMPLETAR].

TERCERO.- Los testigos y peritos que pueden dar razón de los hechos a los efectos de la celebración del Juicio Oral conforme las previsiones del art. 964.3 LECRIM son:

a) Testigos:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

D./Dña. [NOMBRE Y APELLIDOS]

b) Peritos:

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si se aporta perito de parte / Si se solicita reconocimiento de médico forense — el texto de cada opción no venía en el formulario original]

Como documentos se aportan los presentes:

a.- Copia de la reclamación del perjudicado a la aseguradora dando cuenta del siniestro,

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

sin que por esta se haya enviado oferta motivada, en razón de lo cual no se aporta la misma [ELEGIR: se aporta oferta motivada remitida por la aseguradora / b.- Partes médicos respecto de las lesiones sufridas y que se incardinan, al menos, en el art. 147.1 CP. / c.- Presupuesto o factura de los daños del vehículo. / d.- Copia de la póliza de seguro del vehículo denunciante y la referencia de la aseguradora del denunciado que es]

Y es por lo que,

SOLICITO A LA SECCIÓN:

Tenga por presentada esta denuncia, por puestos en su conocimiento los hechos circunstanciados, por aportada la documentación que le acompaña y, en su virtud y al amparo de lo dispuesto en los arts. 962 y ss LECRIM, incoe procedimiento para el juicio sobre delitos leves (3). Y se acuerde la citación para que sea reconocido por el médico forense el/la denunciante en el día que se indique al objeto de la constancia de lesión del art. 147.1 CP, en relación con el art. 152.2 CP.

[OPCIONAL — incluir si procede]

(Si se designa abogado y procurador ya en la denuncia)

OTROSÍ DIGO: que para mi representación y defensa en esta causa designo al/a la Procurador/a D./Dña. [NOMBRE Y APELLIDOS] y al/a la Abogado/a D./Dña. [NOMBRE Y APELLIDOS], quienes firman conmigo este escrito en prueba de aceptación y conformidad.

Por ser de Justicia que pido en [LUGAR], a [FECHA].

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

Firma del/de la denunciante [ÓRGANO]

Firma del/de la denunciante	Firma de Abogado/a	Firma de Procurador/a

NOTAS DEL FORMULARIO

(1) Desde el 20 de marzo de 2024, fecha de entrada en vigor de la reforma operada en los arts. 265 y 266 LECRIM por el RDL 6/2023, se regula expresamente cuál debe ser el contenido de la denuncia, que hasta entonces era flexible, así como la posibilidad de realizarse por vía telemática.

Puede hacerse personalmente o por medio de mandatario con poder especial para un hecho punible determinado y por escrito o de palabra.

— Por escrito: debe ir firmada por el denunciante de forma autógrafa o manuscrita, si es presencial, o por otra persona a su ruego, si no pudiese hacerlo.

— Por vía telemática: con firma electrónica conforme a lo establecido en el artículo 10 de la Ley 39/2015, de 1 de octubre, del Procedimiento Administrativo Común de las Administraciones Públicas y en el Reglamento (UE) 910/2014, de 23 de julio de 2014, relativo a la identificación electrónica y los servicios de confianza para las transacciones electrónicas en el mercado interior.

En el caso de las personas jurídicas, se firmará con certificado electrónico cualificado con atributo de representante, o los medios previstos en la regulación de firma digital que permitan identificar la persona jurídica, así como la persona física que formula la denuncia.

— De palabra: la autoridad que la recibe extiende acta con cuantas noticias tenga el denunciante relativas al hecho denunciado y a sus circunstancias. Es firmada por la autoridad y el denunciante o por otra persona a su ruego.

La denuncia (escrita o verbal) debe contener: la identificación de la persona denunciante, la narración circunstanciada del hecho, la identificación de las personas que hayan cometido el hecho, si fueran conocidas y de quienes lo hayan presenciado o tengan información sobre él y la existencia de cualquier fuente de conocimiento de la que el denunciante tenga noticia, que pueda servir para esclarecer el hecho denunciado.

En caso de persona jurídica o ente sin personalidad jurídica, deberá identificarse también la persona física que formula la denuncia en su nombre, indicando su relación con la persona jurídica o el ente sin personalidad.

No es requisito legal la calificación jurídica de los hechos, pero puede aportarse, si se conoce.

(2) A partir del 3 de marzo de 2019, fecha de entrada en vigor de la reforma del CP operada por LO 2/2019, conoce la jurisdicción penal de las lesiones por imprudentes producidas por imprudencia grave (art. 152.1 CP) o menos grave (art. 152.2 CP) cuando el resultado sea de los previstos en el art. 147.1, 149 ó 150 CP). Si las lesiones se consideran realizadas por imprudencia leve, o son de las que no requieren tratamiento médico o quirúrgico (art. 147.2 CP), habrá que acudir a la vía civil para su resarcimiento.

La LO 11/2022, vigente desde el 15 de septiembre de 2022, especifica que si se comete una infracción grave de las recogidas en el art. 76 del RDLeg. 6/2015, de 30 de octubre, la imprudencia debe ser considerada de menos grave o grave, nunca leve y, por tanto, se dirime dentro de la vía penal.

Para la calificación de la imprudencia como grave o menos grave téngase en cuenta la STS Pleno 421/2020, de 22 de julio, Rec. 1086/2018

(3) No se necesita abogado ni procurador para el enjuiciamiento de delitos leves, excepto para los que lleven aparejada pena de multa cuyo límite máximo sea de al menos seis meses, donde se aplicarán las reglas generales de defensa y representación, es decir, será preceptivo abogado y procurador. (art. 967.1 LECRIM)

En consecuencia, no se necesitará abogado ni procurador en caso de imprudencia menos grave del art. 152.2 CP con resultado de lesión del art. 147.1 CP (necesitan tratamiento médico o quirúrgico y no son invalidantes, pero sí relevantes), puesto que la pena es de multa de 1 a 2 meses. En cambio, sí se requiere abogado y procurador en caso de imprudencia grave del art. 152.1 CP y de la menos grave del art. 152.2 CP si el resultado es de lesiones del art. 149 CP (pérdida o inutilidad de un órgano o miembro principal, o de un sentido, la impotencia, la esterilidad, una grave deformidad, o una grave enfermedad somática o psíquica) o del art. 150 CP (pérdida o la inutilidad de un órgano o miembro no principal, o la deformidad), ya que la pena es de multa de 3 a 12 meses.

================================================================================
