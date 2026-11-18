# Calumnias, injurias, sexting y delitos de odio · España

> Plugin de Claude Code `modelos-injurias-intimidad-y-odio-espana` · **63 formularios** · área: Penal · revisado el 17-11-2026 · requiere Jurisprudenciator

## Para qué sirve

Sirve para delitos contra el honor y la intimidad y para delitos de odio: calumnias e injurias, difusión de imágenes íntimas (sexting), revelación de secretos, ciberacoso e incitación al odio.

Cada formulario es una skill: Claude lo rellena contigo paso a paso y te entrega el escrito en Word, con las normas comprobadas en el BOE.

## Qué puedes hacer con él

Estos son los tipos de escrito que trae, con algunos ejemplos (la lista completa de los 63 está al final):

- **Conformidad** (11). Por ejemplo: Uso de la imagen ajena sin consentimiento en medios de difusión pública: conformidad de la defensa; Acoso para obstaculizar el aborto: conformidad de la defensa; Asociación ilícita: conformidad de la defensa.
- **Recursos e impugnaciones** (13). Por ejemplo: Apelación contra la condena por revenge porn; Apelación contra la condena por humillación a víctimas del terrorismo por internet; Apelación contra la condena por delito contra la libertad de conciencia y sentimientos religiosos.
- **Querellas y denuncias** (13). Por ejemplo: Descubrimiento y revelación de secretos: querella; Revenge porn: denuncia ante la Fiscalía de Menores; Humillación a víctimas del terrorismo por internet (ciberterrorismo): querella.
- **Escritos de acusación** (12). Por ejemplo: Libertad de conciencia y sentimientos religiosos: acusación; Calumnia en redes sociales: acusación; Injurias graves en redes sociales: acusación.
- **Escritos de defensa** (12). Por ejemplo: Humillación a víctimas del terrorismo por internet: defensa; Incitación al odio en redes sociales: defensa; Denegación discriminatoria de una prestación empresarial o profesional: defensa.
- **Medidas cautelares y protección** (1). Por ejemplo: Sexting: la víctima pide la retirada provisional de contenidos de internet como medida cautelar.
- **Solicitudes y escritos de trámite** (1). Por ejemplo: Calumnias: el investigado pide probar la verdad de la imputación (exceptio veritatis).

## Cómo se usa

1. **Pídelo con tus palabras.** Cuéntale a Claude qué escrito necesitas y para qué caso; él elige el formulario. Por ejemplo:
   - «Querella por injurias graves en redes sociales»
   - «Querella por difusión de imágenes íntimas sin consentimiento»
   - «Escrito de acusación por incitación al odio en redes sociales»
2. **Si no da con el formulario**, empieza por el índice del plugin: escribe `/modelos-injurias-intimidad-y-odio-espana:indice` y cuéntale lo que necesitas. Te propondrá el formulario que mejor encaja (o dos o tres para que elijas).
3. **Si ya sabes cuál quieres**, llámalo por su nombre de skill, por ejemplo `/modelos-injurias-intimidad-y-odio-espana:calumnias-investigado-pide-probar-verdad-imputacion-98`. Los nombres están en la lista de formularios de abajo.

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
- **Espacio que ocupa:** unos 6.000 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable modelos-injurias-intimidad-y-odio-espana@plugins-dv`).

## Instalación

Solo la primera vez, añade el catálogo de plugins (sirve para todos). Cambia la ruta por la carpeta donde esté el catálogo (la que contiene `.claude-plugin`); si es un zip, descomprímelo antes en una ruta corta, porque hay nombres de archivo largos:

```bash
claude plugin marketplace add "C:\plugins-dv"
```

Después, instala este plugin:

```bash
claude plugin install modelos-injurias-intimidad-y-odio-espana@plugins-dv
```

En la pestaña Code de la app de Claude también puedes pedírselo a Claude con esas palabras: «instala el plugin modelos-injurias-intimidad-y-odio-espana del catálogo plugins-dv que está en C:\plugins-dv». Al terminar, abre una conversación nueva para que aparezcan sus skills.

## Lista de formularios

Para usar uno directamente: `/modelos-injurias-intimidad-y-odio-espana:<skill>`.

### Conformidad (11)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 226 | Uso de la imagen ajena sin consentimiento en medios de difusión pública: conformidad de la defensa | 2022 | `uso-imagen-ajena-sin-consentimiento-medios-difusion-226` |
| 255 | Acoso para obstaculizar el aborto: conformidad de la defensa | 2022 | `acoso-obstaculizar-aborto-conformidad-defensa-255` |
| 259 | Asociación ilícita: conformidad de la defensa | 2022 | `asociacion-ilicita-conformidad-defensa-259` |
| 517 | Revenge porn: pedir comparecencia para la conformidad | 2019 | `revenge-porn-pedir-comparecencia-conformidad-517` |
| 529 | Humillación a víctimas del terrorismo por internet: defensa con conformidad | 2018 | `humillacion-victimas-terrorismo-internet-defensa-529` |
| 642 | Libertad de conciencia y sentimientos religiosos: defensa con conformidad | 2017 | `libertad-conciencia-sentimientos-religiosos-defensa-642` |
| 648 | Calumnia en redes sociales: defensa con conformidad | 2017 | `calumnia-redes-sociales-defensa-conformidad-648` |
| 649 | Injurias graves con publicidad en redes sociales: defensa con conformidad | 2017 | `injurias-graves-publicidad-redes-sociales-defensa-649` |
| 655 | Incitación al odio en redes sociales: defensa con conformidad | 2017 | `incitacion-odio-redes-sociales-defensa-conformidad-655` |
| 663 | Denegación discriminatoria de una prestación empresarial o profesional: defensa con conformidad | 2017 | `denegacion-discriminatoria-prestacion-empresarial-663` |
| 673 | Ciberbullying: conformidad del letrado del menor con la acusación del fiscal | 2017 | `ciberbullying-conformidad-letrado-menor-acusacion-fiscal-673` |

### Recursos e impugnaciones (13)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 228 | Uso de la imagen ajena sin consentimiento en medios de difusión pública: apelación contra la condena | 2022 | `uso-imagen-ajena-sin-consentimiento-medios-difusion-228` |
| 254 | Acoso para obstaculizar el aborto: apelación contra la condena | 2022 | `acoso-obstaculizar-aborto-apelacion-contra-condena-254` |
| 260 | Asociación ilícita: apelación contra la condena | 2022 | `asociacion-ilicita-apelacion-contra-condena-260` |
| 514 | Apelación contra la condena por revenge porn | 2019 | `apelacion-contra-condena-revenge-porn-514` |
| 530 | Apelación contra la condena por humillación a víctimas del terrorismo por internet | 2018 | `apelacion-contra-condena-humillacion-victimas-terrorismo-530` |
| 639 | Apelación contra la condena por delito contra la libertad de conciencia y sentimientos religiosos | 2017 | `apelacion-contra-condena-delito-contra-libertad-639` |
| 647 | Apelación contra la condena por calumnia en redes sociales | 2017 | `apelacion-contra-condena-calumnia-redes-sociales-647` |
| 650 | Apelación contra la condena por injurias graves en redes sociales | 2017 | `apelacion-contra-condena-injurias-graves-redes-sociales-650` |
| 658 | Apelación contra la condena por incitación al odio en redes sociales | 2017 | `apelacion-contra-condena-incitacion-odio-redes-sociales-658` |
| 659 | Apelación contra la condena por denegación discriminatoria de prestación empresarial o profesional | 2017 | `apelacion-contra-condena-denegacion-discriminatoria-659` |
| 669 | Apelación contra la condena por ciberbullying | 2017 | `apelacion-contra-condena-ciberbullying-669` |
| 717 | Apelación contra la condena por sexting (difusión o redifusión inconsentida de imágenes) | 2017 | `apelacion-contra-condena-sexting-difusion-redifusion-717` |
| 718 | Apelación contra la absolución por sexting (difusión inconsentida de imágenes por internet) | 2017 | `apelacion-contra-absolucion-sexting-difusion-718` |

### Querellas y denuncias (13)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 237 | Uso de la imagen ajena sin consentimiento en medios de difusión pública: querella | 2022 | `uso-imagen-ajena-sin-consentimiento-medios-difusion-237` |
| 256 | Acoso para obstaculizar el aborto: querella | 2022 | `acoso-obstaculizar-aborto-querella-256` |
| 257 | Asociación ilícita: querella | 2022 | `asociacion-ilicita-querella-257` |
| 262 | Descubrimiento y revelación de secretos: querella | 2022 | `descubrimiento-revelacion-secretos-querella-262` |
| 515 | Revenge porn: denuncia ante la Fiscalía de Menores | 2019 | `revenge-porn-denuncia-ante-fiscalia-menores-515` |
| 528 | Humillación a víctimas del terrorismo por internet (ciberterrorismo): querella | 2018 | `humillacion-victimas-terrorismo-internet-ciberterrorismo-528` |
| 641 | Libertad de conciencia y sentimientos religiosos: querella | 2017 | `libertad-conciencia-sentimientos-religiosos-querella-641` |
| 646 | Calumnia en redes sociales: querella | 2017 | `calumnia-redes-sociales-querella-646` |
| 652 | Injurias graves en redes sociales: querella | 2017 | `injurias-graves-redes-sociales-querella-652` |
| 654 | Incitación al odio con publicidad en redes sociales: querella | 2017 | `incitacion-odio-publicidad-redes-sociales-querella-654` |
| 661 | Denegación discriminatoria de una prestación empresarial o profesional: querella | 2017 | `denegacion-discriminatoria-prestacion-empresarial-661` |
| 670 | Ciberbullying: denuncia ante la Fiscalía de Menores | 2017 | `ciberbullying-denuncia-ante-fiscalia-menores-670` |
| 721 | Sexting (difusión o redifusión inconsentida de imágenes por internet): querella | 2017 | `sexting-difusion-redifusion-inconsentida-imagenes-721` |

### Escritos de acusación (12)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 227 | Uso de la imagen ajena sin consentimiento en medios de difusión pública: escrito de acusación | 2022 | `uso-imagen-ajena-sin-consentimiento-medios-difusion-227` |
| 252 | Acoso para obstaculizar el aborto: escrito de acusación | 2022 | `acoso-obstaculizar-aborto-escrito-acusacion-252` |
| 261 | Asociación ilícita: escrito de acusación | 2022 | `asociacion-ilicita-escrito-acusacion-261` |
| 516 | Revenge porn: alegaciones de la acusación | 2019 | `revenge-porn-alegaciones-acusacion-516` |
| 527 | Humillación a víctimas del terrorismo por internet (ciberterrorismo): acusación | 2018 | `humillacion-victimas-terrorismo-internet-ciberterrorismo-527` |
| 640 | Libertad de conciencia y sentimientos religiosos: acusación | 2017 | `libertad-conciencia-sentimientos-religiosos-acusacion-640` |
| 645 | Calumnia en redes sociales: acusación | 2017 | `calumnia-redes-sociales-acusacion-645` |
| 653 | Injurias graves en redes sociales: acusación | 2017 | `injurias-graves-redes-sociales-acusacion-653` |
| 656 | Incitación al odio con publicidad en redes sociales: acusación | 2017 | `incitacion-odio-publicidad-redes-sociales-acusacion-656` |
| 662 | Denegación discriminatoria de una prestación empresarial o profesional: acusación | 2017 | `denegacion-discriminatoria-prestacion-empresarial-662` |
| 671 | Ciberbullying: alegaciones de la acusación particular | 2017 | `ciberbullying-alegaciones-acusacion-particular-671` |
| 675 | Sexting (difusión o redifusión inconsentida de imágenes por internet): acusación | 2017 | `sexting-difusion-redifusion-inconsentida-imagenes-675` |

### Escritos de defensa (12)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 229 | Uso de la imagen ajena sin consentimiento en medios de difusión pública: escrito de defensa | 2022 | `uso-imagen-ajena-sin-consentimiento-medios-difusion-229` |
| 253 | Acoso para obstaculizar el aborto: escrito de defensa | 2022 | `acoso-obstaculizar-aborto-escrito-defensa-253` |
| 258 | Asociación ilícita: escrito de defensa | 2022 | `asociacion-ilicita-escrito-defensa-258` |
| 513 | Revenge porn: alegaciones del letrado del menor acusado | 2019 | `revenge-porn-alegaciones-letrado-menor-acusado-513` |
| 526 | Humillación a víctimas del terrorismo por internet: defensa | 2018 | `humillacion-victimas-terrorismo-internet-defensa-526` |
| 643 | Libertad de conciencia y sentimientos religiosos: defensa | 2017 | `libertad-conciencia-sentimientos-religiosos-defensa-643` |
| 644 | Calumnia en redes sociales: defensa | 2017 | `calumnia-redes-sociales-defensa-644` |
| 651 | Injurias graves en redes sociales: defensa | 2017 | `injurias-graves-redes-sociales-defensa-651` |
| 657 | Incitación al odio en redes sociales: defensa | 2017 | `incitacion-odio-redes-sociales-defensa-657` |
| 660 | Denegación discriminatoria de una prestación empresarial o profesional: defensa | 2017 | `denegacion-discriminatoria-prestacion-empresarial-660` |
| 672 | Ciberbullying: alegaciones de la defensa del menor | 2017 | `ciberbullying-alegaciones-defensa-menor-672` |
| 674 | Sexting (difusión o redifusión inconsentida de imágenes por internet): defensa | 2017 | `sexting-difusion-redifusion-inconsentida-imagenes-674` |

### Medidas cautelares y protección (1)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 722 | Sexting: la víctima pide la retirada provisional de contenidos de internet como medida cautelar | 2017 | `sexting-victima-pide-retirada-provisional-contenidos-722` |

### Solicitudes y escritos de trámite (1)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 98 | Calumnias: el investigado pide probar la verdad de la imputación (exceptio veritatis) | 2023 | `calumnias-investigado-pide-probar-verdad-imputacion-98` |

## Qué hay dentro de cada skill

- `SKILL.md`: los datos que hay que pedir, las elecciones, los párrafos opcionales, los avisos de la revisión, las normas que hay que comprobar y el flujo;
- al final de ese mismo `SKILL.md`, el texto revisado del formulario.

La guía del tema, con las reglas y plazos vigentes comprobados en el BOE, es común a todas las skills del plugin y está en `skills/indice/marco.md`.

