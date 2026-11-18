---
name: sexting-pedir-registro-equipos-informaticos-determinar-720
description: "Redacta el escrito «Sexting: pedir el registro de equipos informáticos para determinar la autoría» (formulario 720 de investigación tecnológica y prueba digital, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Sexting: pedir el registro de equipos informáticos para determinar la autoría

> Formulario 0720 del plugin **Investigación tecnológica y prueba digital** · revisado el 17-11-2026.

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
- [ ] LOCALIDAD (2 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] LUGAR
- [ ] DÍA
- [ ] MES
- [ ] AÑO

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 197.7 del CP
- art. 197.7 CP

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

### Formulario 0720 · Sexting: pedir el registro de equipos informáticos para determinar la autoría

- Año del modelo: 2017
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (2); 10 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Escrito solicitando el registro del domicilio de una persona y de todos los equipos informáticos, para poder determinar si ha sido el autor de un delito de sexting del art. 197.7 del CP por enviar, sin consentimiento de la víctima, imágenes para cuya grabación sí hubo consentimiento.

Documento adaptado a la reforma de la organización judicial introducida por la LO 1/2025, mediante la creación y constitución de los Tribunales de Instancia.

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los tribunales del Ilustre Colegio de procuradores de [COLEGIO], con nº de colegiado [Nº DE COLEGIADO/A] y con despacho profesional abierto en [LOCALIDAD], en representación de la acusación particular D./Dña. [NOMBRE Y APELLIDOS] en las presentes diligencias previas nº [Nº DE PROCEDIMIENTO] por delito del art. 197.7 CP, comparezco ante el órgano judicial (1) y como mejor proceda en derecho, DIGO:

En aplicación del art. 588 sexies a) LECRIM mediante el presente escrito formulo solicitud de Registro domiciliario y de registro de dispositivos de almacenamiento masivo de información, con base en las siguientes:

CONCLUSIONES

ÚNICA.-

El/La querellado/a por delito de sexting del art. 197.7 CP ha negado que fuera quien subió a internet la grabación en la que aparecen las partes menoscabando gravemente la intimidad del querellante.

Por ello, y a fin de que se lleve a cabo prueba pericial informática, se interesa se acuerde por el órgano judicial la entrada y registro en el domicilio del/de la querellado/a sito en [LOCALIDAD], en base a los arts. 558 y ss de la LECRIM. Al mismo tiempo, se solicita el registro e incautación de ordenadores y otros dispositivos desde los que se hubiese podido realizar tal operación de subir a internet el contenido de la grabación aportada a la querella mediante acta notarial (2).

A tal efecto, señala el art. 588 sexies a) LECRIM que:

"Cuando con ocasión de la práctica de un registro domiciliario sea previsible la aprehensión de ordenadores, instrumentos de comunicación telefónica o telemática o dispositivos de almacenamiento masivo de información digital o el acceso a repositorios telemáticos de datos, la resolución del juez de instrucción habrá de extender su razonamiento a la justificación, en su caso, de las razones que legitiman el acceso de los agentes facultados a la información contenida en tales dispositivos.

2. La simple incautación de cualquiera de los dispositivos a los que se refiere el apartado anterior, practicada durante el transcurso de la diligencia de registro domiciliario, no legitima el acceso a su contenido, sin perjuicio de que dicho acceso pueda ser autorizado ulteriormente por el juez competente."

Por todo lo expuesto,

SUPLICO A LA SECCIÓN:

Que se acuerde la práctica de ambas diligencias por ser de interés y tener relación con la causa para la averiguación de los hechos contenidos en la querella.

Es Justicia que pido en [LUGAR], a [DÍA] de [MES] de [AÑO].

Firma de Abogado/a:	Firma de Procurador/a:

NOTAS DEL FORMULARIO

(1) Este escrito debe presentarse en la Sección de Instrucción del Tribunal de Instancia que tramita las diligencias de la difusión de una grabación íntima con la persona que presuntamente lo haya difundido de forma paralela a la denuncia formulada para la incoación de las diligencias previas.

(2) En estos casos la medida limitativa de derechos fundamentales del registro de equipos informáticos puede ser determinante para acreditar la autoría de la difusión de las imágenes que menoscaban gravemente la intimidad de la víctima.

Es preciso que el juez lo autorice expresamente en su auto conforme dispone el art. 588 sexies a) 1 LECRIM.

================================================================================
