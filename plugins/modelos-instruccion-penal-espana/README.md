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

- **Dónde funciona:** en Claude Code y en Claude (web, escritorio y Cowork).
- **Jurisprudenciator es imprescindible:** el plugin trae el conector y cada skill trabaja siempre con él, igual que los plugins de Jurisprudenciator del directorio de Claude. Sin una cuenta de Jurisprudenciator conectada, las skills se paran y no redactan nada. La primera vez hay que iniciar sesión (en Claude Code, con `/mcp`; o con tu URL personal: https://jurisprudenciator.lexiaipro.org/instalacion). Si ya tienes Jurisprudenciator conectado en Claude, las skills usan ese.
- **Espacio que ocupa:** unos 5.000 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable modelos-instruccion-penal-espana@modelos-juridicos-penal-espana`).

## Instalación

**En Claude Code**, añade una vez el catálogo de este repositorio y después instala el plugin:

```bash
claude plugin marketplace add DerechoVirtual/modelos-juridicos-penal-espana
claude plugin install modelos-instruccion-penal-espana@modelos-juridicos-penal-espana
```

Al terminar, abre una conversación nueva para que aparezcan sus skills.

**En Claude (web y escritorio)** también puedes subirlo como ZIP desde **Personalizar → Plugins**. El ZIP de este plugin está en la página de versiones del repositorio: https://github.com/DerechoVirtual/modelos-juridicos-penal-espana/releases/latest

## Qué hay dentro de cada skill

- `SKILL.md`: los datos que hay que pedir, las elecciones, los párrafos opcionales, los avisos de la revisión, las normas que hay que comprobar y el flujo;
- al final de ese mismo `SKILL.md`, el texto revisado del formulario.

La guía del tema, con las reglas y plazos vigentes comprobados en el BOE, es común a todas las skills del plugin y está en `skills/indice/marco.md`.

