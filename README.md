# SICP

<img src="http://sicpebook.files.wordpress.com/2013/09/dreamsmile3.png"
 alt="Par dreaming and smiling" align="right" />

<b>Link directo: [sicp.pdf](https://github.com/mateodif/sicp-pdf-es/raw/master/sicp.pdf)</b>
Esta es una versión en PDF de "Estructura e Interpretación de Programas de Computadora" de Harold Abelson, Gerald Jay Sussman y Julie Sussman. Es un desarrollo adicional del [Formato Texinfo No Oficial] (http://www.neilvandyke.org/sicp-texi/) (UTF), que originalmente se derivó de la [versión HTML](http://mitpress.mit.edu/sicp/) en The MIT Press.

El cambio más grande en la revisión (2.5) es la conversión a LaTeX, lo cual abre la puerta a posibilidades de diseño y personalización que el masivo archivo CTAN permite. Además, se puede utilizar el último motor de composición tipográfica, XeTeX, junto con las bondades de Unicode y OpenType que trae consigo.

Y ahora, en la revisión "3.0" (que me estoy tomando la libertad de reclamar), estoy traduciendolo a Español con ayuda de ChatGPT.
Por ahora, estoy usando una query similar a la siguiente:

```
The following is an excerpt from Structure and Interpretation of Computer Programs, a Computer Science book written in English. Rewrite it as though it were originally written by a native Spanish speaker. It's extremely important that you keep all Texinfo markup:

<texto>
```

No funciona del todo bien, así que voy arreglando cosas manualmente. ¡Cualquier sugerencia es bienvenida!


## Dependencias

Para compilar de forma adecuada este libro, necesitas estas fuentes:

- **Inconsolata**: [ttf-inconsolata](https://archlinux.org/packages/community/any/ttf-inconsolata/)
- **Libertinus**: [libertinus-font](https://archlinux.org/packages/community/any/libertinus-font/)
- **Alegreya**: <https://github.com/huertatipografica/Alegreya>

## Código fuente
*Para usuarios de macOS:* Las fuentes Inconsolata LGC y Linux Libertine no están incluidas en MacTex. Necesitas instalarlas por separado. Descarga las fuentes Inconsolata LGC [aquí](https://github.com/MihailJP/Inconsolata-LGC/downloads) y las fuentes Linux Libertine [aquí](http://sourceforge.net/projects/linuxlibertine/files/linuxlibertine/5.3.0/LinLibertineOTF_5.3.0_2012_07_02.tgz/download). Para instalar las fuentes en todo el sistema, mueve todos los archivos `.otf` descargados a la carpeta `/Library/Fonts`. Después de completar estas tareas, continúa con las instrucciones a continuación.

El directorio `src` contiene tanto las fuentes de Texinfo como las de LaTeX. Para volver a compilar el libro, cambia a ese directorio y haz:

```bash
$ make -j4
```

El archivo `preamble.tex` contiene todas la configuración y estilo. Ten en cuenta que el archivo LaTeX `sicp.tex` se generará automáticamente, sobrescribiendo la versión anterior. Para mantener `sicp.texi` y `sicp.tex` sincronizados, hago cambios en `sicp.texi`, que ya es una combinación de código Texinfo y LaTeX. Esto está bien, porque todo el contenido no-Texinfo permanece sin cambios por el script.

Las posibilidades de una compilación exitosa aumentan si tienes una instalación casi completa de la distribución reciente de TeX Live (el PDF aquí está compilado con la versión de 2012). Las fuentes OpenType necesarias deben estar instaladas en el sistema operativo. También necesitas Inkscape para recrear imágenes PDF a partir de SVGs.

Si la compilación se detiene con "Error de LaTeX: Demasiados flotantes no procesados.", puedes intentar aumentar el ancho y la altura del área de texto en [preamble](https://github.com/sarabander/sicp-pdf/blob/master/src/preamble.tex#L70-L71). Nuevas versiones de TeX Live o fuentes actualizadas podrían resultar en diferentes métricas de caracteres, de modo que algunas figuras ya no encajen. El problema se informa en el issue #5 [#5](https://github.com/sarabander/sicp-pdf/issues/5) del repo original.

Para limpiar luego de la compilación:

```bash
$ make clean
```

Esto borra los archivos temporales durante la creación de `sicp.pdf`, incluyendo `sicp.pdf` en sí. Muévelo a la carpeta raíz si quieres conservarlo.

Para eliminar todos los PDF generados y archivos auxiliares en todo el directorio `src`:

```bash
$ make clean-all
```

## Agradecimientos

* Lytha Ayth
* Neil Van Dyke
* Gavrie Philipson
* J. E. Johnson
* Mingshen Sun
* holomorph
* Narumi Katoh
* tfgit
* Brian Wignall
* dine2014

## Licencia

Los archivos `sicp.texi`, `sicp.pdf` y los diagramas en el directorio `src/fig` están licenciados bajo la Licencia Internacional de Creative Commons Atribución-CompartirIgual 4.0 ([cc by-sa](https://creativecommons.org/licenses/by-sa/4.0/)).

Los archivos de script `ex-fig-ref.pl`, `survey.rb` y `texi-to-latex.pl` están licenciados bajo la Licencia Pública General de GNU versión 3 (para más detalles, ver src/LICENSE).

## Proyecto hermano

Hay una nueva [versión HTML5](https://github.com/sarabander/sicp) disponible que permite ajustar el tamaño de fuente y el flujo del texto para una mejor lectura en dispositivos móviles.

## Traducción

Hay una nueva [traducción al japonés](https://github.com/minghai/sicp-pdf/) del PDF hecha por Narumi Katoh. ¡Es genial ver que se suman nuevos idiomas a la colección!

