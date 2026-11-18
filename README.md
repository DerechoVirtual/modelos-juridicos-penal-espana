# Modelos jurídicos de España para Claude · Penal

18 plugins de modelos de escritos de Penal, uno por tema. Cada modelo es una skill que Claude rellena paso a paso con los datos del caso: 898 skills en total, más una skill `indice` por plugin para encontrar el modelo adecuado.

Todas las skills trabajan con **Jurisprudenciator** (https://jurisprudenciator.lexiaipro.org): antes de redactar comprueban que el conector responde, verifican en fuentes oficiales los artículos y la jurisprudencia que se citan y revisan el escrito con `verificar_escrito` antes de entregarlo. Sin Jurisprudenciator conectado, las skills no redactan.

Las demás jurisdicciones están en repositorios propios: [Administrativo](https://github.com/DerechoVirtual/modelos-juridicos-administrativo-espana), [Civil](https://github.com/DerechoVirtual/modelos-juridicos-civil-espana), [Laboral](https://github.com/DerechoVirtual/modelos-juridicos-laboral-espana).

## Instalación

En Claude Code:

```
/plugin marketplace add DerechoVirtual/modelos-juridicos-penal-espana
/plugin install modelos-ciberdelitos-espana@modelos-juridicos-penal-espana
```

Cada plugin ocupa contexto en la conversación, así que conviene instalar solo los de los temas con los que se trabaja.

En Claude (web y escritorio) también se puede subir cada plugin como ZIP desde **Personalizar → Plugins**. Los ZIP están en la página de [versiones](https://github.com/DerechoVirtual/modelos-juridicos-penal-espana/releases/latest): uno por plugin y [Penal.zip](https://github.com/DerechoVirtual/modelos-juridicos-penal-espana/releases/latest/download/Penal.zip) con todos.

## Plugins

| Plugin | Contenido | Skills | ZIP |
|---|---|---:|---|
| `modelos-ciberdelitos-espana` | Ciberdelitos: phishing, criptoestafas y propiedad intelectual · España | 62 | [descargar](https://github.com/DerechoVirtual/modelos-juridicos-penal-espana/releases/latest/download/modelos-ciberdelitos-espana.zip) |
| `modelos-defensa-de-victimas-espana` | Acusación particular y derechos de la víctima · España | 55 | [descargar](https://github.com/DerechoVirtual/modelos-juridicos-penal-espana/releases/latest/download/modelos-defensa-de-victimas-espana.zip) |
| `modelos-delitos-contra-las-personas-espana` | Lesiones, amenazas, coacciones y homicidio · España | 64 | [descargar](https://github.com/DerechoVirtual/modelos-juridicos-penal-espana/releases/latest/download/modelos-delitos-contra-las-personas-espana.zip) |
| `modelos-delitos-de-trafico-espana` | Alcoholemia, conducción sin carné y juicio rápido · España | 40 | [descargar](https://github.com/DerechoVirtual/modelos-juridicos-penal-espana/releases/latest/download/modelos-delitos-de-trafico-espana.zip) |
| `modelos-delitos-laborales-espana` | Delitos contra los trabajadores y riesgos laborales · España | 23 | [descargar](https://github.com/DerechoVirtual/modelos-juridicos-penal-espana/releases/latest/download/modelos-delitos-laborales-espana.zip) |
| `modelos-delitos-sexuales-espana` | Delitos sexuales (LO 4/2023) · España | 109 | [descargar](https://github.com/DerechoVirtual/modelos-juridicos-penal-espana/releases/latest/download/modelos-delitos-sexuales-espana.zip) |
| `modelos-drogas-y-maltrato-animal-espana` | Tráfico de drogas, petaqueo y maltrato animal · España | 22 | [descargar](https://github.com/DerechoVirtual/modelos-juridicos-penal-espana/releases/latest/download/modelos-drogas-y-maltrato-animal-espana.zip) |
| `modelos-ejecucion-penal-espana` | Después de la condena: suspensión, refundición y prescripción · España | 17 | [descargar](https://github.com/DerechoVirtual/modelos-juridicos-penal-espana/releases/latest/download/modelos-ejecucion-penal-espana.zip) |
| `modelos-estafas-robos-y-hurtos-espana` | Hurtos, robos, estafas y ocupación (LO 1/2026) · España | 84 | [descargar](https://github.com/DerechoVirtual/modelos-juridicos-penal-espana/releases/latest/download/modelos-estafas-robos-y-hurtos-espana.zip) |
| `modelos-euroorden-y-cooperacion-penal-espana` | Euroorden y cooperación penal en la UE · España | 34 | [descargar](https://github.com/DerechoVirtual/modelos-juridicos-penal-espana/releases/latest/download/modelos-euroorden-y-cooperacion-penal-espana.zip) |
| `modelos-fiscalia-europea-espana` | Procedimientos ante la Fiscalía Europea · España | 32 | [descargar](https://github.com/DerechoVirtual/modelos-juridicos-penal-espana/releases/latest/download/modelos-fiscalia-europea-espana.zip) |
| `modelos-injurias-intimidad-y-odio-espana` | Calumnias, injurias, sexting y delitos de odio · España | 64 | [descargar](https://github.com/DerechoVirtual/modelos-juridicos-penal-espana/releases/latest/download/modelos-injurias-intimidad-y-odio-espana.zip) |
| `modelos-instruccion-penal-espana` | Instrucción penal: diligencias, habeas corpus y detenido · España | 50 | [descargar](https://github.com/DerechoVirtual/modelos-juridicos-penal-espana/releases/latest/download/modelos-instruccion-penal-espana.zip) |
| `modelos-penal-economico-espana` | Blanqueo, delitos societarios y penal económico · España | 53 | [descargar](https://github.com/DerechoVirtual/modelos-juridicos-penal-espana/releases/latest/download/modelos-penal-economico-espana.zip) |
| `modelos-prevaricacion-y-malversacion-espana` | Prevaricación, malversación y denuncia falsa · España | 59 | [descargar](https://github.com/DerechoVirtual/modelos-juridicos-penal-espana/releases/latest/download/modelos-prevaricacion-y-malversacion-espana.zip) |
| `modelos-prueba-digital-penal-espana` | Prueba digital: intervenciones, volcados y nulidad · España | 29 | [descargar](https://github.com/DerechoVirtual/modelos-juridicos-penal-espana/releases/latest/download/modelos-prueba-digital-penal-espana.zip) |
| `modelos-recursos-penales-espana` | Reforma, apelación y casación penal · España | 25 | [descargar](https://github.com/DerechoVirtual/modelos-juridicos-penal-espana/releases/latest/download/modelos-recursos-penales-espana.zip) |
| `modelos-violencia-de-genero-espana` | Violencia de género, órdenes de protección e impago de pensiones · España | 76 | [descargar](https://github.com/DerechoVirtual/modelos-juridicos-penal-espana/releases/latest/download/modelos-violencia-de-genero-espana.zip) |

## Estructura

```
.claude-plugin/marketplace.json  catálogo del marketplace
plugins/<plugin>/                .claude-plugin/plugin.json, .mcp.json, skills/, README.md, PRIVACY.md, LICENSE
```

## Aviso

Los escritos que se generan son borradores que debe revisar un abogado; no constituyen asesoramiento jurídico. Las skills no guardan datos del cliente y las consultas a Jurisprudenciator describen el problema jurídico, no los datos personales.

Soporte: https://jurisprudenciator.lexiaipro.org/incidencias · Licencia: ver [LICENSE](LICENSE).
