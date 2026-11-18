---
name: estafa-inquilino-no-paga-alquiler-inquiokupacion-escrito-80
description: "Redacta el escrito «Estafa del inquilino que no paga el alquiler (inquiokupación): escrito de acusación» (formulario 80 de delitos contra el patrimonio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Estafa del inquilino que no paga el alquiler (inquiokupación): escrito de acusación

> Formulario 0080 del plugin **Delitos contra el patrimonio** · revisado el 17-11-2026.

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
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS (9 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] FECHA (3 veces)
- [ ] NÚMERO (4 veces)
- [ ] LOCALIDAD
- [ ] CIRCUNSTANCIA
- [ ] PENA
- [ ] IMPORTE
- [ ] LUGAR
- [ ] NOMBRE DEL NOTARIO
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…ada. Y lo mismo ocurrió con los meses de»; «… agravantes. Concurre en el/la acusado/a»

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (6)

Inclúyelos solo si encajan en los hechos:

- 1.- Interrogatorio del/ de la acusado/a.…
- .- Testifical:…
- D./Dña. [NOMBRE Y APELLIDOS] vecinos que escucharon al arrendatario decir que no iba a pagar las rentas.…
- [OPCIONAL — incluir si procede]…
- .- Pericial:…
- (Si no se adoptó o pidió en su momento)…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 781.1 de la LECrim
- artículo 650 LECrim
- artículo 780 de la Ley de Enjuiciamiento Criminal
- artículo 14 de la LECrim
- art. 248 CP
- art. 22 del CP

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

### Formulario 0080 · Estafa del inquilino que no paga el alquiler (inquiokupación): escrito de acusación

- Año del modelo: 2023
- Revisión 17-11-2026: 4 llamadas a nota sin texto retiradas; 1 párrafos repetibles señalados; 1 bloques de alternativas señalados; 5 párrafos opcionales señalados; 25 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales, actuando en representación de D./Dña. [NOMBRE Y APELLIDOS], acusador particular, según consta acreditado en el Procedimiento Abreviado [Nº DE PROCEDIMIENTO] seguido ante ese órgano judicial, comparezco y como proceda en Derecho DIGO:

Que evacuando el traslado conferido por auto de fecha [FECHA], de conformidad con lo establecido en el artículo 781.1 de la LECrim, en relación con el artículo 650 LECrim, presento ESCRITO DE ACUSACIÓN Y SOLICITO LA APERTURA DEL JUICIO ORAL ante la Sección de lo Penal del Tribunal de Instancia de [SEDE] plaza nº [NÚMERO], al amparo del artículo 780 de la Ley de Enjuiciamiento Criminal, con arreglo a lo dispuesto en el artículo 14 de la LECrim, con base en las siguientes

CONCLUSIONES

PRIMERA.- Los hechos que motivan la acusación son los siguientes:

El/La acusado/a concertó contrato de arrendamiento en fecha [FECHA] con el/la querellante/a con respecto al inmueble propiedad del/de la querellante sito en [LOCALIDAD]. El contrato se concertó por tiempo de un año prorrogable a instancia del/de la arrendatario/a hasta cinco años, con arreglo a la LAU.

El día de la firma del contrato el/la acusado/a abonó el primer mes de fianza y la primera mensualidad, pero con la verdadera intención de dejar de abonar las mensualidades siguientes, como así hizo, ya que el mes de ya empezó a dejar de pagar las rentas pactadas.

El/La querellante envío correo electrónico al/a la acusado/a (doc nº 1) requiriendo el pago de la mensualidad siguiente al contrato no pagada. Y lo mismo ocurrió con los meses de [COMPLETAR] hasta la fecha de la querella. Se han enviado los requerimientos de pago del/de la querellante al/a la acusado/a sin contestación alguna (docs nº 2 al 19).

La intención del/de la acusado/a cuando firmó el arrendamiento fue la de ocupar el inmueble bajo la apariencia del contrato de arrendamiento, pero con la idea de dejar de pagar de inmediato, por lo que concurre engaño bastante para provocar el error en el/la querellante de entregar la posesión del inmueble al/a la acusado/a obligándole a acudir a la justicia para recuperar la posesión.

Al mes siguiente de la firma del contrato y sucesivos el/la querellante envío whatsapps al/a la acusado/a reclamando explicaciones ante el impago, dando el/la acusado/a largas sin sentido alguno sobre por qué dejó de pagar.

Por estos hechos el/la querellante ha sufrido daño moral psicológico acreditado por informe del psicólogo D./Dña. [NOMBRE Y APELLIDOS].

SEGUNDA.- Tales hechos son constitutivos de un delito de estafa del art. 248 CP, puesto que se dan todos los requisitos legales y jurisprudenciales (SSTS 35/2020 de 6 Feb. 2020 y 743/2022 de 20 de julio, Rec. 1648/2020) para ello:

a. Existe engaño bastante por existir un dolo coetáneo al momento de la firma de que el arrendatario dejará de pagar de inmediato la renta.
b. Concurre ánimo de lucro porque se beneficia del uso de un inmueble con la intención de no pagar rentas desde que pase el primer mes.
c. Produce error en el arrendador, ya que le entrega las llaves del inmueble para que lo ocupe en la confianza de que, al pagarle lo pactado de un mes de fianza y el primer mes, continuará pagando las restantes mensualidades, cuando no existe voluntad alguna ni intención de hacerlo.
d. Con su actitud el arrendatario inquiokupa induce al arrendador a que le firme el arrendamiento y le entregue las llaves para ocupar el inmueble con la cobertura aparente del contrato de arrendamiento que actúa como una especie de «tapadera» para tratar de cubrir la existencia, en su caso, de un incumplimiento civil.
e. Existe perjuicio de tercero en los actos de la inquiokupación, dado que el propietario deja de cobrar las rentas, no puede disponer de su inmueble durante el tiempo que dure un procedimiento judicial y se le obliga a impetrar el auxilio de la justicia para poder obtener, en su caso, el lanzamiento.

TERCERA.- Es responsable del delito en concepto de autor/a el/la acusado/a.

CUARTA.-

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

No concurren en el/la acusado/a circunstancias agravantes.

Concurre en el/la acusado/a [COMPLETAR] la circunstancia agravante de [CIRCUNSTANCIA] del art. 22 del CP.

QUINTA.- Procede imponer al/a la acusado/a D./Dña. [NOMBRE Y APELLIDOS] la pena de [PENA].

SEXTA.- El importe de la responsabilidad civil es de [IMPORTE] euros, por daño moral psicológico más las facturas abonadas por impago de rentas hasta el lanzamiento del inmueble.

Las costas deberán ser satisfechas por el/la acusado/a.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita y tenga por realizado el trámite de traslado para acusación.

Es de Justicia que pido en [LUGAR], a [FECHA].

PRIMEROTROSÍ DIGO: Que para el juicio oral intereso la práctica de los siguientes:

MEDIOS DE PRUEBA

[OPCIONAL — incluir si procede]

1.- Interrogatorio del/ de la acusado/a.

[OPCIONAL — incluir si procede]

.- Testifical:

-Declaración de D./Dña. [NOMBRE Y APELLIDOS] víctima de los hechos, para que declare sobre lo ocurrido.
-Declaración de D./Dña. [NOMBRE Y APELLIDOS] encargado de la inmobiliaria donde ser firmó el arrendamiento.
[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

D./Dña. [NOMBRE Y APELLIDOS] vecinos que escucharon al arrendatario decir que no iba a pagar las rentas.

[OPCIONAL — incluir si procede]

[OPCIONAL — incluir si procede]

.- Pericial:

D./Dña. [NOMBRE Y APELLIDOS] psicólogo al que acudió el querellante, que acreditará el daño moral sufrido por la pérdida de la posesión con conducta engañosa del/de la acusado/a.

.- Documental siguiente:

-Contrato de arrendamiento donde consta la cláusula anti inquiokupas (doc nº [NÚMERO]).
-Los requerimientos efectuados al/ a la acusado/a (docs nº [NÚMERO])
-Whatsapps remitidos al/a la acusado/a donde se le requería de pago no dando el arrendatario explicación alguna de no pagar al mes siguiente de la firma del contrato.
Se aporta adveración del LAJ sobre los whatsapps y aportación escrita de su contenido, así como acta notarial del Notario D./Dña. [NOMBRE DEL NOTARIO].
-Nómina del/de la acusado/a y contrato laboral aportados a la firma del contrato que han resultado irregulares. Otros aportados a los nº [NÚMERO] para aparentar solvencia, siendo falsos.
-Acta notarial del notario D./Dña. [NOMBRE Y APELLIDOS] respecto de los whatsapps del/de la acusado/a dando largas injustificadas del impago.

Por todo lo expuesto,

SUPLICO A LA SECCIÓN: que declare pertinentes las pruebas interesadas y acuerde su práctica, así como se adopten las medidas cautelares para asegurar las responsabilidades civiles y las costas.

[OPCIONAL — incluir si procede]

(Si no se adoptó o pidió en su momento)

SEGUNDO OTROSI DIGO: Se interesa que se acuerde la medida cautelar de expulsión inmediata del/de la arrendatario/a acusado/a, en base a los artículos 13 y 544 bis LECRIM, dado que la finalidad de firmar el contrato de arrendamiento fue la de aparentar la cobertura documental para ocupar el inmueble de forma falsa con la originaria intención de dejar de pagar de inmediato.

SUPLICO A LA SECCIÓN: Que acuerde la medida cautelar solicitada.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a	Firma de Procurador/a

================================================================================
