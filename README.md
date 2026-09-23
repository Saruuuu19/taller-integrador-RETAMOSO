# Taller: Corrección y refactorización de una página web

**Autor:** Andres Retamoso

Sitio publicado: `[PEGA AQUÍ EL ENLACE AL SITIO PUBLICADO]`
_(por ejemplo: `https://usuario.github.io/nombre-del-repo/`)_

## Hallazgos

| Defecto | Por qué era un problema | Cómo lo corregí |
| --- | --- | --- |
| Variables y función con nombres poco descriptivos (`x`, `TempValue2`, `a`, `b`, `c`, `calc()`) y variable sin usar (`data1`) | Difícil de leer y mantener: no expresaban qué representaban ni para qué servían, y `data1` era código muerto que generaba ruido. | Renombré a `CANTIDAD_NOTAS` y `NOTA_MINIMA_APROBACION` (constantes), `promedio`, `nota1`/`nota2`/`nota3` y `calcularPromedio()`; eliminé `data1`. |
| IDs y clase con nombres crípticos (`n1`, `n2`, `n3`, `r`, `r2`, `cont1`) | Obligaban a recordar qué significaba cada uno y había que cruzar el HTML, el CSS y el JavaScript a mano para saber qué elemento correspondía a cada nombre. | Renombré a `nota1`, `nota2`, `nota3`, `resultadoPromedio`, `resultadoEstado` y `contenedorPrincipal`, actualizando los `getElementById` y los selectores del CSS. |
| `<title>` genérico (`pagina`) | El usuario no distinguía la pestaña de otras y los lectores de pantalla la anunciaban sin sentido; malas prácticas de accesibilidad y SEO. | Lo cambié a `Calculadora de Promedio`. |
| Código muerto: función comentada `calcularAntiguo`, `console.log` de depuración y `data1` sin usar | Confundía a quien leyera el código (¿se usa o no?), ensuciaba la consola del navegador con mensajes de depuración y aumentaba el tamaño sin aportar nada. | Eliminé la función comentada, los tres `console.log` y la variable `data1`. |
| Formato e indentación inconsistentes (bloque `<script>` sin sangría dentro de `<body>`, líneas en blanco sueltas) | Dificultaba la lectura, provocaba ruido en los diffs y diferencias espurias al comparar versiones. | Apliqué indentación de 4 espacios de forma consistente y una estructura uniforme en ambos archivos. |
| Archivos con espacios, mayúsculas y extensión en mayúsculas (`Mi Pagina De Notas.HTML`, `Estilos Del Sitio.CSS`), con el `href` apuntando a `styles.css` | Los nombres con espacios y mayúsculas son incómodos de trabajar en terminal y en Git, y el desajuste de mayúsculas rompía la hoja de estilos en servidores sensibles a mayúsculas (p. ej. GitHub Pages). | Renombré los archivos a `index.html` y `styles.css`, dejando el `href` coincidiendo exactamente. |
