[简体中文](README.md) | [English](README_EN.md) | [日本語](README_JA.md) | [한국어](README_KO.md) | [Français](README_FR.md) | [Русский](README_RU.md) | **Español** | [العربية](README_AR.md)

# Apex

**El sitio oficial de Ntarstudio (星玖工作室) — y el índice de los quince proyectos.**

> **Este repositorio tiene dos roles**: es el código fuente del sitio del estudio (un archivo HTML, una hoja de estilos, unos pocos scripts nativos) y es **el índice de los quince proyectos**. Este documento se centra en lo segundo: qué es cada proyecto, en qué punto está y dónde mirar. La implementación del sitio se comprime en el capítulo 5 y se mantiene deliberadamente breve.

![Status](https://img.shields.io/badge/status-online-2ea44f?style=flat-square)
[![GitHub license](https://img.shields.io/github/license/ntars/Apex?style=flat-square)](./LICENSE)
[![GitHub Star](https://img.shields.io/github/stars/ntars/Apex?style=flat-square)](https://github.com/ntars/Apex/stargazers)
[![GitHub Fork](https://img.shields.io/github/forks/ntars/Apex?style=flat-square)](https://github.com/ntars/Apex/network/members)
![GitHub Repo size](https://img.shields.io/github/repo-size/ntars/Apex?style=flat-square&color=3cb371)

[![Live](https://img.shields.io/badge/live-www.ntars.cn-0078d4.svg?style=flat-square)](https://www.ntars.cn/)
[![Projects](https://img.shields.io/badge/projects-15-8957e5.svg?style=flat-square)](#)
[![Build](https://img.shields.io/badge/build-none-2ea44f.svg?style=flat-square)](#)

---

## 1. Nombre y posicionamiento

> **仓库描述 / Description**：`星玖工作室官网与十五个开源项目总索引：一个 HTML、一份样式表、几个原生脚本 | The Ntarstudio official site and an index of fifteen open-source projects, in one HTML file and a stylesheet.`
>
> **话题标签 / Topics**（20 个，仅英文）：`frontend`, `landing-page`, `no-framework`, `personal-website`, `portfolio-site`, `pwa`, `service-worker`, `single-page`, `static-site`, `studio-website`, `vanilla-css`, `vanilla-javascript`, `ntarstudio`, `chinese-website`, `html`, `css`, `javascript`, `dark-mode`, `responsive-design`, `no-dependencies`


**Nombre**: Apex, «cumbre». Como sitio oficial del estudio desempeña el papel de una entrada, no de un producto.

**Posicionamiento en una línea**: un sitio estático de una sola página, sin dependencias ni compilación, que enuncia tres cosas con el mínimo código: quién es, qué se construye y dónde mirar.

**Tres límites**:

1. **Es una placa, no una sala de exposiciones.** No incluye funciones de producto, demostraciones en línea ni documentación incrustada. El visitante avanza mediante enlaces directos a cada proyecto.
2. **Son archivos estáticos, no una aplicación.** Sin backend, sin base de datos, sin cuentas. Todo el contenido está escrito en `index.html`; cambiar una línea de texto es un commit.
3. **Es un índice, no una fuente de contenido.** La información real de un proyecto vive en su propio repositorio y su propio sitio. Esta página resume y enlaza; no duplica.

**Por qué este README se centra en los proyectos**: la sección «星玖工作室出品» de la página de inicio enumera los quince proyectos. Esa lista, el capítulo 3 de este documento y el README de perfil de GitHub son tres representaciones de una misma fuente. **Quien quiera una idea rápida de lo que construye el estudio solo necesita esta página** — no hace falta abrir quince repositorios.

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

## 3. Funciones principales

El bloque «星玖工作室出品» de la página de inicio muestra quince proyectos en un único orden alfabético latino; cada tarjeta indica su propio estado, y la formulación de los estados se define en 3.2.

**Los quince proyectos son Amphoreus, Apex, Chiubay, Desop, Flutter-IDE, Gitrule-skill, NovaKit, Ondra, Relax, Serica, TapMC, Taycho-OS, Wacmin, Webroit y Xael.** GitHub los aloja y no es un proyecto; las cuatro direcciones internas de Wacmin son un detalle de implementación y no se enumeran por separado.

### 3.1 Todos los proyectos (A–Z)

> Los quince proyectos se ordenan en un único orden alfabético latino, sin agrupar por estado; un proyecto nuevo se inserta en su posición, nunca se añade al final. Esta lista, el arreglo `PROJECTS` del sitio y el [perfil de ntars](https://github.com/ntars/ntars) se mantienen idénticos. La formulación de los estados se define en 3.2.

#### Amphoreus · En desarrollo

| | |
|---|---|
| Qué es | Una recreación uno a uno del «Libro tal como lo escribo» de Amphoreus, de Honkai: Star Rail, convertida en un mundo simulado que funciona solo: doce Titanes, trece Herederos Dorados y doce Brasas calculados a partir de una semilla, y la misma semilla produce siempre la misma historia |
| Tecnología | Python 3.11+ (solo biblioteca estándar) · SQLite · HTML / CSS / Vanilla JS |
| Estado | En desarrollo: el simulador funciona y `/book` está disponible; faltan las capturas de referencia oficiales, así que no se afirma coincidencia al píxel |
| Plataformas | macOS / Linux / Windows (solo biblioteca estándar) |
| Licencia | MIT |
| Repositorio | <https://github.com/ntars/Amphoreus> |

La misma semilla da siempre la misma historia; otra semilla da otro Amphoreus. El motor de reglas decide *qué ocurrió* y el modelo local solo *cómo se cuenta*. En ejecución la página no carga mapas de bits ni SVG: todas las formas se dibujan con degradados, bordes y `clip-path`.

**Por qué vale la pena verlo**: convierte «narrativa determinista» e «interfaz sin imágenes» en restricciones de ingeniería verificables, no en una demostración de concepto.

#### Apex · En línea

| | |
|---|---|
| Qué es | El sitio que está leyendo: la placa del estudio y el índice de todos los proyectos |
| Tecnología | HTML · CSS · Vanilla JS |
| Licencia | MIT (las reglas derivadas de asorn/asorn-open son Apache-2.0, véase [LICENSING.md](LICENSING.md)) |
| Entrada | <https://www.ntars.cn/> |
| Repositorio | <https://github.com/ntars/Apex> |

Un archivo HTML, una hoja de estilos y unos pocos scripts nativos. Sin framework, sin compilación, sin backend. Cero dependencias significa que ninguna cadena de herramientas podrá romperlo más adelante.

**Por qué vale la pena verlo**: es una muestra de front-end sin compilación: cómo un solo archivo HTML organiza todo un sitio sin depender de una cadena de herramientas condenada a quedar obsoleta.

#### Chiubay (玖白) · Prototipo de investigación

| | |
|---|---|
| Qué es | Criar un agente desde cero a largo plazo: investigación personal sobre mecanismos de AGI, construida como seis bucles de desarrollo |
| Tecnología | Python · NumPy (tensores propios y retropropagación escrita a mano; sin torch, JAX ni pesos preentrenados) |
| Estado | Prototipo de investigación: la pila de tensores propia y el experimento E3 sobre identidad funcionan; los otros cinco bucles siguen en papel |
| Licencia | Apache-2.0 / MIT |
| Repositorio | <https://github.com/ntars/Chiubay> |

El objetivo no es entregar una AGI de nivel humano, sino descomponer «cómo se cría un agente hasta tomar forma» en experimentos de mecanismos refutables. Cada informe dice solo lo que se verificó, nunca que se alcanzó la AGI.

**Por qué vale la pena verlo**: publica las reglas de entrenamiento, el protocolo de evaluación y los límites de fallo, y trata la brecha de cómputo como un límite físico, no como un problema de optimización.

#### Desop · MVP compilable

| | |
|---|---|
| Qué es | Una suite de escritorio estilo macOS para Windows: dock, barra superior, widgets de escritorio e isla dinámica |
| Tecnología | Python 3.10+ · PySide6 (modo usuario) |
| Versión | `0.2.0` |
| Licencia | Apache-2.0 / MIT |
| Repositorio | <https://github.com/ntars/Desop> |

Sin cambios en el sistema, en modo usuario puro; al desinstalar, el escritorio vuelve a su estado original. Los cuatro componentes comparten un juego de tokens de diseño y se activan por separado. El presupuesto de rendimiento es un criterio de publicación: CPU inactiva < 1 %, memoria < 150 MB, ampliación del dock ≥ 55 fps; si no se cumple, no se publica.

**Por qué vale la pena verlo**: responde a la queja habitual de que las herramientas de estética ralentizan el equipo con cifras concretas, no con «ya optimizaremos».

#### Flutter-IDE · Disponible, 0.2.0

| | |
|---|---|
| Qué es | Un IDE visual de Flutter centrado en el código: arrastrar widgets en un lienzo, editar valores en un panel de propiedades y conservar Dart mantenible sin la herramienta |
| Tecnología | Dart 3.14+ · Flutter Desktop |
| Versión | `0.2.0` |
| Estado | Disponible: validación y generación por CLI, árbol de archivos y edición con varias pestañas, arrastre en lienzo, edición de propiedades, selección por VM y recarga en caliente, distribución macOS DMG/ZIP |
| Licencia | Apache-2.0 / MIT |
| Repositorio | <https://github.com/ntars/Flutter-IDE> |

El único criterio para decidir si el proyecto debe existir: borre el IDE y compruebe si el proyecto sigue pasando `flutter run`. Por eso los contornos de intención, las capas y los tokens de diseño son archivos de texto versionados en git; ninguna estructura del proyecto vive solo dentro de la herramienta.

**Por qué vale la pena verlo**: «no quedar encerrado en una herramienta» está escrito como tres criterios de aceptación —sin esquema privado, un cambio produce un solo diff, la misma entrada genera dos veces el mismo resultado— y no como un eslogan.

#### Gitrule-skill · Entregado

| | |
|---|---|
| Qué es | Un conjunto de especificaciones que cubre todo el ciclo de vida de un proyecto: concepción, requisitos, arquitectura, desarrollo, pruebas, despliegue, operación e iteración, además de documentación, cumplimiento y acceso programático para agentes de IA |
| Tecnología | Markdown (sin dependencias de terceros) · CLI en Python · servidor MCP |
| Alcance | 68 especificaciones × 12 idiomas, con los mismos identificadores correspondidos uno a uno en cada directorio de idioma |
| Estado | Entregado: la CLI informa 0 problemas; el Skill, el paquete para expertos y el servidor MCP están disponibles |
| Licencia | MIT |
| Repositorio | <https://github.com/ntars/Gitrule-skill> |

Una especificación por archivo, independiente y consultada según necesidad. Una CLI sin dependencias comprueba enlaces rotos, archivos huérfanos, frases de responsabilidad, bloques de código, recuentos del índice y registro de marcadores; `optimize` solo aplica correcciones seguras de automatizar.

**Por qué vale la pena verlo**: convierte convenciones —qué 20 capítulos necesita un README, cómo se nombra un repositorio, cómo se definen la descripción y los temas— en archivos y comandos verificables. La alineación documental de los quince repositorios lo tomó como única referencia.

#### NovaKit · Etapa de esqueleto

| | |
|---|---|
| Qué es | Las primeras herramientas tras instalar el sistema: archivos, imágenes, texto y utilidades del sistema en una suite sin conexión, sin red y sin cuenta |
| Tecnología | Rust (edition 2024) · Tauri 2 |
| Estado | Etapa de esqueleto: el proyecto y la lista de 36 herramientas están fijados, el código de negocio se está escribiendo, sin versión publicada |
| Plataformas | macOS primero; Windows / Linux planificados |
| Licencia | Apache-2.0 / MIT |
| Repositorio | <https://github.com/ntars/NovaKit> |

Las herramientas se organizan en cuatro niveles —Rust puro, capacidad del sistema, componente externo y complemento de proceso—, cada uno con su implementación y método de aceptación. Los complementos hablan JSON-RPC 2.0 sobre stdio y todos los permisos se deniegan por defecto.

**Por qué vale la pena verlo**: deriva la lista de herramientas de «qué se necesita la primera semana tras instalar el sistema» y fija la frontera de seguridad por niveles en lugar de crecer hasta ser una suite todoterreno.

#### Ondra (空谷) · Beta interna, 3.0.0-alpha.22

| | |
|---|---|
| Qué es | Un compañero de IA de escritorio basado en complementos: la interfaz solo lee las proyecciones de los complementos; emoción, memoria y contexto son los tres mecanismos centrales; todos los datos quedan en la máquina |
| Tecnología | Flutter (escritorio y web) · Cordis 4.1.0 (marco de complementos) · núcleo dsh (Node) |
| Versión | Beta `3.0.0-alpha.22` |
| Plataformas | macOS funciona; Windows tiene paquete de publicación; el núcleo Android arranca en dispositivo (pendiente el apretón de manos real); la web compila; iOS / OHOS solo tienen proyectos generados |
| Licencia | Apache-2.0 / MIT |
| Entrada | <https://ai.ntars.cn/> |
| Repositorio | <https://github.com/ntars/Ondra> |

Tres mecanismos centrales: emoción (una variable de estado con inercia), memoria (una cadena de once eslabones) y contexto (prefijo congelado + inyección incremental + empaquetado de presupuesto). La página de complementos reúne 18 entradas incluidas y 75 de la capa de ensamblaje: 93 en total, cada una activable.

**Por qué vale la pena verlo**: descompone la compañía en mecanismos que se pueden ingenierizar por separado, y un parche del orden de arranque redujo de 55 a cero las degradaciones silenciosas de 18 complementos causadas por `apply` concurrentes. Solo hay una capa de proyección entre la interfaz y los complementos, así que las páginas nunca guardan estado interno de un complemento.

#### Relax (悠然) · Desarrollo temprano

| | |
|---|---|
| Qué es | Una plataforma familiar autoalojada: chat, calendario, archivos y fotos; un solo servidor de un proceso, clientes Android y datos que no salen de casa |
| Tecnología | Rust · Tauri 2 · axum · SQLite · React + TypeScript |
| Estado | Desarrollo temprano: los esqueletos de rutas del servidor (autenticación, sincronización, chat, avisos, calendario y archivos) están puestos; el ciclo de negocio no está terminado |
| Plataformas | Servidor en macOS / Linux; cliente en Android API 24+ |
| Licencia | Apache-2.0 / MIT |
| Repositorio | <https://github.com/ntars/Relax> |

Toda la lógica de negocio vive en Rust: el front-end solo dibuja y llama a `invoke()`, no hace peticiones de red, no se conecta directamente a SQLite y no persiste tokens. Los mensajes entran en una outbox y se envían de forma idempotente por `opId` tras la recuperación.

**Por qué vale la pena verlo**: convierte la «soberanía de los datos» en cinco cerraduras arquitectónicas verificables por máquina, no en un eslogan de privacidad.

#### Serica (行简) · Especificación congelada, implementación detenida en el lexer

| | |
|---|---|
| Qué es | Un lenguaje de programación para aplicaciones sincronizadas entre dispositivos: todo en chino, fuentes `.serica`, comando `serica` y ejecutables nativos como salida |
| Tecnología | Go (compilador semilla stage0) · ruta de autoalojamiento · escribe Mach-O directamente |
| Versión | Especificación v3.1 congelada; la implementación semilla se detiene en el lexer y `check`: la generación de IR (M3) y de código (M4) no está implementada, así que aún no puede producirse ningún ejecutable |
| Alcance | 1928 líneas de semilla frente a un límite de 5000, con tabla de atribución línea por línea; el directorio semilla se elimina tras el autoalojamiento |
| Licencia | Apache-2.0 |
| Plataformas | Verificado solo en macOS arm64 |
| Repositorio | <https://github.com/ntars/Serica> |

Por diseño, el compilador semilla no genera C ni llama a LLVM, ensamblador o enlazador: escribe Mach-O por sí mismo. La puntuación china es gramática en la capa léxica, no tipografía; el diagnóstico da la columna de puntos de código y la columna mostrada (`línea 3, columna 38 (celda 55)`). **Estos son objetivos de diseño, no capacidades actuales**: en el repositorio solo funcionan el lexer y el comando `check`; `ir` devuelve «generador de IR no implementado (M3)» y `build` «generador de código no implementado (M4)», por lo que no puede producirse ningún ejecutable y el lenguaje **no sirve para escribir software de producción**.

**Por qué vale la pena verlo**: convierte «el chino no es solo palabras clave traducidas» en restricciones verificables —límite de 5000 líneas, tabla de atribución línea por línea, borrado de la semilla tras el autoalojamiento y un tipo de salida que un solo `file` confirmará — en lugar de un documento de visión.

#### TapMC · Etapa de esqueleto, 0.1.0

| | |
|---|---|
| Qué es | Un lanzador de Minecraft Java Edition para siete plataformas: instancias, mods y entornos Java se gestionan por separado, y la interfaz y la capa de proceso se separan con un único contrato JSON-RPC |
| Tecnología | Flutter (interfaz) · Rust + eframe (envoltura nativa) · Java 21 (servidor) |
| Estado | Etapa de esqueleto: la cadena funciona; pasan 84 pruebas Java y 21 casos Dart; sin versión publicada |
| Plataformas | Web y Android compilan; las otras cinco no están verificadas |
| Licencia | Apache-2.0 / MIT |
| Repositorio | <https://github.com/ntars/TapMC> |

El backend es la única fuente de verdad y el front-end solo presenta y recoge entrada. Instancias, mods y entornos Java se gestionan por separado; la interfaz y la envoltura nativa comparten un contrato JSON-RPC. El repositorio aún contiene el código y los documentos de un servidor de pruebas temprano junto a la línea del lanzador, sin limpiar.

**Por qué vale la pena verlo**: mantiene en la interfaz la lógica compartida por siete plataformas y entrega la detección de Java y el control de procesos a la envoltura Rust, de modo que la interfaz puede cambiar sin tocar la gestión de procesos. Las capacidades sin terminar (acceso a Modrinth, resolución de dependencias, varias versiones de Java) se enumeran una a una en las limitaciones conocidas y no se cuentan como hechas.

#### Taycho-OS (太初) · Etapa de diseño (marcador de posición)

| | |
|---|---|
| Qué es | Un sistema nativo escrito desde cero en Serica: modelo de ejecución, frontera de capacidades, mecanismo de mensajes, ventanas y texto, todo rehecho |
| Tecnología | Serica (planificado) · ejecutables nativos |
| Estado | Etapa de diseño: solo documentos de diseño y un repositorio marcador; aún no hay código |
| Licencia | Apache-2.0 / MIT |
| Repositorio | <https://github.com/ntars/Taycho-OS> |

No se reutiliza ningún núcleo, runtime o pila gráfica existente; toda E/S y todo acceso al sistema debe declarar una capacidad, y lo no declarado se rechaza.

**Por qué vale la pena verlo**: enuncia «desde cero» como condiciones de frontera verificables por máquina, no como un manifiesto.

#### Wacmin · Disponible (tres direcciones publicables, AppOnWin experimental)

| | |
|---|---|
| Qué es | Una suite de interoperabilidad bidireccional entre macOS y Windows, con una capa de acceso para IA |
| Tecnología | Node.js · Python · Rust |
| Estado | Tres direcciones publicables (Mac2Win / ExeOnMac / Win2Mac); AppOnWin es experimental y no está verificado porque el entorno local no lo permite |
| Licencia | Apache-2.0 / MIT |
| Repositorio | <https://github.com/ntars/Wacmin> |

Cuatro direcciones que cruzan dos anfitriones con dos acciones; las tres primeras son publicables y la cuarta sigue siendo experimental:

| Orden | Dirección | Acción en el anfitrión | Pruebas |
|---|---|---|---|
| 1 | **Mac2Win** | Crear un instalador de Windows en un Mac | 125 |
| 2 | **ExeOnMac** | Ejecutar un programa de Windows en un Mac | 319 |
| 3 | **Win2Mac** | Crear un paquete de aplicación macOS en Windows | 121 |
| 4 | **AppOnWin** | Ejecutar un programa de macOS en Windows | Experimental, no verificado |

**Más una capa de acceso `ai/`**: una misma capa de planificación expuesta en cuatro formas —servidor MCP (para Claude Desktop, WorkBuddy y Cline), CLI unificada, Skill y paquete para expertos—. Las capas de protocolo y transporte suman menos de 900 líneas, sin dependencias de terceros; no se usó el SDK oficial.

**Por qué vale la pena verlo**: ordena el desarrollo por certeza, deja para el final el eslabón con más probabilidad de fallar y define de antemano la vía de degradación: aunque falle la última dirección, las tres primeras se sostienen. Esa dirección no ha producido un resultado de verificación reproducible, así que se marca como experimental y no cuenta como disponible. La capa `ai/` no se añadió como envoltura MCP: surgió al extraer la planificación de la envoltura hacia `directions.mjs`, y esa extracción reveló un defecto dormido: `/api/status` escribía 21 líneas de ayuda en chino en stdout en cada petición y fijaba `exitCode` en 2; la consola nunca lo notó porque no lee su propio stdout, pero la regla MCP que reserva stdout para mensajes del protocolo lo vuelve fatal.

#### Webroit · En línea

| | |
|---|---|
| Qué es | Una caja de herramientas Android en el navegador: ADB y Fastboot por WebUSB, 61 funciones implementadas y 152 planificadas |
| Tecnología | TypeScript · Vite · WebUSB · ya-webadb |
| Forma | Sitio puramente estático: sin backend, sin instalación, sin controladores |
| Licencia | Apache-2.0 / MIT |
| Entrada | <https://adb.ntars.cn/> |
| Repositorio | <https://github.com/ntars/Webroit> |

Todo lo necesario para trastear con Android pasa al navegador. El protocolo ADB se implementa sobre Tango; lo que se entrega es la interfaz y los flujos que el usuario realmente necesita —gestión de aplicaciones, navegación de archivos, terminal, duplicación de pantalla, registros y flasheo—: 61 implementadas y 152 planificadas, cada una con su nivel de riesgo.

**Por qué vale la pena verlo**: elimina toda la capa de «preparación del entorno». El camino habitual es descargar Platform-Tools → configurar PATH → instalar un controlador USB → escribir reglas udev → conectar → escribir comandos; Webroit comprime los cinco primeros pasos en «abrir la página → pulsar conectar → pulsar una función». La dificultad real nunca fue escribir comandos, sino el momento posterior a la instalación en que el dispositivo sigue sin conectar y no se sabe si es el cable, el puerto, el controlador o un `adb.exe` que aún retiene la interfaz.

**Dos puntos más**: todo el producto es un `dist/` estático, y `grep -r "http" dist/` no encuentra ninguna dirección de backend propia: «los datos no salen de esta máquina» es un hecho verificable, no una promesa. Además, cada operación lleva un nivel de riesgo: un comando copiado de otro sitio indica qué cambiará y si se puede deshacer.

#### Xael (玄玖灵犀) · En línea

| | |
|---|---|
| Qué es | Un corpus local y sin conexión de calendarios chinos y literatura adivinatoria: 22 funciones calculadas desde cero, sin tablas de consulta ni red |
| Tecnología | JavaScript (cero dependencias) · PWA · miniprograma de WeChat · uni-app |
| Versión | `5.0.0` |
| Licencia | Apache-2.0 / MIT |
| Entrada | <https://x.ntars.cn/> |
| Repositorio | <https://github.com/ntars/Xael> |

Cubre Cuatro Pilares, Zi Wei Dou Shu, Qi Men Dun Jia, Da Liu Ren, Liu Yao, Mei Hua Yi Shu, Xuan Kong Fei Xing y la elección de fechas del almanaque. La base calendárica deriva las lunas nuevas de series astronómicas en tiempo real en lugar de una tabla; veinte clásicos de dominio público sirven de texto base, cada regla corregida artículo por artículo con su nivel de evidencia indicado. El miniprograma de WeChat y la cuenta oficial se buscan con el mismo nombre.

**Por qué vale la pena verlo**: lleva hasta el final el principio «calcular en vez de consultar» y anota cada conclusión con su base textual y sus puntos de incertidumbre.

### 3.2 Formulación de estados

**El estado del sitio y el del producto no son equivalentes**: un sitio en marcha no implica software instalable, y software en marcha no implica un sitio accesible.

| Proyecto | Estado | Significado |
|---|---|---|
| Apex | En línea | El sitio funciona y el código es público |
| Gitrule-skill | Entregado | 68 especificaciones × 12 idiomas, la CLI informa 0 problemas; sin versión publicada, entrega desde la rama principal |
| Ondra | Beta interna | `3.0.0-alpha.22`: macOS funciona, Windows tiene paquete de publicación, el núcleo Android arranca en dispositivo (apretón de manos pendiente), la web compila |
| Wacmin | Disponible | Mac2Win / ExeOnMac / Win2Mac son publicables, con acceso por CLI y MCP; AppOnWin es experimental y no cuenta como disponible |
| Webroit | En línea | El sitio estático funciona en `adb.ntars.cn`, 61 funciones utilizables, código público |
| Xael | En línea | Existe una versión estable (`5.0.0`) y es utilizable |
| Amphoreus | En desarrollo | Simulador y libro funcionan en local; referencias oficiales incompletas, sin afirmación al píxel |
| Flutter-IDE | Disponible | `0.2.0`: edición de escritorio, arrastre en lienzo, panel de propiedades y distribución macOS utilizables |
| NovaKit | Etapa de esqueleto | El proyecto Tauri 2 y la lista de 36 herramientas están puestos; el código de negocio no ha comenzado |
| Chiubay | Prototipo de investigación | La pila de tensores propia y el experimento E3 funcionan; los otros cinco bucles siguen en papel |
| Taycho-OS | Etapa de diseño | Solo documentos de diseño y repositorio marcador; sin código |
| Relax | Desarrollo temprano | Esqueletos de rutas del servidor puestos; ciclo de negocio sin terminar; sin APK |
| Serica | Especificación congelada | Especificación v3.1 congelada; la implementación semilla se detiene en el lexer y la comprobación, generación de IR y de código sin implementar; sin versión, inutilizable para software de producción |
| TapMC | Etapa de esqueleto | La cadena funciona; pasan 84 pruebas Java y 21 casos Dart; sin versión publicada |
| Desop | MVP compilable | `0.2.0`: la implementación Python + PySide6 en modo usuario compila y funciona, 77 pruebas pasan, aceptación en VM Windows 11 8/8 PASS; aceptación en máquina física pendiente；los widgets de escritorio solo tienen opción de configuración, sin interfaz |

**Por qué los proyectos en etapa de diseño también aparecen en el sitio**: el sitio es la placa del estudio y muestra «lo que se está construyendo», no solo «lo que ya está hecho». Indicar el estado con claridad basta: quien lee «etapa de diseño» o «etapa de esqueleto» sabe que no hay nada que descargar, lo cual es más honesto que ocultarlo.

---

## 4. Características principales

### Destacado 1: quince proyectos en una página, tres fuentes sincronizadas

- **Nombre**: índice de página única.
- **Valor**: resuelve «para saber qué construye este estudio hay que abrir seis repositorios».
- **Implementación**: las tarjetas del sitio, el capítulo 3 de este documento y el README de perfil de GitHub listan el mismo conjunto con la misma redacción de estado.
- **Diferenciación**: la mayoría de las páginas personales solo listan lo publicado o dispersan la información en los README de cada repositorio.
- **Evidencia**: las tres listas coinciden elemento por elemento; véase la tabla de estados en 3.2.

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

**`CACHE_NAME` es actualmente `ntarstudio-v12`.** Cambiar cualquier cosa de la lista de precaché — incluido Typed.js desde CDN — obliga a incrementar la versión, o los visitantes recurrentes se quedarán en la caché antigua.

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
6. **Las tarjetas de proyectos sin publicar no tienen nada que descargar**: el coste de indicar el estado con honestidad — y la razón por la que nada planificado se describe como construido.

---

## 16. Registro de cambios

El registro vive en la página de **GitHub Releases**: <https://github.com/ntars/Apex/releases>

El README describe el estado actual del sitio; las releases registran qué cambió cada vez. Ambos nunca se mezclan.

---

## 17. Hoja de ruta

1. **Automatizar la versión de caché**: sustituir el `CACHE_NAME` escrito a mano por un hash de recursos en tiempo de compilación.
2. **Iconos de las tarjetas**: montar los iconos de los quince proyectos cuando existan; ahora todos son `icon: null`.
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