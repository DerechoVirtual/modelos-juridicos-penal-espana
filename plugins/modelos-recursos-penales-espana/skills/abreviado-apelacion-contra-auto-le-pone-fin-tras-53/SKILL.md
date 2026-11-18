---
name: abreviado-apelacion-contra-auto-le-pone-fin-tras-53
description: "Redacta el escrito «Abreviado: apelación contra el auto que le pone fin tras la audiencia preliminar» (formulario 53 de recursos penales, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Abreviado: apelación contra el auto que le pone fin tras la audiencia preliminar

> Formulario 0053 del plugin **Recursos penales** · revisado el 17-11-2026.

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

## Nota explicativa: puntualizaciones de la revisión

La nota explicativa de este formulario se ha revisado en el BOE. Tenlo en cuenta al redactar:

- Los Juzgados de lo Penal pasaron a ser Secciones de lo Penal el 31-12-2025 (DT 1ª LO 1/2025), así que la referencia a «una vez constituido» ha quedado desfasada.
- El art. 785.3 LECrim remite al plazo y forma de los arts. 790 y siguientes (10 días). Si el auto es de la Sección de lo Penal, resuelve la AP. Si es de la AP y acuerda el sobreseimiento libre o declara la falta de jurisdicción, resuelve la Sala de lo Civil y Penal del TSJ (art. 846 ter LECrim).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión. Empieza con una nota explicativa (para qué sirve el escrito y cuándo se usa) y acaba con sus notas al pie, revisadas en el BOE: léela antes de redactar, pero no la copies en el escrito.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] Nº (2 veces)
- [ ] LOCALIDAD (3 veces)
- [ ] NOMBRE Y APELLIDOS (5 veces)
- [ ] FECHA (4 veces)
- [ ] FECHA DEL AUTO
- [ ] LUGAR
- [ ] Otros 3 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…mandante designa al/a la Procurador/a de»; «…ut supra" indicados. Firma de Abogado/a:»; «…Firma de Procurador/a:»

## Elecciones que hay que hacer

- A LA SECCIÓN / A LA SALA
- a la Audiencia Provincial / al TSJ
- la Audiencia Provincial / el TSJ

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- arts. 785.3 y 790 de la LECrim
- art. 785 LECRIM
- art. 766.3 de la LECrim

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

### Formulario 0053 · Abreviado: apelación contra el auto que le pone fin tras la audiencia preliminar

- Año del modelo: 2025
- Revisión 17-11-2026: 1 llamadas a nota sin texto retiradas; 3 desplegables y casillas convertidos en elección en blanco; 2 desplegables convertidos en elección en blanco; 1 bloques de alternativas señalados; 14 campos de relleno marcados en blanco; 2 etiquetas sin dato marcadas en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 1 huecos del original que se habían perdido sin marca, marcados (FECHA DEL AUTO)
- Nota explicativa incorporada desde la colección Procesal (formulario 44) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Escrito por el que la acusación particular presenta recurso de apelación contra auto dictado después de la audiencia preliminar prevista en el art. 785 LECRIM, según redacción dada por LO 1/2025, vigente desde el 3 de abril de 2025, que pone fin al procedimiento abreviado.

---

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

A la Sección de lo Penal del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

A la Audiencia Provincial de [LOCALIDAD]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales y de D./Dña. [NOMBRE Y APELLIDOS], ya circunstanciado como acusación particular, en PA nº [Nº], ante este órgano comparezco y como sea más procedente en Derecho, DIGO:

Que he sido notificado en fecha [FECHA] del Auto de fecha [FECHA], por el que se pone fin al procedimiento y estimando perjudicial y gravosa la mencionada resolución respecto de mi representado/a, me veo obligado a interponer contra ella en tiempo y forma Recurso de Apelación conforme a los arts. 785.3 y 790 de la LECrim., sobre la base de las siguientes

ALEGACIONES

PRIMERA.- Con fecha [FECHA] se celebró la audiencia preliminar prevista en el art. 785 LECRIM, al objeto de dar cumplimiento y resolver las alegaciones realizadas por la defensa en su escrito de defensa.

SEGUNDA.- Que por auto de fecha [FECHA DEL AUTO] se estimó la alegación consistente en expuesta en la citada comparecencia por la defensa y en base a la que se pone fin al procedimiento, vulnerando el derecho a la tutela judicial efectiva de esta parte, por cuanto

TERCERA.- No cabe dictar el auto que ahora se recurre dado que lo que procede es el señalamiento del juicio y continuar la causa en base al art. 786 y 787 ter LECRIM.

Por lo que,

SUPLICO [ELEGIR: A LA SECCIÓN / A LA SALA]:

Que, teniendo por presentado este escrito se sirva admitirlo, y en su virtud, se tenga por interpuesto en tiempo y forma Recurso de Apelación contra el expresado auto y se reforme el mismo dictando otro en el que se acuerde el señalamiento del juicio.

Es de Justicia que pido en [LUGAR], a [FECHA].

OTROSI PRIMERO DIGO.- Dado que la resolución que se recurre es de las que puede poner fin al procedimiento no procede hacer designación de particulares, debiéndose remitir el expediente íntegro [ELEGIR: a la Audiencia Provincial / al TSJ] de [LOCALIDAD] En caso contrario, en cumplimiento del art. 766.3 de la LECrim, esta parte designa como particulares a remitir a la Sala la totalidad de los Autos.

SUPLICO [ELEGIR: A LA SECCIÓN / A LA SALA]: Que tenga por hecha la anterior manifestación.

OTROSI SEGUNDO DIGO.- Que en la sede de [ELEGIR: la Audiencia Provincial / el TSJ] de [LOCALIDAD] mi mandante designa al/a la Procurador/a de [COMPLETAR], D./Dña. [NOMBRE Y APELLIDOS]

SUPLICO [ELEGIR: A LA SECCIÓN / A LA SALA]: Que tenga por hecha la anterior designación.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a: [COMPLETAR]

Firma de Procurador/a: [COMPLETAR]

D./Dña. [NOMBRE Y APELLIDOS] 	D./Dña. [NOMBRE Y APELLIDOS]

================================================================================

---

#### Notas al pie

(1) Este recurso se presenta: * Ante: la Sección de lo Penal del Tribunal de Instancia (antes, Juzgado de lo Penal) o la AP que dictó la resolución impugnada. * En el plazo de 10 días a partir del siguiente al de la notificación de la resolución impugnada

[NOTA DE REVISIÓN: Los Juzgados de lo Penal pasaron a ser Secciones de lo Penal el 31-12-2025 (DT 1ª LO 1/2025), así que la referencia a «una vez constituido» ha quedado desfasada.]

[NOTA DE REVISIÓN: El art. 785.3 LECrim remite al plazo y forma de los arts. 790 y siguientes (10 días). Si el auto es de la Sección de lo Penal, resuelve la AP. Si es de la AP y acuerda el sobreseimiento libre o declara la falta de jurisdicción, resuelve la Sala de lo Civil y Penal del TSJ (art. 846 ter LECrim).]
