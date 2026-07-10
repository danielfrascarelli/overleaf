# CLAUDE.md

Guía de trabajo para asistir en la redacción de este proyecto de grado. Léela completa antes de tocar `main.tex`. Las instrucciones detalladas del autor viven en [prompts/](prompts/) y tienen prioridad sobre este resumen.

## Qué es este repositorio

Proyecto de grado (Tesis de Ingeniería en Computación, InCo–FING, UdelaR) titulado **"Computación de alto desempeño para el estudio de medios granulares"**, de Daniel Frascarelli. Tutor: **Sergio Nesmachnow**; Co-tutor: Gonzalo Tancredi.

El documento se está **reescribiendo/mejorando** a partir de un informe original. No es código: es un informe científico en LaTeX, en **español académico técnico**. El objetivo de calidad es que el texto sea *formal, empíricamente sólido, estructuralmente coherente* y alineado con el estilo de redacción de Sergio Nesmachnow.

Tema técnico: cálculo paralelo (memoria compartida) del potencial de auto-gravedad en aglomerados granulares densos modelados con DEM, usando discretización en grilla 3D + aproximación jerárquica MADA, con integración en ESyS-Particle.

## Estructura del repositorio

- [main.tex](main.tex) — **el informe completo, archivo único** (clase `book`, español). Esta es la versión viva; edítala directamente aquí.
- [titulo.tex](titulo.tex) — portada (`\input` desde `main.tex`).
- [prompts/](prompts/) — **instrucciones del autor sobre cómo trabajar. Fuente de verdad del *proceso*.**
  - `instructions.txt` — reglas maestras (rol, idioma, estilo, restricciones).
  - `prompt.txt`, `promt chapter vs.txt` — ejemplos de cómo pide trabajo capítulo a capítulo y validaciones.
- [pdfs/](pdfs/) — informe original en PDF (fuente de verdad de *contenido*). `2025.02.10_Tesis.pdf` y `Computación...granulares.pdf` son **idénticos** (mismo md5).
- [images/](images/) — figuras. Subcarpetas por idioma de rótulo: **`es/` (español, las que se usan)**, `en/` (inglés), `na/` (sin texto), `mix/`, `unused/` (descartadas). El documento referencia `images/es/`.
- `sample.bib` — plantilla vestigial; **no** se usa BibTeX (ver Bibliografía).
- `build/`, `main.aux/.log/.pdf/...`, `indent.log` — artefactos de compilación. `main.pdf` y auxiliares están en `.gitignore`.

## Reglas de redacción (obligatorias — resumen de `prompts/instructions.txt`)

1. **Idioma y registro**: español académico técnico. Tono formal, objetivo, impersonal. Nada coloquial, literario ni argumentativo. Sin adjetivos innecesarios. Precisión conceptual por encima de fluidez. No ser verborrágico.
2. **Terminología**: definir cada concepto técnico la primera vez que aparece. Coherencia terminológica estricta: **un concepto = un término**, nunca sinónimos intercambiables.
3. **Sujeto explícito**: no usar sujeto omitido entre párrafos; cada sujeto debe nombrarse explícitamente. Evitar arrastrar el sujeto de un párrafo al siguiente.
4. **Estructura de cada capítulo**: comienza contextualizando el problema → delimita alcance → metodología en etapas numeradas cuando corresponda → define métricas/criterios explícitamente → **separa resultados de interpretación** → sin conclusiones anticipadas.
5. **Acápite**: cada capítulo abre con **una** frase (una línea) que resume su contenido, antes de la primera sección. Ejemplo del documento: *"Este capítulo presenta los fundamentos teóricos y computacionales utilizados en el desarrollo."* Mantener este patrón.
6. **Ecuaciones**: son **objetos independientes**, nunca sueltas en medio de una frase cortada. Toda ecuación va en `equation` con `\label`, y se referencia en el texto por su número: `la ecuación~(\ref{eq:...})`. Las variables se explican en prosa antes o después, no con `itemize` de "donde:".
7. **Figuras y tablas**: se referencian por su **número** (`figura~\ref{...}`, `Tabla~\ref{...}`, `Capítulo~\ref{...}`), nunca con "la figura anterior/siguiente". Toda figura debe tener `\caption` y `\label`.
8. **Rigor**: no introducir afirmaciones sin respaldo. Prohibidos los términos vagos sin referencia bibliográfica ("algunas personas indican", "ciertas evidencias"). No exagerar resultados. No simplificar contenido técnico por estilo.

## Reglas de contenido y fuentes (crítico)

- **No inventar nada. No suponer datos.** Si falta información experimental o metodológica, **decirlo explícitamente**; no rellenar con contenido plausible.
- **Fuentes de verdad de contenido** (únicas): el informe original y el paper *"High Performance Computing of Self-gravity for SSSB"*. Ver el inventario de abajo para su ubicación exacta.
- **Citas prohibidas**: el paper *SSSB* se puede usar como fuente de contenido **pero está prohibido citarlo**.
- **Papers posteriores prohibidos por completo** (ni contenido ni cita): `Nesmachnow2016_Chapter_AParallelMultithreadingAlgorit.pdf`, `performance-improvements-parallel.pdf` y `LARGE-SCALE MULTITHREADING SELF-GRAVITY.pdf` (WSC 2019).
- **PDFs de estilo**: 8 artículos de Nesmachnow + una tesis FING de referencia. Se usan **solo para imitar forma/estilo/estructura**, nunca para copiar frases ni contenido.

## Inventario de PDFs y su uso

Los PDFs **no están en el repo**; viven en `/home/daniel/Documents/facu/fing/` (el directorio padre de `code/overleaf/`). El único PDF versionado es el informe original en [pdfs/](pdfs/). Mapeo por carpeta:

### `/home/daniel/Documents/facu/fing/pdfs/` — referencias de **estilo/formato** (solo forma, nunca contenido ni frases)

8 artículos de Nesmachnow, para imitar estructura (Abstract/Introduction/Methodology/Experiments/Results/Conclusions), densidad de citas, tono impersonal y patrones de redacción:
- `10.3934_mbe.2026006.pdf`
- `A_comparison_of_Generative_Adversarial_Networks_for_image_super-resolution.pdf`
- `Evolutionary_latent_space_search_for_driving_human_portrait_generation.pdf`
- `ijgi-15-00036.pdf`
- `Learning_tenant_behavior_and_evolutionary_approach_for_demand_response_in_colocation_datacenters.pdf`
- `RRNS_Base_Extension_Error-Correcting_Code_..._Distributed_Cloud_Data_Storage.pdf`
- `Understanding_Energy_Consumption_Trends_in_High_Performance_Computing_Nodes.pdf`
- `User-centric_multiobjective_location_of_electric_vehicle_charging_stations_in_a_city-scale_area.pdf`

Tesis de grado FING tutoreada por Sergio, para extraer **exigencias de formato** de tesis (solo formato, no contenido):
- `Algoritmos evolutivos para el diseño de redes de saneamiento en Latinoamérica.pdf`

### `/home/daniel/Documents/facu/fing/pdfs contexto/` — los 8 de estilo + la tesis FING + las 2 fuentes de **contenido**

- `Computación de alto desempeño para el estudio de medios granulares.pdf` → **informe original** (contenido a mejorar). Idéntico al versionado en [pdfs/](pdfs/) (mismo md5).
- `High Performance Computing of Self-gravity for SSSB.pdf` → **fuente de verdad de contenido**. Usable como contenido, **prohibido citarlo**.

### `/home/daniel/Documents/facu/fing/papers mios y nestor/mios/`

- `High Performance Computing of Self-gravity for SSSB.pdf` → misma fuente de contenido (idéntico al de `pdfs contexto/`). Usable, **no citable**.
- `Nesmachnow2016_Chapter_AParallelMultithreadingAlgorit.pdf` → **PROHIBIDO** (desarrollo posterior: ni contenido ni cita).
- `performance-improvements-parallel.pdf` → **PROHIBIDO** (desarrollo posterior: ni contenido ni cita).

### `/home/daniel/Documents/facu/fing/papers mios y nestor/solo nestor/`

- `LARGE-SCALE MULTITHREADING SELF-GRAVITY.pdf` → *Large-Scale Multithreading Self-Gravity Simulations for Astronomical Agglomerates*, Nesmachnow, Rocchetti y Tancredi, **WSC 2019** (Barnes-Hut y "occupied cells"). Desarrollo **posterior** (línea de Néstor Rocchetti): **PROHIBIDO** — ni contenido ni cita.

> Nota: el paper *SSSB* aparece hoy en la bibliografía como `\bibitem{3}` y se referencia en la Introducción (`\cite{3}`) como **hito de difusión del proyecto**, uso distinto de citarlo como fuente de contenido. Si surge la duda, planteársela al autor en lugar de resolverla por cuenta propia.

## Cómo trabaja el autor (proceso — de `prompts/*.txt`)

- **Preguntar antes de generar**: si algo es ambiguo, hacer las preguntas **antes** de producir contenido final. El autor **no quiere borradores** que haya que rehacer tras responder preguntas.
- **Calidad sobre velocidad**: optimizar por una respuesta correcta y completa, no por rapidez. Tomarse el tiempo necesario.
- **Trabajo capítulo a capítulo**: típicamente se piensa primero la *estructura* de un capítulo y recién después se redacta.
- **Rol crítico esperado**: detectar ambigüedades, falta de rigor, problemas de estructura lógica, redundancias entre capítulos e inconsistencias. **Proponer reescrituras concretas**, no sugerencias vagas. **No validar texto incorrecto por cortesía.**
- **Validación conceptual, no textual**: al comparar versiones, el interés es en conceptos, teorías y valores numéricos — no en diferencias de redacción. Verificar que no se agregue información inexistente en el original.

## Convenciones LaTeX de este proyecto

- **Anotaciones de revisión en el texto**: `\red{...}` marca comentarios/pendientes del revisor (rojo); `\blue{...}` (azul); `\todo{}` vía `todonotes`. Muchos bloques comentados con `%` conservan redacciones alternativas — no borrarlos sin acordar. Antes de dar un capítulo por cerrado, resolvé o consultá los `\red{}` que queden.
- **Bibliografía**: **manual**, con `\begin{thebibliography}` y `\bibitem{N}` numérico; se cita con `\cite{N}` (números). Estilo `plain`. **No hay `\bibliography{}` ni BibTeX** pese a que existe `sample.bib`. Para agregar una referencia: añadir un `\bibitem{N}` al final y citarlo con `\cite{N}`.
- **Figuras**: patrón usado —
  ```latex
  \begin{figure}[!ht]
      \setlength{\abovecaptionskip}{3pt}
      \centering
      \includegraphics[scale=...]{images/es/nombre.png}
      \caption{...}
      \label{fig:...}
  \end{figure}
  ```
- **Etiquetas**: `eq:` para ecuaciones, `fig:` para figuras, `sec:`/`ch:` para secciones y capítulos.
- **Comandos propios** (preámbulo de `main.tex`): `\red`, `\blue`, `\norm`, `\alert`.

## Compilar / verificar

`latexmk` y `pdflatex` están instalados. Para compilar sin ensuciar la raíz:

```bash
latexmk -pdf -output-directory=build main.tex
```

Verificá que **compile sin errores** y revisá `build/main.log` ante warnings de referencias (`??`, undefined references) tras editar. No commitees artefactos (`main.pdf`, `.aux`, `.log`, etc. ya están en `.gitignore`).

## Git

- Remoto en GitHub (`danielfrascarelli/overleaf`), sincroniza con Overleaf (aparecen commits "Updates from Overleaf" y merges de ramas `overleaf-...`). El texto puede editarse desde Overleaf en paralelo.
- Mensajes de commit en **español**, breves y descriptivos (ej.: "tabla 6.1", "Cambios pedidos por Sergio").
- **Commit/push solo cuando el autor lo pida.**
