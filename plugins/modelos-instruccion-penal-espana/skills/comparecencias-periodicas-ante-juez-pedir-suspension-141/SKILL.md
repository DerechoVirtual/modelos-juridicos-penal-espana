---
name: comparecencias-periodicas-ante-juez-pedir-suspension-141
description: "Redacta el escrito «Comparecencias periódicas ante el juez: pedir su suspensión o una ampliación temporal» (formulario 141 de instrucción y procedimiento penal, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Comparecencias periódicas ante el juez: pedir su suspensión o una ampliación temporal

> Formulario 0141 del plugin **Instrucción y procedimiento penal** · revisado el 17-11-2026.

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

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión. Empieza con una nota explicativa (para qué sirve el escrito y cuándo se usa) y acaba con sus notas al pie, revisadas en el BOE: léela antes de redactar, pero no la copies en el escrito.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] Nº (2 veces)
- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] DELITO
- [ ] FECHA (2 veces)
- [ ] LUGAR
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…lidad y en espera de juicio, por razones»; «…ransformándola desde la ahora acordada a»

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 530 LECRIM
- art. 530 LECRIM

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

### Formulario 0141 · Comparecencias periódicas ante el juez: pedir su suspensión o una ampliación temporal

- Año del modelo: 2023
- Revisión 17-11-2026: 2 llamadas a nota sin texto retiradas; 11 campos de relleno marcados en blanco; 1 encabezamientos de la Sección del Tribunal de Instancia completados (LO 1/2025); 2 huecos del original que se habían perdido sin marca, marcados (FECHA, Nº DE PROCEDIMIENTO)
- Nota explicativa incorporada desde la colección Procesal (formulario 119) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Escrito por el que la defensa de un encausado, que está en libertad provisional con la obligación de comparecencia periódica en el órgano judicial, conforme al art. 530 LECrim., solicita que se suspenda dicha obligación o bien se amplíe el periodo de tiempo de una comparecencia a otra.

---

A la Sección de Instrucción del Tribunal de Instancia de [SEDE] – plaza n.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS] Procurador/a de los tribunales del Ilustre Colegio de Procuradores de ejercitando la defensa de D./Dña. [NOMBRE Y APELLIDOS] en las diligencias previas nº [Nº DE PROCEDIMIENTO] que se sigue en este órgano judicial por delito de [DELITO], ante este órgano judicial comparezco y, como más procedente sea en derecho, DIGO:

Con fecha se acordó la libertad provisional de mi mandante, pero con obligación de comparecer semanalmente ante este órgano judicial para asegurar su localización y presencia mientras se encuentra en libertad provisional.

La medida fue acordada en virtud de lo dispuesto en el artículo 530 LECRIM, a cuyo tenor:

"El investigado o encausado que hubiere de estar en libertad provisional, con o sin fianza, constituirá apud acta obligación de comparecer en los días que le fueren señalados en el auto respectivo, y además cuantas veces fuere llamado ante el juez o tribunal que conozca de la causa. Para garantizar el cumplimiento de esta obligación, el juez o tribunal podrá acordar motivadamente la retención de su pasaporte."

Desde el dictado del auto acordando la libertad provisional de fecha [FECHA] se ha verificado el cumplimiento exacto de esta comparecencia semanal puntualmente, sin fallo ni inasistencia alguna. Pero, en la actualidad y en espera de juicio, por razones [COMPLETAR] se solicita que se anule esa obligación de comparecencia semanal, o que se transforme en mensual o bimensual, en su caso, para dar cumplimiento a lo dispuesto en el art. 530 LECRIM, dada la prolongación del tiempo para la celebración del juicio y el hecho de atender a las necesidades que se han citado, que son dificultadas por la periódica, o tan cercana en el tiempo, obligación de comparecer ante este órgano judicial, lo que supone una inversión de tiempo de [Nº] horas cada vez que debe producirse, debido al desplazamiento desde a y práctica de las gestiones necesarias para cumplir la comparecencia acordada.

Por ello, intereso se acepte la petición y se acuerde o bien la suspensión de la obligación de comparecer, dado el cumplimiento de la medida hasta la fecha, bien la ampliación del tiempo de la obligación de comparecer, transformándola desde la ahora acordada a [COMPLETAR].

Por todo ello,

SUPLICO A LA SECCIÓN

Se admita el presente escrito y se tenga por efectuadas las alegaciones.

Es de Justicia que pido en [LUGAR], a [FECHA].

Firma de Abogado/a

Firma de Procurador/a

D./Dña. [NOMBRE Y APELLIDOS] 	D./Dña. [NOMBRE Y APELLIDOS]

================================================================================

---

#### Notas al pie

(1) Este escrito puede presentarse en el órgano judicial o sección penal que haya acordado la libertad provisional del investigado/a con obligación de comparecer periódicamente

(2) Importante tener en cuenta en estos casos que la STS Pleno 224/2015 de 14 de abril, Rec. 10919/2014 señala que: "recordábamos que la interpretación jurisprudencial ha sido reiterada en la Sentencia de este mismo Tribunal Supremo nº 758/2014 de 12 de noviembre en la que dijimos: "Esta Sala Segunda del Tribunal Supremo ha adoptado el acuerdo en Pleno no jurisdiccional en 19 de diciembre de 2013 que dice: que "la obligación de comparecencia periódica ante el órgano judicial es la consecuencia de una medida cautelar de libertad provisional. Como tal medida cautelar puede ser compensada conforme al art. 59 del Código Penal, atendiendo al grado de aflictividad que su efectivo y acreditado cumplimiento haya comportado". Con ello, mientras que el investigado está en libertad provisional y mantiene su obligación de comparecer ante este ógano judicial, estas comparecencias serán abonadas en la medida que se estime si la sentencia es condenatoria, para reducir en la liquidación de la pena a cumplir el periodo en el que se hayan mantenido estas comparecencias, en la medida que fije el órgano sentenciador. Ya la STS 1045/2013 de 7 de enero de 2014, recogió esa decisión: "Admitida la existencia de un deber legal de compensación de toda restricción anticipada de derechos sufrida con carácter cautelar, la necesidad de operar conforme a criterios de motivada razonabilidad resulta indispensable. Y, desde luego, el criterio proclamado en la sentencia recurrida puede considerarse ejemplar. Las comparecencias quincenales efectuadas durante 18 meses por el acusado han sido compensadas a razón de 1 día de prisión por cada 10 comparecencias, lo que totalizan 4 días a restar de los 3 años de condena que le fueron impuestos a aquél y que ahora han de ser abonados en la liquidación definitiva. Se trata de un cómputo equilibrado, razonable y, por tanto, susceptible de aplicación en supuestos de igual o similar naturaleza." Ante ello, y con la posterior posibilidad de que se dicte condena de prisión, es preciso valorar al instar la suspensión de estas comparecencias que luego se abonaría una reducción de cumplimiento en la liquidación de 1 día por cada diez comparecencias
