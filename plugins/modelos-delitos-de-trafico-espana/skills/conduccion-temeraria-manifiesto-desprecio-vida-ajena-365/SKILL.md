---
name: conduccion-temeraria-manifiesto-desprecio-vida-ajena-365
description: "Redacta el escrito «Conducción temeraria con manifiesto desprecio por la vida ajena: escrito de acusación» (formulario 365 de seguridad vial, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Conducción temeraria con manifiesto desprecio por la vida ajena: escrito de acusación

> Formulario 0365 del plugin **Seguridad vial** · revisado el 17-11-2026.

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

Pídelos en una sola tanda. Lo que el usuario no sepa se queda como hueco visible.

- [ ] Órgano: SEDE del Tribunal de Instancia y Nº DE PLAZA de la Sección de Instrucción; Nº DE PROCEDIMIENTO (abreviado) y FECHA DEL AUTO que da traslado para acusar
- [ ] Partes: procurador, perjudicado (acusación particular) y **acusado** (nombre y apellidos: el escrito tiene que identificarlo, art. 781.1 LECrim)
- [ ] Hechos: FECHA y HORA; vehículo del acusado (MARCA, MODELO Y MATRÍCULA); VÍA Y PUNTO KILOMÉTRICO; descripción de la conducción (sentido contrario, velocidad, maniobras, distancia recorrida)
- [ ] Resultado: MATRÍCULA DEL VEHÍCULO DAÑADO e IMPORTE DE LOS DAÑOS; lesiones, tratamiento y secuelas según el informe forense (FECHA DEL INFORME y folio); baja laboral (fecha de baja y, si lo hay, de alta)
- [ ] Seguro: ASEGURADORA y Nº DE PÓLIZA; folio de la pieza de responsabilidad civil en el que consta el afianzamiento, o si aún no ha afianzado; TITULAR DEL VEHÍCULO si no es el acusado
- [ ] Pena que se pide dentro de la mitad superior (prisión, meses de multa y CUOTA diaria, años de privación del derecho a conducir) y, si la hay, CIRCUNSTANCIA agravante con su ordinal del art. 22 CP
- [ ] Responsabilidad civil: IMPORTE POR LESIONES, IMPORTE POR SECUELAS, IMPORTE TOTAL y AÑO DE LA VALORACIÓN del baremo; IMPORTE DE LA FIANZA si se pide requerir a la aseguradora
- [ ] Prueba: testigos (nombre y qué vieron), agentes del atestado (cuerpo y TIP), médico forense
- [ ] Pensión provisional: si está acordada, FECHA DEL AUTO DE PENSIÓN
- [ ] LUGAR y FECHA DEL ESCRITO

## Elecciones que hay que hacer

- ordinal del art. 152.1 CP según la lesión: 1.º (art. 147.1) / 2.º (art. 149) / 3.º (art. 150)
- sin circunstancias modificativas / con agravante del art. 22 CP
- baja laboral: continúa / alta
- testigos: a continuación / en escrito aparte; citados por medio de la oficina judicial / mediante exhorto

No hay elección sobre el delito que fija la pena: la del art. 381.1 CP es siempre más grave que la del art. 152.1 (ver la nota de revisión de la conclusión quinta).

## Reglas de este formulario que no puedes saltarte

- **Pena (arts. 381.1 y 382 CP).** Mitad superior del art. 381.1: prisión de tres años y seis meses a cinco años y multa de dieciocho a veinticuatro meses. La privación del derecho a conducir va en todo caso en su mitad superior, de ocho a diez años (art. 382, párrafo segundo). Compruébalo con `buscar_articulo("CP", "381")` y `("CP", "382")` antes de escribir las cifras.
- **Competencia.** Con esas penas juzga la Sección de lo Penal del Tribunal de Instancia (art. 14.3 LECrim). No pongas número de plaza del órgano de enjuiciamiento.
- **Plazo.** Diez días comunes desde el traslado (art. 780.1 LECrim), prorrogables otros diez con petición justificada (art. 781.2). Se presenta ante la Sección de Instrucción que tramita las diligencias.
- **Texto refundido del seguro de vehículos.** `buscar_articulo` no lo localiza por «RDLeg. 8/2004» (hay dos normas con ese número): usa el identificador `BOE-A-2004-18911`.
- **Importes del baremo.** Jurisprudenciator no calcula indemnizaciones. Si el usuario no trae la valoración hecha, deja los importes como hueco y dilo en el resumen.

## Párrafos opcionales (9)

Inclúyelos solo si encajan en los hechos:

- Ocupantes del vehículo del perjudicado.
- Baja laboral del perjudicado.
- Responsabilidad civil subsidiaria del titular del vehículo (art. 120.5.º CP), si no es el acusado.
- Requerimiento a la aseguradora para que afiance (solo si aún no lo ha hecho).
- Interrogatorio del acusado.
- Testifical (un párrafo por testigo; quita los que no existan).
- Pericial médico forense.
- Documental.
- Segundo otrosí sobre la pensión provisional (solo si hay auto que la acordó).

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- arts. 14.3, 240, 650, 764.3, 765, 780.1, 781.1 y 783.2 LECrim
- arts. 22, 27, 28, 47, 53, 56, 117, 120.5.º, 123, 152.1, 381.1 y 382 CP
- arts. 7.1, 7.7 y 9 RDLeg. 8/2004 (`BOE-A-2004-18911`)
- art. 20 (reglas 3.ª, 4.ª y 6.ª) de la Ley 50/1980, de Contrato de Seguro

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

### Formulario 0365 · Conducción temeraria con manifiesto desprecio por la vida ajena: escrito de acusación

- Año del modelo: 2021
- Revisión 17-11-2026: 4 llamadas a nota sin texto retiradas; 2 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 1 desplegables convertidos en elección en blanco; 1 bloques de alternativas señalados; 5 párrafos opcionales señalados; 26 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)
- Segunda revisión 17-11-2026 (tras redactar un escrito de prueba con él): 7 huecos que se habían perdido, recuperados (importes, matrícula, identificación del acusado); 3 citas de la ley del seguro corregidas (art. 7.7 y 7.1 RDLeg. 8/2004; art. 20.6.º LCS); añadida la regla del art. 382, párrafo segundo, CP; retirados restos del caso de origen

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº DE PLAZA]

D./Dña. [NOMBRE Y APELLIDOS DEL PROCURADOR] Procurador/a de los Tribunales, actuando en representación de D./Dña. [NOMBRE Y APELLIDOS DEL PERJUDICADO], acusador particular, según consta acreditado en el Procedimiento Abreviado [Nº DE PROCEDIMIENTO] seguido ante ese órgano judicial, comparezco y como proceda en Derecho DIGO:

Que evacuando el traslado conferido por auto de fecha [FECHA DEL AUTO], de conformidad con lo establecido en el artículo 780.1 de la LECrim, presento ESCRITO DE ACUSACIÓN contra D./Dña. [NOMBRE Y APELLIDOS DEL ACUSADO] Y SOLICITO LA APERTURA DEL JUICIO ORAL ante la Sección de lo Penal del Tribunal de Instancia de [SEDE], al amparo del artículo 781.1 de la Ley de Enjuiciamiento Criminal, en relación con el art. 650 LECRIM, con arreglo a lo dispuesto en el artículo 14.3 de la LECrim y con base en las siguientes

[NOTA DE REVISIÓN: El traslado para acusar lo regula el art. 780.1 LECrim y el contenido del escrito, el art. 781.1, que exige identificar a la persona contra la que se dirige la acusación: el original no la nombraba. No se indica la plaza de la Sección de lo Penal: la fija el reparto tras el auto de apertura (art. 783.2 LECrim). Fuente: LECrim arts. 780, 781 y 783 (BOE-A-1882-6036).]

CONCLUSIONES

PRIMERA.- El día [FECHA DE LOS HECHOS] a las [HORA] horas, el/la acusado/a circulaba con el vehículo [MARCA, MODELO Y MATRÍCULA] por [VÍA Y PUNTO KILOMÉTRICO] cuando, con evidente temeridad y con manifiesto desprecio a la vida de los demás, realizó la siguiente conducta: [DESCRIBIR LA CONDUCCIÓN].

La forma de la conducción conllevó un serio peligro para indeterminados usuarios de la vía como consecuencia de un acto de la circulación, ya que no solo causó las lesiones a mi representado/a, sino que pudo causarlas a otros usuarios de la vía.

Como consecuencia de los hechos relatados, que pudieron acabar con la vida de mi representado/a [OPCIONAL: y de los ocupantes de su vehículo], resultaron daños en el vehículo matrícula [MATRÍCULA DEL VEHÍCULO DAÑADO] por importe de [IMPORTE DE LOS DAÑOS] euros y lesiones en mi representado/a consistentes en [DESCRIBIR LAS LESIONES, EL TRATAMIENTO Y LAS SECUELAS].

[OPCIONAL — incluir si procede]

Mi representado/a causó baja laboral el día [FECHA DE LA BAJA] y [ELEGIR: continúa de baja en la actualidad / recibió el alta el día [FECHA DEL ALTA]].

La aseguradora del vehículo del/de la acusado/a es [ASEGURADORA], póliza n.º [Nº DE PÓLIZA].

SEGUNDA.- Tales hechos son constitutivos del delito de conducción temeraria con manifiesto desprecio a la vida de los demás del art. 381.1 CP con resultado de lesiones por imprudencia grave del art. 152.1.[ELEGIR: 1.º / 2.º / 3.º] CP, en relación con el art. 382 CP.

[NOTA DE REVISIÓN: El ordinal del art. 152.1 depende de la lesión: 1.º, lesiones del art. 147.1; 2.º, las del art. 149; 3.º, las del art. 150. Fuente: CP art. 152 (redacc. LO 11/2022, BOE-A-2022-14965).]

TERCERA.- Es responsable del delito en concepto de autor/a el/la acusado/a, D./Dña. [NOMBRE Y APELLIDOS DEL ACUSADO] (arts. 27 y 28 CP).

CUARTA.-

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

No concurren en el/la acusado/a circunstancias modificativas de la responsabilidad penal.

Concurre en el/la acusado/a la circunstancia agravante de [CIRCUNSTANCIA] del art. 22.[ORDINAL] del CP.

QUINTA.- Procede imponer al/a la acusado/a, en aplicación del art. 382 CP, la pena de la infracción más gravemente penada en su mitad superior, que es la del delito del art. 381.1 CP: [PENA DE PRISIÓN] de prisión, con inhabilitación especial para el derecho de sufragio pasivo durante el tiempo de la condena (art. 56 CP), multa de [Nº DE MESES] meses con una cuota diaria de [CUOTA] euros y responsabilidad personal subsidiaria en caso de impago (art. 53 CP), y privación del derecho a conducir vehículos a motor y ciclomotores por tiempo de [Nº DE AÑOS] años (art. 382, párrafo segundo, CP), con pérdida de vigencia del permiso (art. 47 CP).

[NOTA DE REVISIÓN: El art. 381.1 castiga con prisión de dos a cinco años, multa de doce a veinticuatro meses y privación del derecho a conducir de seis a diez años; es siempre más grave que cualquiera de las penas del art. 152.1, de modo que la elección «conducción temeraria / lesiones» del original no procede. Mitad superior: prisión de tres años y seis meses a cinco años y multa de dieciocho a veinticuatro meses. Desde la LO 2/2019, cuando el resultado lesivo concurre con el art. 381 la privación del derecho a conducir se impone en todo caso en su mitad superior: de ocho a diez años. El original omitía la multa y esta regla. Fuente: CP arts. 381 y 382 (redacc. LO 2/2019, BOE-A-2019-2973).]

SEXTA.- Como responsabilidad civil, el/la acusado/a indemnizará a D./Dña. [NOMBRE Y APELLIDOS DEL PERJUDICADO] en la cantidad total de [IMPORTE TOTAL] euros, con la responsabilidad civil directa de la Compañía de Seguros [ASEGURADORA] (art. 117 CP), que al folio [Nº DE FOLIO] de la pieza de responsabilidad civil consta que afianzó las responsabilidades de este orden, [OPCIONAL: y la responsabilidad civil subsidiaria de D./Dña. [TITULAR DEL VEHÍCULO], titular del vehículo (art. 120.5.º CP),] por los siguientes conceptos:

- [IMPORTE DE LOS DAÑOS] euros por daños en el vehículo matrícula [MATRÍCULA DEL VEHÍCULO DAÑADO].

Las siguientes cantidades han sido calculadas con arreglo al sistema de valoración del título IV y el anexo del RDLeg. 8/2004, de 29 de octubre, con las cuantías actualizadas al año [AÑO DE LA VALORACIÓN]:

- [IMPORTE POR LESIONES] euros por las lesiones temporales.

- [IMPORTE POR SECUELAS] euros por las secuelas.

Dichas cantidades devengarán, a cargo de la aseguradora, el interés del art. 20 de la Ley 50/1980, de Contrato de Seguro, desde la fecha del siniestro (art. 9 RDLeg. 8/2004).

Las costas deberán ser satisfechas por el/la acusado/a, incluidas las de esta acusación particular (art. 123 CP y art. 240 LECrim).

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita, tenga por evacuado el traslado conferido y por formulada acusación contra D./Dña. [NOMBRE Y APELLIDOS DEL ACUSADO], y acuerde la apertura del juicio oral ante la Sección de lo Penal del Tribunal de Instancia de [SEDE].

[OPCIONAL — incluir si procede]

(Si la aseguradora aún no ha afianzado o consignado las cantidades por responsabilidad civil)

Igualmente, intereso que en el auto de apertura del juicio oral se requiera a la Compañía de Seguros [ASEGURADORA], con base en el art. 7.7 RDLeg. 8/2004, de 29 de octubre, y los arts. 764.3 y 765 LECrim, para que, hasta el límite del seguro obligatorio, afiance la cantidad de [IMPORTE DE LA FIANZA] euros para hacer frente a las responsabilidades civiles que se deriven de los hechos que han dado lugar a las presentes actuaciones.

[NOTA DE REVISIÓN: El deber del asegurador de afianzar y de abonar las pensiones provisionales está hoy en el apartado 7 del art. 7 RDLeg. 8/2004; el apartado 6, que citaba el original, regula el plazo del reconocimiento por el Instituto de Medicina Legal. Fuente: RDLeg. 8/2004 art. 7 (redacc. Ley 5/2025, BOE-A-2025-15424; texto en BOE-A-2004-18911).]

Es de Justicia que pido en [LUGAR], a [FECHA DEL ESCRITO].

OTROSÍ DIGO: Que para el juicio oral intereso la práctica de los siguientes:

MEDIOS DE PRUEBA

Los propuestos por el Ministerio Fiscal, aunque este renuncie a ellos, y además los siguientes:

[OPCIONAL — incluir si procede]

1.- Interrogatorio del/de la acusado/a.

[OPCIONAL — incluir si procede]

2.- Testifical: declaración de los testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados [ELEGIR: por medio de la oficina judicial / mediante exhorto]:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

-D./Dña. [NOMBRE Y APELLIDOS DEL TESTIGO], que presenció el accidente.

-Agentes de [CUERPO] con TIP [NÚMEROS], autores del atestado.

-D./Dña. [NOMBRE Y APELLIDOS DEL TESTIGO], representante del taller donde se efectuó o se efectuará la reparación.

-D./Dña. [NOMBRE Y APELLIDOS DEL TESTIGO], representante del centro de trabajo del/de la perjudicado/a.

[OPCIONAL — incluir si procede]

3.- Pericial: del/de la médico forense D./Dña. [NOMBRE Y APELLIDOS DEL FORENSE], para que ratifique y aclare su informe de sanidad de fecha [FECHA DEL INFORME] (folio [Nº DE FOLIO]).

[OPCIONAL — incluir si procede]

4.- Documental, por lectura de los siguientes folios:

-Atestado elaborado por [CUERPO].

-Fotografías del estado del vehículo y del lugar del accidente [OPCIONAL: y de los demás daños materiales causados].

-Facturas o presupuesto de reparación del vehículo.

-Facturas de los gastos médicos.

-Reclamación del perjudicado a la aseguradora del/de la acusado/a (art. 7.1 RDLeg. 8/2004), a efectos del devengo de los intereses de demora desde la fecha del siniestro (art. 20.6.º de la Ley 50/1980, de Contrato de Seguro, y art. 9 RDLeg. 8/2004).

[NOTA DE REVISIÓN: La reclamación previa al asegurador está en el art. 7.1 RDLeg. 8/2004 (el 7.2 regula la oferta motivada) y el término inicial de los intereses, en la regla 6.ª del art. 20 LCS (la 3.ª solo define cuándo hay mora). Fuente: RDLeg. 8/2004 art. 7 (BOE-A-2004-18911); Ley 50/1980 art. 20 (BOE-A-1980-22501).]

Por todo lo expuesto,

SUPLICO A LA SECCIÓN: que declare pertinentes las pruebas interesadas y acuerde su práctica.

[OPCIONAL — incluir solo si hay pensión provisional acordada]

SEGUNDO OTROSÍ DIGO: que interesa a esta parte que se mantenga el abono de la pensión provisional acordada por este órgano judicial en auto de fecha [FECHA DEL AUTO DE PENSIÓN] (art. 765.1 LECrim) hasta la firmeza de la sentencia.

SUPLICO A LA SECCIÓN: que así lo acuerde.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a	Firma de Procurador/a

================================================================================
