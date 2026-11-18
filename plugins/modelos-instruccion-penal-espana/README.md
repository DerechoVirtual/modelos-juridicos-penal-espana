# Instrucción penal: diligencias, habeas corpus y detenido · España

> Plugin de Claude Code `modelos-instruccion-penal-espana` · **49 formularios** · área: Penal · revisado el 17-11-2026 · requiere Jurisprudenciator

## Para qué sirve

Sirve para la fase de instrucción y los trámites del proceso penal: competencia y declinatoria, diligencias previas (petición de diligencias, reapertura, sobreseimiento), habeas corpus, asistencia al detenido, declaraciones telemáticas e intérprete, ante la Sección de Instrucción del Tribunal de Instancia.

Cada formulario es una skill: Claude lo rellena contigo paso a paso y te entrega el escrito en Word, con las normas comprobadas en el BOE.

## Qué puedes hacer con él

Estos son los tipos de escrito que trae, con algunos ejemplos (la lista completa de los 49 está al final):

- **Conformidad** (3). Por ejemplo: Procedimiento común: calificación del Fiscal y la acusación particular con conformidad del acusado; Conformidad en el juicio oral con discrepancia en lo civil: calificación conjunta; Procedimiento abreviado: defensa conforme con la acusación salvo en la responsabilidad civil.
- **Querellas y denuncias** (1). Por ejemplo: Ampliar la denuncia contra un nuevo denunciado.
- **Escritos de defensa** (1). Por ejemplo: Administración responsable civil subsidiaria: escrito de defensa.
- **Medidas cautelares y protección** (4). Por ejemplo: Habeas corpus: solicitud del abogado de la persona privada de libertad; Cambiar la prisión provisional por internamiento en centro de deshabituación; Pedir la rebaja de la fianza por responsabilidad civil.
- **Resoluciones, actas y documentos** (3). Por ejemplo: Delitos cometidos en el extranjero: auto de archivo por falta de jurisdicción; Aceptación de decreto: decreto del fiscal con la propuesta de pena; Aceptación de decreto: comparecencia del encausado ante el juez.
- **Solicitudes y escritos de trámite** (37). Por ejemplo: Pedir la acumulación de procesos penales seguidos ante el mismo órgano; Abogado con discapacidad: pedir que se adapte la sala de vistas para el juicio o la actuación; Información del abogado al cliente sobre la gravedad del conflicto y estrategia (art. 6 LO 5/2024).

## Cómo se usa

1. **Pídelo con tus palabras.** Cuéntale a Claude qué escrito necesitas y para qué caso; él elige el formulario. Por ejemplo:
   - «Pedir diligencias de prueba en unas diligencias previas»
   - «Solicitud de habeas corpus»
   - «Pedir la reapertura de unas diligencias previas archivadas»
2. **Si no da con el formulario**, empieza por el índice del plugin: escribe `/modelos-instruccion-penal-espana:indice` y cuéntale lo que necesitas. Te propondrá el formulario que mejor encaja (o dos o tres para que elijas).
3. **Si ya sabes cuál quieres**, llámalo por su nombre de skill, por ejemplo `/modelos-instruccion-penal-espana:pedir-acumulacion-procesos-penales-seguidos-ante-mismo-25`. Los nombres están en la lista de formularios de abajo.

## Qué hace Claude cuando usas un formulario

1. Comprueba que Jurisprudenciator está conectado. Si no lo está, se para y te dice cómo conectarlo: no redacta nada sin él.
   Todos los datos jurídicos del escrito (artículos vigentes, sentencias con su ECLI, convenios, datos registrales) salen de Jurisprudenciator; nunca de memoria.
2. Te pide en una sola tanda los datos del caso (partes, órgano, fechas, importes…). Lo que no sepas queda como hueco visible.
3. Resuelve contigo las opciones que el formulario deja abiertas y decide qué párrafos opcionales entran según los hechos.
4. Aplica las correcciones y avisos de la revisión del 17-11-2026 (reformas legales, órganos, plazos).
5. Comprueba en el BOE, con Jurisprudenciator, cada norma que cita el escrito; si alguna ha cambiado, usa la redacción vigente y te lo dice.
6. Te indica el plazo y ante quién se presenta, y te entrega el escrito en Word con un resumen de lo que queda pendiente.

El resultado es un borrador para que lo revise un profesional antes de presentarlo.

## Antes de empezar

- **Dónde funciona:** en Claude Code, en la terminal o en la pestaña Code de la app de Claude. Desde esta carpeta no se puede instalar en el chat ni en Cowork: para eso habría que publicarlo en un repositorio de GitHub.
- **Jurisprudenciator es imprescindible:** el plugin trae el conector y cada skill trabaja siempre con él, igual que los plugins de Jurisprudenciator del directorio de Claude. Sin una cuenta de Jurisprudenciator conectada, las skills se paran y no redactan nada. La primera vez hay que iniciar sesión (en Claude Code, con `/mcp`; o con tu URL personal: https://jurisprudenciator.lexiaipro.org/instalacion). Si ya tienes Jurisprudenciator conectado en Claude, las skills usan ese.
- **Espacio que ocupa:** unos 5.000 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable modelos-instruccion-penal-espana@plugins-dv`).

## Instalación

Solo la primera vez, añade el catálogo de plugins (sirve para todos). Cambia la ruta por la carpeta donde esté el catálogo (la que contiene `.claude-plugin`); si es un zip, descomprímelo antes en una ruta corta, porque hay nombres de archivo largos:

```bash
claude plugin marketplace add "C:\plugins-dv"
```

Después, instala este plugin:

```bash
claude plugin install modelos-instruccion-penal-espana@plugins-dv
```

En la pestaña Code de la app de Claude también puedes pedírselo a Claude con esas palabras: «instala el plugin modelos-instruccion-penal-espana del catálogo plugins-dv que está en C:\plugins-dv». Al terminar, abre una conversación nueva para que aparezcan sus skills.

## Lista de formularios

Para usar uno directamente: `/modelos-instruccion-penal-espana:<skill>`.

### Conformidad (3)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 52 | Procedimiento común: calificación del Fiscal y la acusación particular con conformidad del acusado | 2025 | `procedimiento-comun-calificacion-fiscal-acusacion-52` |
| 95 | Conformidad en el juicio oral con discrepancia en lo civil: calificación conjunta | 2023 | `conformidad-juicio-oral-discrepancia-lo-civil-95` |
| 697 | Procedimiento abreviado: defensa conforme con la acusación salvo en la responsabilidad civil | 2017 | `procedimiento-abreviado-defensa-conforme-acusacion-salvo-697` |

### Querellas y denuncias (1)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 69 | Ampliar la denuncia contra un nuevo denunciado | 2024 | `ampliar-denuncia-contra-nuevo-denunciado-69` |

### Escritos de defensa (1)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 433 | Administración responsable civil subsidiaria: escrito de defensa | 2020 | `administracion-responsable-civil-subsidiaria-escrito-433` |

### Medidas cautelares y protección (4)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 128 | Habeas corpus: solicitud del abogado de la persona privada de libertad | 2023 | `habeas-corpus-solicitud-abogado-persona-privada-libertad-128` |
| 166 | Cambiar la prisión provisional por internamiento en centro de deshabituación | 2022 | `cambiar-prision-provisional-internamiento-centro-166` |
| 477 | Pedir la rebaja de la fianza por responsabilidad civil | 2019 | `pedir-rebaja-fianza-responsabilidad-civil-477` |
| 478 | Pedir la rebaja de la fianza para eludir la prisión provisional | 2019 | `pedir-rebaja-fianza-eludir-prision-provisional-478` |

### Resoluciones, actas y documentos (3)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 38 | Delitos cometidos en el extranjero: auto de archivo por falta de jurisdicción | 2025 | `delitos-cometidos-extranjero-auto-archivo-falta-38` |
| 771 | Aceptación de decreto: decreto del fiscal con la propuesta de pena | 2016 | `aceptacion-decreto-decreto-fiscal-propuesta-pena-771` |
| 772 | Aceptación de decreto: comparecencia del encausado ante el juez | 2016 | `aceptacion-decreto-comparecencia-encausado-ante-juez-772` |

### Solicitudes y escritos de trámite (37)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 25 | Pedir la acumulación de procesos penales seguidos ante el mismo órgano | 2026 | `pedir-acumulacion-procesos-penales-seguidos-ante-mismo-25` |
| 62 | Abogado con discapacidad: pedir que se adapte la sala de vistas para el juicio o la actuación | 2024 | `abogado-discapacidad-pedir-adapte-sala-vistas-juicio-62` |
| 63 | Información del abogado al cliente sobre la gravedad del conflicto y estrategia (art. 6 LO 5/2024) | 2024 | `informacion-abogado-cliente-sobre-gravedad-conflicto-63` |
| 67 | Pedir que se repita una declaración en instrucción por privar al letrado de su libertad de expresión | 2024 | `pedir-repita-declaracion-instruccion-privar-letrado-67` |
| 71 | Investigado o acusado: pedir declarar por vía telemática (desde el 20 de marzo de 2024) | 2024 | `investigado-acusado-pedir-declarar-via-telematica-desde-71` |
| 72 | Testigo enfermo o lesionado: declarar por vía telemática desde casa (desde el 20 de marzo de 2024) | 2024 | `testigo-enfermo-lesionado-declarar-via-telematica-desde-72` |
| 73 | Pedir que testigo o perito declaren en persona en el juicio oral (desde el 20 de marzo de 2024) | 2024 | `pedir-testigo-perito-declaren-persona-juicio-oral-desde-73` |
| 74 | Pedir que testigo o perito declaren por vía telemática (desde el 20 de marzo de 2024) | 2024 | `pedir-testigo-perito-declaren-via-telematica-desde-20-74` |
| 75 | Acusado: pedir estar presente físicamente en los juicios (desde el 20 de marzo de 2024) | 2024 | `acusado-pedir-estar-presente-fisicamente-juicios-desde-75` |
| 76 | Pedir que el acusado declare en último lugar en la práctica de la prueba | 2024 | `pedir-acusado-declare-ultimo-lugar-practica-prueba-76` |
| 78 | Acusado: comparecencia telemática por justa causa o fuerza mayor (desde el 20 de marzo de 2024) | 2024 | `acusado-comparecencia-telematica-justa-causa-fuerza-78` |
| 116 | Abreviado: el investigado pide el sobreseimiento tras diligencias complementarias | 2023 | `abreviado-investigado-pide-sobreseimiento-tras-116` |
| 117 | Pedir la reapertura de diligencias previas archivadas | 2023 | `pedir-reapertura-diligencias-previas-archivadas-117` |
| 119 | Pedir que las diligencias previas pasen a juicio por delito leve | 2023 | `pedir-diligencias-previas-pasen-juicio-delito-leve-119` |
| 120 | Investigado: pedir diligencias de prueba en las diligencias previas | 2023 | `investigado-pedir-diligencias-prueba-diligencias-previas-120` |
| 122 | Denunciante: pedir que se notifique el auto que inadmite la denuncia | 2023 | `denunciante-pedir-notifique-auto-inadmite-denuncia-122` |
| 130 | Abogado del detenido: pedir a la policía diligencias inmediatas | 2023 | `abogado-detenido-pedir-policia-diligencias-inmediatas-130` |
| 141 | Comparecencias periódicas ante el juez: pedir su suspensión o una ampliación temporal | 2023 | `comparecencias-periodicas-ante-juez-pedir-suspension-141` |
| 230 | Declinatoria por falta de jurisdicción | 2022 | `declinatoria-falta-jurisdiccion-230` |
| 231 | Declinatoria por falta de competencia objetiva por razón de la materia | 2022 | `declinatoria-falta-competencia-objetiva-razon-materia-231` |
| 232 | Pedir que se reclamen las actuaciones al órgano jerárquicamente inferior | 2022 | `pedir-reclamen-actuaciones-organo-jerarquicamente-232` |
| 233 | Declinatoria por falta de competencia territorial | 2022 | `declinatoria-falta-competencia-territorial-233` |
| 234 | Acumular causas penales conexas y pedir la inhibición a la Sección competente | 2022 | `acumular-causas-penales-conexas-pedir-inhibicion-seccion-234` |
| 236 | Revocar la renuncia a la acción civil en el proceso penal | 2022 | `revocar-renuncia-accion-civil-proceso-penal-236` |
| 357 | Procedimiento ordinario: pedir la nulidad de actuaciones judiciales | 2021 | `procedimiento-ordinario-pedir-nulidad-actuaciones-357` |
| 420 | Abogado: intervenir por videoconferencia en el juicio penal (desde el 20 de marzo de 2024) | 2020 | `abogado-intervenir-videoconferencia-juicio-penal-desde-420` |
| 422 | Abogado: intervenir por videoconferencia en juicio penal telemático (hasta el 19 de marzo de 2024) | 2020 | `abogado-intervenir-videoconferencia-juicio-penal-422` |
| 487 | Oponerse a la prórroga de la instrucción | 2019 | `oponerse-prorroga-instruccion-487` |
| 518 | Reclamar los honorarios del letrado en un procedimiento penal (jura de cuentas) | 2019 | `reclamar-honorarios-letrado-procedimiento-penal-jura-518` |
| 741 | Repetir la declaración del investigado por no haber tenido traductor o intérprete | 2016 | `repetir-declaracion-investigado-no-haber-tenido-741` |
| 743 | Pedir traductor o intérprete para el investigado o acusado | 2016 | `pedir-traductor-interprete-investigado-acusado-743` |
| 744 | Pedir la presencia física del intérprete (defensa del investigado o acusado) | 2016 | `pedir-presencia-fisica-interprete-defensa-investigado-744` |
| 745 | Pedir que se compruebe la exactitud de la traducción o interpretación (defensa del investigado) | 2016 | `pedir-compruebe-exactitud-traduccion-interpretacion-745` |
| 746 | Renunciar al derecho a traductor e intérprete (investigado o acusado) | 2016 | `renunciar-derecho-traductor-e-interprete-investigado-746` |
| 757 | Pedir que se determine la edad del encausado extranjero | 2016 | `pedir-determine-edad-encausado-extranjero-757` |
| 758 | Pedir diligencias para determinar la edad del encausado | 2016 | `pedir-diligencias-determinar-edad-encausado-758` |
| 803 | Defensa: pedir que se tramite por el proceso por aceptación de decreto | 2016 | `defensa-pedir-tramite-proceso-aceptacion-decreto-803` |

## Qué hay dentro de cada skill

- `SKILL.md`: los datos que hay que pedir, las elecciones, los párrafos opcionales, los avisos de la revisión, las normas que hay que comprobar y el flujo;
- `formulario.md`: el texto revisado del formulario;
- `marco.md`: la guía del tema, con las reglas y plazos vigentes comprobados en el BOE.

