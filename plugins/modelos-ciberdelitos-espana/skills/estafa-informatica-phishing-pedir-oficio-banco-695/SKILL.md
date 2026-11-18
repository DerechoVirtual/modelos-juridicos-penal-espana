---
name: estafa-informatica-phishing-pedir-oficio-banco-695
description: "Redacta el escrito «Estafa informática (phishing): pedir oficio al banco para identificar al autor» (formulario 695 de ciberdelitos y propiedad intelectual, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Estafa informática (phishing): pedir oficio al banco para identificar al autor

> Formulario 0695 del plugin **Ciberdelitos y propiedad intelectual** · revisado el 17-11-2026.

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
- [ ] COLEGIO
- [ ] Nº DE COLEGIADO/A
- [ ] LOCALIDAD
- [ ] NÚMERO
- [ ] FECHA
- [ ] IMPORTE
- [ ] LUGAR
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…rriente que tiene en la entidad bancaria»; «…para»

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 249.1 a) CP

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

### Formulario 0695 · Estafa informática (phishing): pedir oficio al banco para identificar al autor

- Año del modelo: 2017
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (1); 11 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito por el que el denunciante solicita a una entidad bancaria que identifique al titular de una cuenta destino de una transferencia bancaria hecha a través de una presunta estafa informática (phising) del art. 249.1 a) CP.

Actualizado conforme a la LO 14/2022, con entrada en vigor el 12 de enero de 2023.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a del Ilustre Colegio de procuradores de [COLEGIO], con nº de colegiado/a [Nº DE COLEGIADO/A] y con despacho profesional abierto en [LOCALIDAD], en representación de D./Dña. [NOMBRE Y APELLIDOS], denunciante en las DP nº [NÚMERO] comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

Que, dado que se están llevando a cabo diligencias de investigación para la averiguar la persona que accedió al ordenador de mi representado/a y, por ello, a sus claves de acceso a la cuenta corriente que tiene en la entidad bancaria [COMPLETAR] para [COMPLETAR], con fecha [FECHA], extraer de su cuenta corriente la suma de [IMPORTE] euros por transferencia bancaria a la cuenta corriente de la que es titular el autor (1), intereso se dirija oficio a la citada entidad bancaria, a fin de que identifique la titularidad de la cuenta corriente

Por lo expuesto,

SUPLICO A LA SECCIÓN:

Que tenga por presentado este escrito, lo admita y tenga por realizado el trámite interesado para la identificación de la persona que puede haber realizado el acceso a la cuenta de mi representado a fin de que se le reciba declaración sobre los hechos de la denuncia.

Es Justicia que pido en [LUGAR].

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) La estafa informática, regulada hasta el 11 de enero de 2023 en el art. 248.2 a) y desde el 12 de enero de 2023, fecha de entrada en vigor de la LO 14/2022, en el art. 249.1 a) CP, consiste en la producción de un daño patrimonial cuantificable mediante un comportamiento externo, impropio de un proceso automatizado informático, que altera los datos gestionados por éste, con ánimo lucro y en perjuicio de tercero.

Los elementos típicos que integran el delito de estafa informática son:

-La manipulación informática y artificio semejante,
-transferencia patrimonial no consentida por el titular del mismo,
-ánimo de lucro, y
-perjuicio en tercero.

Modalidades típicas de estafas informáticas son el "phishing" y el "pharming" que son dos tipos de fraudes informáticos cuya finalidad común es la de apoderarse de información personal de un usuario de Internet, para acceder a sus cuentas de correo o de redes sociales y obtener adicionalmente datos de sus contactos virtuales, a fin de comerciarlos ilícitamente, o bien, conseguir claves en su banco (por medio de internet) para de este modo ingresar a las cuentas corrientes bancarias de los titulares y disponer de su dinero en las cuentas realizando una operación de transferencia de activos a un tercero que se denomina "mule".

Para averiguar la autoría se hace precisa la intervención de la Brigada de Investigación Tecnológica, que es la Unidad policial destinada a responder a los retos que plantean las nuevas formas de delincuencia: pornografía infantil, estafas y fraudes por Internet, fraudes en el uso de las comunicaciones, ataques cibernéticos, piratería...

La Brigada de Investigación Tecnológica está encuadrada en la Unidad de Delincuencia Económica y Fiscal (UDEF) que es el órgano de la Dirección General de la Policía y de la Guardia Civil encargado de la investigación y persecución de las actividades delictivas, de ámbito nacional e internacional, en materia de delincuencia económica y fiscal, así como la coordinación operativa y apoyo técnico a las respectivas Unidades Territoriales.

Su misión consiste en obtener las pruebas, perseguir a los delincuentes y poner a unas y otros a disposición judicial. Sus herramientas son la formación continua de los investigadores, la colaboración de las más punteras instituciones públicas y privadas, la participación activa en los foros internacionales de cooperación policial y la colaboración ciudadana.

En estos casos de estafas informáticas los agentes de la policía judicial podrán haber detectado el número de IP del ordenador desde el que se ha cometido la estafa informática y, tras ello, por la vía del art. 588 ter k LECRIM (introducido por la LO 13/2015, de 5 de octubre) se habrá interesado la orden judicial para la averiguación de la identidad del autor.

================================================================================
