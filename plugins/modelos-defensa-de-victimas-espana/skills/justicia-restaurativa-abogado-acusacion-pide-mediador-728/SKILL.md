---
name: justicia-restaurativa-abogado-acusacion-pide-mediador-728
description: "Redacta el escrito «Justicia restaurativa: el abogado de la acusación pide al mediador estar presente» (formulario 728 de víctimas y justicia restaurativa, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Justicia restaurativa: el abogado de la acusación pide al mediador estar presente

> Formulario 0728 del plugin **Víctimas y justicia restaurativa** · revisado el 17-11-2026.

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

- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] NÚMERO
- [ ] DELITO
- [ ] Nº
- [ ] FECHA (2 veces)
- [ ] LUGAR
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…r en el despacho del mediador el próximo»; «…, a [FECHA]. Firma de Abogado/a:»

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- Ley 4/2015

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

### Formulario 0728 · Justicia restaurativa: el abogado de la acusación pide al mediador estar presente

- Año del modelo: 2017
- Revisión 17-11-2026: 10 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que el abogado de la víctima del delito da razones al mediador para que le permita participar en el proceso de mediación para defender sus intereses y para facilitar su positiva conclusión, conforme prevé el art. 15.2 de la L 4/2015 del Estatuto de la Víctima del Delito y la DA 9ª.8 LECRIM.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

Al mediador D./Dña. [NOMBRE Y APELLIDOS]

D./Dña. [NOMBRE Y APELLIDOS] abogado/a en ejercicio y ejercitando la acusación particular de D./Dña. [NOMBRE Y APELLIDOS] y en su nombre y representación en las DP nº [NÚMERO] que se siguen en este órgano judicial, por delito de [DELITO] del art. del CP, contra D./Dña. [NOMBRE Y APELLIDOS] comparezco y, como más procedente sea en derecho, DIGO:

Que se ha citado a la víctima del delito para comparecer en el despacho del mediador el próximo [COMPLETAR] a las [Nº] horas, en base a lo cual se me ha dado traslado por mi cliente solicitando mi presencia en el proceso de la mediación, lo que facilitaría su positiva conclusión y podría posibilitar la adopción del acuerdo que a todas las partes beneficiaría.

Resulta claro y notorio que la víctima del delito sufre en todo este proceso judicial y extrajudicial por la necesidad que tiene de recibir ayuda externa que le permita poder asumir la situación por la que está atravesando. Incluso la propia Ley 4/2015 del Estatuto de la víctima del delito recoge en su articulado la posibilidad de que la víctima se haga acompañar de la persona que desee en las actuaciones policiales y judiciales, por lo que con mayor razón en procesos como este extrajudiciales se hace preciso que también sea acompañada, en este caso por su propio letrado/a para poder estar en condiciones de saber si debe, o no, firmar, ese acuerdo.

Además, señala el Art. 15.2 Ley 4/2015 del Estatuto de la víctima que:

"2. Los debates desarrollados dentro del procedimiento de mediación serán confidenciales y no podrán ser difundidos sin el consentimiento de ambas partes. Los mediadores y otros profesionales que participen en el procedimiento de mediación, estarán sujetos a secreto profesional con relación a los hechos y manifestaciones de que hubieran tenido conocimiento en el ejercicio de su función."

Igualmente, la Disposición Adicional 9.8 de la LECRIM establece que:

"8. Concluido el procedimiento restaurativo, los servicios emitirán un informe sobre el resultado positivo o negativo de la actividad realizada, acompanando, en caso positivo, el acta de reparación con los acuerdos a los que las partes hayan llegado, que estará firmado por las partes personalmentey por sus letrados, si los hubiera."

Así, se recoge que los letrados de las partes podrán participar en este proceso de mediación penal siempre y cuando guarden la confidencialidad de su desarrollo.

Conocida es la filosofía que puede existir en algunos sectores de que la mediación debe desarrollarse al margen de los representantes de las partes en el proceso judicial, pero desde nuestro punto de vista es un error prescindir de los abogados de la acusación y la defensa, porque si se ha asesorado a víctima y acusado de que acudan a la mediación, nuestra presencia en el proceso de mediación solo puede aportar aspectos positivos a la resolución favorable del conflicto, y, sin embargo, nuestra ausencia podría contribuir a dificultar ese objetivo final, ya que aunque la labor del mediador sea muy positiva y profesional, tanto víctima (acusación), como acusado (defensa) se verán más y mejor acompañados en el servicio de mediación elegido y/o designado si cuentan con el/la abogado/a de la acusación y de la defensa.

Hay que tener en cuenta que la presencia del letrado es fundamental en el proceso de mediación penal por cuanto la consecuencia es el proceso de conformidad penal y la presencia del letrado fomenta y ayuda al acuerdo ante el consejo al cliente de su conducta en la mediación para la mejora de sus intereses y para una consecución de la satisfacción de la responsabilidad civil que se debería abonar por el acusado y su repercusión posterior en la conformidad.

Por todo ello,

SOLICITO se admita la presencia del firmante el día [FECHA] para poder tomar participación activa en la consecución de un acuerdo, si tras el desarrollo del proceso de mediación se entendiese que ello es positivo para los intereses de mi cliente.

En [LUGAR], a [FECHA].

Firma de Abogado/a: [COMPLETAR]

================================================================================
