---
name: danos-denuncia-escrita-ante-policia-129
description: "Redacta el escrito «Daños: denuncia escrita ante la policía» (formulario 129 de delitos contra el patrimonio, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Daños: denuncia escrita ante la policía

> Formulario 0129 del plugin **Delitos contra el patrimonio** · revisado el 17-11-2026.

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

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión. Empieza con una nota explicativa (para qué sirve el escrito y cuándo se usa), revisada en el BOE: léela antes de redactar, pero no la copies en el escrito.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] DNI/NIE
- [ ] CALLE (2 veces)
- [ ] Nº (4 veces)
- [ ] FECHA (3 veces)
- [ ] MARCA/MODELO
- [ ] MATRÍCULA
- [ ] LOCALIDAD
- [ ] LUGAR
- [ ] Otros 3 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…A la comisaría de policía de»; «…núm. [Nº] de esta ciudad»; «… conocimiento de la Comisaría de Policía»

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 268 de la LECrim

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

### Formulario 0129 · Daños: denuncia escrita ante la policía

- Año del modelo: 2023
- Revisión 17-11-2026: 16 campos de relleno marcados en blanco; 2 huecos del original que se habían perdido sin marca, marcados (NOMBRE Y APELLIDOS)
- Nota explicativa incorporada desde la colección Procesal (formulario 115) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Escrito por el que se presenta denuncia sin abogado ni procurador ante la policía por haber sufrido daños en su vehículo que pueden ser constitutivos de delito.

---

A la comisaría de policía de [COMPLETAR]

D./Dª. [NOMBRE Y APELLIDOS], mayor de edad, con DNI [DNI/NIE], domiciliado en C/ [CALLE] núm. [Nº] de esta ciudad [COMPLETAR], por medio de la presente DENUNCIO los siguientes

HECHOS

PRIMERO.- Que el pasado día [FECHA] a las [Nº] horas dejé correctamente estacionado el vehículo de mi propiedad modelo [MARCA/MODELO] y matrícula [MATRÍCULA] a la altura del núm. [Nº] de la calle [CALLE] en perfecto estado.

Esta mañana, sobre las [Nº] horas, al ir a recoger el citado vehículo, el mismo presentaba daños en el lateral izquierdo consistentes en diversas rayas en la chapa ubicadas la puerta del conductor y rotura del espejo retrovisor izquierdo el cual fue arrancado totalmente.

SEGUNDO.- Que no me consta la existencia de testigos presenciales sobre los hechos, si bien quiero hacer constar que he recibido reiteradas amenazas por parte de mi vecino D. [NOMBRE Y APELLIDOS], con domicilio en [LOCALIDAD], con el cual estoy enemistado hace tiempo, el cual el pasado día [FECHA] me manifestó en tono amenazante que «vigiles un poco más tu coche, no sea cosa que le vaya a pasar algo», lo cual pongo en conocimiento de la Policía por si pudiera tener relación con estos hechos y servir a la investigación policial.

TERCERO.- Asimismo, intereso que a la mayor brevedad se practique inspección ocular del vehículo en comprobación del hecho delictivo, constatando los daños descritos, y por si pudieran obtenerse pruebas del delito que denuncio.

Los hechos relatados los pongo en conocimiento de la Comisaría de Policía [COMPLETAR], mediante el presente escrito, por si fueran constitutivos de delito y a fin de que se proceda a la comprobación y averiguación de los mismos, instando la práctica de las diligencias arriba expresadas.

CUARTO.- Asimismo, al amparo de lo dispuesto en el art. 268 de la LECrim, solicito que sea entregado al portador de este escrito resguardo acreditativo de la presentación de esta denuncia.

En [LUGAR], a [FECHA].

Firma del/de la denunciante

================================================================================
