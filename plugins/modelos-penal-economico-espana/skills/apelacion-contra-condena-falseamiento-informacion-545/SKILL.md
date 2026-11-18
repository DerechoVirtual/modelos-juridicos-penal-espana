---
name: apelacion-contra-condena-falseamiento-informacion-545
description: "Redacta el escrito «Apelación contra la condena por falseamiento de información financiera por internet» (formulario 545 de delitos económicos y de empresa, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Apelación contra la condena por falseamiento de información financiera por internet

> Formulario 0545 del plugin **Delitos económicos y de empresa** · revisado el 17-11-2026.

## Paso 0: Jurisprudenciator en esta skill (obligatorio)

**Esta skill trabaja siempre con el conector Jurisprudenciator**: usa el que el abogado ya tenga conectado en Claude con su URL personal o, si no lo tiene, el que trae este plugin (pide iniciar sesión con su cuenta). Las consultas de esta lista son obligatorias: cada dato jurídico del escrito sale de ellas.

- **Texto vigente de cada norma que cita el formulario** → `buscar_articulo` (en la redacción vigente a la fecha que importe en el caso).
- **Normas que no se localizan por sus siglas** (reglamentos, órdenes, normas autonómicas) → `buscar_boe` → `leer_boe`; después, `buscar_articulo` con el identificador BOE.
- **Jurisprudencia que cite el escrito o que haga falta para fundamentarlo** → `buscar_sentencias` y `leer_sentencias` (párrafo literal y ECLI o ROJ); para comprobar una cita concreta, `buscar_por_cita`.
- **Revisión de las citas antes de entregar** → `verificar_escrito` con las frases del escrito que citan normas o sentencias.
- **Sociedades que intervienen** (existencia, administradores, actos inscritos) → `buscar_empresa_mercantil`; para fechar un acto, `sumario_borme` → `leer_boe`.
- **Criterio de Hacienda y del TEAC** → `buscar_consultas_hacienda` → `leer_consulta_hacienda`; `buscar_doctrina_teac` → `leer_resolucion_teac`.

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
- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] NÚMERO
- [ ] FECHA (3 veces)
- [ ] LUGAR
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «…Documental consistente en aportación de:»

## Elecciones que hay que hacer

- no se pudieron proponer en primera instancia / se denegaron indebidamente habiéndose formulado protesta / no se practicaron por causas no imputables al apelante

## Párrafos opcionales (5)

Inclúyelos solo si encajan en los hechos:

- PRIMER OTROSÍ DIGO: En aplicación del art. 790.3 LECrim., se solicitan las siguientes pruebas (5), que [ELEGIR…
- 1.- Testifical: A cuyo fin deberán ser citadas a través de la oficina judicial las siguientes personas:…
- - D./Dña. [NOMBRE Y APELLIDOS].…
- .- Pericial técnica contradictoria con la de la acusación sobre la falsedad de la información financiera, a cu…
- .- Documental consistente en aportación de: [COMPLETAR].…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 282 bis CP
- artículo 790 de la Ley de Enjuiciamiento Criminal
- art. 282 bis CP
- art. 790.3 LECrim
- artículo 790.2 de la Ley de Enjuiciamiento Criminal

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

### Formulario 0545 · Apelación contra la condena por falseamiento de información financiera por internet

- Año del modelo: 2018
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (5); 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 4 párrafos opcionales señalados; 9 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que se recurre en apelación la condena por delito de falseamiento de información financiera del artículo 282 bis CP, alegando que no ha habido tal falseamiento, demostrado con pericial técnica contradictoria.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de lo Penal del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, actuando en nombre y representación del recurrente D./Dña. [NOMBRE Y APELLIDOS] en el juicio oral número [NÚMERO] sobre delito contra el mercado y los consumidores del artículo 282 bis CP, ante este órgano judicial comparezco y, como más procedente sea en derecho, DIGO:

Que con fecha [FECHA] se le ha notificado a esta parte la sentencia recaída en fecha [FECHA] y, por no considerarla ajustada a derecho, dicho con todo respeto y en términos de estricta defensa, dentro del término legal (2) interpongo contra la misma recurso de apelación en ambos efectos, conforme a lo prevenido en el artículo 790 de la Ley de Enjuiciamiento Criminal, para ante la Audiencia Provincial, en base a las siguientes

ALEGACIONES (3)

ÚNICA.-

La resolución que se recurre padece errores en la apreciación de la prueba como se explica a continuación:

No negamos que el resultado final de la inversión no fuera el esperado, pero no ha habido ninguna falsedad de la información económico-financiera expuesta por internet y en otros medios de publicidad, sino que fue el devenir de la situación económica el que provocó que la inversión no fuera positiva finalmente, por lo que los inversionistas también corren el riesgo con su inversión que no pueden trasladar a la empresa, ya que lo asumen cuando realizan la misma.

Siendo la clave del tipo penal del art. 282 bis CP el falseamiento (4), se aporta dictamen pericial contradictorio con el de la querella interpuesta que desmonta ese dictamen determinante de la inexistencia del falseamiento denunciado.

No hay por ello prueba válida de ilícito penal alguno.

Por lo tanto, se ha infringido la presunción de inocencia, ya que es conocida al respecto la abundantísima doctrina reiteradamente expuesta por el Tribunal Supremo (ver la STS de 4 de mayo de 1995, rec. 3299/1994) relativa a que es fundamental, para enervar la presunción, que los jueces hayan dispuesto de prueba válida, practicada de forma inmediata y contradictoria en el plenario. Publicidad, oralidad, inmediación y contradicción. Y que los datos objetivos cuando están suficientemente probados en las actuaciones se constituyen en factores valedores para la destrucción del derecho fundamental si concurren, cual ahora no acontece, con otros medios probatorios (STS de 24 de enero de 1995, rec. 2745/1994).

En su virtud,

SUPLICO A LA SECCIÓN:

Se sirva tener por interpuesto en tiempo y forma recurso de apelación en ambos efectos contra la sentencia recaída en los precitados autos, lo admita a trámite, acordando la remisión de lo actuado a la Audiencia Provincial a fin de que se dicte sentencia en la que se revoque la recurrida y se absuelva a mi representado/a de la condena impuesta.

Es justicia que pido en [LUGAR], a [FECHA].

[OPCIONAL — incluir si procede]

PRIMER OTROSÍ DIGO: En aplicación del art. 790.3 LECrim., se solicitan las siguientes pruebas (5), que [ELEGIR: no se pudieron proponer en primera instancia / se denegaron indebidamente habiéndose formulado protesta / no se practicaron por causas no imputables al apelante].

[OPCIONAL — incluir si procede]

1.- Testifical: A cuyo fin deberán ser citadas a través de la oficina judicial las siguientes personas:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS].

[OPCIONAL — incluir si procede]

.- Pericial técnica contradictoria con la de la acusación sobre la falsedad de la información financiera, a cuyo fin deberá ser citado/a a través de la oficina judicial el/la siguiente perito:

- D./Dña. [NOMBRE Y APELLIDOS].

[OPCIONAL — incluir si procede]

.- Documental consistente en aportación de: [COMPLETAR].

SUPLICO A LA SECCIÓN: Que tenga por solicitadas las pruebas propuestas.

SEGUNDO OTROSÍ DIGO: Que, conforme a lo establecido en el artículo 790.2 de la Ley de Enjuiciamiento Criminal, designo como domicilio para notificaciones la sala del Colegio de Procuradores, sita en el mismo edificio de la Audiencia Provincial.

SUPLICO A LA SECCIÓN: Que tenga por efectuada la anterior designación.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este recurso se presenta ante el Juez de lo Penal que dictó la resolución impugnada.

(2) Plazo para presentar el recurso: de 10 días a partir del siguiente al de la notificación de la sentencia.

(3) Deben exponerse de forma ordenada las alegaciones que quepan contra la sentencia sobre quebrantamiento de normas y garantías procesales, error en la apreciación de la prueba o infracción de normas del ordenamiento jurídico.

(4) Se trata de un delito que se comete por personas que tengan cargo de administrador, ya de derecho, ya de hecho, admitiendo en esta segunda modalidad a cualquier persona que tenga cargo de representación societaria, como puede ser director general. Apoderado, etc. Se refiere a este cargo respecto a entidades que sean emisoras de valores negociados en mercado de valores y que lleven a cabo conductas de falsedad en la información económica de la publicidad. El objetivo, que se exige como elemento del tipo, es la de captar inversores o depositantes para colocar productos financieros u obtener financiación.

La mera falsedad ya conlleva la comisión del delito, ya que si se causa el perjuicio se agrava la pena, ya que la pena básica del apartado 1º es de 1 a 4 años, pero de 2 años y 6 meses a 4 años en el caso del párrafo 2º de que se cause el perjuicio. Y si hay grave perjuicio la pena va en un arco de 1 a seis años.

(5) Puede pedirse la práctica de pruebas que no se pudieron proponer en primera instancia o que se denegaron indebidamente si se formuló protesta y las admitidas y no practicadas por causas no imputables al apelante. Véanse STC 22/2013 de 31 de enero y STS 32/2012, de 25 de enero, rec. 932/2011.

================================================================================
