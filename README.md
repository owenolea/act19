# Portal de Normativas y Planes de Estudio

## Introducción

Este proyecto consiste en una página web para consultar una selección de normativas educativas de la Dirección General de Cultura y Educación (DGCyE) de la Provincia de Buenos Aires. Su objetivo es facilitar la búsqueda de resoluciones, disposiciones y circulares mediante filtros simples y enlaces a documentos publicados en el Portal ABC.

La aplicación presenta los resultados en tarjetas y permite combinarlos según texto, tipo de norma y año. La interfaz se actualiza dinámicamente en el navegador, sin recargar la página.

## Funcionalidades

- Búsqueda por número, palabra clave o descripción.
- Filtro por tipo de norma: resolución, disposición o circular.
- Filtro por año: 2024, 2025 y 2026.
- Combinación de búsqueda y filtros.
- Búsqueda que no distingue mayúsculas ni tildes.
- Contador dinámico de resultados encontrados.
- Mensaje informativo cuando no hay coincidencias.
- Enlaces a los documentos oficiales, abiertos en una pestaña nueva.
- Diseño adaptable a celulares, tablets y computadoras.
- Estructura semántica y regiones de resultados anunciadas con `aria-live`.
- Estilos de foco visibles para facilitar la navegación con teclado.

## Desarrollo

Los registros de ejemplo se almacenan en el arreglo `baseDatosNormativas`, que contiene para cada norma un identificador, número o título, tipo, año, descripción y enlace al documento.

La función `filtrarNormativas()` obtiene los valores de los controles y utiliza `Array.prototype.filter()` para seleccionar los registros que coinciden con todos los criterios. Antes de comparar el texto, `normalizarTexto()` convierte las letras a minúsculas y elimina las marcas diacríticas, permitiendo, por ejemplo, buscar términos con o sin tilde.

La función `renderizarResultados()` actualiza el contador y muestra las tarjetas correspondientes. Si no hay coincidencias, presenta un mensaje para que se prueben otros filtros. Los filtros se aplican al cargar la página y cada vez que cambia el texto o una opción seleccionada.

## Stack tecnológico

- HTML5 semántico.
- CSS3, con diseño responsive mediante CSS Grid y media queries.
- JavaScript ES6+.
- DOM API para leer controles y actualizar resultados.
- `Array.prototype.filter()` para filtrar las normativas.
- Google Chrome u otro navegador moderno.
- Visual Studio Code (entorno sugerido).

## Arquitectura

La aplicación está implementada como una página independiente:

- **Presentación:** estructura HTML, buscador, filtros y contenedores de resultados.
- **Estilos:** reglas CSS incluidas en el bloque `<style>` de `index.html`.
- **Comportamiento y datos:** funciones JavaScript y arreglo de normativas incluidos en el bloque `<script>` de `index.html`.
- **Fuentes documentales:** enlaces a documentos alojados en el Portal ABC de la DGCyE.

No requiere instalación de dependencias ni servicios externos para ejecutar el filtrado. Se necesita conexión a internet para abrir los documentos enlazados.

## Estructura del repositorio

```text
act19-main/
├── index.html   # Interfaz, estilos, datos de ejemplo y lógica del buscador
└── README.md    # Documentación del proyecto
```

## Ejecución

1. Descargá o cloná el repositorio.
2. Abrí `index.html` directamente en un navegador, o ejecutalo con una extensión de servidor local como Live Server.
3. Ingresá un texto de búsqueda y, si lo necesitás, seleccioná el tipo de norma o el año.
4. Usá el enlace de cada resultado para consultar el documento oficial.

## Fuentes y alcance de los datos

El proyecto incluye una selección breve de normativas a modo de muestra. No es un catálogo oficial exhaustivo ni reemplaza la consulta de las publicaciones vigentes de la DGCyE. Verificá siempre la versión y validez de cada documento en la fuente oficial.

## Equipo de desarrollo

- Owen Olea
