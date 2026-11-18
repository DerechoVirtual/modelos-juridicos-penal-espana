---
name: robo-uso-vehiculo-motor-acusacion-870
description: "Redacta el escrito «Robo de uso de vehículo de motor: acusación» (formulario 870 de delitos contra el patrimonio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Robo de uso de vehículo de motor: acusación

> Formulario 0870 del plugin **Delitos contra el patrimonio** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (5 veces)
- [ ] COLEGIO
- [ ] Nº DE COLEGIADO/A
- [ ] LOCALIDAD
- [ ] ACTO O RESOLUCIÓN
- [ ] FECHA (2 veces)
- [ ] CALLE
- [ ] MATRÍCULA
- [ ] IMPORTE (2 veces)
- [ ] CIRCUNSTANCIA
- [ ] PENA
- [ ] LUGAR
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…horas, el/la acusado/a»; «…que se encontraba estacionado en»

## Elecciones que hay que hacer

- judicialmente / mediante exhorto

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (5)

Inclúyelos solo si encajan en los hechos:

- 1.- INTERROGATORIO del/de la acusado/a.…
- .- TESTIFICAL, interrogatorio de testigo que se menciona a continuación y que deberá ser citado [ELEGIR: judic…
- Dña.…
- .- PERICIAL del perito que elaboró el informe de daños.…
- .- DOCUMENTAL: documentación acreditativa de la titularidad del vehículo y de documentos aportados a autos tal…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 244.2 CP
- artículo 780.1 de la Ley de Enjuiciamiento Criminal
- art. 781 LECrim
- art. 780 LECrim
- art. 650 LECrim
- art. 244.2 del Código Penal
- art. 22 CP
- artículo 656 LECr
- art. 777.2 LECrim
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

### Formulario 0870 · Robo de uso de vehículo de motor: acusación

- Año del modelo: 2016
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (2); 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 1 bloques de alternativas señalados; 4 párrafos opcionales señalados; 20 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la acusación presenta sus conclusiones provisionales en un procedimiento abreviado por supuesto delito de robo de uso de vehículo del art. 244.2 CP, por entrar en un vehículo ajeno mediante la fuerza, usarlo y dejarlo después abandonado en la vía pública.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los tribunales del Ilustre Colegio de Abogados [COLEGIO], con nº de colegiado/a [Nº DE COLEGIADO/A] y con despacho profesional abierto en [LOCALIDAD], en representación del acusador/a particular D./Dña. [NOMBRE Y APELLIDOS], comparezco ante este órgano judicial y como mejor proceda en derecho (1), DIGO:

En aplicación del artículo 780.1 de la Ley de Enjuiciamiento Criminal, mediante el presente escrito formulo en plazo solicitud de apertura de juicio oral ante la Sección de lo Penal del Tribunal de Instancia por la vía del art. 781 LECrim y escrito de acusación por la vía del art. 780 LECrim, en relación con el art. 650 LECrim contra [ACTO O RESOLUCIÓN] con base en las siguientes:

CONCLUSIONES

PRIMERA.- El día [FECHA] siendo, aproximadamente, las [Nº] horas, el/la acusado/a [COMPLETAR] esperó a que saliera del aparcamiento sito en la calle [CALLE] el dueño del vehículo matrícula [MATRÍCULA] que se encontraba estacionado en [COMPLETAR] y, aprovechando que el titular de este vehículo salió del parking, entró el/la acusado/a en el mismo por la puerta que estaba abierta. El aparcamiento no disponía de vigilancia alguna, lo que provocó que el/la acusado/a se acercara al vehículo por la puerta del conductor y golpeara el cristal del mismo, rompiéndolo e introduciéndose por la misma ventana en el interior del vehículo hasta colocarse en el asiento del piloto. A continuación, hizo un "puente" para encenderlo, llevándose el vehículo del aparcamiento para utilizarlo, aunque sin intención de apropiárselo, ya que el vehículo fue recuperado aparcado en la calle al día siguiente, al darse cuenta un amigo del querellante de su presencia, al conocerlo, una vez tuvo conocimiento de que había sido sustraído. El vehículo tenía daños por valor de [IMPORTE] euros, tanto al haber hecho el puente, como a resultas de un accidente que tuvo el/la acusado/a, como consta en el informe pericial que se adjuntó a la querella.

La autoría del/de la acusado/a consta en el informe de huellas de los agentes intervinientes en los hechos.

SEGUNDA.- Tales hechos son constitutivos del delito de robo de uso de vehículo del art. 244.2 del Código Penal (2).

TERCERA.- Es responsable del delito de robo de uso de vehículo de motor en concepto de autor/a el/la acusado/a.

CUARTA.-

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

No concurre con respecto al/a la acusado/a ninguna circunstancia modificativa de la responsabilidad penal.

Concurre respecto de el/la acusado/a la agravante genérica de [CIRCUNSTANCIA] del art. 22 CP.

QUINTA.- Procede imponer al/a la acusado/a por el delito de robo de uso de vehículo la pena de [PENA].

SEXTA.- Los daños causados en el vehículo ascienden a la suma de [IMPORTE] euros que se reclaman en concepto de responsabilidad civil.

Las costas deberán ser satisfechas por el/la acusado/a.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita y tenga por realizado el trámite de traslado para acusación.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que, para el juicio oral, intereso la práctica de los siguientes:

MEDIOS DE PRUEBA

Los propuestos por el Ministerio Fiscal y además los siguientes:

[OPCIONAL — incluir si procede]

1.- INTERROGATORIO del/de la acusado/a.

[OPCIONAL — incluir si procede]

.- TESTIFICAL, interrogatorio de testigo que se menciona a continuación y que deberá ser citado [ELEGIR: judicialmente / mediante exhorto]. (Tener en cuenta lo dispuesto en el artículo 656 LECr, que dispone que hay que identificar bien a los testigos)

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

Dña.

[OPCIONAL — incluir si procede]

.- PERICIAL del perito que elaboró el informe de daños.

D./Dña. [NOMBRE Y APELLIDOS]

Y de los agentes autores del informe de huellas dactilares encontradas en el vehículo.

D./Dña. [NOMBRE Y APELLIDOS]

D./Dña. [NOMBRE Y APELLIDOS]

[OPCIONAL — incluir si procede]

.- DOCUMENTAL: documentación acreditativa de la titularidad del vehículo y de documentos aportados a autos tales como informe de daños y de huellas de agentes policiales.

Por todo lo expuesto,

SUPLICO A LA SECCIÓN: que declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a	Firma de Procurador/a

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 10 días hábiles desde que el Juez le emplaza para ello, por la vía del art. 780 LECrim.

En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos, al comienzo del juicio oral pueden aportarse más pruebas.

También debe pedirse que se reproduzca la grabación o lectura literal de la prueba practicada anticipadamente en la fase de diligencias previas (art. 777.2 LECrim).

(2) En los casos de sustracción de vehículos caben en el art. 244 CP varias opciones:

a.- Que lo restituyera, directa o indirectamente, en un plazo no superior a cuarenta y ocho horas (art. 244.1 CP) Hurto de uso.

b.- Empleando fuerza en las cosas (art. 244.2 CP) robo de uso.

c.- Que no se efectúe la devolución (art. 244.3 CP) Hurto o robo.

d.- Que se emplee en la comisión violencia o intimidación en las personas. (art. 244.4 CP) Robo de uso.

En el art. 244 del CP se aprecia una doble remisión. Después de describir los hechos susceptibles de ser estimados como hurto de uso y robo de uso con fuerza en las cosas y fijar sus penas, se especifica en su apartado 3 que «de no efectuarse la restitución en el plazo señalado --no superior a cuarenta y ocho horas--, se castigará el hecho como hurto o robo en sus respectivos casos».

Se exige que no concurra el ánimo de apropiación y que ésta no se lleve a cabo porque, si así se hiciera, serían delitos de robo o hurto, según la modalidad.

Si, además de empleo de fuerza como en este caso, se utilizase violencia o intimidación en las personas, se aplica el art. 244.4 CP que remite a las penas de prisión de 2 a 5 años del art. 242 CP.

================================================================================
