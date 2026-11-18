---
name: infraccion-normas-riesgos-laborales-imprudencia-grave-686
description: "Redacta el escrito «Infracción de normas de riesgos laborales por imprudencia grave: defensa» (formulario 686 de delitos contra los derechos de los trabajadores, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Infracción de normas de riesgos laborales por imprudencia grave: defensa

> Formulario 0686 del plugin **Delitos contra los derechos de los trabajadores** · revisado el 17-11-2026.

## Paso 0: Jurisprudenciator en esta skill (obligatorio)

**Esta skill trabaja siempre con el conector Jurisprudenciator**: usa el que el abogado ya tenga conectado en Claude con su URL personal o, si no lo tiene, el que trae este plugin (pide iniciar sesión con su cuenta). Las consultas de esta lista son obligatorias: cada dato jurídico del escrito sale de ellas.

- **Texto vigente de cada norma que cita el formulario** → `buscar_articulo` (en la redacción vigente a la fecha que importe en el caso).
- **Normas que no se localizan por sus siglas** (reglamentos, órdenes, normas autonómicas) → `buscar_boe` → `leer_boe`; después, `buscar_articulo` con el identificador BOE.
- **Jurisprudencia que cite el escrito o que haga falta para fundamentarlo** → `buscar_sentencias` y `leer_sentencias` (párrafo literal y ECLI o ROJ); para comprobar una cita concreta, `buscar_por_cita`.
- **Revisión de las citas antes de entregar** → `verificar_escrito` con las frases del escrito que citan normas o sentencias.
- **Convenio colectivo aplicable** (salario, jornada, categorías, faltas y sanciones) → `buscar_convenio` → `leer_convenio`; si sigue vigente o está denunciado, `vigencia_convenio`.
- **Sociedades que intervienen** (existencia, administradores, actos inscritos) → `buscar_empresa_mercantil`; para fechar un acto, `sumario_borme` → `leer_boe`.

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
- [ ] NOMBRE Y APELLIDOS (5 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] DELITO
- [ ] LUGAR
- [ ] FECHA

## Elecciones que hay que hacer

- judicialmente / mediante exhorto

## Párrafos opcionales (3)

Inclúyelos solo si encajan en los hechos:

- 1.- Declaración de los/as siguientes testigos, que deberán ser citados/as [ELEGIR: judicialmente / mediante ex…
- - D./Dña. [NOMBRE Y APELLIDOS], trabajador/a.…
- .- Documental: consistente en acta de la Inspección de trabajo y copia del programa de las medidas de segurida…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 317 CP
- artículo 784.1 de la Ley de Enjuiciamiento Criminal
- art. 784 LECRIM
- art. 316 CP
- artículo 14.2 Ley 31/1995
- artículo 8.3 CP
- artículo 316 CP
- artículo 77 CP
- art. 777.2 LECr

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

### Formulario 0686 · Infracción de normas de riesgos laborales por imprudencia grave: defensa

- Año del modelo: 2017
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (3); 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 2 párrafos opcionales señalados; 8 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que un empresario presenta sus alegaciones en defensa de acusación por un delito contra los derechos de los trabajadores (art. 317 CP) por no adopción de ninguna medida de seguridad por imprudencia grave.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, en la representación que tengo acreditada de D./Dña. [NOMBRE Y APELLIDOS], acusado/a en las diligencias previas número [Nº DE PROCEDIMIENTO] por el supuesto delito de [DELITO], comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

Que, conforme a lo preceptuado en el artículo 784.1 de la Ley de Enjuiciamiento Criminal, manifiesto mi disconformidad con los escritos de acusación y formulo en plazo (1) escrito de defensa, en base a las siguientes:

CONCLUSIONES

PRIMERA.- Disconforme con la correlativa del Ministerio Fiscal y del acusador particular.

Los hechos que incluye la Fiscalía y la acusación particular, tal y como ocurrieron en realidad, no son constitutivos de infracción punible como delito de imprudencia grave del art. 317 CP. (2) Así, debe tenerse en cuenta que la responsabilidad penal es subjetiva, es decir, descansa en la culpabilidad del causante del daño (art. 5.º CP), mientras que la responsabilidad laboral o civil pueda apreciarse con criterios objetivos o cuasi objetivos.

Cierto es que el/la acusado/a tenía una específica obligación legal o contractual de prevenir el riesgo que comportaba la actuación del/de la trabajador/a para su vida e integridad física, pero solo en las medidas de vigilancia y protección relacionadas, - y aquí está la clave- con la actividad laboral, a fin de que el/la trabajador/a no padeciera por razón del trabajo que tenía encomendado; ahora bien, para exigirle algún tipo de responsabilidad penal es necesario que haya incurrido por negligencia en alguna omisión de medida de seguridad y este incumplimiento no se ha producido, sino alguna infracción leve prevista en la legislación de prevención de riesgos laborales.

No se debe confundir con ello la responsabilidad penal con la civil o la laboral que tienen distintos grados de actuación y formas de manifestarse.

En conclusión, pues, entendemos que el/la acusado/a no incurrió en acción u omisión imprudente, por lo que debe ser absuelto/a.

SEGUNDA.- Niego las correlativas. Mi representado/a no es autor/a del delito por el que se procede ni de ningún otro.

TERCERA.- Disconforme con las correlativas. Al no ser autor/a de ningún delito no pueden existir circunstancias modificativas de la responsabilidad inexistente.

CUARTA.- Disconforme con las correlativas. Procede absolver a mi representado/a con todos los pronunciamientos favorables, por no ser el/la autor/a.

QUINTA.- Disconforme con las correlativas. No puede existir responsabilidad civil cuando no existe delito. Y por lo mismo procede declarar las costas de oficio.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito con sus copias, los admita y por realizada la calificación.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que, para el acto del juicio oral, propongo los siguientes:

MEDIOS DE PRUEBA (3)

Todos los propuestos por el Ministerio Fiscal y el acusador particular y, además, los siguientes:

[OPCIONAL — incluir si procede]

1.- Declaración de los/as siguientes testigos, que deberán ser citados/as [ELEGIR: judicialmente / mediante exhorto]:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS], trabajador/a.

- D./Dña. [NOMBRE Y APELLIDOS], inspector/a de trabajo.

- D./Dña. [NOMBRE Y APELLIDOS], encargado/a del cumplimiento de medidas de seguridad.

[OPCIONAL — incluir si procede]

.- Documental: consistente en acta de la Inspección de trabajo y copia del programa de las medidas de seguridad implementadas en la empresa.

Por lo expuesto,

SUPLICO A LA SECCIÓN: Que declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en el plazo de 10 días desde el traslado del art. 784 LECRIM por el letrado de la administración de Justicia.

(2) Una cosa es la falta de prevención del riesgo equivalente a la omisión de las medidas necesarias y adecuadas exigidas conforme a la legislación laboral y otra distinta su insuficiencia o defectuosidad, lo que debe dar lugar a los dos tipos de comisión previstos, el art. 316 CP doloso y el art. 317 CP imprudente, radicando su diferencia en el elemento subjetivo: conciencia del peligro cuando se trata del tipo doloso, y a pesar de ello se omiten las medidas adecuadas y necesarias, e infracción del deber del cuidado por ausencia de todas las previsibles exigibles al garante de la seguridad y salud de los trabajadores (artículo 14.2 Ley 31/1995). Debe tenerse en cuenta que el ámbito ordinario e intenso de la protección corresponde sustancialmente al derecho laboral y que su trascendencia penal debe constituir remedio extremo. (STS 1355/2000, de 26 de julio, rec. 4716/1998).

El elemento normativo recogido en el art. 316 CP como «infracción de las normas de prevención de riesgos laborales» ha llevado a calificar a este delito como un tipo penal en blanco y, en consecuencia, el art. 317 CP constituye la incriminación de la realización imprudente de un tipo penal en blanco. Para proceder a la interpretación del art. 317 CP, por tanto, es necesario precisar qué contenido tiene ese elemento normativo en la configuración típica del tipo doloso (art. 316 CP) y, tras ello, comprobar si ese mismo contenido debe o no dársele en la interpretación del tipo imprudente.

La normativa infringida en materia de prevención de riesgos laborales suele referirse a los artículos 3 ,14, 15, 17.1 de la Ley 31/95, de 8 de noviembre, Prevención de Riesgos Laborales. Estos incumplimientos deben ser puestos en relación con la normativa específica de equipos de trabajo establecida en el artículo 3.5 y anexo II 1. 14 del Real Decreto 1215/97, por el que se establecen las disposiciones mínimas de seguridad y salud para la utilización de equipos de trabajo por los trabajadores.

Se ha señalado que el art. 316 CP refleja la imprudencia consciente, es comisión por omisión dolosa y el art. 317 CP la imprudencia inconsciente, la comisión por omisión imprudente o por culpa.

Cuando concurra el art. 317 CP con un tipo de imprudencia de resultado de muerte o lesiones se castiga conforme al principio de consunción ( artículo 8.3 CP ) absorbiendo el delito de resultado, por progresión delictiva, al de peligro que describe el artículo 316 CP, aunque habrá supuestos en los que resultaría de aplicación el concurso ideal ( artículo 77 CP ) "... cuando el resultado producido constituye solamente uno de los posibles resultados de la conducta omisiva del responsable de las medidas de seguridad ..." (STS 1036/2002, de 4 de junio, rec. 3307/2000 y STS 2445/2001, de 22 de diciembre, rec. 279/2000).

(3) En los medios de prueba deben indicarse todos aquéllos que se desee practicar en el acto del juicio oral. De todos modos, al comienzo del juicio oral pueden aportarse más pruebas.

También debe pedirse que se reproduzca la grabación o lectura literal de la prueba practicada anticipadamente en la fase de diligencias previas (art. 777.2 LECr.).

================================================================================
