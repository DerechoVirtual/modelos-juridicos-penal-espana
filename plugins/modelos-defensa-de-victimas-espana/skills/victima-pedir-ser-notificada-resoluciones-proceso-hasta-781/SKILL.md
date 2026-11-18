---
name: victima-pedir-ser-notificada-resoluciones-proceso-hasta-781
description: "Redacta el escrito «Víctima: pedir ser notificada de las resoluciones del proceso (hasta el 6 de octubre de 2022)» (formulario 781 de víctimas y justicia restaurativa, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Víctima: pedir ser notificada de las resoluciones del proceso (hasta el 6 de octubre de 2022)

> Formulario 0781 del plugin **Víctimas y justicia restaurativa** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] AÑO
- [ ] LUGAR
- [ ] FECHA
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «… el que llevar a cabo las comunicaciones»; «…, a [FECHA]. Firma del solicitante:»

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 5.1. m) Ley 4/2015
- artículo 7 Ley 4/2015
- artículo 13 de la Ley 4/2015

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

### Formulario 0781 · Víctima: pedir ser notificada de las resoluciones del proceso (hasta el 6 de octubre de 2022)

- Año del modelo: 2016
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; restos de formato retirados; notas del formulario agrupadas al final (4); 4 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 1 huecos del original que se habían perdido sin marca, marcados (Nº DE PROCEDIMIENTO)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la víctima en un proceso penal solicita que le sean notificadas las resoluciones enumeradas en el artículo 7 de la L 4/2015, del Estatuto [NOTA DE REVISIÓN: El Estatuto de la víctima del delito es la Ley 4/2015, de 27 de abril. Fuente: Ley 4/2015, BOE-A-2015-4606, art. 7.] de la Víctima del Delito.

A LA SECCIÓN DE INSTRUCCIÓN DEL TRIBUNAL DE INSTANCIA DE [SEDE] – PLAZA N.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] víctima en las Diligencias previas nº [Nº DE PROCEDIMIENTO]/[AÑO] incoadas en este juzgado, por medio de la presente, y conforme a lo dispuesto en el artículo 5.1. m) Ley 4/2015, de 27 de abril, del Estatuto de la víctima del delito, DIGO:

Que, a tenor de lo dispuesto en el artículo 7 Ley 4/2015, de 27 de abril, se interesa que, a partir de la presente solicitud, me sean notificadas, entre otras las siguientes resoluciones (1):

a.- Fecha, hora y lugar del juicio.
b.- Contenido de la acusación dirigida contra el infractor.
c.- La resolución por la que se acuerde no iniciar el procedimiento penal.
d.- La sentencia que ponga fin al procedimiento.
e.- Las resoluciones que acuerden la prisión o la posterior puesta en libertad del infractor, así como la posible fuga del mismo.
f.- Las resoluciones que acuerden la adopción de medidas cautelares personales o que modifiquen las ya acordadas, cuando hubieran tenido por objeto garantizar la seguridad de la víctima. (2)
g.- Las resoluciones o decisiones de cualquier autoridad judicial o penitenciaria que afecten a sujetos condenados por delitos cometidos con violencia o intimidación y que supongan un riesgo para la seguridad de la víctima. En estos casos y a estos efectos, la Administración penitenciaria comunicará inmediatamente a la autoridad judicial la resolución adoptada para su notificación a la víctima afectada.
h.- Las resoluciones a que se refiere el artículo 13 de la Ley 4/2015, de 27 de abril.
i.- Información relativa a la situación en que se encuentra el procedimiento, salvo que ello pudiera perjudicar el correcto desarrollo de la causa. (3)

Para ello se facilita mi dirección de correo electrónico en el que llevar a cabo las comunicaciones [COMPLETAR] (4)

En [LUGAR], a [FECHA].

Firma del solicitante: [COMPLETAR]

D./Dña. [NOMBRE Y APELLIDOS]

NOTAS DEL FORMULARIO

(1) A partir de la reforma que la LO 10/2022, de garantía integra de la libertad sexual hace en el art. 5 de la L 4/2015, de 27 de abril, vigente desde el 7 de octubre de 2022, toda víctima tiene derecho a ser notificada de forma inmediata de las resoluciones del proceso penal, sin ser necesario ya que presente solicitud para ello.

(2) Cuando se trate de víctimas de delitos de violencia de género, las resoluciones de las letras e) y f) le serán notificadas sin que esta lo solicite. Deberá manifestar su deseo de no recibir dichas notificaciones presentando escrito en sentido negativo.

(3) Artículo 7.4 Ley 4/2015, de 27 de abril.

(4) Si la víctima no dispusiera de una dirección de correo electrónico, se remitirán por correo ordinario a la dirección que hubiera facilitado. En el caso de ciudadanos residentes fuera de la Unión Europea, si no se dispusiera de una dirección de correo electrónico o postal en la que realizar la comunicación, se remitirá a la oficina diplomática o consular española en el país de residencia para que la publique.

Si la víctima se hubiera personado formalmente en el procedimiento, las resoluciones serán notificadas a su procurador y serán comunicadas a la víctima en la dirección de correo electrónico que haya facilitado.

Con ello, en el caso de personación de la víctima, existe obligación de una doble notificación no perdiendo la víctima su derecho a ser notificada aunque esté personada con procurador.

Las víctimas podrán manifestar en cualquier momento su deseo de no ser informadas de las resoluciones citadas, quedando sin efecto la solicitud realizada.

================================================================================
