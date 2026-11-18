---
name: petaqueo-combustible-liquido-narcolancha-escrito-defensa-11
description: "Redacta el escrito «Petaqueo (combustible líquido a narcolancha): escrito de defensa» (formulario 11 de salud pública y maltrato animal, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Petaqueo (combustible líquido a narcolancha): escrito de defensa

> Formulario 0011 del plugin **Salud pública y maltrato animal** · revisado el 17-11-2026.

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
- [ ] COLEGIO
- [ ] Nº DE COLEGIADO/A
- [ ] LOCALIDAD
- [ ] Nº DE PROCEDIMIENTO
- [ ] AÑO
- [ ] FECHA
- [ ] LUGAR
- [ ] Otros 7 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «… circulaba con su lancha por la bahía de»; «…ocedió a registrar su lancha encontrando»; «…, que llevaba a un barco que se dedica a»; «…, que estaba amarrado en el puerto de»; «…, a»; «…:»; «….- Documental siguiente:»

## Elecciones que hay que hacer

- judicialmente / mediante exhorto

## Párrafos opcionales (2)

Inclúyelos solo si encajan en los hechos:

- 1.- Declaración de los/as siguientes testigos, que deberán ser citados/as [ELEGIR: judicialmente / mediante ex…
- .- Documental siguiente: [COMPLETAR].…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 568.2 CP
- artículo 800.2 LECRIM

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

### Formulario 0011 · Petaqueo (combustible líquido a narcolancha): escrito de defensa

- Año del modelo: 2026
- Revisión 17-11-2026: 1 desplegables y casillas convertidos en elección en blanco; 2 párrafos opcionales señalados; 19 campos de relleno marcados en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Al Juez en servicio de Guardia

D./Dña. [NOMBRE Y APELLIDOS], Letrado/a del Ilustre Colegio de Abogados de [COLEGIO], con nº de colegiado/a [Nº DE COLEGIADO/A] y con despacho profesional abierto en [LOCALIDAD], en representación del/de la acusado/a D./Dña. [NOMBRE Y APELLIDOS], en el juicio rápido número [Nº DE PROCEDIMIENTO] del año [AÑO] por el supuesto delito del art. 568.2 CP, comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

Que, conforme a lo preceptuado en el artículo 800.2 LECRIM, manifiesto mi disconformidad con el escrito de acusación y formulo escrito de defensa con base en las siguientes:

CONCLUSIONES

PRIMERA

Disconforme con la correlativa del Ministerio Fiscal. Los hechos que realmente sucedieron fueron los siguientes: mi representado circulaba con su lancha por la bahía de [COMPLETAR], el día [FECHA], cuando fue abordado por una patrulla marítima, que procedió a registrar su lancha encontrando [COMPLETAR] bidones de gasolina, que llevaba a un barco que se dedica a [COMPLETAR], que estaba amarrado en el puerto de [COMPLETAR], ya que se había quedado sin respostaje, no siendo el destino de la gasolina proveer de la misma a narcoclanchas.

SEGUNDA

Niego la correlativa porque los hechos en los que intervino mi representado/a no son constitutivos de delito.

TERCERA

Niego la correlativa. Sin delito no puede hablarse de responsabilidad criminal de ninguna clase.

CUARTA

Disconforme con las correlativas. Sin delito y sin responsable no pueden existir circunstancias modificativas de la responsabilidad.

QUINTA

Disconforme con la correlativa. Procede absolver a mi representado/a con todos los pronunciamientos favorables.

SEXTA

Disconforme con la correlativa. No puede existir responsabilidad civil cuando no existe delito. Y por lo mismo procede declarar las costas de oficio.

Por lo expuesto,

SUPLICO A LA SECCIÓN

Que tenga por presentado este escrito con sus copias, los admita y por realizada la calificación.

Por ser de Justicia que pido [LUGAR], a [COMPLETAR].

OTROSÍ DIGO: Que para el acto del juicio oral propongo los siguientes:

MEDIOS DE PRUEBA

Todos los propuestos por el Ministerio Fiscal y, además, los siguientes:

[OPCIONAL — incluir si procede]

1.- Declaración de los/as siguientes testigos, que deberán ser citados/as [ELEGIR: judicialmente / mediante exhorto]: [COMPLETAR].

-D/Dña [NOMBRE Y APELLIDOS] titular del barco que iba a recibir la gasolina,

-D/Dña [NOMBRE Y APELLIDOS] empleado del barco que iba a recibir la gasolina y que contactó con mi representado/a para solicitarle la gasolina.

[OPCIONAL — incluir si procede]

.- Documental siguiente: [COMPLETAR].

Por lo expuesto,

SUPLICO A LA SECCIÓN: declare pertinentes las pruebas interesadas y acuerde su práctica.

Es Justicia que reitero en el lugar y fecha "ut supra" indicados.

Firma de Abogado/a y número de colegiado:

D./Dña. [NOMBRE Y APELLIDOS]

================================================================================
