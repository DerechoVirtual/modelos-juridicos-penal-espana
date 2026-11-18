---
name: sexting-victima-pide-retirada-provisional-contenidos-722
description: "Redacta el escrito «Sexting: la víctima pide la retirada provisional de contenidos de internet como medida cautelar» (formulario 722 de honor, intimidad y delitos de odio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Sexting: la víctima pide la retirada provisional de contenidos de internet como medida cautelar

> Formulario 0722 del plugin **Honor, intimidad y delitos de odio** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] COLEGIO
- [ ] Nº DE PROCEDIMIENTO
- [ ] DELITO
- [ ] LUGAR
- [ ] DÍA
- [ ] MES
- [ ] AÑO

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 197.7 CP
- art. 13 de la LECRIM
- art. 13 LECRIM
- art. 109.4 LECRIM
- artículo 57 del Código Penal

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

### Formulario 0722 · Sexting: la víctima pide la retirada provisional de contenidos de internet como medida cautelar

- Año del modelo: 2017
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (3); 8 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que la víctima de un delito de sexting del art. 197.7 CP solicita que el juez acuerde paralizar la difusión de las imágenes objeto del delito, con base en el art. 13 de la LECRIM.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº] (1)

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los Tribunales del Ilustre Colegio de Procuradores de [COLEGIO] ejercitando la acusación particular en nombre y representación de D./Dña. [NOMBRE Y APELLIDOS] (2) en las diligencias previas nº [Nº DE PROCEDIMIENTO] que se siguen por delito de [DELITO] contra D./Dña. [NOMBRE Y APELLIDOS] ante este órgano judicial comparezco y, como más procedente sea en derecho, DIGO:

Que se interesa se proceda a adoptar una medida cautelar consistente en la prohibición de la difusión del contenido de la grabación que es objeto de la querella en su día presentada, a fin de evitar el daño que se está causando en la actualidad a mi representado/a por la difusión en internet del contenido de la grabación íntima de la misma con el/la querellado/a sin autorización para difundirla, en base a las siguientes:

CONCLUSIONES

PRIMERA.- El art. 13 LECRIM, según redacción dada por LO 10/2022, de garantía integral de la libertad sexual prevé que:

"En la instrucción de delitos cometidos a través de internet, del teléfono o de cualquier otra tecnología de la información o de la comunicación, el juzgado podrá acordar, como primeras diligencias, de oficio o a instancia de parte, las medidas cautelares consistentes en la retirada provisional de contenidos ilícitos, en la interrupción provisional de los servicios que ofrezcan dichos contenidos o en el bloqueo provisional de unos y otros cuando radiquen en el extranjero."

SEGUNDA.- En este caso el objeto de las diligencias es un delito de sexting del art. 197.7 CP, (3) incluido en el Título X de los delitos contra la intimidad y el derecho a la propia imagen, por cuanto se considera procedente y proporcionado a la gravedad de lo ocurrido que se adopte la medida de retirada provisional de la grabación en internet, que se enraiza en esencia en el propio delito cometido, ya que el/la denunciante no desea que se difunda esa grabación por redes sociales.

Por todo ello,

SUPLICO A LA SECCIÓN:

Se acepte la petición y se acuerde la medida interesada y se comunique la resolución a las Fuerzas y Cuerpos de Seguridad del Estado a fin de que se dé traslado a los servidores de internet para que borren de inmediato la grabación subida a internet, cuya copia se adjunta por referencia al acta notarial de la Notaría de D./Dña. [NOMBRE Y APELLIDOS] donde consta el contenido de la grabación en los diversos buscadores de internet citados en el acta notarial adjunta interesando se dirijan a estos para suprimir su difusión.

En [LUGAR], a [DÍA] de [MES] de [AÑO].

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en la Sección de instrucción del Tribunal de Instancia que tramita las diligencias de la difusión de una grabación íntima con la persona que presuntamente lo haya difundido de forma paralela a la denuncia formulada para la incoación de las diligencias previas.

(2) No es obligatorio que la víctima se persone en el proceso penal para presentar este escrito. Puede hacerlo por sí misma y, en base al art. 109.4 LECRIM, este órgano judicial debería ofrecerle esta opción en la citación a juicio a fin de que pueda presentar, o no, este escrito.

(3) Nótese que el delito de sexting está incluido entre los que el art 57 CP recoge para proteger a la víctima y garantizar que el acusado no se le acerque y/ o no se pueda relacionar con ella mediante la imposición en sentencia de penas de prohibición de comunicación y aproximación. Pero, además, el art. 109.4 LECRIM dice que en los procesos que se sigan por delitos comprendidos en el artículo 57 del Código Penal, (sexting entre ellos) el Letrado de la Administración de Justicia asegurará la comunicación a la víctima de los actos procesales que puedan afectar a su seguridad.

================================================================================
