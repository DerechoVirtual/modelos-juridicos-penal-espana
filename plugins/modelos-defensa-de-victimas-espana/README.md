# Acusación particular y derechos de la víctima · España

> Plugin de Claude Code `modelos-defensa-de-victimas-espana` · **54 formularios** · área: Penal · revisado el 17-11-2026 · requiere Jurisprudenciator

## Para qué sirve

Sirve para representar a la víctima: derechos del Estatuto de la víctima, acusación particular, declaración telemática y protección frente a los medios, prueba preconstituida de menores, mediación penal y justicia restaurativa.

Cada formulario es una skill: Claude lo rellena contigo paso a paso y te entrega el escrito en Word, con las normas comprobadas en el BOE.

## Qué puedes hacer con él

Estos son los tipos de escrito que trae, con algunos ejemplos (la lista completa de los 54 está al final):

- **Conformidad** (3). Por ejemplo: Acuerdo de reparación: el investigado pide remitir la causa a enjuiciamiento para conformarse; Víctima que se opone a la posible conformidad del acusado; Acuerdo de reparación: conformidad del acusado ante el órgano de enjuiciamiento.
- **Recursos e impugnaciones** (4). Por ejemplo: Sobreseimiento libre: reforma y subsidiaria apelación de la víctima; Beneficios penitenciarios sobre el límite de cumplimiento: reforma y apelación de la víctima; Libertad condicional del penado: reforma y apelación de la víctima.
- **Escritos de acusación** (1). Por ejemplo: Prueba preconstituida de menor o discapacitado: la acusación pide reproducirla en juicio.
- **Escritos de defensa** (1). Por ejemplo: Menor o discapacitado: la defensa propone que declare en el plenario.
- **Resoluciones, actas y documentos** (11). Por ejemplo: Mediación penal: traslado inicial del expediente a los letrados de las partes; Mediación penal: entrevista inicial informativa; Mediación penal: traslado del acuerdo a los letrados por el equipo de mediación.
- **Solicitudes y escritos de trámite** (33). Por ejemplo: Ejecutoria penal: el condenado pide la derivación a los servicios de justicia restaurativa; Menor afectado por un proceso penal: su representante pide que sea oído; Persona mayor de edad afectada por un proceso penal: pedir ser oída.
- **Otros** (1). Por ejemplo: Víctima: oponerse a la clasificación en tercer grado del penado.

## Cómo se usa

1. **Pídelo con tus palabras.** Cuéntale a Claude qué escrito necesitas y para qué caso; él elige el formulario. Por ejemplo:
   - «Pedir que la declaración de un menor de 14 años sea prueba preconstituida»
   - «Acuerdo de mediación penal por impago de pensiones»
   - «Petición de la acusación particular para derivar la causa a justicia restaurativa»
2. **Si no da con el formulario**, empieza por el índice del plugin: escribe `/modelos-defensa-de-victimas-espana:indice` y cuéntale lo que necesitas. Te propondrá el formulario que mejor encaja (o dos o tres para que elijas).
3. **Si ya sabes cuál quieres**, llámalo por su nombre de skill, por ejemplo `/modelos-defensa-de-victimas-espana:acuerdo-reparacion-investigado-pide-archivo-causa-penal-46`. Los nombres están en la lista de formularios de abajo.

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
- **Espacio que ocupa:** unos 5.000 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable modelos-defensa-de-victimas-espana@plugins-dv`).

## Instalación

Solo la primera vez, añade el catálogo de plugins (sirve para todos). Cambia la ruta por la carpeta donde esté el catálogo (la que contiene `.claude-plugin`); si es un zip, descomprímelo antes en una ruta corta, porque hay nombres de archivo largos:

```bash
claude plugin marketplace add "C:\plugins-dv"
```

Después, instala este plugin:

```bash
claude plugin install modelos-defensa-de-victimas-espana@plugins-dv
```

En la pestaña Code de la app de Claude también puedes pedírselo a Claude con esas palabras: «instala el plugin modelos-defensa-de-victimas-espana del catálogo plugins-dv que está en C:\plugins-dv». Al terminar, abre una conversación nueva para que aparezcan sus skills.

## Lista de formularios

Para usar uno directamente: `/modelos-defensa-de-victimas-espana:<skill>`.

### Conformidad (3)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 47 | Acuerdo de reparación: el investigado pide remitir la causa a enjuiciamiento para conformarse | 2025 | `acuerdo-reparacion-investigado-pide-remitir-causa-47` |
| 49 | Acuerdo de reparación: conformidad del acusado ante el órgano de enjuiciamiento | 2025 | `acuerdo-reparacion-conformidad-acusado-ante-organo-49` |
| 59 | Víctima que se opone a la posible conformidad del acusado | 2025 | `victima-opone-posible-conformidad-acusado-59` |

### Recursos e impugnaciones (4)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 773 | Sobreseimiento libre: reforma y subsidiaria apelación de la víctima | 2016 | `sobreseimiento-libre-reforma-subsidiaria-apelacion-773` |
| 780 | Beneficios penitenciarios sobre el límite de cumplimiento: reforma y apelación de la víctima | 2016 | `beneficios-penitenciarios-sobre-limite-cumplimiento-780` |
| 782 | Libertad condicional del penado: reforma y apelación de la víctima | 2016 | `libertad-condicional-penado-reforma-apelacion-victima-782` |
| 783 | Tercer grado del penado: reforma y apelación de la víctima | 2016 | `tercer-grado-penado-reforma-apelacion-victima-783` |

### Escritos de acusación (1)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 418 | Prueba preconstituida de menor o discapacitado: la acusación pide reproducirla en juicio | 2020 | `prueba-preconstituida-menor-discapacitado-acusacion-pide-418` |

### Escritos de defensa (1)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 419 | Menor o discapacitado: la defensa propone que declare en el plenario | 2020 | `menor-discapacitado-defensa-propone-declare-plenario-419` |

### Resoluciones, actas y documentos (11)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 723 | Mediación penal: traslado inicial del expediente a los letrados de las partes | 2017 | `mediacion-penal-traslado-inicial-expediente-letrados-723` |
| 724 | Mediación penal: entrevista inicial informativa | 2017 | `mediacion-penal-entrevista-inicial-informativa-724` |
| 725 | Mediación penal: traslado del acuerdo a los letrados por el equipo de mediación | 2017 | `mediacion-penal-traslado-acuerdo-letrados-equipo-725` |
| 726 | Mediación penal: oficio del mediador al juez sobre si hubo acuerdo | 2017 | `mediacion-penal-oficio-mediador-juez-sobre-si-hubo-726` |
| 727 | Mediación penal: ficha del expediente | 2017 | `mediacion-penal-ficha-expediente-727` |
| 729 | Mediación penal: citación del abogado mediador a los letrados de las partes | 2017 | `mediacion-penal-citacion-abogado-mediador-letrados-729` |
| 730 | Mediación penal: diligencia de ingreso de cantidad tras el acuerdo | 2017 | `mediacion-penal-diligencia-ingreso-cantidad-tras-acuerdo-730` |
| 731 | Mediación penal: acuerdo por hurto a un familiar | 2017 | `mediacion-penal-acuerdo-hurto-familiar-731` |
| 732 | Mediación penal: acuerdo con cambio de calificación jurídica de los hechos | 2017 | `mediacion-penal-acuerdo-cambio-calificacion-juridica-732` |
| 734 | Mediación penal: acuerdo por impago de pensiones | 2017 | `mediacion-penal-acuerdo-impago-pensiones-734` |
| 738 | Mediación penal: cuestionario del mediador al mediado y su valoración | 2016 | `mediacion-penal-cuestionario-mediador-mediado-valoracion-738` |

### Solicitudes y escritos de trámite (33)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 46 | Acuerdo de reparación: el investigado pide el archivo de la causa penal | 2025 | `acuerdo-reparacion-investigado-pide-archivo-causa-penal-46` |
| 48 | Ejecutoria penal: el condenado pide la derivación a los servicios de justicia restaurativa | 2025 | `ejecutoria-penal-condenado-pide-derivacion-servicios-48` |
| 50 | Ejecutoria penal: alegaciones de la víctima a la impugnación de la liquidación de condena | 2025 | `ejecutoria-penal-alegaciones-victima-impugnacion-50` |
| 57 | Ejecutoria penal: la víctima contesta a las alegaciones del condenado | 2025 | `ejecutoria-penal-victima-contesta-alegaciones-condenado-57` |
| 64 | Menor afectado por un proceso penal: su representante pide que sea oído | 2024 | `menor-afectado-proceso-penal-representante-pide-sea-oido-64` |
| 66 | Persona mayor de edad afectada por un proceso penal: pedir ser oída | 2024 | `persona-mayor-edad-afectada-proceso-penal-pedir-ser-oida-66` |
| 77 | Acusación particular: pedir que la víctima declare por vía telemática (desde el 20 de marzo de 2024) | 2024 | `acusacion-particular-pedir-victima-declare-via-77` |
| 274 | Delito contra menor: la acusación particular niega la prescripción (hasta el 2 de abril de 2025) | 2022 | `delito-contra-menor-acusacion-particular-niega-274` |
| 352 | Menor de 14 años: la acusación pide su declaración como prueba preconstituida | 2021 | `menor-14-anos-acusacion-pide-declaracion-como-prueba-352` |
| 353 | Menor o discapacitado: la acusación pide que no se le cite al juicio oral | 2021 | `menor-discapacitado-acusacion-pide-no-le-cite-juicio-353` |
| 354 | Víctima menor o discapacitada: videoconferencia en el juicio oral (hasta el 19 de marzo de 2024) | 2021 | `victima-menor-discapacitada-videoconferencia-juicio-oral-354` |
| 355 | Víctima o perjudicado: personarse después del escrito de acusación | 2021 | `victima-perjudicado-personarse-despues-escrito-acusacion-355` |
| 356 | Víctima o perjudicado: personarse después de la sentencia | 2021 | `victima-perjudicado-personarse-despues-sentencia-356` |
| 417 | Víctima menor pero mayor de 14 años: la acusación pide su declaración como prueba preconstituida | 2020 | `victima-menor-pero-mayor-14-anos-acusacion-pide-417` |
| 421 | Víctima: videoconferencia en juicio mixto telemático-presencial (hasta el 19 de marzo de 2024) | 2020 | `victima-videoconferencia-juicio-mixto-telematico-421` |
| 728 | Justicia restaurativa: el abogado de la acusación pide al mediador estar presente | 2017 | `justicia-restaurativa-abogado-acusacion-pide-mediador-728` |
| 733 | Pedir la suspensión de la pena aportando acuerdo de reparación (condenado) | 2017 | `pedir-suspension-pena-aportando-acuerdo-reparacion-733` |
| 739 | Justicia restaurativa: el investigado pide derivar la causa penal | 2016 | `justicia-restaurativa-investigado-pide-derivar-causa-739` |
| 740 | Justicia restaurativa: la acusación particular pide derivar la causa penal | 2016 | `justicia-restaurativa-acusacion-particular-pide-derivar-740` |
| 747 | Padres de víctima mayor de edad: personación como acusación particular | 2016 | `padres-victima-mayor-edad-personacion-como-acusacion-747` |
| 748 | Víctima: pedir su evaluación antes de adoptar medidas de protección | 2016 | `victima-pedir-evaluacion-antes-adoptar-medidas-748` |
| 749 | Víctima: pedir que se prohíba a los medios grabar el juicio o difundir información | 2016 | `victima-pedir-prohiba-medios-grabar-juicio-difundir-749` |
| 750 | Víctima: pedir la devolución de bienes concretos incautados | 2016 | `victima-pedir-devolucion-bienes-concretos-incautados-750` |
| 751 | Víctima: pedir ser reconocida por el médico forense | 2016 | `victima-pedir-ser-reconocida-medico-forense-751` |
| 752 | Víctima: pedir que el juicio se celebre a puerta cerrada | 2016 | `victima-pedir-juicio-celebre-puerta-cerrada-752` |
| 753 | Víctima: pedir la traducción de una resolución | 2016 | `victima-pedir-traduccion-resolucion-753` |
| 754 | Víctima: pedir ir acompañada en su declaración ante el juez | 2016 | `victima-pedir-ir-acompanada-declaracion-ante-juez-754` |
| 774 | Víctima: oponerse a la libertad condicional del penado | 2016 | `victima-oponerse-libertad-condicional-penado-774` |
| 775 | Víctima: anunciar que va a recurrir un auto | 2016 | `victima-anunciar-va-recurrir-auto-775` |
| 776 | Víctima: informar al juez sobre la ejecución de la pena, la responsabilidad civil o el comiso | 2016 | `victima-informar-juez-sobre-ejecucion-pena-776` |
| 778 | Víctima: oponerse a los beneficios penitenciarios del penado | 2016 | `victima-oponerse-beneficios-penitenciarios-penado-778` |
| 779 | Víctima: pedir reglas de conducta para el penado en libertad condicional | 2016 | `victima-pedir-reglas-conducta-penado-libertad-779` |
| 781 | Víctima: pedir ser notificada de las resoluciones del proceso (hasta el 6 de octubre de 2022) | 2016 | `victima-pedir-ser-notificada-resoluciones-proceso-hasta-781` |

### Otros (1)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 777 | Víctima: oponerse a la clasificación en tercer grado del penado | 2016 | `victima-oponerse-clasificacion-tercer-grado-penado-777` |

## Qué hay dentro de cada skill

- `SKILL.md`: los datos que hay que pedir, las elecciones, los párrafos opcionales, los avisos de la revisión, las normas que hay que comprobar y el flujo;
- `formulario.md`: el texto revisado del formulario;
- `marco.md`: la guía del tema, con las reglas y plazos vigentes comprobados en el BOE.

## Uso interno

Plugin de uso interno. Antes de venderlo o dárselo a alumnos, hay que sustituir los textos por plantillas de redacción propia.
