# Delitos sexuales (LO 4/2023) · España

> Plugin de Claude Code `modelos-delitos-sexuales-espana` · **108 formularios** · área: Penal · revisado el 17-11-2026 · requiere Jurisprudenciator

## Para qué sirve

Sirve para los delitos contra la libertad sexual con la numeración vigente tras la LO 4/2023 (y la de la LO 10/2022 para hechos de esa época): agresión sexual y violación, delitos contra menores de 16 años, sextorsión, grooming, pornografía infantil y acoso sexual.

Cada formulario es una skill: Claude lo rellena contigo paso a paso y te entrega el escrito en Word, con las normas comprobadas en el BOE.

## Qué puedes hacer con él

Estos son los tipos de escrito que trae, con algunos ejemplos (la lista completa de los 108 está al final):

- **Conformidad** (11). Por ejemplo: Exposición de actos sexuales a menor de 16 años: conformidad de la defensa; Agresión sexual atenuada: conformidad de la defensa; Agresión sexual atenuada (LO 4/2023): conformidad de la defensa.
- **Recursos e impugnaciones** (19). Por ejemplo: Agresión sexual: casación contra la denegación de la revisión de condena; Violación: impugnación y oposición al recurso de casación; Violación (LO 4/2023): apelación contra la condena.
- **Querellas y denuncias** (24). Por ejemplo: Violación a menor de 16 años (LO 4/2023): querella; Agresión sexual a menor de 16 años (LO 4/2023): querella; Agresión sexual sin acceso carnal (LO 4/2023): querella.
- **Escritos de acusación** (24). Por ejemplo: Agresión sexual a menor de 16 años, art. 181.2 CP (LO 4/2023): calificación del acusador particular; Violación bajo sumisión química: calificación provisional de la acusación; Violación a menor de 16 años por sextorsión (LO 4/2023): calificación del acusador particular.
- **Escritos de defensa** (26). Por ejemplo: Agresión sexual atenuada a menor de 16 años (LO 4/2023): escrito de defensa; Agresión sexual a menor de 16 años: calificación de la defensa alegando consentimiento; Violación por internet (sextorsión, LO 4/2023): calificación provisional de la defensa.
- **Solicitudes y escritos de trámite** (4). Por ejemplo: Agresión sexual: pedir revisión de la pena con la casación ya interpuesta; Agresión sexual: la defensa modifica su calificación para pedir rebaja de pena; Agresión sexual: pedir en ejecutoria la revisión de la pena.

## Cómo se usa

1. **Pídelo con tus palabras.** Cuéntale a Claude qué escrito necesitas y para qué caso; él elige el formulario. Por ejemplo:
   - «Querella por agresión sexual a un menor de 16 años»
   - «Escrito de defensa por acoso sexual»
   - «Escrito de acusación por child grooming»
2. **Si no da con el formulario**, empieza por el índice del plugin: escribe `/modelos-delitos-sexuales-espana:indice` y cuéntale lo que necesitas. Te propondrá el formulario que mejor encaja (o dos o tres para que elijas).
3. **Si ya sabes cuál quieres**, llámalo por su nombre de skill, por ejemplo `/modelos-delitos-sexuales-espana:agresion-sexual-casacion-contra-denegacion-revision-79`. Los nombres están en la lista de formularios de abajo.

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
- **Espacio que ocupa:** unos 9.000 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable modelos-delitos-sexuales-espana@plugins-dv`).

## Instalación

Solo la primera vez, añade el catálogo de plugins (sirve para todos). Cambia la ruta por la carpeta donde esté el catálogo (la que contiene `.claude-plugin`); si es un zip, descomprímelo antes en una ruta corta, porque hay nombres de archivo largos:

```bash
claude plugin marketplace add "C:\plugins-dv"
```

Después, instala este plugin:

```bash
claude plugin install modelos-delitos-sexuales-espana@plugins-dv
```

En la pestaña Code de la app de Claude también puedes pedírselo a Claude con esas palabras: «instala el plugin modelos-delitos-sexuales-espana del catálogo plugins-dv que está en C:\plugins-dv». Al terminar, abre una conversación nueva para que aparezcan sus skills.

## Lista de formularios

Para usar uno directamente: `/modelos-delitos-sexuales-espana:<skill>`.

### Conformidad (11)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 170 | Exposición de actos sexuales a menor de 16 años: conformidad de la defensa | 2022 | `exposicion-actos-sexuales-menor-16-anos-conformidad-170` |
| 182 | Agresión sexual atenuada: conformidad de la defensa | 2022 | `agresion-sexual-atenuada-conformidad-defensa-182` |
| 185 | Agresión sexual atenuada (LO 4/2023): conformidad de la defensa | 2022 | `agresion-sexual-atenuada-lo-4-2023-conformidad-defensa-185` |
| 210 | Child grooming (acoso a menores por TIC con fines sexuales): conformidad de la defensa | 2022 | `child-grooming-acoso-menores-tic-fines-sexuales-210` |
| 223 | Acoso callejero o piropo soez (trato degradante sexual): conformidad de la defensa | 2022 | `acoso-callejero-piropo-soez-trato-degradante-sexual-223` |
| 299 | Promover por internet delitos sexuales contra menores o discapacitados: conformidad de la defensa | 2021 | `promover-internet-delitos-sexuales-contra-menores-299` |
| 567 | Corrupción de menores o personas con discapacidad por medios tecnológicos: defensa con conformidad | 2018 | `corrupcion-menores-personas-discapacidad-medios-567` |
| 571 | Utilizar menores o personas con discapacidad en pornografía por internet: defensa con conformidad | 2018 | `utilizar-menores-personas-discapacidad-pornografia-571` |
| 597 | Distribución de pornografía a menores o personas con discapacidad: defensa con conformidad | 2018 | `distribucion-pornografia-menores-personas-discapacidad-597` |
| 610 | Exhibicionismo ante menor o persona con discapacidad en redes sociales: defensa con conformidad | 2018 | `exhibicionismo-ante-menor-persona-discapacidad-redes-610` |
| 823 | Acoso sexual: defensa con conformidad | 2016 | `acoso-sexual-defensa-conformidad-823` |

### Recursos e impugnaciones (19)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 79 | Agresión sexual: casación contra la denegación de la revisión de condena | 2023 | `agresion-sexual-casacion-contra-denegacion-revision-79` |
| 143 | Violación: impugnación y oposición al recurso de casación | 2023 | `violacion-impugnacion-oposicion-recurso-casacion-143` |
| 174 | Exposición de actos sexuales a menor de 16 años: apelación contra la condena | 2022 | `exposicion-actos-sexuales-menor-16-anos-apelacion-contra-174` |
| 184 | Agresión sexual atenuada: apelación contra la condena | 2022 | `agresion-sexual-atenuada-apelacion-contra-condena-184` |
| 188 | Agresión sexual atenuada (LO 4/2023): apelación contra la condena | 2022 | `agresion-sexual-atenuada-lo-4-2023-apelacion-contra-188` |
| 191 | Violación (LO 4/2023): apelación contra la condena | 2022 | `violacion-lo-4-2023-apelacion-contra-condena-191` |
| 192 | Violación por internet (sextorsión, LO 4/2023): apelación contra la condena | 2022 | `violacion-internet-sextorsion-lo-4-2023-apelacion-contra-192` |
| 196 | Violación a menor de 16 años por sextorsión (LO 4/2023): apelación contra la condena | 2022 | `violacion-menor-16-anos-sextorsion-lo-4-2023-apelacion-196` |
| 201 | Violación: apelación contra la condena | 2022 | `violacion-apelacion-contra-condena-201` |
| 207 | Violación por internet (sextorsión): apelación contra la condena | 2022 | `violacion-internet-sextorsion-apelacion-contra-condena-207` |
| 211 | Child grooming (acoso a menores por TIC con fines sexuales): apelación contra la condena | 2022 | `child-grooming-acoso-menores-tic-fines-sexuales-211` |
| 214 | Agresión sexual a menor de 16 años por internet (sextorsión): apelación contra la condena | 2022 | `agresion-sexual-menor-16-anos-internet-sextorsion-214` |
| 225 | Acoso callejero o piropo soez (trato degradante sexual): apelación contra la condena | 2022 | `acoso-callejero-piropo-soez-trato-degradante-sexual-225` |
| 305 | Promover por internet delitos sexuales contra menores o discapacitados: apelación contra la condena | 2021 | `promover-internet-delitos-sexuales-contra-menores-305` |
| 566 | Apelación contra la condena por corrupción de menores o con discapacidad por medios tecnológicos | 2018 | `apelacion-contra-condena-corrupcion-menores-discapacidad-566` |
| 569 | Apelación contra la condena por utilizar menores o con discapacidad en pornografía por internet | 2018 | `apelacion-contra-condena-utilizar-menores-discapacidad-569` |
| 599 | Apelación contra la condena por distribuir pornografía a menores o personas con discapacidad | 2018 | `apelacion-contra-condena-distribuir-pornografia-menores-599` |
| 607 | Apelación contra la condena por exhibicionismo ante menor o persona con discapacidad | 2018 | `apelacion-contra-condena-exhibicionismo-ante-menor-607` |
| 819 | Apelación contra la condena por acoso sexual | 2016 | `apelacion-contra-condena-acoso-sexual-819` |

### Querellas y denuncias (24)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 86 | Violación a menor de 16 años (LO 4/2023): querella | 2023 | `violacion-menor-16-anos-lo-4-2023-querella-86` |
| 90 | Agresión sexual a menor de 16 años (LO 4/2023): querella | 2023 | `agresion-sexual-menor-16-anos-lo-4-2023-querella-90` |
| 93 | Agresión sexual sin acceso carnal (LO 4/2023): querella | 2023 | `agresion-sexual-sin-acceso-carnal-lo-4-2023-querella-93` |
| 172 | Exposición de actos sexuales a menor de 16 años: querella | 2022 | `exposicion-actos-sexuales-menor-16-anos-querella-172` |
| 178 | Violación bajo sumisión química: querella | 2022 | `violacion-bajo-sumision-quimica-querella-178` |
| 183 | Agresión sexual atenuada: querella | 2022 | `agresion-sexual-atenuada-querella-183` |
| 186 | Agresión sexual atenuada (LO 4/2023): querella | 2022 | `agresion-sexual-atenuada-lo-4-2023-querella-186` |
| 193 | Violación por internet (sextorsión, LO 4/2023): querella | 2022 | `violacion-internet-sextorsion-lo-4-2023-querella-193` |
| 198 | Violación a menor de 16 años por sextorsión (LO 4/2023): querella | 2022 | `violacion-menor-16-anos-sextorsion-lo-4-2023-querella-198` |
| 205 | Violación por internet (sextorsión): querella | 2022 | `violacion-internet-sextorsion-querella-205` |
| 206 | Child grooming (acoso a menores por TIC con fines sexuales): querella | 2022 | `child-grooming-acoso-menores-tic-fines-sexuales-querella-206` |
| 212 | Agresión sexual a menor de 16 años por internet (sextorsión): querella | 2022 | `agresion-sexual-menor-16-anos-internet-sextorsion-212` |
| 216 | Violación (LO 4/2023): querella | 2022 | `violacion-lo-4-2023-querella-216` |
| 218 | Violación: querella | 2022 | `violacion-querella-218` |
| 220 | Violación: denuncia | 2022 | `violacion-denuncia-220` |
| 224 | Acoso callejero o piropo soez (trato degradante sexual): querella | 2022 | `acoso-callejero-piropo-soez-trato-degradante-sexual-224` |
| 300 | Promover por internet delitos sexuales contra menores o discapacitados: querella | 2021 | `promover-internet-delitos-sexuales-contra-menores-300` |
| 564 | Corrupción de menores o personas con discapacidad por medios tecnológicos: querella | 2018 | `corrupcion-menores-personas-discapacidad-medios-564` |
| 573 | Utilizar menores o personas con discapacidad en pornografía por internet: querella | 2018 | `utilizar-menores-personas-discapacidad-pornografia-573` |
| 600 | Distribución de pornografía a menores o personas con discapacidad: querella | 2018 | `distribucion-pornografia-menores-personas-discapacidad-600` |
| 609 | Exhibicionismo ante menor o persona con discapacidad en redes sociales: querella | 2018 | `exhibicionismo-ante-menor-persona-discapacidad-redes-609` |
| 822 | Acoso sexual: querella | 2016 | `acoso-sexual-querella-822` |
| 828 | Determinación a ejercer la prostitución: querella | 2016 | `determinacion-ejercer-prostitucion-querella-828` |
| 829 | Corrupción de menores: querella | 2016 | `corrupcion-menores-querella-829` |

### Escritos de acusación (24)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 87 | Violación a menor de 16 años (LO 4/2023): calificación provisional del acusador particular | 2023 | `violacion-menor-16-anos-lo-4-2023-calificacion-87` |
| 88 | Agresión sexual a menor de 16 años, art. 181.2 CP (LO 4/2023): calificación del acusador particular | 2023 | `agresion-sexual-menor-16-anos-art-181-2-cp-lo-4-2023-88` |
| 94 | Agresión sexual sin acceso carnal (LO 4/2023): escrito de acusación | 2023 | `agresion-sexual-sin-acceso-carnal-lo-4-2023-escrito-94` |
| 171 | Exposición de actos sexuales a menor de 16 años: escrito de acusación | 2022 | `exposicion-actos-sexuales-menor-16-anos-escrito-171` |
| 177 | Violación bajo sumisión química: calificación provisional de la acusación | 2022 | `violacion-bajo-sumision-quimica-calificacion-provisional-177` |
| 180 | Agresión sexual atenuada: escrito de acusación | 2022 | `agresion-sexual-atenuada-escrito-acusacion-180` |
| 187 | Agresión sexual atenuada (LO 4/2023): escrito de acusación | 2022 | `agresion-sexual-atenuada-lo-4-2023-escrito-acusacion-187` |
| 195 | Violación a menor de 16 años por sextorsión (LO 4/2023): calificación del acusador particular | 2022 | `violacion-menor-16-anos-sextorsion-lo-4-2023-195` |
| 197 | Violación por internet (sextorsión, LO 4/2023): calificación provisional del acusador particular | 2022 | `violacion-internet-sextorsion-lo-4-2023-calificacion-197` |
| 202 | Violación con agravante de convivencia: calificación provisional de la acusación | 2022 | `violacion-agravante-convivencia-calificacion-provisional-202` |
| 204 | Violación por internet (sextorsión): calificación provisional del acusador particular | 2022 | `violacion-internet-sextorsion-calificacion-provisional-204` |
| 209 | Child grooming (acoso a menores por TIC con fines sexuales): escrito de acusación | 2022 | `child-grooming-acoso-menores-tic-fines-sexuales-escrito-209` |
| 213 | Agresión sexual a menor de 16 años por internet (sextorsión): calificación del acusador particular | 2022 | `agresion-sexual-menor-16-anos-internet-sextorsion-213` |
| 217 | Violación (LO 4/2023): calificación provisional del acusador particular | 2022 | `violacion-lo-4-2023-calificacion-provisional-acusador-217` |
| 219 | Violación: calificación provisional del acusador particular | 2022 | `violacion-calificacion-provisional-acusador-particular-219` |
| 222 | Acoso callejero o piropo soez (trato degradante sexual): escrito de acusación | 2022 | `acoso-callejero-piropo-soez-trato-degradante-sexual-222` |
| 301 | Promover por internet delitos sexuales contra menores o discapacitados: escrito de acusación | 2021 | `promover-internet-delitos-sexuales-contra-menores-301` |
| 565 | Corrupción de menores o personas con discapacidad por medios tecnológicos: acusación | 2018 | `corrupcion-menores-personas-discapacidad-medios-565` |
| 570 | Utilizar menores o personas con discapacidad en pornografía por internet: acusación | 2018 | `utilizar-menores-personas-discapacidad-pornografia-570` |
| 598 | Distribución de pornografía a menores o personas con discapacidad: acusación | 2018 | `distribucion-pornografia-menores-personas-discapacidad-598` |
| 611 | Exhibicionismo ante menor o persona con discapacidad en redes sociales: acusación | 2018 | `exhibicionismo-ante-menor-persona-discapacidad-redes-611` |
| 820 | Acoso sexual: acusación | 2016 | `acoso-sexual-acusacion-820` |
| 826 | Determinación a ejercer la prostitución: acusación | 2016 | `determinacion-ejercer-prostitucion-acusacion-826` |
| 827 | Corrupción de menores: acusación | 2016 | `corrupcion-menores-acusacion-827` |

### Escritos de defensa (26)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 85 | Violación a menor de 16 años (LO 4/2023): calificación provisional de la defensa | 2023 | `violacion-menor-16-anos-lo-4-2023-calificacion-85` |
| 89 | Agresión sexual a menor de 16 años, art. 181.2 CP (LO 4/2023): calificación de la defensa | 2023 | `agresion-sexual-menor-16-anos-art-181-2-cp-lo-4-2023-89` |
| 91 | Agresión sexual atenuada a menor de 16 años (LO 4/2023): escrito de defensa | 2023 | `agresion-sexual-atenuada-menor-16-anos-lo-4-2023-escrito-91` |
| 92 | Agresión sexual sin acceso carnal (LO 4/2023): escrito de defensa | 2023 | `agresion-sexual-sin-acceso-carnal-lo-4-2023-escrito-92` |
| 173 | Exposición de actos sexuales a menor de 16 años: escrito de defensa | 2022 | `exposicion-actos-sexuales-menor-16-anos-escrito-defensa-173` |
| 175 | Agresión sexual a menor de 16 años (LO 4/2023): calificación de la defensa alegando consentimiento | 2022 | `agresion-sexual-menor-16-anos-lo-4-2023-calificacion-175` |
| 176 | Violación bajo sumisión química: calificación provisional de la defensa | 2022 | `violacion-bajo-sumision-quimica-calificacion-provisional-176` |
| 179 | Agresión sexual a menor de 16 años: calificación de la defensa alegando consentimiento | 2022 | `agresion-sexual-menor-16-anos-calificacion-defensa-179` |
| 181 | Agresión sexual atenuada: escrito de defensa | 2022 | `agresion-sexual-atenuada-escrito-defensa-181` |
| 189 | Agresión sexual atenuada (LO 4/2023): escrito de defensa | 2022 | `agresion-sexual-atenuada-lo-4-2023-escrito-defensa-189` |
| 190 | Violación (LO 4/2023): calificación provisional de la defensa | 2022 | `violacion-lo-4-2023-calificacion-provisional-defensa-190` |
| 194 | Violación por internet (sextorsión, LO 4/2023): calificación provisional de la defensa | 2022 | `violacion-internet-sextorsion-lo-4-2023-calificacion-194` |
| 199 | Violación a menor de 16 años por sextorsión (LO 4/2023): calificación provisional de la defensa | 2022 | `violacion-menor-16-anos-sextorsion-lo-4-2023-199` |
| 200 | Violación: calificación provisional de la defensa | 2022 | `violacion-calificacion-provisional-defensa-200` |
| 203 | Violación por internet (sextorsión): calificación provisional de la defensa | 2022 | `violacion-internet-sextorsion-calificacion-provisional-203` |
| 208 | Child grooming (acoso a menores por TIC con fines sexuales): escrito de defensa | 2022 | `child-grooming-acoso-menores-tic-fines-sexuales-escrito-208` |
| 215 | Agresión sexual a menor de 16 años por internet (sextorsión): calificación provisional de la defensa | 2022 | `agresion-sexual-menor-16-anos-internet-sextorsion-215` |
| 221 | Acoso callejero o piropo soez (trato degradante sexual): escrito de defensa | 2022 | `acoso-callejero-piropo-soez-trato-degradante-sexual-221` |
| 298 | Promover por internet delitos sexuales contra menores o discapacitados: escrito de defensa | 2021 | `promover-internet-delitos-sexuales-contra-menores-298` |
| 568 | Corrupción de menores o personas con discapacidad por medios tecnológicos: defensa | 2018 | `corrupcion-menores-personas-discapacidad-medios-568` |
| 572 | Utilizar menores o personas con discapacidad en pornografía por internet: defensa | 2018 | `utilizar-menores-personas-discapacidad-pornografia-572` |
| 601 | Distribución de pornografía a menores o personas con discapacidad: defensa | 2018 | `distribucion-pornografia-menores-personas-discapacidad-601` |
| 608 | Exhibicionismo ante menor o persona con discapacidad en redes sociales: defensa | 2018 | `exhibicionismo-ante-menor-persona-discapacidad-redes-608` |
| 821 | Acoso sexual: defensa | 2016 | `acoso-sexual-defensa-821` |
| 824 | Corrupción de menores: defensa | 2016 | `corrupcion-menores-defensa-824` |
| 825 | Determinación a ejercer la prostitución: defensa | 2016 | `determinacion-ejercer-prostitucion-defensa-825` |

### Solicitudes y escritos de trámite (4)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 144 | Agresión sexual: pedir revisión de la pena con la casación ya interpuesta | 2023 | `agresion-sexual-pedir-revision-pena-casacion-ya-144` |
| 145 | Agresión sexual: la defensa modifica su calificación para pedir rebaja de pena | 2023 | `agresion-sexual-defensa-modifica-calificacion-pedir-145` |
| 146 | Agresión sexual: pedir en ejecutoria la revisión de la pena | 2023 | `agresion-sexual-pedir-ejecutoria-revision-pena-146` |
| 147 | Agresión sexual: pedir revisión de la pena con la apelación ya interpuesta | 2023 | `agresion-sexual-pedir-revision-pena-apelacion-ya-147` |

## Qué hay dentro de cada skill

- `SKILL.md`: los datos que hay que pedir, las elecciones, los párrafos opcionales, los avisos de la revisión, las normas que hay que comprobar y el flujo;
- al final de ese mismo `SKILL.md`, el texto revisado del formulario.

La guía del tema, con las reglas y plazos vigentes comprobados en el BOE, es común a todas las skills del plugin y está en `skills/indice/marco.md`.

