# Ciberdelitos: phishing, criptoestafas y propiedad intelectual · España

> Plugin de Claude Code `modelos-ciberdelitos-espana` · **61 formularios** · área: Penal · revisado el 17-11-2026 · requiere Jurisprudenciator

## Para qué sirve

Sirve para fraudes y delitos informáticos: estafa informática (phishing, vishing, pharming), fraudes con criptomonedas, acceso ilegal a sistemas, daños informáticos y delitos contra la propiedad intelectual e industrial.

Cada formulario es una skill: Claude lo rellena contigo paso a paso y te entrega el escrito en Word, con las normas comprobadas en el BOE.

## Qué puedes hacer con él

Estos son los tipos de escrito que trae, con algunos ejemplos (la lista completa de los 61 está al final):

- **Conformidad** (10). Por ejemplo: Estafa con criptomonedas: conformidad de la defensa; Estafa informática (vishing): defensa con conformidad; Facilitar fraudulentamente el acceso a un servicio de radiodifusión: defensa con conformidad.
- **Recursos e impugnaciones** (12). Por ejemplo: Apelación contra la condena por estafa informática (vishing); Apelación contra la condena por facilitar fraudulentamente el acceso a un servicio de radiodifusión; Apelación contra la condena por falsificación de moneda con alta tecnología.
- **Querellas y denuncias** (13). Por ejemplo: Estafa informática (phishing) en cuenta bancaria: querella; Falsificación de moneda con alta tecnología: querella; Propiedad industrial por internet: querella.
- **Escritos de acusación** (12). Por ejemplo: Propiedad intelectual por internet: acusación; Acceso ilegal a sistemas informáticos (allanamiento o intrusismo): acusación; Pharming y estafa informática (phishing): acusación.
- **Escritos de defensa** (12). Por ejemplo: Daños informáticos (ciberataque): defensa; Suplantación de identidad en redes sociales (falsedad en documento privado): defensa; Estafa informática (phishing): defensa.
- **Solicitudes y escritos de trámite** (2). Por ejemplo: Avisar al banco de un crédito no formalizado por el cliente y del cargo de su cuota en cuenta; Estafa informática (phishing): pedir oficio al banco para identificar al autor.

## Cómo se usa

1. **Pídelo con tus palabras.** Cuéntale a Claude qué escrito necesitas y para qué caso; él elige el formulario. Por ejemplo:
   - «Denuncia por una estafa informática de phishing»
   - «Querella por acceso ilegal a un sistema informático»
   - «Escrito de acusación por un delito contra la propiedad intelectual en internet»
2. **Si no da con el formulario**, empieza por el índice del plugin: escribe `/modelos-ciberdelitos-espana:indice` y cuéntale lo que necesitas. Te propondrá el formulario que mejor encaja (o dos o tres para que elijas).
3. **Si ya sabes cuál quieres**, llámalo por su nombre de skill, por ejemplo `/modelos-ciberdelitos-espana:estafa-criptomonedas-escrito-defensa-131`. Los nombres están en la lista de formularios de abajo.

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
- **Espacio que ocupa:** unos 6.000 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable modelos-ciberdelitos-espana@plugins-dv`).

## Instalación

Solo la primera vez, añade el catálogo de plugins (sirve para todos). Cambia la ruta por la carpeta donde esté el catálogo (la que contiene `.claude-plugin`); si es un zip, descomprímelo antes en una ruta corta, porque hay nombres de archivo largos:

```bash
claude plugin marketplace add "C:\plugins-dv"
```

Después, instala este plugin:

```bash
claude plugin install modelos-ciberdelitos-espana@plugins-dv
```

En la pestaña Code de la app de Claude también puedes pedírselo a Claude con esas palabras: «instala el plugin modelos-ciberdelitos-espana del catálogo plugins-dv que está en C:\plugins-dv». Al terminar, abre una conversación nueva para que aparezcan sus skills.

## Lista de formularios

Para usar uno directamente: `/modelos-ciberdelitos-espana:<skill>`.

### Conformidad (10)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 132 | Estafa con criptomonedas: conformidad de la defensa | 2023 | `estafa-criptomonedas-conformidad-defensa-132` |
| 490 | Estafa informática (vishing): defensa con conformidad | 2019 | `estafa-informatica-vishing-defensa-conformidad-490` |
| 552 | Facilitar fraudulentamente el acceso a un servicio de radiodifusión: defensa con conformidad | 2018 | `facilitar-fraudulentamente-acceso-servicio-radiodifusion-552` |
| 621 | Propiedad industrial por internet: defensa con conformidad | 2018 | `propiedad-industrial-internet-defensa-conformidad-621` |
| 628 | Propiedad intelectual por internet: defensa con conformidad | 2018 | `propiedad-intelectual-internet-defensa-conformidad-628` |
| 629 | Acceso ilegal a sistemas informáticos (allanamiento o intrusismo): defensa con conformidad | 2018 | `acceso-ilegal-sistemas-informaticos-allanamiento-629` |
| 665 | Pharming y estafa informática (phishing): defensa con conformidad del scammer o del mulero | 2017 | `pharming-estafa-informatica-phishing-defensa-conformidad-665` |
| 680 | Daños informáticos (ciberataque): defensa con conformidad | 2017 | `danos-informaticos-ciberataque-defensa-conformidad-680` |
| 688 | Suplantación de identidad (falsedad en documento privado): defensa con conformidad | 2017 | `suplantacion-identidad-falsedad-documento-privado-688` |
| 876 | Propiedad intelectual: defensa con conformidad | 2016 | `propiedad-intelectual-defensa-conformidad-876` |

### Recursos e impugnaciones (12)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 133 | Estafa con criptomonedas: apelación contra la condena | 2023 | `estafa-criptomonedas-apelacion-contra-condena-133` |
| 491 | Apelación contra la condena por estafa informática (vishing) | 2019 | `apelacion-contra-condena-estafa-informatica-vishing-491` |
| 551 | Apelación contra la condena por facilitar fraudulentamente el acceso a un servicio de radiodifusión | 2018 | `apelacion-contra-condena-facilitar-fraudulentamente-551` |
| 605 | Apelación contra la condena por falsificación de moneda con alta tecnología | 2018 | `apelacion-contra-condena-falsificacion-moneda-alta-605` |
| 620 | Apelación contra la condena por delito contra la propiedad industrial por internet | 2018 | `apelacion-contra-condena-delito-contra-propiedad-620` |
| 625 | Apelación contra la condena por delito contra la propiedad intelectual por internet | 2018 | `apelacion-contra-condena-delito-contra-propiedad-625` |
| 630 | Apelación contra la condena por acceso ilegal a sistemas informáticos (allanamiento o intrusismo) | 2018 | `apelacion-contra-condena-acceso-ilegal-sistemas-630` |
| 668 | Pharming y estafa informática (phishing): apelación del scammer o del mulero contra la condena | 2017 | `pharming-estafa-informatica-phishing-apelacion-scammer-668` |
| 677 | Apelación contra la condena por daños informáticos (ciberataque) | 2017 | `apelacion-contra-condena-danos-informaticos-ciberataque-677` |
| 689 | Apelación contra la condena por falsedad en documento privado por suplantación en redes sociales | 2017 | `apelacion-contra-condena-falsedad-documento-privado-689` |
| 692 | Apelación contra la condena por estafa informática (phishing) | 2017 | `apelacion-contra-condena-estafa-informatica-phishing-692` |
| 875 | Apelación contra la condena por delito contra la propiedad intelectual | 2016 | `apelacion-contra-condena-delito-contra-propiedad-875` |

### Querellas y denuncias (13)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 134 | Estafa con criptomonedas: querella | 2023 | `estafa-criptomonedas-querella-134` |
| 434 | Estafa informática (phishing) en cuenta bancaria: querella | 2020 | `estafa-informatica-phishing-cuenta-bancaria-querella-434` |
| 492 | Estafa informática (vishing): querella | 2019 | `estafa-informatica-vishing-querella-492` |
| 555 | Facilitar fraudulentamente el acceso a un servicio de radiodifusión: querella | 2018 | `facilitar-fraudulentamente-acceso-servicio-radiodifusion-555` |
| 606 | Falsificación de moneda con alta tecnología: querella | 2018 | `falsificacion-moneda-alta-tecnologia-querella-606` |
| 623 | Propiedad industrial por internet: querella | 2018 | `propiedad-industrial-internet-querella-623` |
| 624 | Propiedad intelectual por internet: querella | 2018 | `propiedad-intelectual-internet-querella-624` |
| 633 | Acceso a sistemas informáticos sin autorización del titular (allanamiento o intrusismo): querella | 2018 | `acceso-sistemas-informaticos-sin-autorizacion-titular-633` |
| 666 | Pharming y estafa informática (phishing): querella | 2017 | `pharming-estafa-informatica-phishing-querella-666` |
| 678 | Daños informáticos (ciberataque): querella | 2017 | `danos-informaticos-ciberataque-querella-678` |
| 691 | Suplantación de identidad en redes sociales (falsedad en documento privado): denuncia | 2017 | `suplantacion-identidad-redes-sociales-falsedad-documento-691` |
| 696 | Estafa informática (phishing): denuncia | 2017 | `estafa-informatica-phishing-denuncia-696` |
| 848 | Tenencia de programas informáticos para falsificar tarjetas bancarias: querella | 2016 | `tenencia-programas-informaticos-falsificar-tarjetas-848` |

### Escritos de acusación (12)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 135 | Estafa con criptomonedas: escrito de acusación | 2023 | `estafa-criptomonedas-escrito-acusacion-135` |
| 493 | Estafa informática (vishing): acusación | 2019 | `estafa-informatica-vishing-acusacion-493` |
| 554 | Facilitar fraudulentamente el acceso a un servicio de radiodifusión: acusación | 2018 | `facilitar-fraudulentamente-acceso-servicio-radiodifusion-554` |
| 604 | Falsificación de moneda con alta tecnología: calificación provisional de la acusación particular | 2018 | `falsificacion-moneda-alta-tecnologia-calificacion-604` |
| 622 | Propiedad industrial por internet: acusación | 2018 | `propiedad-industrial-internet-acusacion-622` |
| 626 | Propiedad intelectual por internet: acusación | 2018 | `propiedad-intelectual-internet-acusacion-626` |
| 632 | Acceso ilegal a sistemas informáticos (allanamiento o intrusismo): acusación | 2018 | `acceso-ilegal-sistemas-informaticos-allanamiento-632` |
| 664 | Pharming y estafa informática (phishing): acusación | 2017 | `pharming-estafa-informatica-phishing-acusacion-664` |
| 679 | Daños informáticos (ciberataque): acusación | 2017 | `danos-informaticos-ciberataque-acusacion-679` |
| 690 | Suplantación de identidad en redes sociales (falsedad en documento privado): acusación | 2017 | `suplantacion-identidad-redes-sociales-falsedad-documento-690` |
| 693 | Estafa informática (phishing): acusación | 2017 | `estafa-informatica-phishing-acusacion-693` |
| 877 | Propiedad intelectual: acusación | 2016 | `propiedad-intelectual-acusacion-877` |

### Escritos de defensa (12)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 131 | Estafa con criptomonedas: escrito de defensa | 2023 | `estafa-criptomonedas-escrito-defensa-131` |
| 489 | Estafa informática (vishing): defensa | 2019 | `estafa-informatica-vishing-defensa-489` |
| 553 | Facilitar fraudulentamente el acceso a un servicio de radiodifusión: defensa | 2018 | `facilitar-fraudulentamente-acceso-servicio-radiodifusion-553` |
| 603 | Falsificación de moneda con alta tecnología: calificación provisional de la defensa | 2018 | `falsificacion-moneda-alta-tecnologia-calificacion-603` |
| 619 | Propiedad industrial por internet: defensa | 2018 | `propiedad-industrial-internet-defensa-619` |
| 627 | Propiedad intelectual por internet: defensa | 2018 | `propiedad-intelectual-internet-defensa-627` |
| 631 | Acceso ilegal a sistemas informáticos (allanamiento o intrusismo): defensa | 2018 | `acceso-ilegal-sistemas-informaticos-allanamiento-631` |
| 667 | Pharming y estafa informática (phishing): defensa del scammer o del mulero | 2017 | `pharming-estafa-informatica-phishing-defensa-scammer-667` |
| 676 | Daños informáticos (ciberataque): defensa | 2017 | `danos-informaticos-ciberataque-defensa-676` |
| 687 | Suplantación de identidad en redes sociales (falsedad en documento privado): defensa | 2017 | `suplantacion-identidad-redes-sociales-falsedad-documento-687` |
| 694 | Estafa informática (phishing): defensa | 2017 | `estafa-informatica-phishing-defensa-694` |
| 874 | Propiedad intelectual: defensa | 2016 | `propiedad-intelectual-defensa-874` |

### Solicitudes y escritos de trámite (2)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 695 | Estafa informática (phishing): pedir oficio al banco para identificar al autor | 2017 | `estafa-informatica-phishing-pedir-oficio-banco-695` |
| 849 | Avisar al banco de un crédito no formalizado por el cliente y del cargo de su cuota en cuenta | 2016 | `avisar-banco-credito-no-formalizado-cliente-cargo-cuota-849` |

## Qué hay dentro de cada skill

- `SKILL.md`: los datos que hay que pedir, las elecciones, los párrafos opcionales, los avisos de la revisión, las normas que hay que comprobar y el flujo;
- al final de ese mismo `SKILL.md`, el texto revisado del formulario.

La guía del tema, con las reglas y plazos vigentes comprobados en el BOE, es común a todas las skills del plugin y está en `skills/indice/marco.md`.

