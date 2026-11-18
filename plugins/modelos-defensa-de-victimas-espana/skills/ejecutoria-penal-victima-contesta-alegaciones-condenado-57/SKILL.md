---
name: ejecutoria-penal-victima-contesta-alegaciones-condenado-57
description: "Redacta el escrito «Ejecutoria penal: la víctima contesta a las alegaciones del condenado» (formulario 57 de víctimas y justicia restaurativa, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Ejecutoria penal: la víctima contesta a las alegaciones del condenado

> Formulario 0057 del plugin **Víctimas y justicia restaurativa** · revisado el 17-11-2026.

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

## Antes de usarlo: avisos de la revisión

El planteamiento del formulario está desfasado en algo. Corrígelo antes de redactar:

- La regla 1.ª del art. 80.2 CP cambió con la LO 1/2026 (desde el 10-4-2026): computan las condenas anteriores por delitos leves que integren un tipo agravado por multirreincidencia; deben revisarse los antecedentes del penado antes de pedir u oponerse a la suspensión.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión. Empieza con una nota explicativa (para qué sirve el escrito y cuándo se usa), revisada en el BOE: léela antes de redactar, pero no la copies en el escrito.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] Nº (2 veces)
- [ ] LOCALIDAD
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] NÚMERO
- [ ] FECHA (4 veces)
- [ ] IMPORTE (3 veces)
- [ ] DESCRIBIR
- [ ] LUGAR
- [ ] Otros 6 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…ación que tiene acreditada de la víctima»; «… a la pena de y responsabilidad civil de»; «… civiles. Señala el art. 80.2.3º CP que:»; «…fauna tipificado y penado en el artículo»; «… bienes, todos ellos de lícito comercio:»; «…se practiquen las siguientes diligencias»

## Elecciones que hay que hacer

- haber sido confirmada / no interponerse recurso contra la misma
- SECCIÓN / SALA

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (8)

Inclúyelos solo si encajan en los hechos:

- PRIMERA.- Con respecto a la petición de suspensión de ejecución de pena impuesta de dos años de prisión nos op…
- SEGUNDA.- No aceptamos el aplazamiento del pago de la responsabilidad civil para que resulte procedente la sus…
- TERCERA.- No aceptamos la suspensión de la ejecución de la pena con las condiciones o sustitución de los arts.…
- CUARTA.- Al ser la sentencia arriba referenciada condenatoria por un delito relativo a la protección de la flo…
- QUINTA.- Al ser la sentencia arriba referenciada condenatoria por un delito relativo a [DESCRIBIR], del art. d…
- SEXTA.- En la sentencia arriba referenciada se imponía al/a la condenado/a el comiso de los siguientes bienes,…
- SÉPTIMA.- Que habiendo resultado infructuoso el requerimiento de afianzamiento de las responsabilidades pecuni…
- OCTAVA.- Esta representación interesa que se acuerde el comiso del vehículo utilizado en los hechos, al amparo…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 988 bis.2 de la Ley de Enjuiciamiento Criminal
- arts. 83 y 84 CP
- artículo 339 del Código Penal
- artículo 385 bis del Código Penal

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

### Formulario 0057 · Ejecutoria penal: la víctima contesta a las alegaciones del condenado

- Año del modelo: 2025
- Revisión 17-11-2026: 1 desplegables y casillas convertidos en elección en blanco; 1 desplegables convertidos en elección en blanco; 1 bloques de alternativas señalados; 8 párrafos opcionales señalados; 15 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 3 huecos del original que se habían perdido sin marca, marcados (FECHA, IMPORTE)
- Avisos de la revisión: La regla 1.ª del art. 80.2 CP cambió con la LO 1/2026 (desde el 10-4-2026): computan las condenas anteriores por delitos leves que integren un tipo agravado por multirreincidencia; deben revisarse los antecedentes del penado antes de pedir u oponerse a la suspensión.
- Nota explicativa incorporada desde la colección Procesal (formulario 52) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Escrito de la víctima contestando a las alegaciones del condenado en ejecutoria penal sobre la suspensión de la pena privativa de libertad impuesta, la forma de cumplimiento de la responsabilidad civil y cualquier otra relativa a la ejecución de los pronunciamientos de la sentencia, incluida la sustitución de la pena, en su caso, conforme al art. 988 bis 2 LECRIM, introducido por LO 1/2025, de Eficiencia de la Justicia, vigente desde el 3 de abril de 2025. Recuerde que....

---

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

A la Sección de lo Penal del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

A la Audiencia Provincial de [LOCALIDAD]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales en la representación que tiene acreditada de la víctima [COMPLETAR] en EJECUTORIA PENAL nº [NÚMERO], tras sentencia nº [Nº] de condena por delito de a la pena de y responsabilidad civil de [COMPLETAR], siendo firme por [ELEGIR: haber sido confirmada / no interponerse recurso contra la misma], comparezco ante este órgano judicial y, como mejor proceda en derecho, DIGO:

Que, conforme a lo preceptuado en el artículo 988 bis.2 de la Ley de Enjuiciamiento Criminal (según redacción dada por LO 1/2025) y tras el traslado dado de las alegaciones de la defensa del condenado en la ejecutoria penal en fecha [FECHA] por este órgano judicial, manifestamos en plazo nuestra oposición a las mismas, con base en las siguientes:

ALEGACIONES

[OPCIONAL — incluir si procede]

PRIMERA.- Con respecto a la petición de suspensión de ejecución de pena impuesta de dos años de prisión nos oponemos a la misma, dado que no se ha satisfecho la totalidad de las responsabilidades civiles.

Señala el art. 80.2.3º CP que: [COMPLETAR]

"2. Serán condiciones necesarias para dejar en suspenso la ejecución de la pena, las siguientes:

...3.ª Que se hayan satisfecho las responsabilidades civiles que se hubieren originado."

No se han satisfecho las indemnizaciones fijadas en sentencia, por lo que no procede la suspensión de la ejecución de la pena.

[OPCIONAL — incluir si procede]

SEGUNDA.- No aceptamos el aplazamiento del pago de la responsabilidad civil para que resulte procedente la suspensión de la ejecución de la pena. La sentencia de fecha [FECHA] fija como responsabilidad civil la suma de [IMPORTE] euros. El condenado tan solo ha satisfecho la cantidad de [IMPORTE] euros. Los hechos ocurrieron en fecha [FECHA].A fecha de hoy el condenado ha tenido tiempo suficiente para cumplir la responsabilidad civil que ya se reclamó en el escrito de acusación. No se ha hecho esfuerzo alguno para el pago, por lo que supone una burla al sistema judicial y a la víctima plantear ahora un aplazamiento de pago de la suma que ya se conocía y se reclamaba de hace tiempo, habiendo producido a la víctima un daño relevante que tampoco sería resarcido ni con el pago.

[OPCIONAL — incluir si procede]

TERCERA.- No aceptamos la suspensión de la ejecución de la pena con las condiciones o sustitución de los arts. 83 y 84 CP.

La gravedad del hecho delictivo y la victimización producida por el condenado en la persona de la víctima, hacen inviable cualquier tipo de aceptación por su parte, a la que ni tan siquiera se le ha planteado una mediación penal para pedir perdón o mostrar el arrepentimiento por los hechos declarados probados.

Por lo expuesto,

[OPCIONAL — incluir si procede]

CUARTA.- Al ser la sentencia arriba referenciada condenatoria por un delito relativo a la protección de la flora, fauna tipificado y penado en el artículo [COMPLETAR] del Código Penal, al amparo de lo dispuesto en el artículo 339 del Código Penal, esta representación interesa que se imponga al/a la condenado/a la adopción de las siguientes medidas necesarias, encaminadas a restaurar el equilibrio ecológico perturbado:

a)

b)

c)

[OPCIONAL — incluir si procede]

QUINTA.- Al ser la sentencia arriba referenciada condenatoria por un delito relativo a [DESCRIBIR], del art. del Código Penal, esta representación, al amparo de lo dispuesto en el artículo 288.I del Código Penal, interesa que se acuerde la publicación de la sentencia en los siguientes periódicos oficiales:

Asimismo, y puesto que la conducta del/de la condenado/a ha causado un grave perjuicio a mi mandante, se interesa la reproducción total/parcial de la sentencia en los siguientes medios informativos, siempre a costa del/de la condenado/a:

[OPCIONAL — incluir si procede]

SEXTA.- En la sentencia arriba referenciada se imponía al/a la condenado/a el comiso de los siguientes bienes, todos ellos de lícito comercio: [COMPLETAR].

Asimismo, la mencionada sentencia imponía al/a la condenado/a la obligación de abonar a mi representado/a, en concepto de responsabilidad civil, la cantidad de [IMPORTE] euros.

Por ello, esta representación, de acuerdo con lo dispuesto en el artículo 127 octies 3 del Código Penal, interesa que se proceda a vender los bienes decomisados y que su producto se aplique a cubrir las responsabilidades civiles declaradas a favor de mi mandante.

[OPCIONAL — incluir si procede]

SÉPTIMA.- Que habiendo resultado infructuoso el requerimiento de afianzamiento de las responsabilidades pecuniarias de D./Dña. [NOMBRE Y APELLIDOS] en la presente Pieza Separada de Responsabilidad Civil, y no constando en la causa la existencia de bienes susceptibles de embargo en garantía de las mismas, interesamos que se ordene sin demora la investigación de los bienes y fuentes de ingresos que el/la responsable civil pueda tener a su nombre, a cuyo efecto solicitamos se practiquen las siguientes diligencias [COMPLETAR].

[OPCIONAL — incluir si procede]

OCTAVA.- Esta representación interesa que se acuerde el comiso del vehículo utilizado en los hechos, al amparo de lo dispuesto en el artículo 385 bis del Código Penal y que, de conformidad con lo dispuesto en el artículo 127 octies.3 Código Penal, dicho vehículo sea vendido, aplicándose su producto a satisfacer la responsabilidad civil que, a favor de mi mandante, le ha sido impuesta al/a la penado/a.

SUPLICO A LA [ELEGIR: SECCIÓN / SALA]:

Que tenga por presentado este escrito con sus copias, los admita, acuerde lo solicitado y por opuestos a cualquier tipo de beneficio de los solicitados por el condenado en la presente causa.

Es de Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a	Firma de Procurador/a

================================================================================
