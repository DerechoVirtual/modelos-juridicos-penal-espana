# Hurtos, robos, estafas y ocupación (LO 1/2026) · España

> Plugin de Claude Code `modelos-estafas-robos-y-hurtos-espana` · **83 formularios** · área: Penal · revisado el 17-11-2026 · requiere Jurisprudenciator

## Para qué sirve

Sirve para los delitos patrimoniales, con la reforma de la LO 1/2026: hurto (también multirreincidente, de móviles y de productos agrarios), robo, estafa, apropiación indebida, administración desleal, usurpación y ocupación, insolvencias punibles y falsedades.

Cada formulario es una skill: Claude lo rellena contigo paso a paso y te entrega el escrito en Word, con las normas comprobadas en el BOE.

## Qué puedes hacer con él

Estos son los tipos de escrito que trae, con algunos ejemplos (la lista completa de los 83 está al final):

- **Conformidad** (14). Por ejemplo: Hurto de productos agrarios o ganaderos: defensa con conformidad; Estafa multirreincidente o leve agravada: conformidad de la defensa; Hurto de móvil: defensa con conformidad.
- **Recursos e impugnaciones** (19). Por ejemplo: Delito continuado: apelación contra la condena pidiendo la unidad natural de acción; Estafa del inquilino que no paga el alquiler (inquiokupación): apelación contra la condena; Hurto multirreincidente: apelación contra la condena.
- **Querellas y denuncias** (16). Por ejemplo: Daños: denuncia escrita ante la policía; Alteración de lindes: denuncia; Insolvencia punible: querella.
- **Escritos de acusación** (16). Por ejemplo: Defraudación de fluido eléctrico: escrito de acusación; Allanamiento de morada por ocupación de inmueble: calificación provisional de la acusación; Administración desleal: escrito de acusación.
- **Escritos de defensa** (17). Por ejemplo: Alzamiento de bienes (frustración de la ejecución): defensa; Apropiación indebida: defensa; Falsedad en documento público: defensa.
- **Solicitudes y escritos de trámite** (1). Por ejemplo: Usurpación de inmueble: pedir que se suspenda el desahucio.

## Cómo se usa

1. **Pídelo con tus palabras.** Cuéntale a Claude qué escrito necesitas y para qué caso; él elige el formulario. Por ejemplo:
   - «Conformidad de la defensa en un hurto multirreincidente»
   - «Querella por estafa»
   - «Denuncia por la ocupación de un inmueble que no es morada»
2. **Si no da con el formulario**, empieza por el índice del plugin: escribe `/modelos-estafas-robos-y-hurtos-espana:indice` y cuéntale lo que necesitas. Te propondrá el formulario que mejor encaja (o dos o tres para que elijas).
3. **Si ya sabes cuál quieres**, llámalo por su nombre de skill, por ejemplo `/modelos-estafas-robos-y-hurtos-espana:hurto-productos-agrarios-ganaderos-defensa-conformidad-1`. Los nombres están en la lista de formularios de abajo.

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
- **Espacio que ocupa:** unos 7.000 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable modelos-estafas-robos-y-hurtos-espana@plugins-dv`).

## Instalación

Solo la primera vez, añade el catálogo de plugins (sirve para todos). Cambia la ruta por la carpeta donde esté el catálogo (la que contiene `.claude-plugin`); si es un zip, descomprímelo antes en una ruta corta, porque hay nombres de archivo largos:

```bash
claude plugin marketplace add "C:\plugins-dv"
```

Después, instala este plugin:

```bash
claude plugin install modelos-estafas-robos-y-hurtos-espana@plugins-dv
```

En la pestaña Code de la app de Claude también puedes pedírselo a Claude con esas palabras: «instala el plugin modelos-estafas-robos-y-hurtos-espana del catálogo plugins-dv que está en C:\plugins-dv». Al terminar, abre una conversación nueva para que aparezcan sus skills.

## Lista de formularios

Para usar uno directamente: `/modelos-estafas-robos-y-hurtos-espana:<skill>`.

### Conformidad (14)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 1 | Hurto de productos agrarios o ganaderos: defensa con conformidad | 2026 | `hurto-productos-agrarios-ganaderos-defensa-conformidad-1` |
| 15 | Estafa multirreincidente o leve agravada: conformidad de la defensa | 2026 | `estafa-multirreincidente-leve-agravada-conformidad-15` |
| 21 | Hurto de móvil: defensa con conformidad | 2026 | `hurto-movil-defensa-conformidad-21` |
| 26 | Delito continuado: conformidad de la defensa admitiendo la unidad natural de acción | 2026 | `delito-continuado-conformidad-defensa-admitiendo-unidad-26` |
| 83 | Estafa del inquilino que no paga el alquiler (inquiokupación): conformidad del arrendatario | 2023 | `estafa-inquilino-no-paga-alquiler-inquiokupacion-83` |
| 140 | Hurto multirreincidente: conformidad de la defensa | 2023 | `hurto-multirreincidente-conformidad-defensa-140` |
| 392 | Insolvencia punible: conformidad de la defensa | 2020 | `insolvencia-punible-conformidad-defensa-392` |
| 402 | Defraudación de fluido eléctrico: conformidad de la defensa | 2020 | `defraudacion-fluido-electrico-conformidad-defensa-402` |
| 406 | Allanamiento de morada por ocupación de inmueble: conformidad de la defensa | 2020 | `allanamiento-morada-ocupacion-inmueble-conformidad-406` |
| 425 | Administración desleal: conformidad de la defensa | 2020 | `administracion-desleal-conformidad-defensa-425` |
| 445 | Alzamiento de bienes (frustración de la ejecución): defensa con conformidad | 2020 | `alzamiento-bienes-frustracion-ejecucion-defensa-445` |
| 447 | Apropiación indebida: defensa con conformidad | 2020 | `apropiacion-indebida-defensa-conformidad-447` |
| 861 | Usurpación de inmueble con violencia (okupas): defensa con conformidad en el abreviado | 2016 | `usurpacion-inmueble-violencia-okupas-defensa-conformidad-861` |
| 864 | Hurto: defensa con conformidad | 2016 | `hurto-defensa-conformidad-864` |

### Recursos e impugnaciones (19)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 3 | Hurto de productos agrarios o ganaderos: apelación del acusado contra la sentencia | 2026 | `hurto-productos-agrarios-ganaderos-apelacion-acusado-3` |
| 5 | Hurto de productos agrarios o ganaderos: apelación de la acusación contra la sentencia | 2026 | `hurto-productos-agrarios-ganaderos-apelacion-acusacion-5` |
| 17 | Estafa multirreincidente o leve agravada: apelación contra la condena | 2026 | `estafa-multirreincidente-leve-agravada-apelacion-contra-17` |
| 19 | Hurto de móvil: apelación del condenado contra la sentencia | 2026 | `hurto-movil-apelacion-condenado-contra-sentencia-19` |
| 20 | Hurto de móvil: apelación de la acusación contra la sentencia | 2026 | `hurto-movil-apelacion-acusacion-contra-sentencia-20` |
| 28 | Delito continuado: apelación contra la condena pidiendo la unidad natural de acción | 2026 | `delito-continuado-apelacion-contra-condena-pidiendo-28` |
| 82 | Estafa del inquilino que no paga el alquiler (inquiokupación): apelación contra la condena | 2023 | `estafa-inquilino-no-paga-alquiler-inquiokupacion-82` |
| 136 | Hurto multirreincidente: apelación contra la condena | 2023 | `hurto-multirreincidente-apelacion-contra-condena-136` |
| 377 | Usurpación de inmueble: el propietario se opone a que se suspenda el desahucio | 2021 | `usurpacion-inmueble-propietario-opone-suspenda-desahucio-377` |
| 391 | Insolvencia punible: apelación contra la condena | 2020 | `insolvencia-punible-apelacion-contra-condena-391` |
| 399 | Defraudación de fluido eléctrico: apelación contra la condena | 2020 | `defraudacion-fluido-electrico-apelacion-contra-condena-399` |
| 404 | Allanamiento de morada por ocupación de inmueble: apelación contra la condena | 2020 | `allanamiento-morada-ocupacion-inmueble-apelacion-contra-404` |
| 424 | Administración desleal: apelación contra la condena | 2020 | `administracion-desleal-apelacion-contra-condena-424` |
| 444 | Apelación contra la condena por alzamiento de bienes (frustración de la ejecución) | 2020 | `apelacion-contra-condena-alzamiento-bienes-frustracion-444` |
| 448 | Apelación contra la condena por apropiación indebida | 2020 | `apelacion-contra-condena-apropiacion-indebida-448` |
| 485 | Apelación contra la condena por robo de uso de vehículo de motor | 2019 | `apelacion-contra-condena-robo-uso-vehiculo-motor-485` |
| 852 | Apelación contra la condena por falsedad en documento privado y estafa | 2016 | `apelacion-contra-condena-falsedad-documento-privado-852` |
| 858 | Apelación contra la condena por usurpación de inmueble con violencia (okupas) | 2016 | `apelacion-contra-condena-usurpacion-inmueble-violencia-858` |
| 862 | Apelación contra la condena por hurto | 2016 | `apelacion-contra-condena-hurto-862` |

### Querellas y denuncias (16)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 16 | Estafa multirreincidente o leve agravada: querella | 2026 | `estafa-multirreincidente-leve-agravada-querella-16` |
| 27 | Delito continuado: querella | 2026 | `delito-continuado-querella-27` |
| 81 | Estafa del inquilino que no paga el alquiler (inquiokupación): querella | 2023 | `estafa-inquilino-no-paga-alquiler-inquiokupacion-81` |
| 129 | Daños: denuncia escrita ante la policía | 2023 | `danos-denuncia-escrita-ante-policia-129` |
| 138 | Hurto multirreincidente: querella | 2023 | `hurto-multirreincidente-querella-138` |
| 235 | Alteración de lindes: denuncia | 2022 | `alteracion-lindes-denuncia-235` |
| 394 | Insolvencia punible: querella | 2020 | `insolvencia-punible-querella-394` |
| 407 | Ocupación pacífica de inmueble que no es morada: denuncia | 2020 | `ocupacion-pacifica-inmueble-no-es-morada-denuncia-407` |
| 408 | Allanamiento de morada por ocupación de inmueble: denuncia | 2020 | `allanamiento-morada-ocupacion-inmueble-denuncia-408` |
| 410 | Defraudación de fluido eléctrico: denuncia | 2020 | `defraudacion-fluido-electrico-denuncia-410` |
| 423 | Administración desleal: querella | 2020 | `administracion-desleal-querella-423` |
| 520 | Estafa y falsedad en documento público: querella | 2019 | `estafa-falsedad-documento-publico-querella-520` |
| 855 | Usurpación de inmueble con violencia (okupas): querella | 2016 | `usurpacion-inmueble-violencia-okupas-querella-855` |
| 863 | Hurto: denuncia | 2016 | `hurto-denuncia-863` |
| 872 | Hurto de uso de vehículo de motor: querella | 2016 | `hurto-uso-vehiculo-motor-querella-872` |
| 873 | Robo de uso de vehículo de motor: querella | 2016 | `robo-uso-vehiculo-motor-querella-873` |

### Escritos de acusación (16)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 4 | Hurto de productos agrarios o ganaderos: escrito de acusación | 2026 | `hurto-productos-agrarios-ganaderos-escrito-acusacion-4` |
| 14 | Estafa multirreincidente o leve agravada: escrito de acusación | 2026 | `estafa-multirreincidente-leve-agravada-escrito-acusacion-14` |
| 23 | Hurto de móvil: escrito de acusación | 2026 | `hurto-movil-escrito-acusacion-23` |
| 30 | Delito continuado: escrito de acusación | 2026 | `delito-continuado-escrito-acusacion-30` |
| 80 | Estafa del inquilino que no paga el alquiler (inquiokupación): escrito de acusación | 2023 | `estafa-inquilino-no-paga-alquiler-inquiokupacion-escrito-80` |
| 139 | Hurto multirreincidente: escrito de acusación | 2023 | `hurto-multirreincidente-escrito-acusacion-139` |
| 390 | Insolvencia punible: escrito de acusación | 2020 | `insolvencia-punible-escrito-acusacion-390` |
| 400 | Defraudación de fluido eléctrico: escrito de acusación | 2020 | `defraudacion-fluido-electrico-escrito-acusacion-400` |
| 409 | Allanamiento de morada por ocupación de inmueble: calificación provisional de la acusación | 2020 | `allanamiento-morada-ocupacion-inmueble-calificacion-409` |
| 427 | Administración desleal: escrito de acusación | 2020 | `administracion-desleal-escrito-acusacion-427` |
| 450 | Apropiación indebida: acusación | 2020 | `apropiacion-indebida-acusacion-450` |
| 850 | Falsedad en documento mercantil en concurso medial con estafa: acusación | 2016 | `falsedad-documento-mercantil-concurso-medial-estafa-850` |
| 865 | Hurto: acusación | 2016 | `hurto-acusacion-865` |
| 866 | Usurpación de inmueble con violencia (okupas): acusación | 2016 | `usurpacion-inmueble-violencia-okupas-acusacion-866` |
| 868 | Hurto de uso de vehículo de motor: acusación | 2016 | `hurto-uso-vehiculo-motor-acusacion-868` |
| 870 | Robo de uso de vehículo de motor: acusación | 2016 | `robo-uso-vehiculo-motor-acusacion-870` |

### Escritos de defensa (17)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 2 | Hurto de productos agrarios o ganaderos: escrito de defensa | 2026 | `hurto-productos-agrarios-ganaderos-escrito-defensa-2` |
| 18 | Estafa multirreincidente o leve agravada: escrito de defensa | 2026 | `estafa-multirreincidente-leve-agravada-escrito-defensa-18` |
| 22 | Hurto de móvil: escrito de defensa | 2026 | `hurto-movil-escrito-defensa-22` |
| 29 | Delito continuado: escrito de defensa proponiendo la unidad natural de acción | 2026 | `delito-continuado-escrito-defensa-proponiendo-unidad-29` |
| 84 | Estafa del inquilino que no paga el alquiler (inquiokupación): defensa del arrendatario | 2023 | `estafa-inquilino-no-paga-alquiler-inquiokupacion-defensa-84` |
| 137 | Hurto multirreincidente: escrito de defensa | 2023 | `hurto-multirreincidente-escrito-defensa-137` |
| 393 | Insolvencia punible: escrito de defensa | 2020 | `insolvencia-punible-escrito-defensa-393` |
| 401 | Defraudación de fluido eléctrico: escrito de defensa | 2020 | `defraudacion-fluido-electrico-escrito-defensa-401` |
| 405 | Allanamiento de morada por ocupación de inmueble: calificación provisional de la defensa | 2020 | `allanamiento-morada-ocupacion-inmueble-calificacion-405` |
| 426 | Administración desleal: escrito de defensa | 2020 | `administracion-desleal-escrito-defensa-426` |
| 446 | Alzamiento de bienes (frustración de la ejecución): defensa | 2020 | `alzamiento-bienes-frustracion-ejecucion-defensa-446` |
| 449 | Apropiación indebida: defensa | 2020 | `apropiacion-indebida-defensa-449` |
| 851 | Falsedad en documento público: defensa | 2016 | `falsedad-documento-publico-defensa-851` |
| 860 | Usurpación de inmueble con violencia (okupas): defensa | 2016 | `usurpacion-inmueble-violencia-okupas-defensa-860` |
| 867 | Hurto: defensa | 2016 | `hurto-defensa-867` |
| 869 | Hurto de uso de vehículo de motor: defensa | 2016 | `hurto-uso-vehiculo-motor-defensa-869` |
| 871 | Robo de uso de vehículo de motor: defensa | 2016 | `robo-uso-vehiculo-motor-defensa-871` |

### Solicitudes y escritos de trámite (1)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 378 | Usurpación de inmueble: pedir que se suspenda el desahucio | 2021 | `usurpacion-inmueble-pedir-suspenda-desahucio-378` |

## Qué hay dentro de cada skill

- `SKILL.md`: los datos que hay que pedir, las elecciones, los párrafos opcionales, los avisos de la revisión, las normas que hay que comprobar y el flujo;
- `formulario.md`: el texto revisado del formulario;
- `marco.md`: la guía del tema, con las reglas y plazos vigentes comprobados en el BOE.

## Uso interno

Plugin de uso interno. Antes de venderlo o dárselo a alumnos, hay que sustituir los textos por plantillas de redacción propia.
