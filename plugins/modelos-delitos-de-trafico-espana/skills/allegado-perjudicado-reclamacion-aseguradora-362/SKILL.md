---
name: allegado-perjudicado-reclamacion-aseguradora-362
description: "Redacta el escrito «Allegado del perjudicado: reclamación a la aseguradora» (formulario 362 de seguridad vial, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Allegado del perjudicado: reclamación a la aseguradora

> Formulario 0362 del plugin **Seguridad vial** · revisado el 17-11-2026.

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

- [ ] NOMBRE Y APELLIDOS (5 veces)
- [ ] LUGAR
- [ ] DÍA
- [ ] MES
- [ ] AÑO
- [ ] FECHA
- [ ] Nº (2 veces)
- [ ] MARCA/MODELO (2 veces)
- [ ] MATRÍCULA (2 veces)
- [ ] DESCRIBIR
- [ ] IMPORTE (5 veces)
- [ ] Otros 15 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…A la atención de:»; «…Compañía de Seguros:»; «…de [MES] de [AÑO]. Póliza de seguro:»; «… Póliza de seguro: [COMPLETAR] Vehículo:»; «…Vehículo: [COMPLETAR] Tomador:»; «…Tomador: [COMPLETAR] Muy Sres. Míos:»; «…El día [FECHA] a las [Nº] horas»; «…a las [Nº] horas [COMPLETAR] en»; «…, matrícula [MATRÍCULA] de titularidad»; «…de titularidad [COMPLETAR], asegurado en»; «…a del automóvil cubierta por la Compañía»; «…con nº [Nº] de póliza»; …

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículos 62.1 y 67 del Real Decreto Legislativo 8/2004
- Ley 50/1980

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

### Formulario 0362 · Allegado del perjudicado: reclamación a la aseguradora

- Año del modelo: 2021
- Revisión 17-11-2026: 22 campos de relleno marcados en blanco; 8 etiquetas sin dato marcadas en blanco; 4 huecos del original que se habían perdido sin marca, marcados (IMPORTE)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

D./Dña. [NOMBRE Y APELLIDOS]

A la atención de: [COMPLETAR]

Compañía de Seguros: [COMPLETAR]

En [LUGAR], a [DÍA] de [MES] de [AÑO].

Póliza de seguro: [COMPLETAR]

Vehículo: [COMPLETAR]

Tomador: [COMPLETAR]

Muy Sres. Míos: [COMPLETAR]

El día [FECHA] a las [Nº] horas [COMPLETAR] en [COMPLETAR], mi allegado/allegada D./Dña. [NOMBRE Y APELLIDOS] cuando conducía el vehículo modelo [MARCA/MODELO], matrícula [MATRÍCULA] de titularidad [COMPLETAR], asegurado en [COMPLETAR], sufrió un accidente de tráfico consistente en [DESCRIBIR] al colisionar con el vehículo modelo [MARCA/MODELO], matrícula [MATRÍCULA] conducido por D./Dña. [NOMBRE Y APELLIDOS], con cobertura de responsabilidad civil obligatoria del automóvil cubierta por la Compañía [COMPLETAR] con nº [Nº] de póliza [COMPLETAR].

El accidente fue causado por D./Dña. [NOMBRE Y APELLIDOS] según [COMPLETAR].

Como consecuencia del mismo allegado/allegada D./Dña. [NOMBRE Y APELLIDOS] falleció. Se adjunta certificado de defunción. Por ello, y en aplicación de los artículos 62.1 y 67 del Real Decreto Legislativo 8/2004, de 29 de octubre, por el que se aprueba el texto refundido de la Ley sobre responsabilidad civil y seguro en la circulación de vehículos a motor, tengo la condición de perjudicado. Para acreditar mi condición y la convivencia familiar con la víctima durante un mínimo de cinco años inmediatamente anteriores al fallecimiento, así como la cercanía a ella en parentesco o afectividad, presento

Por consecuencia del anterior siniestro, se me causaron los siguientes perjuicios:

- PERJUICIO PERSONAL BÁSICO: [IMPORTE] euros.

Aplicación de la Tabla 1 A, categoría 5:

A cada allegado

- PERJUICIO PERSONAL PARTICULAR: [IMPORTE] euros.

Aplicación de la Tabla 1 B: [COMPLETAR]

Perjuicios particulares	Explicación	Incrementos sobre perjuicio personal básico
Discapacidad física o psíquica del perjudicado previa o a resultas del accidente.

Tiene por objeto compensar la alteración perceptible que el fallecimiento de la víctima provoca en la vida del perjudicado.

Para que este perjuicio sea resarcible se requiere como mínimo un grado de discapacidad del 33%.

	Del 25% al 75%

- PERJUICIO PATRIMONIAL: DAÑO EMERGENTE (Tabla 1 C): [IMPORTE] euros.

Aplicación de la Tabla 1 C: [COMPLETAR]

DAÑO EMERGENTE
1. Perjuicio patrimonial básico (*)
Sin necesidad de justificación (cantidad por cada perjudicado)	494,19 €
Gastos con necesidad de justificación que excedan del importe anterior	Su importe
2. Gastos Específicos
Gastos de traslado del fallecido, entierro, funeral y repatriación	Su importe

(*) Si el importe de dichos gastos excede del establecido en el apartado anterior, su resarcimiento requiere justificación

- PERJUICIO PATRIMONIAL: LUCRO CESANTE (Tabla 1 C 4): [IMPORTE] euros.

Aplicación de la Tabla 1.C.7 y 1.C.7.D para allegados con discapacidad: sólo tienen la condición de personas perjudicadas las incluidas en el artículo 62 que acrediten que dependían económicamente de la víctima. Tabla 1.C.4 y 1.C.4.D: criterios:

1. Ingreso neto: tramos desde 9.000 euros hasta 120.000 euros.
2. Edad del allegado: hasta 16 y hasta 65 años o más.

Por todo lo anterior, el importe total de la cuantía indemnizatoria que reclamo es de [IMPORTE] euros.

Pongo estos hechos en su conocimiento a los efectos previstos en el artículo 7.1 de la Ley de responsabilidad civil y seguro en la circulación de vehículos a motor. Y se comunica que, según el art. 20. 6.º de la Ley 50/1980, de 8 de octubre, Ley del Contrato de Seguro, el deber de comunicar el siniestro por parte del asegurado es el que figura en la póliza, o en su defecto el de 7 días a partir de haberlo conocido, lo que deberá tenerse en cuenta a los efectos del interés por mora del asegurador.

Se adjunta la siguiente documentación:

A la espera de sus noticias, reciba un saludo:

================================================================================
