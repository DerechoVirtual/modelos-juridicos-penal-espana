# Violencia de género, órdenes de protección e impago de pensiones · España

> Plugin de Claude Code `modelos-violencia-de-genero-espana` · **75 formularios** · área: Penal · revisado el 17-11-2026 · requiere Jurisprudenciator

## Para qué sirve

Sirve para la violencia de género y doméstica ante la Sección de Violencia sobre la Mujer: orden de protección, quebrantamiento, maltrato habitual, abandono de familia, impago de pensiones, sustracción de menores y cuestiones de competencia.

Cada formulario es una skill: Claude lo rellena contigo paso a paso y te entrega el escrito en Word, con las normas comprobadas en el BOE.

## Qué puedes hacer con él

Estos son los tipos de escrito que trae, con algunos ejemplos (la lista completa de los 75 está al final):

- **Conformidad** (5). Por ejemplo: Lesiones al animal de la pareja: conformidad de la defensa; Sustracción de menores: conformidad de la defensa; Inutilizar dispositivos electrónicos de control (violencia de género): defensa con conformidad.
- **Recursos e impugnaciones** (11). Por ejemplo: Orden de protección denegada: oposición a la apelación; Tentativa de asesinato con agravantes de parentesco y de género: apelación contra la condena; Orden de protección por violencia de género: reforma y subsidiario de apelación del acusado.
- **Querellas y denuncias** (10). Por ejemplo: Delito leve ante Violencia sobre la Mujer: denuncia con petición de juicio inmediato; Quebrantamiento de condena (prohibición de comunicación online): querella; Matrimonio ilegal: querella.
- **Escritos de acusación** (11). Por ejemplo: Entrega de menor por precio para alterar la filiación: acusación; Impago de prestaciones por separación, divorcio o nulidad matrimonial: acusación; Abandono de familia: acusación.
- **Escritos de defensa** (11). Por ejemplo: Maltrato habitual (violencia de género): defensa; Quebrantamiento de medida cautelar de alejamiento: defensa; Lesiones al animal de la pareja: escrito de defensa.
- **Medidas cautelares y protección** (7). Por ejemplo: Delito contra las relaciones familiares: la acusación particular pide el alejamiento cautelar; Violencia de género: la defensa se opone a suspender cautelarmente el régimen de visitas; Tentativa de homicidio o asesinato: la acusación particular pide suspender la patria potestad.
- **Resoluciones, actas y documentos** (7). Por ejemplo: Inhibición a otra Sección de Violencia sobre la Mujer por víctimas con distintos domicilios: auto; Delito sexual: auto de inhibición de Violencia sobre la Mujer a Violencia contra la Infancia; Falta de competencia de la Sección de Violencia sobre la Mujer en un proceso de familia: auto.
- **Solicitudes y escritos de trámite** (13). Por ejemplo: Declinatoria a favor de la Sección de Violencia sobre la Mujer por agresión sexual a menor; Declinatoria a Violencia contra la Infancia por agresión sexual a hija menor y a su madre; Declinatoria a Violencia contra la Infancia por agresión sexual a menor por su pareja.

## Cómo se usa

1. **Pídelo con tus palabras.** Cuéntale a Claude qué escrito necesitas y para qué caso; él elige el formulario. Por ejemplo:
   - «Escrito de acusación por impago de pensiones»
   - «Escrito de defensa por maltrato habitual»
   - «Denuncia por delito leve ante la Sección de Violencia sobre la Mujer con petición de juicio inmediato»
2. **Si no da con el formulario**, empieza por el índice del plugin: escribe `/modelos-violencia-de-genero-espana:indice` y cuéntale lo que necesitas. Te propondrá el formulario que mejor encaja (o dos o tres para que elijas).
3. **Si ya sabes cuál quieres**, llámalo por su nombre de skill, por ejemplo `/modelos-violencia-de-genero-espana:inhibicion-otra-seccion-violencia-sobre-mujer-victimas-31`. Los nombres están en la lista de formularios de abajo.

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
- **Espacio que ocupa:** unos 7.000 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable modelos-violencia-de-genero-espana@plugins-dv`).

## Instalación

Solo la primera vez, añade el catálogo de plugins (sirve para todos). Cambia la ruta por la carpeta donde esté el catálogo (la que contiene `.claude-plugin`); si es un zip, descomprímelo antes en una ruta corta, porque hay nombres de archivo largos:

```bash
claude plugin marketplace add "C:\plugins-dv"
```

Después, instala este plugin:

```bash
claude plugin install modelos-violencia-de-genero-espana@plugins-dv
```

En la pestaña Code de la app de Claude también puedes pedírselo a Claude con esas palabras: «instala el plugin modelos-violencia-de-genero-espana del catálogo plugins-dv que está en C:\plugins-dv». Al terminar, abre una conversación nueva para que aparezcan sus skills.

## Lista de formularios

Para usar uno directamente: `/modelos-violencia-de-genero-espana:<skill>`.

### Conformidad (5)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 112 | Lesiones al animal de la pareja: conformidad de la defensa | 2023 | `lesiones-animal-pareja-conformidad-defensa-112` |
| 287 | Sustracción de menores: conformidad de la defensa | 2021 | `sustraccion-menores-conformidad-defensa-287` |
| 480 | Inutilizar dispositivos electrónicos de control (violencia de género): defensa con conformidad | 2019 | `inutilizar-dispositivos-electronicos-control-violencia-480` |
| 510 | Quebrantamiento de condena (prohibición de comunicación online): defensa con conformidad | 2019 | `quebrantamiento-condena-prohibicion-comunicacion-online-510` |
| 859 | Quebrantamiento de medida cautelar de alejamiento: defensa con conformidad | 2016 | `quebrantamiento-medida-cautelar-alejamiento-defensa-859` |

### Recursos e impugnaciones (11)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 102 | Orden de protección denegada: oposición a la apelación | 2023 | `orden-proteccion-denegada-oposicion-apelacion-102` |
| 114 | Lesiones al animal de la pareja: apelación contra la condena | 2023 | `lesiones-animal-pareja-apelacion-contra-condena-114` |
| 285 | Tentativa de asesinato con agravantes de parentesco y de género: apelación contra la condena | 2021 | `tentativa-asesinato-agravantes-parentesco-genero-285` |
| 289 | Sustracción de menores: apelación contra la condena | 2021 | `sustraccion-menores-apelacion-contra-condena-289` |
| 374 | Orden de protección por violencia de género: reforma y subsidiario de apelación del acusado | 2021 | `orden-proteccion-violencia-genero-reforma-subsidiario-374` |
| 389 | Violencia de género: apelación contra el sobreseimiento y archivo provisional | 2020 | `violencia-genero-apelacion-contra-sobreseimiento-archivo-389` |
| 416 | Abandono de familia: apelación contra la absolución | 2020 | `abandono-familia-apelacion-contra-absolucion-416` |
| 451 | Impugnar la apelación contra la condena por quebrantamiento de medida cautelar de alejamiento | 2020 | `impugnar-apelacion-contra-condena-quebrantamiento-medida-451` |
| 481 | Inutilizar dispositivos electrónicos de control (violencia de género): apelación contra la condena | 2019 | `inutilizar-dispositivos-electronicos-control-violencia-481` |
| 509 | Apelación contra la condena por quebrantamiento de condena (prohibición de comunicación online) | 2019 | `apelacion-contra-condena-quebrantamiento-condena-509` |
| 853 | Apelación contra la condena por quebrantamiento de medida cautelar de alejamiento | 2016 | `apelacion-contra-condena-quebrantamiento-medida-cautelar-853` |

### Querellas y denuncias (10)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 113 | Lesiones al animal de la pareja: querella | 2023 | `lesiones-animal-pareja-querella-113` |
| 286 | Tentativa de asesinato con agravantes de parentesco y de género: querella | 2021 | `tentativa-asesinato-agravantes-parentesco-genero-286` |
| 288 | Sustracción de menores: querella | 2021 | `sustraccion-menores-querella-288` |
| 383 | Delito leve ante Violencia sobre la Mujer: denuncia con petición de juicio inmediato | 2021 | `delito-leve-ante-violencia-sobre-mujer-denuncia-peticion-383` |
| 482 | Inutilizar dispositivos electrónicos de control (violencia de género): querella | 2019 | `inutilizar-dispositivos-electronicos-control-violencia-482` |
| 511 | Quebrantamiento de condena (prohibición de comunicación online): querella | 2019 | `quebrantamiento-condena-prohibicion-comunicacion-online-511` |
| 806 | Matrimonio ilegal: querella | 2016 | `matrimonio-ilegal-querella-806` |
| 807 | Entrega de menor por precio para alterar la filiación: querella | 2016 | `entrega-menor-precio-alterar-filiacion-querella-807` |
| 835 | Maltrato habitual (violencia de género): querella | 2016 | `maltrato-habitual-violencia-genero-querella-835` |
| 854 | Quebrantamiento de medida cautelar de alejamiento: querella | 2016 | `quebrantamiento-medida-cautelar-alejamiento-querella-854` |

### Escritos de acusación (11)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 115 | Lesiones al animal de la pareja: escrito de acusación | 2023 | `lesiones-animal-pareja-escrito-acusacion-115` |
| 283 | Tentativa de asesinato con agravantes de parentesco y de género: calificación de la acusación | 2021 | `tentativa-asesinato-agravantes-parentesco-genero-283` |
| 290 | Sustracción de menores: escrito de acusación | 2021 | `sustraccion-menores-escrito-acusacion-290` |
| 484 | Inutilizar dispositivos electrónicos de control (violencia de género): acusación | 2019 | `inutilizar-dispositivos-electronicos-control-violencia-484` |
| 512 | Quebrantamiento de condena (prohibición de comunicación online): acusación | 2019 | `quebrantamiento-condena-prohibicion-comunicacion-online-512` |
| 804 | Matrimonio ilegal: acusación | 2016 | `matrimonio-ilegal-acusacion-804` |
| 809 | Entrega de menor por precio para alterar la filiación: acusación | 2016 | `entrega-menor-precio-alterar-filiacion-acusacion-809` |
| 812 | Impago de prestaciones por separación, divorcio o nulidad matrimonial: acusación | 2016 | `impago-prestaciones-separacion-divorcio-nulidad-812` |
| 813 | Abandono de familia: acusación | 2016 | `abandono-familia-acusacion-813` |
| 831 | Maltrato habitual (violencia de género): acusación | 2016 | `maltrato-habitual-violencia-genero-acusacion-831` |
| 857 | Quebrantamiento de medida cautelar de alejamiento: acusación | 2016 | `quebrantamiento-medida-cautelar-alejamiento-acusacion-857` |

### Escritos de defensa (11)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 111 | Lesiones al animal de la pareja: escrito de defensa | 2023 | `lesiones-animal-pareja-escrito-defensa-111` |
| 284 | Tentativa de asesinato con agravantes de parentesco y de género: calificación de la defensa | 2021 | `tentativa-asesinato-agravantes-parentesco-genero-284` |
| 291 | Sustracción de menores: escrito de defensa | 2021 | `sustraccion-menores-escrito-defensa-291` |
| 483 | Inutilizar dispositivos electrónicos de control (violencia de género): defensa | 2019 | `inutilizar-dispositivos-electronicos-control-violencia-483` |
| 508 | Quebrantamiento de condena (prohibición de comunicación online): defensa | 2019 | `quebrantamiento-condena-prohibicion-comunicacion-online-508` |
| 805 | Matrimonio ilegal: defensa | 2016 | `matrimonio-ilegal-defensa-805` |
| 808 | Entrega de menor por precio para alterar la filiación: defensa | 2016 | `entrega-menor-precio-alterar-filiacion-defensa-808` |
| 810 | Abandono de familia: defensa | 2016 | `abandono-familia-defensa-810` |
| 811 | Impago de prestaciones por separación, divorcio o nulidad matrimonial: defensa | 2016 | `impago-prestaciones-separacion-divorcio-nulidad-811` |
| 834 | Maltrato habitual (violencia de género): defensa | 2016 | `maltrato-habitual-violencia-genero-defensa-834` |
| 856 | Quebrantamiento de medida cautelar de alejamiento: defensa | 2016 | `quebrantamiento-medida-cautelar-alejamiento-defensa-856` |

### Medidas cautelares y protección (7)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 273 | Delito contra las relaciones familiares: la acusación particular pide el alejamiento cautelar | 2022 | `delito-contra-relaciones-familiares-acusacion-particular-273` |
| 318 | Violencia de género: la defensa se opone a suspender cautelarmente el régimen de visitas | 2021 | `violencia-genero-defensa-opone-suspender-cautelarmente-318` |
| 319 | Tentativa de homicidio o asesinato: la acusación particular pide suspender la patria potestad | 2021 | `tentativa-homicidio-asesinato-acusacion-particular-pide-319` |
| 320 | Tentativa de homicidio o asesinato: la defensa se opone a suspender la patria potestad | 2021 | `tentativa-homicidio-asesinato-defensa-opone-suspender-320` |
| 736 | Menor víctima de violencia doméstica: pedir al juez penal suspender las visitas del progenitor | 2016 | `menor-victima-violencia-domestica-pedir-juez-penal-736` |
| 768 | Violencia de género con hijos menores: la víctima pide suspender el régimen de visitas | 2016 | `violencia-genero-hijos-menores-victima-pide-suspender-768` |
| 784 | Víctima con hijos mayores y menores: pedir medidas cautelares civiles en el proceso penal | 2016 | `victima-hijos-mayores-menores-pedir-medidas-cautelares-784` |

### Resoluciones, actas y documentos (7)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 31 | Inhibición a otra Sección de Violencia sobre la Mujer por víctimas con distintos domicilios: auto | 2025 | `inhibicion-otra-seccion-violencia-sobre-mujer-victimas-31` |
| 32 | Delito sexual: auto de inhibición de Violencia sobre la Mujer a Violencia contra la Infancia | 2025 | `delito-sexual-auto-inhibicion-violencia-sobre-mujer-32` |
| 33 | Falta de competencia de la Sección de Violencia sobre la Mujer en un proceso de familia: auto | 2025 | `falta-competencia-seccion-violencia-sobre-mujer-proceso-33` |
| 34 | Delito sexual (procesos previos al 3/10/2025): Violencia sobre la Mujer rechaza la inhibición (auto) | 2025 | `delito-sexual-procesos-previos-3-10-2025-violencia-sobre-34` |
| 36 | Inhibición a Violencia sobre la Mujer del domicilio de la víctima a fecha del hecho: auto | 2025 | `inhibicion-violencia-sobre-mujer-domicilio-victima-fecha-36` |
| 37 | Impago de pensión alimenticia: Violencia sobre la Mujer rechaza la inhibición de Instrucción (auto) | 2025 | `impago-pension-alimenticia-violencia-sobre-mujer-rechaza-37` |
| 39 | Inhibición de Instrucción a favor de Violencia sobre la Mujer del domicilio de la víctima: auto | 2025 | `inhibicion-instruccion-favor-violencia-sobre-mujer-39` |

### Solicitudes y escritos de trámite (13)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 40 | Declinatoria a favor de la Sección de Violencia sobre la Mujer por agresión sexual a menor | 2025 | `declinatoria-favor-seccion-violencia-sobre-mujer-40` |
| 41 | Declinatoria a Violencia contra la Infancia por agresión sexual a hija menor y a su madre | 2025 | `declinatoria-violencia-contra-infancia-agresion-sexual-41` |
| 42 | Declinatoria a Violencia contra la Infancia por agresión sexual a menor por su pareja | 2025 | `declinatoria-violencia-contra-infancia-agresion-sexual-42` |
| 43 | Declinatoria a favor de la Sección de Violencia sobre la Mujer por trata de menores | 2025 | `declinatoria-favor-seccion-violencia-sobre-mujer-trata-43` |
| 44 | Declinatoria a favor de la Sección de Violencia sobre la Mujer por impago de alimentos a hijo menor | 2025 | `declinatoria-favor-seccion-violencia-sobre-mujer-impago-44` |
| 45 | Declinatoria a Violencia contra la Infancia por impago de pensión compensatoria y alimenticia | 2025 | `declinatoria-violencia-contra-infancia-impago-pension-45` |
| 275 | Perdón del ofendido menor o discapacitado: pedir que no surta efecto (hasta el 2 de abril de 2025) | 2022 | `perdon-ofendido-menor-discapacitado-pedir-no-surta-275` |
| 276 | La defensa propone a la Fiscalía un programa de resolución de conflictos o parentalidad positiva | 2022 | `defensa-propone-fiscalia-programa-resolucion-conflictos-276` |
| 373 | Declinatoria por conexidad a favor de la Sección de Violencia sobre la Mujer | 2021 | `declinatoria-conexidad-favor-seccion-violencia-sobre-373` |
| 375 | Inhibitoria ante el Juez de Violencia sobre la Mujer | 2021 | `inhibitoria-ante-juez-violencia-sobre-mujer-375` |
| 376 | Violencia sobre la Mujer: personación de la víctima en diligencias previas | 2021 | `violencia-sobre-mujer-personacion-victima-diligencias-376` |
| 769 | Víctima en el proceso penal: pedir modificar las medidas civiles del proceso de familia | 2016 | `victima-proceso-penal-pedir-modificar-medidas-civiles-769` |
| 785 | Víctima de violencia de género: separación o divorcio ante la Sección de Violencia sobre la Mujer | 2016 | `victima-violencia-genero-separacion-divorcio-ante-785` |

## Qué hay dentro de cada skill

- `SKILL.md`: los datos que hay que pedir, las elecciones, los párrafos opcionales, los avisos de la revisión, las normas que hay que comprobar y el flujo;
- `formulario.md`: el texto revisado del formulario;
- `marco.md`: la guía del tema, con las reglas y plazos vigentes comprobados en el BOE.

