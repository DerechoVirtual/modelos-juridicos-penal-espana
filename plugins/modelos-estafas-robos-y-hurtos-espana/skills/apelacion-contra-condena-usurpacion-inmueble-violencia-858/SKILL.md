---
name: apelacion-contra-condena-usurpacion-inmueble-violencia-858
description: "Redacta el escrito «Apelación contra la condena por usurpación de inmueble con violencia (okupas)» (formulario 858 de delitos contra el patrimonio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Apelación contra la condena por usurpación de inmueble con violencia (okupas)

> Formulario 0858 del plugin **Delitos contra el patrimonio** · revisado el 17-11-2026.

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
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS (8 veces)
- [ ] NÚMERO
- [ ] COLEGIO
- [ ] LOCALIDAD
- [ ] FECHA (4 veces)
- [ ] LUGAR
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «…uando compareció la comisión judicial el»

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 245.1 CP
- artículo 790 de la Ley de Enjuiciamiento Criminal
- artículo 245.1 del Código Penal
- artículo 790.2 de la Ley de Enjuiciamiento Criminal
- art. 847 LECrim
- artículo 849 de la LECrim

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

### Formulario 0858 · Apelación contra la condena por usurpación de inmueble con violencia (okupas)

- Año del modelo: 2016
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (2); 16 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Recurso de apelación presentado por el condenado en procedimiento abreviado en sentencia por delito de usurpación de inmueble con violencia (movimiento okupa) del art. 245.1 CP, por padecer errores en la apreciación de la prueba.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de lo Penal del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, dirigido por el/la Letrado/a abajo firmante D./Dña. [NOMBRE Y APELLIDOS], colegiado/a n.º [NÚMERO] del Ilustre Colegio de Abogados de [COLEGIO], con despacho profesional abierto en [LOCALIDAD], actuando en nombre y representación del/de la condenado/a D./Dña. [NOMBRE Y APELLIDOS] en el juicio oral / sobre delito de usurpación de inmueble del art. 245.1 CP, ante este órgano judicial comparezco y, como más procedente sea en derecho, DIGO:

Que con fecha de [FECHA] se le ha notificado a esta parte la sentencia recaída en fecha [FECHA]. Y, por no considerarla ajustada a derecho, dicho con todo respeto y en términos de estricta defensa, dentro del término legal interpongo contra la misma recurso de apelación (1) en ambos efectos, conforme a lo prevenido en el artículo 790 de la Ley de Enjuiciamiento Criminal, para ante la Audiencia Provincial, en base a las siguientes

ALEGACIONES

ÚNICA.-

La resolución que se recurre padece errores en la apreciación de la prueba como se explica a continuación:

La estancia de D./Dña. [NOMBRE Y APELLIDOS] en el inmueble lo fue solo de forma momentánea por unos días y no con vocación de permanencia, lo que determina la atipicidad de la conducta. (2)

Hay que recordar que el Tribunal Supremo, en STS 800/2014, de 12 de noviembre, Rec. 2374/2013 señala que los delitos de usurpación, tipificados en el Capítulo V del Título XIII del Código Penal de 1995 constituyen una modalidad de delitos patrimoniales que tutelan específicamente los derechos reales sobre bienes inmuebles.

En ellos el bien jurídico protegido es el patrimonio inmobiliario, y como delitos patrimoniales la lesión del bien jurídico requiere que se ocasione un perjuicio al titular del patrimonio afectado, que es el sujeto pasivo del delito y el empleo de violencia o intimidación.

La modalidad delictiva específica de ocupación de inmuebles, introducida en el artículo 245.1 del Código Penal de 1995, requiere para su comisión los siguientes elementos:

a) La ocupación, con violencia o intimidación, de un inmueble, vivienda o edificio que en ese momento no constituya morada de alguna persona, realizada con cierta vocación de permanencia.
b) Que esta perturbación posesoria puede ser calificada penalmente como ocupación, ya que la interpretación de la acción típica debe realizarse desde la perspectiva del bien jurídico protegido y del principio de proporcionalidad que informa el sistema penal (Art 49 3º de la Carta de Derechos Fundamentales de la Unión Europea). Desde ambas perspectivas.

La ocupación inmobiliaria tipificada penalmente es la que conlleva un riesgo relevante para la posesión del sujeto pasivo sobre el inmueble afectado, que es lo que dota de lesividad y significación típica a la conducta, por lo que las ocupaciones ocasionales o esporádicas, sin vocación de permanencia o de escasa intensidad, son ajenas al ámbito de aplicación del tipo.

c) Que el realizador de la ocupación carezca de título jurídico que legitime esa posesión, pues en el caso de que hubiera sido autorizado para ocupar el inmueble, aunque fuese temporalmente o en calidad de precarista, la acción no debe reputarse como delictiva, y el titular deberá acudir al ejercicio de las acciones civiles procedentes para recuperar su posesión.
d) Que conste la voluntad contraria a tolerar la ocupación por parte del titular del inmueble, bien antes de producirse, bien después, lo que especifica este artículo al contemplar el mantenimiento en el edificio "contra la voluntad de su titular", voluntad que deberá ser expresa.
e) Que concurra dolo en el autor, que abarca el conocimiento de la ajeneidad del inmueble y de la ausencia de autorización, unido a la voluntad de afectación del bien jurídico tutelado por el delito, es decir la efectiva perturbación de la posesión del titular de la finca ocupada.

Pues bien, como consta en este caso de la declaración de D./Dña. [NOMBRE Y APELLIDOS], acusado/a en estas diligencias y de los/as testigos que declararon en el juicio oral D./Dña. [NOMBRE Y APELLIDOS], D./Dña. [NOMBRE Y APELLIDOS] y D./Dña. [NOMBRE Y APELLIDOS], el/la recurrente no estuvo en ese inmueble con vocación de permanencia nunca. Es más, cuando compareció la comisión judicial el [COMPLETAR], abandonó el inmueble ante la medida cautelar judicialmente adoptada, saliendo voluntariamente del inmueble. No había voluntad de permanencia. Ni hubo agresión al conserje del edificio en modo alguno.

En su virtud,

SUPLICO A LA SECCIÓN:

Se sirva tener por interpuesto en tiempo y forma recurso de apelación en ambos efectos contra la sentencia de fecha [FECHA] recaída en los precitados autos, lo admita a trámite, acordando la remisión de lo actuado a la Audiencia Provincial a fin de que se dicte sentencia en la que se revoque la recurrida y se absuelva a mi representado/a de la condena impuesta.

OTROSÍ DIGO: Que conforme a lo establecido en el artículo 790.2 de la Ley de Enjuiciamiento Criminal, designo como domicilio para notificaciones la sala del Colegio de Procuradores sita en el mismo edificio de la Audiencia Provincial.

SUPLICO A LA SECCIÓN: Que tenga por efectuada la anterior designación.

Es justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este recurso se presenta:

-Ante: el Juez de lo Penal que dictó la resolución impugnada.
-En el plazo de 10 días a partir del siguiente al de la notificación de la sentencia.

Deben exponerse, de forma ordenada, las alegaciones que quepan contra la sentencia sobre quebrantamiento de normas y garantías procesales, error en la apreciación de la prueba o infracción de normas del ordenamiento jurídico.

Puede pedirse la práctica de pruebas que no se pudieron proponer en el procedimiento abreviado o que se denegaron indebidamente, si se formuló protesta, y las admitidas y no practicadas por causas no imputables al apelante. Véanse STC 22/2013, de 31 de enero y STS 32/2012, de 25 de enero, rec. 932/2011.

A partir del 6 de diciembre de 2015, fecha de entrada en vigor de la L 41/2015, de 5 de octubre, de reforma de la LECrim., contra las sentencias dictadas por las Audiencias Provinciales en grado de apelación ante las dictadas por la Sección de de lo Penal del Tribunal de Instancia cabe, según el art. 847 LECrim., recurso de casación por infracción de ley del motivo previsto en el número 1.º del artículo 849 de la LECrim. Son las dictadas por los jueces de lo penal recurridas en apelación y resueltas por la Audiencia "Cuando, dados los hechos que se declaren probados en las resoluciones comprendidas en los dos artículos anteriores, se hubiere infringido un precepto penal de carácter sustantivo u otra norma jurídica del mismo carácter que deba ser observada en la aplicación de ley penal." Ahora bien, el recurrente deberá citar el precepto penal o la norma jurídica infringida, es decir, se trata de un claro error de norma, no una diferente valoración de la prueba.

(2) La frontera en este delito entre el ilícito civil del precario y el art. 245.1 CP radica en la violencia o intimidación empleada y la permanencia en el inmueble forzando la entrada sin ningún título que le habilite para su permanencia en el inmueble, mientras que en las situaciones de precario hay siempre dudas acerca de la titularidad o razón de esa permanencia. Pero en el delito del art. 245.1 CP existen datos de inexistencia de autorización de acceso tales como haber forzado la cerradura o actos violentos de acceso típicos en la "ocupación".

================================================================================
