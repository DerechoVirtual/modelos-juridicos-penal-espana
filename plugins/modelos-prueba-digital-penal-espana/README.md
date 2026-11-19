# Prueba digital: intervenciones, volcados y nulidad · España

> Plugin de Claude Code `modelos-prueba-digital-penal-espana` · **28 formularios** · área: Penal · revisado el 17-11-2026 · requiere Jurisprudenciator

## Para qué sirve

Sirve para la prueba digital en el proceso penal: intervenciones telefónicas, volcado de dispositivos, prueba digital y pericial informática, comunicaciones entre abogados, y nulidad de la prueba obtenida ilícitamente.

Cada formulario es una skill: Claude lo rellena contigo paso a paso y te entrega el escrito en Word, con las normas comprobadas en el BOE.

## Qué puedes hacer con él

Estos son los tipos de escrito que trae, con algunos ejemplos (la lista completa de los 28 está al final):

- **Recursos e impugnaciones** (1). Por ejemplo: Apelación contra una condena basada en prueba ilícita.
- **Escritos de acusación** (1). Por ejemplo: Prueba digital y pericial informática: propuesta en el escrito de acusación.
- **Escritos de defensa** (3). Por ejemplo: Nulidad de las intervenciones telefónicas: defensa; Tráfico de drogas con intervenciones telefónicas nulas: defensa; Impugnar una prueba digital en el escrito de defensa.
- **Resoluciones, actas y documentos** (1). Por ejemplo: Computación en la nube (cloud computing): contrato de acceso a datos por cuenta de terceros.
- **Solicitudes y escritos de trámite** (22). Por ejemplo: Prueba ilícita: el acusado pide audiencia preliminar (antes y después del 3 de abril de 2025); Intervenciones telefónicas: negarse a dar al juez el patrón del móvil para el volcado; Excluir del proceso las comunicaciones entre abogados defensores aportadas sin autorización.

## Cómo se usa

1. **Pídelo con tus palabras.** Cuéntale a Claude qué escrito necesitas y para qué caso; él elige el formulario. Por ejemplo:
   - «Pedir la nulidad de las intervenciones telefónicas»
   - «Impugnar una prueba digital en el escrito de defensa»
   - «Aportar como prueba un acta notarial del contenido de una web»
2. **Si no da con el formulario**, empieza por el índice del plugin: escribe `/modelos-prueba-digital-penal-espana:indice` y cuéntale lo que necesitas. Te propondrá el formulario que mejor encaja (o dos o tres para que elijas).
3. **Si ya sabes cuál quieres**, llámalo por su nombre de skill, por ejemplo `/modelos-prueba-digital-penal-espana:prueba-ilicita-acusado-pide-audiencia-preliminar-antes-60`. Los nombres están en la lista de formularios de abajo.

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

- **Dónde funciona:** en Claude Code y en Claude (web, escritorio y Cowork).
- **Jurisprudenciator es imprescindible:** el plugin trae el conector y cada skill trabaja siempre con él, igual que los plugins de Jurisprudenciator del directorio de Claude. Sin una cuenta de Jurisprudenciator conectada, las skills se paran y no redactan nada. La primera vez hay que iniciar sesión (en Claude Code, con `/mcp`; o con tu URL personal: https://jurisprudenciator.lexiaipro.org/instalacion). Si ya tienes Jurisprudenciator conectado en Claude, las skills usan ese.
- **Espacio que ocupa:** unos 3.000 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable modelos-prueba-digital-penal-espana@modelos-juridicos-penal-espana`).

## Instalación

**En Claude Code**, añade una vez el catálogo de este repositorio y después instala el plugin:

```bash
claude plugin marketplace add DerechoVirtual/modelos-juridicos-penal-espana
claude plugin install modelos-prueba-digital-penal-espana@modelos-juridicos-penal-espana
```

Al terminar, abre una conversación nueva para que aparezcan sus skills.

**En Claude (web y escritorio)** también puedes subirlo como ZIP desde **Personalizar → Plugins**. El ZIP de este plugin está en la página de versiones del repositorio: https://github.com/DerechoVirtual/modelos-juridicos-penal-espana/releases/latest

## Qué hay dentro de cada skill

- `SKILL.md`: los datos que hay que pedir, las elecciones, los párrafos opcionales, los avisos de la revisión, las normas que hay que comprobar y el flujo;
- al final de ese mismo `SKILL.md`, el texto revisado del formulario.

La guía del tema, con las reglas y plazos vigentes comprobados en el BOE, es común a todas las skills del plugin y está en `skills/indice/marco.md`.

## Lista completa de formularios

Cada formulario es una skill. Puedes pedirlo con tus palabras o llamarlo por su nombre (`/modelos-prueba-digital-penal-espana:<skill>`). Son 28, agrupados por tipo de escrito:

- **Índice del plugin** (`indice`): te ayuda a elegir el formulario adecuado cuando no sabes cuál usar; le cuentas el caso y te propone uno, o dos o tres para que elijas.

### Recursos e impugnaciones (1)

- **Apelación contra una condena basada en prueba ilícita** (`apelacion-contra-condena-basada-prueba-ilicita-701`). Recurso de apelación contra una sentencia condenatoria que se apoya en prueba ilícita, para pedir su nulidad y la absolución del condenado al no poder valorarse las pruebas obtenidas con vulneración de derechos.

### Escritos de acusación (1)

- **Prueba digital y pericial informática: propuesta en el escrito de acusación** (`prueba-digital-pericial-informatica-propuesta-escrito-703`). Sirve para que la acusación proponga, dentro de su escrito de acusación, prueba digital y pericial informática, indicando qué soportes y qué peritos se solicitan para acreditar los hechos.

### Escritos de defensa (3)

- **Impugnar una prueba digital en el escrito de defensa** (`impugnar-prueba-digital-escrito-defensa-704`). Escrito de defensa para impugnar la prueba digital (mensajes, correos, capturas o archivos) propuesta por la acusación, cuestionando su autenticidad, integridad o licitud y pidiendo que no se admita o no se valore.
- **Nulidad de las intervenciones telefónicas: defensa** (`nulidad-intervenciones-telefonicas-defensa-562`). Escrito de defensa que pide declarar nula la intervención de las comunicaciones telefónicas por falta de motivación o de base suficiente, y excluir de la causa las pruebas que de ella derivan.
- **Tráfico de drogas con intervenciones telefónicas nulas: defensa** (`trafico-drogas-intervenciones-telefonicas-nulas-defensa-563`). Escrito de defensa en una causa por tráfico de drogas cuya prueba nace de intervenciones telefónicas nulas, para pedir que se excluyan y se absuelva al acusado por falta de prueba lícita.

### Resoluciones, actas y documentos (1)

- **Computación en la nube (cloud computing): contrato de acceso a datos por cuenta de terceros** (`computacion-nube-cloud-computing-contrato-acceso-datos-735`). Contrato por el que el responsable del tratamiento de datos personales encarga a un proveedor de computación en la nube el acceso a esos datos por su cuenta, con las obligaciones propias del encargado del tratamiento.

### Solicitudes y escritos de trámite (22)

- **Aportar como prueba comunicaciones o documentos entre defensores con autorización** (`aportar-como-prueba-comunicaciones-documentos-entre-68`). Escrito por el que un abogado aporta como prueba en la instrucción las comunicaciones o documentos que intercambió con el letrado contrario en otro procedimiento, al contar con autorización para utilizarlos.
- **Deducir testimonio por posible delito hallado en correspondencia o correo electrónico intervenidos** (`deducir-testimonio-posible-delito-hallado-711`). Escrito para pedir al juez que deduzca testimonio cuando en la correspondencia o el correo electrónico intervenidos aparece un posible delito distinto, de modo que se abra otro procedimiento para investigarlo.
- **Defensa: pedir la nulidad de la prueba digital aportada** (`defensa-pedir-nulidad-prueba-digital-aportada-705`). Escrito de la defensa para pedir la nulidad de la prueba digital aportada por la acusación o el querellante, por vulnerar derechos fundamentales o carecer de garantías de autenticidad e integridad.
- **Excluir del proceso las comunicaciones entre abogados defensores aportadas sin autorización** (`excluir-proceso-comunicaciones-entre-abogados-defensores-65`). Escrito presentado en la instrucción por el que un abogado pide excluir del proceso las comunicaciones o documentos intercambiados con el letrado contrario en otro procedimiento, por no existir autorización para usarlos.
- **Grabaciones y transcripciones intervenidas: pedir que se incluya información** (`grabaciones-transcripciones-intervenidas-pedir-incluya-765`). Escrito para solicitar al juez que se incluya determinada información en las grabaciones y transcripciones de las comunicaciones intervenidas, de modo que consten completas en la causa.
- **Grabaciones y transcripciones intervenidas: retirar lo que afecte a la vida privada** (`grabaciones-transcripciones-intervenidas-retirar-lo-766`). Escrito para pedir al juez que se retire o excluya de las grabaciones y transcripciones intervenidas aquello que afecte a la vida privada y no guarde relación con la investigación.
- **Intervenciones telefónicas: negarse a dar al juez el patrón del móvil para el volcado** (`intervenciones-telefonicas-negarse-dar-juez-patron-movil-61`). Escrito para oponerse a entregar al juez el patrón de desbloqueo del móvil con fines de volcado, alegando que falta base suficiente de investigación y que se trata de una diligencia derivada de prueba ilícita.
- **Pedir al fiscal que solicite al juez intervenir la correspondencia del investigado** (`pedir-fiscal-solicite-juez-intervenir-correspondencia-764`). Escrito para pedir al fiscal que solicite al juez la intervención de la correspondencia del investigado, exponiendo los indicios y la necesidad de la medida.
- **Pedir al fiscal que solicite al juez intervenir las comunicaciones** (`pedir-fiscal-solicite-juez-intervenir-comunicaciones-763`). Escrito para pedir al fiscal que solicite al juez la intervención de las comunicaciones de un investigado, con la exposición de los indicios que justifican la medida.
- **Pedir datos de comunicaciones electrónicas para averiguar un delito** (`pedir-datos-comunicaciones-electronicas-averiguar-delito-713`). Solicitud al juez de instrucción para que se requieran datos de comunicaciones electrónicas (tráfico, localización o titularidad) a los operadores, con el fin de averiguar un delito.
- **Pedir el registro remoto de equipos informáticos por delitos cometidos con ellos** (`pedir-registro-remoto-equipos-informaticos-delitos-712`). Solicitud al juez de instrucción de autorización para el registro remoto de equipos informáticos cuando se investigan delitos cometidos mediante ellos, con la justificación de la necesidad y proporcionalidad de la medida.
- **Pedir la apertura de la correspondencia ya intervenida** (`pedir-apertura-correspondencia-ya-intervenida-714`). Escrito para pedir al juez la apertura de la correspondencia que ya ha sido intervenida, para que se examine su contenido en la instrucción y se incorpore a la causa si resulta relevante.
- **Pedir la captación de imágenes del investigado o de su entorno en lugar público** (`pedir-captacion-imagenes-investigado-entorno-lugar-716`). Solicitud al juez de instrucción de autorización para captar imágenes del investigado o de su entorno en un lugar público, como diligencia de investigación en una causa penal.
- **Pedir la instalación de dispositivos técnicos de localización y seguimiento** (`pedir-instalacion-dispositivos-tecnicos-localizacion-715`). Solicitud al juez de instrucción de autorización para instalar dispositivos técnicos de localización y seguimiento del investigado, con la justificación de su necesidad y proporcionalidad.
- **Prueba ilícita: el acusado pide audiencia preliminar (antes y después del 3 de abril de 2025)** (`prueba-ilicita-acusado-pide-audiencia-preliminar-antes-60`). Escrito de la defensa del acusado para pedir una audiencia preliminar que resuelva si la prueba es ilícita antes del juicio oral, ya sea en el procedimiento abreviado o en el ordinario.
- **Querellado: impugnar la prueba digital (WhatsApp u otros) aportada en la instrucción** (`querellado-impugnar-prueba-digital-whatsapp-u-otros-709`). Escrito del querellado para impugnar la prueba digital, como WhatsApp u otros mensajes, que el querellante ha aportado en la instrucción, cuestionando su autenticidad, su integridad o su licitud.
- **Querellante: aportar acta notarial del contenido de una web como prueba preconstituida** (`querellante-aportar-acta-notarial-contenido-web-como-702`). Escrito del querellante para aportar, como prueba preconstituida, un acta notarial que recoge el contenido de una página web, con el fin de acreditar los hechos denunciados en la instrucción.
- **Querellante: aportar prueba digital en la instrucción** (`querellante-aportar-prueba-digital-instruccion-708`). Escrito del querellante para aportar en la fase de instrucción pruebas digitales (mensajes, correos, archivos o capturas) que acrediten los hechos denunciados, con los datos de su obtención.
- **Querellante: pedir que se reproduzca una grabación y aportarla como prueba preconstituida** (`querellante-pedir-reproduzca-grabacion-aportarla-como-706`). Escrito del querellante para que se reproduzca en sede judicial una grabación y se aporte como prueba preconstituida, de modo que quede asegurada su validez y su contenido para el juicio.
- **Querellante: proponer o aportar pericial informática en instrucción ante prueba digital impugnada** (`querellante-proponer-aportar-pericial-informatica-707`). Escrito del querellante para proponer o aportar una pericial informática durante la instrucción cuando la parte contraria ha impugnado la prueba digital, con el fin de acreditar su autenticidad e integridad.
- **Sexting: pedir el registro de equipos informáticos para determinar la autoría** (`sexting-pedir-registro-equipos-informaticos-determinar-720`). Solicitud al juez de instrucción del registro de equipos informáticos en un caso de sexting para determinar quién es el autor de la difusión de las imágenes o contenidos íntimos.
- **Usar en otro proceso penal lo obtenido al intervenir correspondencia o comunicaciones** (`usar-otro-proceso-penal-lo-obtenido-intervenir-767`). Escrito para pedir autorización judicial para emplear en otro proceso penal lo obtenido al intervenir correspondencia o comunicaciones en una causa distinta, incorporándolo como prueba.
