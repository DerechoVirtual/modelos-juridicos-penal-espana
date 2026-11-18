---
name: administracion-responsable-civil-subsidiaria-escrito-433
description: "Redacta el escrito «Administración responsable civil subsidiaria: escrito de defensa» (formulario 433 de instrucción y procedimiento penal, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Administración responsable civil subsidiaria: escrito de defensa

> Formulario 0433 del plugin **Instrucción y procedimiento penal** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS
- [ ] Nº DE PROCEDIMIENTO
- [ ] FECHA
- [ ] IMPORTE
- [ ] LUGAR
- [ ] Otros 5 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…o en representación de la Administración»; «…ilmente la Administración que represento»; «…2. Testifical, de D»; «…siguientes diligencias sumariales: folio»; «…; y folio»

## Párrafos opcionales (3)

Inclúyelos solo si encajan en los hechos:

- 1. Interrogatorio del acusado.…
- 2. Testifical, de D [COMPLETAR], jefe del departamento de licencias, de cuya comparecencia al acto del juicio …
- 3. Documental, mediante lectura de las siguientes diligencias sumariales: folio [COMPLETAR]; y folio [COMPLETA…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 121 CP
- art. 784.1 de la Ley de Enjuiciamiento Criminal
- arts. 650 y 652 de la LECrim
- art. 121 del Código Penal

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

### Formulario 0433 · Administración responsable civil subsidiaria: escrito de defensa

- Año del modelo: 2020
- Revisión 17-11-2026: 3 párrafos opcionales señalados; 10 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la defensa de una Administración Pública presenta sus conclusiones provisionales en un procedimiento abreviado frente a su presunta responsabilidad civil subsidiaria por el delito cometido por un funcionario, conforme al art. 121 CP.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, actuando en representación de la Administración [COMPLETAR], presunta responsable civil subsidiaria en este procedimiento, según consta acreditado en el Procedimiento Abreviado [Nº DE PROCEDIMIENTO] seguido ante ese órgano judicial, comparezco y, como proceda en Derecho, DIGO:

Que, evacuando el traslado conferido por auto de fecha [FECHA], de conformidad con lo dispuesto en el art. 784.1 de la Ley de Enjuiciamiento Criminal, en relación con los arts. 650 y 652 de la LECrim, mediante el presente escrito manifiesto mi absoluta disconformidad con la solicitud de responsabilidad civil subsidiaria deducida contra mi representada, formulando las siguientes

CONCLUSIONES PROVISIONALES

PRIMERA.- En total disconformidad con la correlativa de las acusaciones.

Se acepta que el/la acusado/a era funcionario/a de la Administración, pero se niega que su conducta sea constitutiva de delito, que fuera desempeñada en el ejercicio de su cargo, y que los presuntos daños y perjuicios derivados de la misma tengan conexión directa con el funcionamiento del servicio que tenía encomendado el funcionario en cuestión.

Los hechos relatados en la conclusión primera de la acusación quedan fuera del ejercicio del cargo del funcionario en el departamento de asistencia social, puesto que se refieren a la posible influencia del mismo en la resolución dictada por el departamento de licencias, de manera que la actuación está fuera de las competencias y atribuciones del/de la funcionario/a público/a acusado/a. Del mismo modo, los daños y perjuicios alegados no derivan de un funcionamiento anormal del servicio de licencias, puesto que en ningún momento se cuestiona la legalidad de la resolución de concesión de la licencia, sino de la posible interferencia del/de la funcionario/a acusado/a en la voluntad del personal del departamento de licencias.

La jurisprudencia condiciona la responsabilidad civil subsidiaria del art. 121 CP a que la persona dependiente esté en el ejercicio de sus funciones y a que la actividad de desempeño de servicio público que realice determine directamente la lesión como consecuencia del mismo (STS, Sala Segunda, 5 julio 2002 y STS 13 junio 2003, entre otras), lo cual no se produce en este caso, según los hechos del escrito de acusación.

SEGUNDA.- En total disconformidad con la correlativa de las acusaciones. Los hechos relatados no son constitutivos de delito, por lo que no se da el supuesto de hecho de exigencia de responsabilidad civil subsidiaria.

TERCERA.- En total disconformidad con la correlativa de las acusaciones. El/La acusado/a no es responsable al no ser los hechos constitutivos de delito.

CUARTA.- En total disconformidad con la correlativa de las acusaciones. Sin responsabilidad criminal imputable no cabe hablar de circunstancias modificativas.

QUINTA.- En total disconformidad con la correlativa de las acusaciones. De los citados hechos no responde civilmente la Administración que represento [COMPLETAR], al no darse los requisitos del art. 121 del Código Penal puesto que: (i) no aparece cometido delito doloso o culposo por el/la funcionario/a acusado/a; (ii) los hechos relatados en el escrito de acusación no están realizados en el ejercicio del cargo o función que tenía el/la acusado/a en la Administración que represento; y (iii) los daños y perjuicios reclamados no tienen conexión directa con el funcionamiento de los servicios públicos que estaban encomendados al/a la funcionario/a acusado/a.

De forma subsidiaria, existe pluspetición, puesto que los daños y perjuicios acreditados ascienden a la cantidad de [IMPORTE] euros, y no a la solicitada por las acusaciones, por lo que el pronunciamiento debe limitarse a dicha cantidad.

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por evacuado el trámite conferido y por formulado el escrito de defensa.

Es Justicia que pido en [LUGAR]

PRIMER OTROSÍ DIGO: Que, para el acto del juicio oral, esta representación propone los siguientes medios de prueba, necesarios para la defensa de sus intereses:

[OPCIONAL — incluir si procede]

1. Interrogatorio del acusado.

[OPCIONAL — incluir si procede]

2. Testifical, de D [COMPLETAR], jefe del departamento de licencias, de cuya comparecencia al acto del juicio cuidará esta parte.

[OPCIONAL — incluir si procede]

3. Documental, mediante lectura de las siguientes diligencias sumariales: folio [COMPLETAR]; y folio [COMPLETAR]

SUPLICO A LA SECCIÓN: Que tenga por propuesta la prueba para ante el órgano judicial de enjuiciamiento.

Es Justicia que reitero en lugar y fecha "ut supra"

Firma de Abogado/a	Firma de Procurador/a

================================================================================
