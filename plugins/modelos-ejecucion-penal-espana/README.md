# Después de la condena: suspensión, refundición y prescripción · España

> Plugin de Claude Code `modelos-ejecucion-penal-espana` · **16 formularios** · área: Penal · revisado el 17-11-2026 · requiere Jurisprudenciator

## Para qué sirve

Sirve para la fase posterior a la condena: liquidación de condena, suspensión de la pena, prescripción, refundición, revisión por una ley penal más favorable, libertad vigilada, impago de la multa y decomiso.

Cada formulario es una skill: Claude lo rellena contigo paso a paso y te entrega el escrito en Word, con las normas comprobadas en el BOE.

## Qué puedes hacer con él

Estos son los tipos de escrito que trae, con algunos ejemplos (la lista completa de los 16 está al final):

- **Recursos e impugnaciones** (8). Por ejemplo: Ejecutoria penal: impugnar la liquidación de condena hecha por el LAJ; Suspensión de pena denegada: apelación pidiendo la excepcional (hasta el 2 de abril de 2025); Refundición de condenas: interponer recurso de casación.
- **Escritos de defensa** (1). Por ejemplo: Ejecutoria penal: alegaciones de la defensa del condenado.
- **Solicitudes y escritos de trámite** (6). Por ejemplo: Pedir la revisión de la condena por retroactividad de la norma penal más favorable; Impago de multa: suspender la responsabilidad personal subsidiaria (hasta el 2 de abril de 2025); Prescripción de la pena: petición del penado (hasta el 2 de abril de 2025).
- **Otros** (1). Por ejemplo: Decomiso: contestación a la demanda por tercero rebelde o que no pudo oponerse.

## Cómo se usa

1. **Pídelo con tus palabras.** Cuéntale a Claude qué escrito necesitas y para qué caso; él elige el formulario. Por ejemplo:
   - «Impugnar la liquidación de condena»
   - «Pedir la revisión de la condena por una ley penal más favorable»
   - «Pedir la modificación de la libertad vigilada»
2. **Si no da con el formulario**, empieza por el índice del plugin: escribe `/modelos-ejecucion-penal-espana:indice` y cuéntale lo que necesitas. Te propondrá el formulario que mejor encaja (o dos o tres para que elijas).
3. **Si ya sabes cuál quieres**, llámalo por su nombre de skill, por ejemplo `/modelos-ejecucion-penal-espana:ejecutoria-penal-impugnar-liquidacion-condena-hecha-laj-51`. Los nombres están en la lista de formularios de abajo.

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
- **Espacio que ocupa:** unos 1.000 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable modelos-ejecucion-penal-espana@modelos-juridicos-penal-espana`).

## Instalación

**En Claude Code**, añade una vez el catálogo de este repositorio y después instala el plugin:

```bash
claude plugin marketplace add DerechoVirtual/modelos-juridicos-penal-espana
claude plugin install modelos-ejecucion-penal-espana@modelos-juridicos-penal-espana
```

Al terminar, abre una conversación nueva para que aparezcan sus skills.

**En Claude (web y escritorio)** también puedes subirlo como ZIP desde **Personalizar → Plugins**. El ZIP de este plugin está en la página de versiones del repositorio: https://github.com/DerechoVirtual/modelos-juridicos-penal-espana/releases/latest

## Qué hay dentro de cada skill

- `SKILL.md`: los datos que hay que pedir, las elecciones, los párrafos opcionales, los avisos de la revisión, las normas que hay que comprobar y el flujo;
- al final de ese mismo `SKILL.md`, el texto revisado del formulario.

La guía del tema, con las reglas y plazos vigentes comprobados en el BOE, es común a todas las skills del plugin y está en `skills/indice/marco.md`.

## Lista completa de formularios

Cada formulario es una skill. Puedes pedirlo con tus palabras o llamarlo por su nombre (`/modelos-ejecucion-penal-espana:<skill>`). Son 16, agrupados por tipo de escrito:

- **Índice del plugin** (`indice`): te ayuda a elegir el formulario adecuado cuando no sabes cuál usar; le cuentas el caso y te propone uno, o dos o tres para que elijas.

### Recursos e impugnaciones (8)

- **Decomiso autónomo: apelación del tercero contra la sentencia condenatoria** (`decomiso-autonomo-apelacion-tercero-contra-sentencia-755`). Recurso de apelación del tercero afectado contra la sentencia condenatoria que acuerda un decomiso autónomo sobre bienes que le pertenecen, para pedir que se revoque o se limite el decomiso.
- **Decomiso en el proceso penal: apelación del tercero afectado contra la condena** (`decomiso-proceso-penal-apelacion-tercero-afectado-contra-760`). Recurso de apelación del tercero afectado por un decomiso acordado en el proceso penal contra la sentencia de condena, defendiendo su titularidad sobre los bienes y pidiendo que se deje sin efecto.
- **Ejecutoria penal: impugnar la liquidación de condena hecha por el LAJ** (`ejecutoria-penal-impugnar-liquidacion-condena-hecha-laj-51`). Recurso del penado en la ejecutoria penal para impugnar la liquidación de condena practicada por el letrado de la Administración de Justicia, pidiendo que se rectifique el cómputo de la pena.
- **Ejecutoria penal: reforma y subsidiario de apelación contra el auto que resuelve alegaciones** (`ejecutoria-penal-reforma-subsidiario-apelacion-contra-56`). Recurso de reforma y, subsidiariamente, de apelación contra el auto de ejecución penal que resuelve las alegaciones sobre la suspensión; exige revisar los antecedentes del penado por el cambio en el cómputo de delitos leves.
- **Ejecutoria penal: súplica contra el auto que resuelve alegaciones** (`ejecutoria-penal-suplica-contra-auto-resuelve-55`). Recurso de súplica contra el auto dictado en ejecución penal que resuelve las alegaciones sobre la suspensión de la pena; conviene revisar antes los antecedentes del penado por el cambio sobre condenas por delitos leves.
- **Refundición de condenas: interponer recurso de casación** (`refundicion-condenas-interponer-recurso-casacion-557`). Escrito del condenado para interponer recurso de casación contra el auto de refundición de condenas, con los motivos que fundamentan la impugnación y la petición de que se acuerde una refundición distinta.
- **Refundición de condenas: preparar la casación por infracción de ley** (`refundicion-condenas-preparar-casacion-infraccion-ley-561`). Escrito del condenado para preparar el recurso de casación por infracción de ley contra la resolución sobre refundición de condenas, anunciando los motivos y solicitando el testimonio necesario.
- **Suspensión de pena denegada: apelación pidiendo la excepcional (hasta el 2 de abril de 2025)** (`suspension-pena-denegada-apelacion-pidiendo-excepcional-100`). Recurso de apelación del penado contra la denegación de la suspensión de la pena, solicitando la suspensión excepcional; modelo para el régimen aplicable hasta el 2 de abril de 2025 y con antecedentes por revisar.

### Escritos de defensa (1)

- **Ejecutoria penal: alegaciones de la defensa del condenado** (`ejecutoria-penal-alegaciones-defensa-condenado-58`). Escrito de alegaciones de la defensa del condenado en la ejecutoria penal, por ejemplo sobre la suspensión o la sustitución de la pena, con revisión previa de sus antecedentes por el cambio sobre delitos leves.

### Solicitudes y escritos de trámite (6)

- **Decomiso autónomo: designar bienes para decomisar** (`decomiso-autonomo-designar-bienes-decomisar-756`). Escrito en un decomiso autónomo para designar los bienes concretos que se solicita decomisar, con su identificación y relación con el delito, dirigido al órgano que tramita el procedimiento.
- **Decomiso de bienes: pedir que se llame al proceso penal al tercero afectado** (`decomiso-bienes-pedir-llame-proceso-penal-tercero-761`). Escrito para pedir que se cite al proceso penal al tercero afectado por el decomiso de bienes, de modo que pueda defender sus derechos sobre ellos antes de que se acuerde la medida.
- **Impago de multa: suspender la responsabilidad personal subsidiaria (hasta el 2 de abril de 2025)** (`impago-multa-suspender-responsabilidad-personal-168`). Solicitud del condenado por impago de multa para que se suspenda la responsabilidad personal subsidiaria por falta de pago, ante el órgano de ejecución; modelo para el régimen aplicable hasta el 2 de abril de 2025.
- **Pedir la modificación de la libertad vigilada** (`pedir-modificacion-libertad-vigilada-759`). Solicitud para modificar las condiciones de la libertad vigilada impuesta al penado, ya sea para suprimir, sustituir o ajustar alguna de las obligaciones, ante el órgano de ejecución de la condena.
- **Pedir la revisión de la condena por retroactividad de la norma penal más favorable** (`pedir-revision-condena-retroactividad-norma-penal-mas-142`). Solicitud del penado para que se revise la sentencia condenatoria firme por haberse aprobado una norma penal más favorable con efecto retroactivo, pidiendo que se reduzca o deje sin efecto la pena.
- **Prescripción de la pena: petición del penado (hasta el 2 de abril de 2025)** (`prescripcion-pena-peticion-penado-hasta-2-abril-2025-384`). Escrito del penado en el que pide que se declare la prescripción de la pena impuesta y su cancelación, ante el órgano de ejecución; modelo para el régimen aplicable hasta el 2 de abril de 2025.

### Otros (1)

- **Decomiso: contestación a la demanda por tercero rebelde o que no pudo oponerse** (`decomiso-contestacion-demanda-tercero-rebelde-no-pudo-762`). Escrito de contestación a la demanda de decomiso presentado por el tercero que fue declarado rebelde o no pudo oponerse en su día, para defender sus derechos sobre los bienes afectados.
