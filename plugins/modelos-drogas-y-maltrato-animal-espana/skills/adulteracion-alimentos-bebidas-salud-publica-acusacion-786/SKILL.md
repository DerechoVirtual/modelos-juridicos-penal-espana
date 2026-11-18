---
name: adulteracion-alimentos-bebidas-salud-publica-acusacion-786
description: "Redacta el escrito «Adulteración de alimentos o bebidas (salud pública): acusación» (formulario 786 de salud pública y maltrato animal, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Adulteración de alimentos o bebidas (salud pública): acusación

> Formulario 0786 del plugin **Salud pública y maltrato animal** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (8 veces)
- [ ] COLEGIO
- [ ] LOCALIDAD
- [ ] FECHA (2 veces)
- [ ] MARCA/MODELO
- [ ] PENA
- [ ] IMPORTE
- [ ] LUGAR
- [ ] Otros 4 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…o, por lo que se desplazó al hospital de»; «… estado con las siguientes consecuencias»; «…ientes aditivos o agentes no autorizados»; «…mido contenía la sustancia no autorizada»

## Elecciones que hay que hacer

- a continuación / en escrito aparte
- judicialmente / mediante exhorto

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (4)

Inclúyelos solo si encajan en los hechos:

- 1.- Interrogatorio del/de la acusado/a.…
- .- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y …
- .- Pericial: declaración de los/as peritos que se mencionan a continuación, que deberán ser citados/as judicia…
- .- Documental: por lectura de todo lo actuado hasta el momento de la vista oral.…

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 364 CP
- artículo 780.1 de la Ley de Enjuiciamiento Criminal
- art. 781 LECRIM
- art. 780 LECRIM
- art. 650 LECRIM
- art. 22 del CP
- artículo 656 LECr
- art. 363 CP

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

### Formulario 0786 · Adulteración de alimentos o bebidas (salud pública): acusación

- Año del modelo: 2016
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; restos de formato retirados; notas del formulario agrupadas al final (3); 1 desplegables y casillas convertidos en elección en blanco; 1 desplegables convertidos en elección en blanco; 1 bloques de alternativas señalados; 4 párrafos opcionales señalados; 19 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la acusación en un procedimiento abreviado solicita la apertura del juicio oral y presenta sus conclusiones provisionales calificando los hechos de delito contra la salud pública por adulterar alimentos o bebidas del art. 364 CP.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales del Ilustre Colegio de Procuradores de [COLEGIO] y con despacho profesional abierto en [LOCALIDAD], en representación del acusador particular D./Dña. [NOMBRE Y APELLIDOS], comparezco ante este órgano judicial y como mejor proceda en derecho, DIGO:

En aplicación del artículo 780.1 de la Ley de Enjuiciamiento Criminal, mediante el presente escrito formulo solicitud de apertura de juicio oral ante la Sección de lo Penal del Tribunal de Instancia por la vía del art. 781 LECRIM y, en plazo (1), escrito de acusación por la vía del art. 780 LECRIM, en relación con el art. 650 LECRIM, contra con base en las siguientes:

CONCLUSIONES

PRIMERA.- Con fecha [FECHA] D./Dña. [NOMBRE Y APELLIDOS] consumió para comer en su hogar el producto marca [MARCA/MODELO], que estaba embotellado. Esa misma tarde se sintió indispuesto/a y con fuertes dolores en el estómago, por lo que se desplazó al hospital de [COMPLETAR] donde, en urgencias, se agravó su estado con las siguientes consecuencias [COMPLETAR].

A raíz de la intervención por el centro hospitalario se le informó de que había ingerido un alimento en malas condiciones que contenía los siguientes aditivos o agentes no autorizados [COMPLETAR].

Es por ello por lo que, tras ponerse en contacto con la empresa encargada de fabricar el producto, recibió una contestación negativa a su reclamación extrajudicial, pese a remitirles un informe médico en el que, por la analítica realizada, se descubrió que el bote consumido contenía la sustancia no autorizada [COMPLETAR], que además consta en el informe analítico realizado por D./Dña. [NOMBRE Y APELLIDOS].

A consecuencia de la intoxicación estuvo dos semanas de baja médica no pudiendo acudir a su trabajo y con fuertes dolores estomacales que no han dejado secuelas.

SEGUNDA.- Tales hechos son constitutivos del delito de adulteración de alimentos, sustancias o bebidas del art. 364 CP. (2)

TERCERA.- Es responsable del delito del art. 364 CP en concepto de autor/a el/la acusado/a.

CUARTA.-

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

No concurren con respecto al/a la acusado/a circunstancias agravantes.

Concurre con respecto al/a la acusado/a la agravante de del art. 22 del CP.

QUINTA.- Procede imponer al/a la acusado/a la pena de [PENA] por el delito del art. 364 CP.

SEXTA.- En concepto de responsabilidad civil el/la acusado/a deberá satisfacer la suma de [IMPORTE] euros por las dos semanas de baja médica, en base al Anexo del RDLeg. 8/2004, del baremo de indemnización de accidentes de tráfico aplicable por analogía a cualquier otro supuesto ajeno al derecho de la circulación.

Las costas deberán ser satisfechas por el/la acusado/a.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita y tenga por realizado el trámite de traslado para acusación.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que para el juicio oral intereso la práctica de los siguientes:

MEDIOS DE PRUEBA (3)

[OPCIONAL — incluir si procede]

1.- Interrogatorio del/de la acusado/a.

[OPCIONAL — incluir si procede]

.- Testifical: declaración de los/as testigos que se mencionan [ELEGIR: a continuación / en escrito aparte] y que deberán ser citados/as [ELEGIR: judicialmente / mediante exhorto], (Tener en cuenta lo dispuesto en el artículo 656 LECr, que dispone que hay que identificar bien a los testigos)

- D./Dña. [NOMBRE Y APELLIDOS], amigo/a que acompañó a D./Dña. [NOMBRE Y APELLIDOS] al centro médico tras haber consumido el citado alimento.

[OPCIONAL — incluir si procede]

.- Pericial: declaración de los/as peritos que se mencionan a continuación, que deberán ser citados/as judicialmente:

- D./Dña. [NOMBRE Y APELLIDOS], autor/a del informe de lesiones.
- D./Dña. [NOMBRE Y APELLIDOS], autor/a del informe sobre analítica del agente encontrado en el bote de comida.

[OPCIONAL — incluir si procede]

.- Documental: por lectura de todo lo actuado hasta el momento de la vista oral.

Por todo lo expuesto,

SUPLICO A LA SECCIÓN: Que declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 10 días hábiles desde la notificación del auto del juez por la vía del art. 780 LECRIM solicitando la apertura del juicio oral formulando escrito de acusación.

(2) Este es un delito esencialmente doloso tipificado en el art. 364 CP que lleva aparejada la pena de 1 a 4 años de prisión, multa de seis a doce meses e inhabilitación especial de tres a seis años del art. 363 CP [NOTA DE REVISIÓN: El art. 363 CP, al que remite el art. 364.1, impone conjuntamente prisión, multa e inhabilitación especial. Fuente: Código Penal, BOE-A-1995-25444, arts. 363 y 364.] y sanciona la adulteración con aditivos o agentes no autorizados susceptibles de causar daños a la salud de las personas efectuado en alimentos sustancias o bebidas. Se exige como elemento objetivo del tipo penal que en los informes periciales se constate la posibilidad de que esos agentes causen o puedan causar un daño a la salud de las personas, ya que si pese a no estar autorizados los aditivos o agentes no causan daño o no lo pueden causar no sería delito, sino una posible infracción administrativa.

Si el acusado es el propietario o responsable de la producción de la fábrica donde se llevó a cabo la operación la pena será además de inhabilitación especial para esa profesión por 6 a 10 años.

Se impondrá la misma pena al que realice cualquiera de las siguientes conductas:

1.º Administrar a los animales cuyas carnes o productos se destinen al consumo humano sustancias no permitidas que generen riesgo para la salud de las personas, o en dosis superiores o para fines distintos a los autorizados.
2.º Sacrificar animales de abasto o destinar sus productos al consumo humano, sabiendo que se les ha administrado las sustancias mencionadas en el número anterior.
3.º Sacrificar animales de abasto a los que se hayan aplicado tratamientos terapéuticos mediante sustancias de las referidas en el apartado 1.º
4.º Despachar al consumo público las carnes o productos de los animales de abasto sin respetar los períodos de espera en su caso reglamentariamente previstos.

(3) En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos, al comienzo del juicio oral pueden aportarse más pruebas.

También debe pedirse que se reproduzca la grabación o lectura literal de la prueba practicada anticipadamente en la fase de diligencias previas (art. 777.2. LECr.)

================================================================================
