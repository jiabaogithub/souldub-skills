# Video Translate Skill – Traducción de vídeo con IA, doblaje y subtítulos SRT [![Security: B — Skills Directory](https://www.skillsdirectory.com/api/skills/gravityvortex-souldub-video-translate/badge)](https://www.skillsdirectory.com/skills/gravityvortex-souldub-video-translate)

[English](README.md) | [简体中文](README.zh-CN.md) | [Español](README.es.md) | [ไทย](README.th.md)

<p align="center">
  <img src="cover-readme.png" alt="Video Translate Skill – portada de la skill de traducción de vídeo con SoulDub AI" width="760">
</p>

**Video Translate Skill** es un flujo de trabajo de traducción de vídeo impulsado por IA que traduce el audio hablado de tus vídeos a otro idioma, genera subtítulos SRT sincronizados, crea doblaje con texto a voz (TTS) y vuelve a integrar la nueva pista de audio en el vídeo, todo en un único proceso automatizado.

Está construido sobre **SoulDub AI** y traduce vídeos MP4 locales con **doblaje con voz original**, de modo que el doblaje conserva el carácter del hablante original. Cuando el procesamiento termina, puedes descargar:

- el **vídeo traducido**
- **subtítulos en el idioma de destino** (SRT)
- **subtítulos SRT bilingües**

---

## Tabla de contenido

- [¿Qué es Video Translate Skill?](#what-is-video-translate-skill)
- [Funciones](#features)
- [Instalación](#installation)
- [Requisitos](#requirements)
- [Uso](#usage)
- [Cómo funciona](#how-it-works)
- [Archivos de salida](#output-files)
- [Configuración y privacidad](#configuration--privacy)
- [Casos de uso](#use-cases)
- [FAQ](#faq)

---

<a name="what-is-video-translate-skill"></a>
## ¿Qué es Video Translate Skill?

Video Translate Skill es un **traductor de vídeo con IA** totalmente automatizado para creadores, educadores y equipos que necesitan contenido de vídeo multilingüe. En lugar de transcribir, traducir, subtitular, grabar voces en off y editar manualmente, tú proporcionas un archivo MP4 local y la skill se encarga de todo el proceso: reconocimiento de voz, traducción, sincronización de subtítulos, doblaje con TTS y mezcla de audio.

<a name="features"></a>
## Funciones

- **Traducción de vídeo con IA** – traduce el contenido hablado de un idioma a otro.
- **Doblaje con voz original** – impulsado por SoulDub AI para conservar el carácter vocal del hablante.
- **Generación de subtítulos sincronizados** – produce subtítulos SRT precisos sincronizados con el habla.
- **Subtítulos SRT bilingües** – el idioma de origen y el de destino se muestran juntos, ideales para el aprendizaje de idiomas y la revisión.
- **Doblaje con texto a voz (TTS)** – genera un habla de sonido natural en el idioma de destino.
- **Mezcla automática de audio** – sustituye la pista de audio original por la doblada.
- **Compatibilidad con MP4 local** – funciona directamente con archivos MP4 de tu equipo.

<a name="installation"></a>
## Instalación

Instala la skill para tu agente de IA con un solo comando:

```bash
npx skills add jiabaogithub/souldub-skills --skill souldub-video-translate
```

<a name="requirements"></a>
## Requisitos

- Python 3.11 o posterior
- [`uv`](https://docs.astral.sh/uv/)
- Conexión a internet
- Una clave de API de SoulDub
- Acceso de lectura al vídeo de origen y acceso de escritura a la carpeta de salida

### Configura tu clave de API

Usa cualquiera de estos dos métodos:

```yaml
# ~/.souldub/souldub.config.yaml
souldub_api_key: "YOUR_API_KEY"
```

```bash
export SOULDUB_API_KEY="YOUR_API_KEY"
```

Comprueba la autenticación:

```bash
uv run scripts/video_translation.py auth status
```

<a name="usage"></a>
## Uso

Después de la instalación, solo tienes que indicar al agente la **ruta del vídeo** y el **idioma de destino**, por ejemplo:

> Traduce `/path/to/video.mp4` al inglés con doblaje con voz original.

El agente te pedirá cualquier información que falte, iniciará la tarea, informará del progreso y devolverá las rutas de salida.

<a name="how-it-works"></a>
## Cómo funciona

1. **Entrada** – proporciona un vídeo MP4 local y elige el idioma de destino.
2. **Traducción** – el audio hablado se reconoce y se traduce al idioma de destino.
3. **Subtítulos** – se generan subtítulos SRT sincronizados, incluida la versión bilingüe.
4. **Doblaje** – el TTS crea el habla doblada, con voz original mediante SoulDub AI.
5. **Mezcla** – la nueva pista de audio se vuelve a integrar en el vídeo.
6. **Descarga** – obtén el vídeo traducido y los archivos de subtítulos.

<a name="output-files"></a>
## Archivos de salida

| Archivo | Descripción |
| --- | --- |
| Vídeo traducido (MP4) | Vídeo con la pista de audio doblada en el idioma de destino |
| SRT en el idioma de destino | Subtítulos sincronizados en el idioma traducido |
| SRT bilingüe | Subtítulos que muestran el texto original y el traducido |

De forma predeterminada, los archivos se guardan como `result.mp4`, `translated.srt` y `bilingual.srt` en una carpeta `souldub_outputs/` junto al vídeo de origen.

<a name="configuration--privacy"></a>
## Configuración y privacidad

- Los archivos de la skill instalada se tratan como de solo lectura; el estado de ejecución se guarda en el directorio de estado de usuario de tu plataforma.
- Los resultados se escriben en `souldub_outputs/` junto al vídeo de origen de forma predeterminada.
- La skill no persiste claves de API, URL de carga prefirmadas, URL de pasarela de medios ni parámetros temporales firmados.

<a name="use-cases"></a>
## Casos de uso

- Localización de vídeo para lanzamientos de productos y marketing globales
- Traducción de cursos y tutoriales para la educación en línea
- Distribución de contenido transfronterizo en YouTube, TikTok y más
- Subtítulos multilingües para accesibilidad y aprendizaje de idiomas

<a name="faq"></a>
## FAQ

**¿Qué hace Video Translate Skill?**\
Traduce el habla de un vídeo a otro idioma, genera subtítulos SRT, crea doblaje con IA mediante TTS y fusiona el nuevo audio en el vídeo.

**¿Qué formato de vídeo se admite?**\
Vídeos MP4 locales.

**¿Puedo conservar la voz del hablante original?**\
Sí. La skill utiliza SoulDub AI para el doblaje con voz original.

**¿Qué formatos de subtítulos obtengo?**\
SRT en el idioma de destino y SRT bilingüe.

---

Si **Video Translate Skill** te resulta útil, dale una ⭐ al repositorio para que más gente descubra esta herramienta de traducción de vídeo con IA.
