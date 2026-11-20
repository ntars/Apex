[简体中文](README.md) | [English](README_EN.md) | [日本語](README_JA.md) | [한국어](README_KO.md) | [Français](README_FR.md) | [Русский](README_RU.md) | **Español** | [العربية](README_AR.md)

# Apex

**El sitio oficial de Ntarstudio (星玖工作室) — y el índice de los diez proyectos.**

> **Este repositorio tiene dos roles**: es el código fuente del sitio del estudio (un archivo HTML, una hoja de estilos, unos pocos scripts nativos) y es **el índice de los diez proyectos**. Este documento se centra en lo segundo: qué es cada proyecto, en qué punto está y dónde mirar. La implementación del sitio se comprime en el capítulo 5 y se mantiene deliberadamente breve.

![Status](https://img.shields.io/badge/status-online-2ea44f?style=flat-square)
[![GitHub license](https://img.shields.io/github/license/ntars/Apex?style=flat-square)](./LICENSE)
[![GitHub Star](https://img.shields.io/github/stars/ntars/Apex?style=flat-square)](https://github.com/ntars/Apex/stargazers)
[![GitHub Fork](https://img.shields.io/github/forks/ntars/Apex?style=flat-square)](https://github.com/ntars/Apex/network/members)
![GitHub Repo size](https://img.shields.io/github/repo-size/ntars/Apex?style=flat-square&color=3cb371)

[![Live](https://img.shields.io/badge/live-www.ntars.cn-0078d4.svg?style=flat-square)](https://www.ntars.cn/)
[![Projects](https://img.shields.io/badge/projects-9-8957e5.svg?style=flat-square)](#)
[![Build](https://img.shields.io/badge/build-none-2ea44f.svg?style=flat-square)](#)

---

## 1. Nombre y posicionamiento

> **仓库描述 / Description**：`Apex —— 星玖工作室（Ntarstudio）官网与十个项目总索引：一个 HTML、一份样式表、几个原生脚本 | The Ntarstudio official site and an index of its ten projects: one HTML file, one stylesheet, a few plain scripts.`
>
> **话题标签 / Topics**（20 个，仅英文）：`frontend`, `landing-page`, `no-framework`, `personal-website`, `portfolio-site`, `pwa`, `service-worker`, `single-page`, `static-site`, `studio-website`, `vanilla-css`, `vanilla-javascript`, `ntarstudio`, `chinese-website`, `html`, `css`, `javascript`, `dark-mode`, `responsive-design`, `no-dependencies`


**Nombre**: Apex, «cumbre». Como sitio oficial del estudio desempeña el papel de una entrada, no de un producto.

**Posicionamiento en una línea**: un sitio estático de una sola página, sin dependencias ni compilación, que enuncia tres cosas con el mínimo código: quién es, qué se construye y dónde mirar.

**Tres límites**:

1. **Es una placa, no una sala de exposiciones.** No incluye funciones de producto, demostraciones en línea ni documentación incrustada. El visitante avanza mediante enlaces directos a cada proyecto.
2. **Son archivos estáticos, no una aplicación.** Sin backend, sin base de datos, sin cuentas. Todo el contenido está escrito en `index.html`; cambiar una línea de texto es un commit.
3. **Es un índice, no una fuente de contenido.** La información real de un proyecto vive en su propio repositorio y su propio sitio. Esta página resume y enlaza; no duplica.

**Por qué este README se centra en los proyectos**: la sección «星玖工作室出品» de la página de inicio enumera los diez proyectos. Esa lista, el capítulo 3 de este documento y el README de perfil de GitHub son tres representaciones de una misma fuente. **Quien quiera una idea rápida de lo que construye el estudio solo necesita esta página** — no hace falta abrir diez repositorios.

---

## 2. Presentación

### 2.1 Contexto

Los sitios de estudio suelen fallar de dos maneras. O se convierten en sitios multipágina gestionados por un CMS que se estancan en seis meses y acaban más antiguos que los productos; o se convierten en portafolios demostrativos donde la primera pantalla está saturada de animaciones y el visitante no encuentra los enlaces a los proyectos.

### 2.2 Problemas que aborda

El visitante debe obtener tres respuestas de inmediato: **quién es, qué se construye, dónde mirar**. Si la página tarda más de tres segundos en responder, ha fallado.

### 2.3 Enfoque central

El sitio tiene exactamente tres responsabilidades:

| Responsabilidad | Enfoque |
|---|---|
| Establecer la identidad de marca | La primera pantalla vincula 星玖工作室 / Ntarstudio / Ntars |
| Orientar hacia el código abierto | Seis tarjetas que enlazan directamente a las direcciones canónicas |
| Enunciar los hechos con honestidad | La información no publicada o retirada nunca aparece en la página, las palabras clave ni los datos estructurados |

### 2.4 Casos de uso

- La placa oficial de un pequeño estudio independiente;
- Un sitio estático que debe mantenerse estable con un mantenimiento casi nulo;
- Una muestra didáctica de front-end sin compilación.

### 2.5 No objetivos

- Sin cuentas, formularios, cookies, analítica, publicidad ni API de backend;
- Sin jQuery / Vue / React / bibliotecas de componentes UI, sin Tailwind, sin Vite / Webpack / Rollup;
- Sin escrituras en `localStorage` (la única excepción se trata en 5.1: el estado del tema deliberadamente no se persiste).

---

## 3. Funciones principales: los diez proyectos

La sección «星玖工作室出品» de la página de inicio muestra diez proyectos, agrupados por estado — publicados o entregados primero, en desarrollo en medio, planificados al final — y ordenados por nombre latino dentro de cada grupo.

**Los diez proyectos son Apex, Gitrule-skill, Ondra, Wacmin, Webroit, Xael, Flutter-IDE, Serica, TapMC y Desop.** GitHub es la plataforma que los aloja, no un proyecto; las cuatro direcciones internas de Wacmin son un detalle de implementación y no se enumeran por separado.

### 3.1 Publicados, entregados y en desarrollo

#### Apex · En línea

| | |
|---|---|
| Qué es | El sitio que estás leyendo — la placa del estudio y el índice de proyectos |
| Tecnologías | HTML · CSS · Vanilla JS |
| Licencia | MIT (Apache-2.0 para las partes derivadas) |
| Entrada | <https://www.ntars.cn/> |
| Repositorio | <https://github.com/ntars/Apex> |

Un archivo HTML, una hoja de estilos, unos pocos scripts nativos. Sin framework, sin compilación, sin backend. Cero dependencias significa que seguirá funcionando dentro de tres años.

**Por qué vale la pena**: es una muestra de front-end sin compilación — cómo un solo archivo HTML organiza todo un sitio y sobrevive seis años sin actualizaciones.

#### Gitrule-skill · Entregado

| | |
|---|---|
| Qué es | Un conjunto de especificaciones genéricas que cubre todo el ciclo de vida: definición, requisitos, arquitectura, desarrollo, pruebas, despliegue, operación, iteración, además de documentación, cumplimiento y acceso programático por IA |
| Tecnologías | Markdown (sin dependencias de terceros) · CLI en Python · servidor MCP |
| Volumen | 66 especificaciones en chino simplificado e inglés, una a una |
| Estado | Entregado: el CLI no informa problemas; Skill, paquete de experto y servidor MCP están disponibles |
| Licencia | MIT |
| Repositorio | <https://github.com/ntars/Gitrule-skill> |

Una especificación por archivo, independiente y consultada según necesidad. Un CLI sin dependencias comprueba enlaces rotos, archivos huérfanos, frases de responsabilidad, bloques de código, recuentos de índice y registro de marcadores.

**Por qué vale la pena**: convierte convenciones —qué 20 capítulos necesita un README, cómo se nombra un repositorio, cómo se redactan descripción y temas— en archivos y comandos verificables. La alineación de los diez repositorios se apoyó en esta base única.

#### Ondra (空谷) · Beta interna

| | |
|---|---|
| Qué es | Compañero de IA de escritorio totalmente modular: la interfaz solo lee la proyección de los complementos; emoción, memoria y contexto son los tres mecanismos clave; los datos se quedan en el equipo |
| Tecnologías | Flutter (escritorio y web) · Cordis 4.1.0 (marco de complementos) · núcleo dsh (Node) |
| Versión | `2.0.0-alpha` |
| Plataformas | macOS ejecutable, web compilable; las demás solo tienen proyectos generados |
| Licencia | Apache-2.0 / MIT |
| Entrada | <https://ai.ntars.cn/> |
| Repositorio | <https://github.com/ntars/Ondra> |

Tres mecanismos clave: emoción (estado con inercia), memoria (cadena de once eslabones), contexto (prefijo congelado + inyección incremental + presupuesto). La página de complementos fusiona 18 entradas incluidas y 75 de la capa de ensamblaje, 93 en total.

**Por qué vale la pena**: descompone el acompañamiento en mecanismos que se pueden ingenierizar por separado, y un parche de orden de arranque redujo de 55 a 0 las degradaciones silenciosas de 18 complementos.

#### Wacmin · Disponible

| | |
|---|---|
| Qué es | Suite de interoperabilidad bidireccional entre macOS y Windows |
| Tecnologías | Node.js · Python · Rust |
| Licencia | MIT |
| Repositorio | <https://github.com/ntars/Wacmin> |

Completa cuatro direcciones cruzando «anfitrión» con «acción»: producir un instalador de Windows en Mac, ejecutar un programa de Windows en Mac, producir un paquete de macOS en Windows, ejecutar un programa de mac en Windows. Las cuatro comparten una capa de contrato con códigos de salida y segmentos de error unificados.

**Por qué vale la pena**: ordena el desarrollo por certeza, deja el fallo más probable para el final y define de antemano una ruta de degradación — incluso si falla, las tres primeras se sostienen.

#### Webroit · En línea

| | |
|---|---|
| Qué es | Una caja de herramientas Android en el navegador: ADB y Fastboot por WebUSB, 152 funciones |
| Tecnologías | TypeScript · Vite · WebUSB · ya-webadb |
| Forma | Sitio puramente estático: sin backend, sin instalación, sin controladores |
| Licencia | Apache-2.0 / MIT |
| Entrada | <https://adb.ntars.cn/> |
| Repositorio | <https://github.com/ntars/Webroit> |

Lleva al navegador todo lo necesario para trastear con Android. El protocolo ADB se implementa sobre Tango; lo que se entrega es la interfaz y los flujos que un usuario emplea de verdad: gestión de aplicaciones, navegación de archivos, terminal, duplicación de pantalla, registros y flasheo, 152 funciones en total, cada una con su nivel de riesgo.

**Por qué merece la pena**: elimina por completo la capa de «preparación del entorno». La ruta clásica es descargar Platform-Tools → configurar el PATH → instalar controladores USB → escribir reglas udev → conectar → teclear comandos; comprime los cinco primeros pasos en «abrir la página → pulsar conectar → pulsar una función». Y la dificultad real nunca fue teclear comandos, sino ese momento en que ya está todo instalado y sigue sin conectar, sin poder distinguir si es el cable, el puerto, el controlador o un `adb.exe` que quedó en segundo plano ocupando la interfaz.

**Dos detalles más**: el producto es un `dist/` estático y `grep -r "http" dist/` no encuentra ninguna dirección de backend propia: «los datos no salen de tu equipo» es un hecho verificable, no una promesa. Además clasifica cada operación por riesgo, de modo que un comando copiado de cualquier sitio indica qué va a cambiar y si se puede deshacer.

#### Xael (玄玖灵犀) · Publicado

| | |
|---|---|
| Qué es | Corpus sin conexión de metafísica china: 22 funciones calculadas desde los principios primeros, sin tablas de consulta, sin red |
| Tecnologías | JavaScript (sin dependencias) · PWA · miniprograma de WeChat · uni-app |
| Versión | 5.0.0 |
| Licencia | Apache-2.0 / MIT |
| Entrada | <https://x.ntars.cn/> |
| Repositorio | <https://github.com/ntars/Xael> |

Cubre Cuatro Pilares, Zi Wei Dou Shu, Qi Men Dun Jia, Da Liu Ren, Liu Yao, Mei Hua Yi Shu, Estrellas Voladoras Xuan Kong y selección de fechas del almanaque. La base calendárica deriva las lunas nuevas de series astronómicas en tiempo real en lugar de incluir una tabla; veinte clásicos de dominio público sirven como textos base, con cada regla corregida elemento por elemento y su nivel de evidencia indicado. El miniprograma y la cuenta oficial se buscan con el mismo nombre.

**Por qué vale la pena**: lleva «calcular en lugar de consultar» hasta el final y anota cada conclusión con su base textual y la incertidumbre restante.

#### Flutter-IDE · Etapa de esqueleto

| | |
|---|---|
| Qué es | Un IDE visual de Flutter centrado en el código: arrastrar en un lienzo, editar en paneles y obtener Dart mantenible sin la herramienta |
| Tecnologías | Dart 3.14+ · Flutter Desktop |
| Versión | `0.1.0` |
| Estado | Esqueleto: espacio de trabajo, 47 tokens de diseño, protocolo de bloques y cinco reglas de validación terminados; codegen, escritura AST y selección pendientes |
| Licencia | Apache-2.0 / MIT |
| Repositorio | <https://github.com/ntars/Flutter-IDE> |

El único criterio de viabilidad: elimine el IDE y el proyecto debe seguir pasando `flutter run`. Por eso los esquemas de intención, las capas y los tokens de diseño son archivos de texto en git; no hay estructuras que vivan solo dentro de la herramienta.

**Por qué vale la pena**: «no quedar atado a una herramienta» está escrito como tres criterios de aceptación —sin Schema privado, un cambio produce un solo diff, la misma entrada genera dos veces el mismo resultado— y no como un eslogan.

#### Serica（行简）· Etapa de esqueleto

| | |
|---|---|
| Qué es | Un lenguaje de programación para apps sincronizadas entre dispositivos: todo en chino, fuentes `.serica`, comando `serica`, ejecutables nativos como salida |
| Tecnologías | Go (compilador semilla stage0) · vía de autoalojamiento · escribe Mach-O directamente |
| Versión | Etapa `P1b` pre-alpha; P0b superó la aceptación estricta en macOS arm64 el 2026-11-20 |
| Tamaño | 1928 líneas de semilla con un techo de 5000, con tabla de atribución línea por línea; el directorio semilla se elimina tras el autoalojamiento |
| Licencia | Apache-2.0 (núcleo y semilla) / MIT (especificaciones y ecosistema) |
| Plataformas | Verificado solo en macOS arm64, el resto sin probar |
| Repositorio | <https://github.com/ntars/Serica> |

El compilador semilla no genera C ni llama a LLVM, ensamblador o enlazador: escribe el Mach-O él mismo. La puntuación china es gramática en la capa léxica, no tipografía; los diagnósticos dan a la vez la columna en puntos de código y la columna mostrada (`línea 3, columna 38 (visual 55)`), y reconstruir la misma fuente produce bytes idénticos. Hoy funcionan las constantes de compilación, los cortes por puntos de código, la aritmética entera, las operaciones de bits, los arreglos constantes y una ventana declarativa — **insuficiente para escribir software de producción**.

**Por qué vale la pena** : «el chino no es solo traducir palabras clave» se convierte en restricciones de ingeniería verificables — techo de 5000 líneas, tabla de atribución línea por línea, borrado de la semilla tras el autoalojamiento y un tipo de salida que un solo `file` confirma.

#### TapMC · Etapa de esqueleto

| | |
|---|---|
| Qué es | Esqueleto de juego sandbox multijugador modular: un front Flutter en siete plataformas y un servidor Java, unidos por un único contrato JSON-RPC 2.0 |
| Tecnologías | Flutter (front) · Java 21 (servidor) |
| Estado | Esqueleto: el camino funciona, 61 pruebas de servidor y 18 de front pasan; sin versión publicada |
| Plataformas | Web y Android compilan; las otras cinco quedan por verificar |
| Licencia | Apache-2.0 / MIT |
| Repositorio | <https://github.com/ntars/TapMC> |

El servidor es la única fuente de verdad; el front solo muestra y recoge entrada. Mundo en rejilla 24×16, cinco tipos de bloque. Los mods solo reciben `ModContext`, nunca `WorldGrid`: las reglas no se pueden saltar.

**Por qué vale la pena**: la pregunta «dónde se calculan las reglas» queda fijada por una restricción de compilación, no por disciplina en la revisión. El núcleo no depende de la red, así que toda la lógica se prueba sin abrir un puerto (22 casos).

### 3.2 Planificados

**El proyecto siguiente solo tiene documentación — ningún código ejecutable.** La redacción del estado separa estrictamente «publicado» y «planificado».


#### Desop · Planificado

| | |
|---|---|
| Qué es | Suite de personalización del escritorio de Windows: dock, barra de menús, widgets, isla dinámica |
| Tecnologías | Por definir |
| Licencia | Apache-2.0 / MIT |
| Repositorio | <https://github.com/ntars/Desop> |

Cero cambios en el sistema, modo usuario puro, desinstalar lo restaura todo. Los cuatro componentes comparten un conjunto de tokens de diseño y pueden activarse por separado. El presupuesto de rendimiento es una puerta de publicación: CPU inactiva < 1 %, memoria < 150 MB, magnificación del dock ≥ 55 fps — si no se cumple, no se publica.

**Por qué vale la pena**: responde a la queja habitual de que las herramientas de personalización ralentizan la máquina con cifras concretas, no con «optimizaremos más adelante».

### 3.3 Redacción del estado

**El estado del sitio y el del producto no son equivalentes** — un sitio funcionando no significa software instalable, y software funcionando no significa sitio accesible.

| Proyecto | Estado | Significado |
|---|---|---|
| Apex | En línea | El sitio funciona y el código es público |
| Gitrule-skill | Entregado | 66 especificaciones en chino e inglés, el CLI no informa problemas; sin número de versión, se entrega desde la rama principal |
| Ondra | Beta interna | `2.0.0-alpha`: macOS ejecutable, web compilable; las demás solo generadas |
| Wacmin | Disponible | Las cuatro direcciones terminadas y probadas, con acceso CLI y MCP |
| Webroit | En línea | Sitio estático en servicio en adb.ntars.cn, 26 funciones utilizables, código público |
| Xael | Publicado | Existe una versión estable, descargable y usable |
| Flutter-IDE | Etapa de esqueleto | Contratos, tokens y cinco reglas de validación utilizables; codegen, escritura AST y selección sin implementar; sin versión publicada |
| Serica | Etapa de esqueleto | El compilador semilla convierte el subconjunto P0b/P1b en Mach-O, y P0b superó la aceptación en macOS arm64; sin versión publicada e inservible para software de producción |
| TapMC | Etapa de esqueleto | El camino funciona y 79 pruebas pasan; sin versión publicada |
| Desop | Planificado | Solo documentación, sin código ejecutable |

**Por qué los proyectos planificados aparecen en el sitio**: el sitio es la placa del estudio, muestra «lo que se está construyendo», no solo «lo que ya está hecho». Indicar el estado con claridad basta — quien lee «Planificado» sabe que no hay nada que descargar, lo cual es más honesto que ocultarlo.

---

## 4. Características principales

### Destacado 1: diez proyectos en una página, tres fuentes sincronizadas

- **Nombre**: índice de página única.
- **Valor**: resuelve «para saber qué construye este estudio hay que abrir seis repositorios».
- **Implementación**: las tarjetas del sitio, el capítulo 3 de este documento y el README de perfil de GitHub listan el mismo conjunto con la misma redacción de estado.
- **Diferenciación**: la mayoría de las páginas personales solo listan lo publicado o dispersan la información en los README de cada repositorio.
- **Evidencia**: las tres listas coinciden elemento por elemento; véase la tabla de estados en 5.9.

### Destacado 2: cero dependencias, cero compilación, editar y refrescar

- **Nombre**: sin cadena de herramientas.
- **Valor**: resuelve «deja de compilar tras seis meses sin cambios».
- **Implementación**: sin `node_modules`, sin `package.json`, sin archivo de bloqueo. `python3 -m http.server 8000` basta para previsualizar.
- **Diferenciación**: la mayoría de los «sitios mínimos» siguen usando Vite o Webpack con el argumento de que «la plantilla ya lo traía».
- **Evidencia**: no hay `package.json` en la raíz; el despliegue es «push a main → EdgeOne Pages publica automáticamente».

### Destacado 3: el tema sigue al sistema, sin destello blanco en el primer fotograma

- **Nombre**: tema inicial bloqueado en dos fotogramas.
- **Valor**: resuelve el destello blanco al abrir la página en un sistema oscuro.
- **Implementación**: un script en línea ejecutado de forma síncrona en `<head>` lee `prefers-color-scheme` y escribe el resultado en `<html data-theme>`; primero añade `theme-lock` para suprimir las transiciones y lo retira tras dos fotogramas consecutivos de `requestAnimationFrame` una vez estabilizado el tema.
- **Diferenciación**: la práctica común fija el tema en `DOMContentLoaded` o no hace nada para evitar el destello.
- **Evidencia**: una regla de transición unificada de 0,5 s bajo `html:not(.theme-lock)`.

### Destacado 4: el halo de las tarjetas sigue al puntero sin tocar el DOM

- **Nombre**: halo impulsado por variables CSS.
- **Valor**: resuelve «los efectos de hover provocan reflujo de maquetación».
- **Implementación**: `app.min.js` calcula las coordenadas del puntero relativas a la tarjeta y las escribe en `--mouse-x` / `--mouse-y`; el `::before` de la tarjeta pinta el halo con `radial-gradient`.
- **Diferenciación**: el enfoque habitual mueve un elemento posicionado de forma absoluta en cada `mousemove`, forzando composición y reflujo.
- **Evidencia**: `app.min.js` solo calcula coordenadas y escribe variables.

### Destacado 5: los dos escollos de desplazamiento del diálogo, resueltos

- **Nombre**: compensación de la barra de desplazamiento y dirección de salida.
- **Valor**: resuelve dos errores que comete casi cualquier diálogo artesanal — la página que se desplaza a la derecha al abrirse y el panel «aspirado» hacia una esquina al cerrarse.
- **Implementación**: al abrir, añadir `padding-right` antes de `overflow: hidden`; al cerrar, esperar a que termine la transición de `opacity` (con un temporizador de respaldo de 500 ms) antes de restaurar el desplazamiento, animando solo `opacity` y nunca `transform`.
- **Diferenciación**: tocar `transform` desplaza el panel hacia el origen de transformación, lo que se percibe como un imán.
- **Evidencia**: bajo `prefers-reduced-motion` la animación se omite y el temporizador de 500 ms es la única vía que cierra el diálogo.

---

## 5. Detalles de diseño y decisiones de ingeniería

**Este es el único capítulo dedicado al sitio en sí.** Está deliberadamente comprimido — los proyectos son lo importante.

### 5.1 Tema: sigue al sistema, anulable manualmente, no se recuerda

Hacer doble clic en «星玖工作室出品» invierte el tema manualmente y sincroniza `<meta name="theme-color">` para que la barra de direcciones del móvil coincida.

**El estado manual deliberadamente no se escribe en `localStorage`.** La experiencia por defecto sigue al sistema; cada interruptor guardado es un estado más que explicar. Recargar vuelve a la preferencia del sistema.

### 5.2 Cinco bloques de página

De arriba abajo: saludo, separador, proyectos, entrada «contacto» arriba a la derecha, pie de página. Más cuatro capas superpuestas permanentes (canvas de fuegos artificiales, canvas de estela, canvas de partículas de fondo, decoración inferior).

Sin router, sin DOM virtual; el desplazamiento es nativo.

### 5.3 Tres bandas de dispositivo en el saludo

| Dispositivo | Detección | Visualización |
|---|---|---|
| Móvil | Viewport < 768 px | Hi, I'm **Ntars** |
| Tableta | 768–1180 px con táctil | Modo estudio en horizontal, modo personal en vertical |
| Escritorio | El resto | Hi, We're **Ntarstudio** |

La detección de tableta exige además `ontouchstart in window` o `navigator.maxTouchPoints > 0`, de lo contrario una ventana grande de navegador de escritorio se detectaría mal.

### 5.4 Tarjetas de proyecto: guiadas por configuración

Las tarjetas se renderizan desde el arreglo `PROJECTS`, cada entrada con título, descripción, enlace e icono opcional. `grid-template-columns: repeat(auto-fill, minmax(240px, 1fr))` con 16 px de separación da tres columnas en escritorio y una en pantallas estrechas, sin media queries.

Cambiar el estado de un proyecto es cambiar una línea de datos, no un bloque de HTML — lo que evita «cambié la tarjeta pero olvidé los metadatos» y «las tarjetas divergieron estructuralmente».

### 5.5 Seis scripts en lugar de uno

| Archivo | Responsabilidad |
|---|---|
| `security.js` | Desactiva selección/copia/clic derecho/atajos; detección de manipulación |
| `app.min.js` | Halo de tarjetas: coordenadas del puntero → variables CSS |
| `anime.js` | anime.js v2.0.2 (tercero, MIT, sin modificar) |
| `firework.js` | Partículas de fuegos artificiales |
| `trail.js` | Estela del puntero |
| `bg.js` | Partículas de fondo y conexiones |

Cada archivo hace una cosa y puede retirarse por separado. La única dependencia dura es `firework.js` respecto a `anime.js`, de ahí el orden fijo: `security → app.min → anime → firework → trail → bg`.

### 5.6 El número de versión de la caché es el paso más fácil de olvidar

**`CACHE_NAME` es actualmente `ntarstudio-v10`.** Cambiar cualquier cosa de la lista de precaché — incluido Typed.js desde CDN — obliga a incrementar la versión, o los visitantes recurrentes se quedarán en la caché antigua.

### 5.7 Los límites honestos de las medidas de seguridad

`security.js` intercepta selección, copia, corte, clic derecho, arrastre, F12 y los atajos de ver código fuente.

**Para que quede claro: estas medidas solo elevan el umbral de la copia ocasional; no aportan ninguna protección del contenido.** El código de front-end siempre es visible para el visitante y ningún script cambia eso.

### 5.8 Lista blanca de CSP

| Directiva | Valor |
|---|---|
| `default-src` / `script-src` | `'self'`, en línea, `https://unpkg.com` |
| `img-src` | `'self'` y `data:` |
| `frame-src` / `object-src` | `'none'` |
| `connect-src` | `'self'` (la página no hace peticiones a API externas) |

Además `nosniff`, `X-Frame-Options: DENY` y `referrer: no-referrer`.

### 5.9 La disciplina de los tres lugares

Cuando cambia el estado de un proyecto (publicación, retirada, cambio de dominio), estos tres deben actualizarse juntos:

1. El arreglo `PROJECTS` en `index.html`;
2. El capítulo 3 de este documento;
3. La tabla de proyectos del README de perfil de GitHub `ntars/ntars`.

**Los proyectos retirados no vuelven de ninguna forma** — ni en la página, ni en las palabras clave, ni en los datos estructurados.

---

## 6. Pila tecnológica y dependencias

### 6.1 Pila

| Capa | Elección |
|---|---|
| Estructura | HTML5 nativo, etiquetas semánticas más complemento `role` |
| Estilos | CSS nativo: propiedades personalizadas + Grid + Flexbox |
| Interacción | JavaScript nativo (mayormente sintaxis ES5) |
| Animación | anime.js v2.0.2, solo para partículas de fuegos artificiales |
| Tipografías | Pila de fuentes del sistema; sin fuentes web |
| Sin conexión | Service Worker + Web App Manifest |
| Despliegue | EdgeOne Pages |

### 6.2 Componentes de terceros

| Componente | Versión | Titular | Licencia | Inclusión | Uso |
|---|---|---|---|---|---|
| asorn/asorn-open | — | asorn | Apache-2.0 | Derivación de código | Base inicial |
| anime.js | v2.0.2 | Julian Garnier (2017) | MIT | Archivo completo incrustado | Línea de tiempo y suavizado de fuegos artificiales |
| Typed.js | 2.0.16 | Matt Boldt | MIT | CDN unpkg + precaché SW | Efecto de escritura del saludo |

**Derivación**: este proyecto modifica, amplía y rediseña la interfaz y la estructura sobre asorn/asorn-open, por lo que es una obra derivada. Conforme a la cláusula 4 de Apache-2.0 se conservan el aviso de copyright original, el texto completo de la licencia y una declaración de cambios.

### 6.3 Explícitamente no utilizados

Fuentes web de terceros · bibliotecas de iconos de terceros · frameworks de front-end y bibliotecas UI · analítica y seguimiento · publicidad y widgets de comentarios/soporte · cookies y escrituras en almacenamiento local · API de backend y bases de datos.

### 6.4 Dependencias indirectas

Ninguna. No existen dependencias transitivas.

---

## 7. Instalación y despliegue

```bash
python3 -m http.server 8000
# abrir http://localhost:8000
```

Sin paso de compilación; editar y refrescar. El Service Worker solo se registra en `localhost` o HTTPS — `file://` no está soportado.

**Solo hay una ruta de despliegue**: push a `main` → EdgeOne Pages publica automáticamente, con `www.ntars.cn` apuntando al sitio. El repositorio no contiene archivos de workflow.

---

## 8. Inicio rápido

### 8.1 Para conocer los proyectos

Lee el capítulo 3 anterior o visita <https://www.ntars.cn/>.

### 8.2 Para ejecutar el sitio en local

1. `git clone https://github.com/ntars/Apex.git`
2. `cd Apex && python3 -m http.server 8000`
3. Abrir `http://localhost:8000`
4. Doble clic en «星玖工作室出品» para verificar el cambio de tema
5. Reducir la ventana por debajo de 768 px para verificar el texto en modo móvil
6. Hacer clic en «Contacto» arriba a la derecha para verificar el diálogo

---

## 9. Configuración

No hay archivo de configuración. Todo lo ajustable está en tres lugares:

| Contenido | Ubicación | Qué cambiar |
|---|---|---|
| Tarjetas de proyecto | el arreglo `PROJECTS` en `index.html` | Título, descripción, enlace, icono opcional |
| Colores del tema | `:root` y `[data-theme="dark"]` en `assets/css/base.css` | Propiedades CSS personalizadas |
| Versión de caché | `CACHE_NAME` en `sw.js` | Incrementar siempre que cambie un recurso precacheado |

---

## 10. API y módulos

No hay API. Las responsabilidades de los scripts están en 5.5. El orden de carga es fijo: `security → app.min → anime → firework → trail → bg`.

---

## 11. Estructura del repositorio

```
Apex/
├── index.html                 # Estructura + metadatos + cuatro scripts en línea
├── manifest.json              # Manifiesto PWA
├── sw.js                      # Service Worker
├── LICENSE                    # Texto completo MIT
├── LICENSE-Apache-2.0.txt     # Texto completo Apache-2.0 (partes derivadas de asorn)
├── NOTICE                     # Avisos de copyright y de terceros
├── README.md / README_EN.md
└── assets/
    ├── css/
    │   ├── base.css           # La única hoja de estilos cargada
    │   ├── base.scss          # Fuente de estilos correspondiente a base.css
    │   └── base.min.css       # Versión minificada
    ├── js/
    │   ├── security.js
    │   ├── app.min.js
    │   ├── anime.js           # Tercero, MIT
    │   ├── firework.js
    │   ├── trail.js
    │   └── bg.js
    └── img/                   # Logotipo N+T propio e iconos PWA
```

---

## 12. Rendimiento

| Métrica | Valor | Notas |
|---|---|---|
| Pasos de compilación | 0 | Sin empaquetado ni minificación |
| Peticiones externas en la primera pantalla | 1 | Typed.js (CDN unpkg, precacheado) |
| Fuentes web | 0 | Pila de fuentes del sistema |
| Reflujos de maquetación | 0 | El halo solo escribe variables CSS |
| Visitas repetidas | Servido desde caché | Service Worker, caché primero |

---

## 13. Seguridad y privacidad

| Dimensión | Enfoque |
|---|---|
| Cookies | No se usan |
| Almacenamiento local | Sin escrituras (el estado manual del tema deliberadamente no se persiste) |
| Analítica | Ninguna |
| Peticiones de terceros | Solo Typed.js (CDN unpkg) |
| CSP | Lista blanca declarada; `object-src` / `frame-src` en `'none'` |
| Clickjacking | `X-Frame-Options: DENY` |
| Fuga de referente | `referrer: no-referrer` |

**Una nota honesta sobre la protección del contenido de front-end**: `security.js` solo eleva el umbral de la copia ocasional y no aporta protección alguna.

---

## 14. Compatibilidad

| Entorno | Estado | Notas |
|---|---|---|
| Navegadores modernos | ✅ Completo | Propiedades CSS personalizadas nativas + Grid |
| Navegadores antiguos | ⚠️ Degradado | Los scripts son mayormente ES5; el tema no se aplica pero el contenido sigue legible |
| Móvil (< 768 px) | ✅ | Una columna a todo el ancho |
| Tableta (768–1180 px con táctil) | ✅ | Doble modo según orientación |
| Escritorio (≥ 1180 px) | ✅ | Tarjetas en tres columnas |
| Abierto vía `file://` | ⚠️ Parcial | El Service Worker no se registra; el resto funciona |

---

## 15. Problemas conocidos y limitaciones

1. **La versión de caché depende de una persona**: olvidar incrementar `CACHE_NAME` deja a los visitantes recurrentes en una caché antigua, sin que se levante ningún error.
2. **El estado manual del tema no se persiste**: recargar vuelve a la preferencia del sistema — por diseño.
3. **El cambio por toque está desactivado en tabletas**: el modo sigue la orientación.
4. **La protección del contenido de front-end no funciona**: `security.js` solo eleva el umbral.
5. **Typed.js viene de un CDN**: si unpkg no es accesible, el efecto de escritura falla, aunque el resto del contenido no se ve afectado.
6. **Las tarjetas de proyectos planificados no tienen nada que descargar**: el coste de indicar el estado con honestidad — y la razón por la que nada planificado se describe como construido.

---

## 16. Registro de cambios

El registro vive en la página de **GitHub Releases**: <https://github.com/ntars/Apex/releases>

El README describe el estado actual del sitio; las releases registran qué cambió cada vez. Ambos nunca se mezclan.

---

## 17. Hoja de ruta

1. **Automatizar la versión de caché**: sustituir el `CACHE_NAME` escrito a mano por un hash de recursos en tiempo de compilación.
2. **Iconos de las tarjetas**: montar los iconos de los diez proyectos cuando existan; ahora todos son `icon: null`.
3. **Auditoría de accesibilidad**: hay `role`, `tabindex` y `aria-*`, pero no se ha hecho un recorrido completo con teclado ni una prueba con lector de pantalla.
4. **Reducir dependencias de terceros**: Typed.js es lo bastante simple para reemplazarlo con unas cuarenta líneas nativas.
5. **Imagen de vista previa Open Graph**: actualmente no hay `og:image`.

---

## 18. Contribuir

### 18.1 Autoverificación antes de cambiar algo

1. Los títulos, descripciones y enlaces de las seis tarjetas coinciden con el estado real de los proyectos;
2. `description`, `keywords`, `og:*`, JSON-LD y `canonical` permanecen sincronizados con el texto;
3. Si cambió algún recurso precacheado, `CACHE_NAME` se incrementó;
4. Se revisaron los temas claro y oscuro;
5. Sin truncamiento ni desbordamiento en anchos de móvil, tableta y escritorio;
6. El fondo no se desplaza mientras el diálogo está abierto y la posición no salta tras cerrarlo;
7. **Un cambio de estado se edita en tres lugares** (arreglo `PROJECTS`, capítulo 3 de este documento, README de perfil de GitHub).

### 18.2 Disciplina de publicación

- Verificar `CACHE_NAME` tras cada cambio de contenido;
- Cuando cambia el estado de un proyecto, actualizar juntos la tarjeta, los metadatos y la tabla de estados;
- Los proyectos retirados nunca deben volver a la página, las palabras clave ni los datos estructurados;
- Confirmar la compatibilidad de licencia antes de añadir un componente de terceros y registrarlo en `NOTICE` antes de hacer commit.

### 18.3 Contacto

| Canal | Dirección |
|---|---|
| Sitio | <https://www.ntars.cn/> |
| GitHub | <https://github.com/ntars> |
| README de perfil | <https://github.com/ntars/ntars> |
| Correo | <ntars@qq.com> · <ntarsx@163.com> |

---

## 19. Copyright y licencia

| Ámbito | Licencia |
|---|---|
| Código propio (estructura, estilos, scripts y cambios posteriores) | MIT, ver [`LICENSE`](LICENSE) |
| Partes derivadas de asorn/asorn-open | Apache-2.0, ver [`LICENSE-Apache-2.0.txt`](LICENSE-Apache-2.0.txt) |
| Nombres de marca, logotipo, diseño de interfaz | Todos los derechos reservados, ver [`NOTICE`](NOTICE) |

La redistribución debe conservar `NOTICE`, `LICENSE`, `LICENSE-Apache-2.0.txt` y los avisos de copyright y licencia en la cabecera de `assets/js/anime.js`.

**Nombres y marcas.** Los nombres y marcas 「星玖工作室」, 「Ntarstudio」, 「玄玖灵犀」, 「Xael」, 「NT-Xhex」, 「空谷」, 「Ondra」, 「Wacmin」, 「TapMC」, 「Desop」, 「行简」 y 「Serica」 pertenecen a Ntarstudio. MIT y Apache-2.0 conceden solo derechos de autor, no derechos de marca.

Copyright (c) 2024–2026 星玖工作室 Ntarstudio

---

## 20. NOTICE — Cumplimiento de código abierto

Cada componente y recurso de terceros utilizado por este proyecto se divulga elemento por elemento en [NOTICE](NOTICE).

| Componente | Inclusión | Licencia | Modificación |
|---|---|---|---|
| asorn/asorn-open | Derivación de código | Apache-2.0 | Modificado (interfaz y estructura rediseñadas) |
| anime.js v2.0.2 | Archivo completo incrustado | MIT | Sin modificar |
| Typed.js 2.0.16 | CDN unpkg | MIT | Sin modificar |

**Se cumplen las obligaciones de la cláusula 4 de Apache-2.0**: se conservan el aviso de copyright original, el texto completo de la licencia y una declaración de cambios.

**Procedimiento para añadir un componente de terceros**: confirmar la compatibilidad de licencia con el MIT / Apache-2.0 de este proyecto → registrarlo en `NOTICE` (nombre, versión, titular, licencia, dirección, uso, modificación) → luego hacer commit. Cuando no se pueda confirmar una licencia, marcarla como «no confirmada» y suspender la fusión.

---

Ntarstudio · <https://www.ntars.cn/>