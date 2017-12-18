# front-end-checklist

Lista de recursos y checklist para realizar comprobación de un site / proyecto antes de pasar a producción.

Está indicada la **prioridad de cada acción / comprobación **. ![High][high_img] y ![Medium][medium_img] son las prioridades que debemos comprobar **siempre que sea posible**. Hemos marcado como ![Low][low_img] aquellas que nos parecen menos prioritarias o que **dependen de las características técnicas del proyecto**.

## Generales. Salida a producción

- [ ] ![High][high_img] Comprobar que están todos los [elementos del layout base](https://github.com/carloscabo/front-end-checklist/blob/master/resources/layout.html)
  - Favicon ( [convertico.com](http://convertico.com/) )
  - `lang` en el `head`
  - OpenGraph
  - Twitter Card
- [ ] ![Medium][medium_img] Uso de elementos semanticos cuando sea posible ( `header`, `section`, `articles`, `footer`, `main` )
- [ ] ![Medium][medium_img] [Detectar IE con JS](https://gist.github.com/carloscabo/1b92432965e141d03f27771b6212b98f) porque IE [ya no soporta los comentarios condicionales](https://msdn.microsoft.com/en-us/library/hh801214(v=vs.85).aspx)
- [ ] ![High][high_img] [Valida en HTML en el W3C](https://validator.w3.org/)
  - Ayuda a detectar errores típicos de HTML
  - Puede ayudar a prevenir errores graves como tener varios `id` o varios `h1` en la página que pueden inclusi generar problemas en JS.
- [ ] ![High][high_img] Testear con el **AdBlocker** puesto
- [ ] ![High][high_img] Revisar la consola para enlaces rotos o errores de JS
- [ ] ![Medium][medium_img] Hay un sistema que añada prefijos al CSS ( postCSS? )
- [ ] ![High][high_img] JS y el CSS concatenados y minificados
  - ![High][high_img] Tenemos puesto el linter de JS en el editor SIEMPRE
  - Idealmente un fichero de JS y uno de CSS
  - El JS al final del `body` (normalmente es lo mejor)
  - Si hay CSS crítico ponerlo _inline_ en el `head`

Línea intencionalmente vacía.

## Funcionalidad

  - [ ] ![High][high_img] Funciona la validación de formularios
  - [ ] ![Medium][medium_img] Los formularios se pueden nevagar con `tab`

## &nbsp;Páginas

  - [ ] ![High][high_img] Página 404 / 500
  - [ ] ![High][high_img] ¿Hay emails o newsletters? ( <https://www.emailonacid.com/> )

## Responsive y crossbrowser

- [ ] ![High][high_img] Revisar en: desktop ( **1920w** ), tablet ( iPad, **768w** y **1024w** _landscape_ ), mobile ( **360w** )
  - ![Medium][medium_img] Se adapta de forma fluida en resoluciones intermedias
- [ ] ![High][high_img] Revisar en small-desktop ( MacBook Air 11" **1366x600** )
  - ![Low][low_img] ¿Elementos importante que queden fuera del _fold_?
- **Navegadores y SOs**
  - [ ] ![High][high_img] Chrome
  - [ ] ![High][high_img] Firefox
  - [ ] ![High][high_img] Safari
  - [ ] ![High][high_img] IE11
  - [ ] ![High][high_img] Edge
  - [ ] ![High][high_img] Simulador de iOS al menos para iPhone
  - [ ] ![High][high_img] Chrome de Android última versión

## Imágenes

- [ ] ![Medium][medium_img] Optimizar imágenes estáticas
  - [ImageOptim](https://imageoptim.com/es.html)
  - [TinyPNG](https://tinypng.com/) para PNGs con zonas transparentes grandes que pesen mucho
  - [SVGO](https://github.com/svg/svgo) para optimzar los SVGs
- [ ] ![Medium][medium_img] Alternativas para móviles
  - Usaremos `picture` si necesitamos que haya alternativas para mobile. Hay un [bonito _polyfill_ para IE10+](http://scottjehl.github.io/picturefill/)
- [ ] ![Low][low_img] Usamos _lazyload_ para componentes / páginas que usen muchos elementos de imagen

## Contenido y SEO

- [ ] ![Low][low_img] Hay un `robots.txt`
- [ ] ![Low][low_img] Todas las imágenes tienen `alt`  
  ```css
    /* Para resaltarlas en el navegador ;) */
    img[alt=""],
    img:not([alt]) {
      border: 5px dashed #c000;
    }
  ```
  - [ ] ![Low][low_img] Echar un ojo a las [guidelines de Accesibildiad de WGAC 2.0](https://www.w3.org/TR/2006/WD-WCAG20-20060427/appendixB.html)
    - En organismos institucionales o grandes empresas puede ser obligatorio cumplir un `A` o incluso un `AA`.
  - [ ] ![High][high_img] Los _breadcrumbs_ tienen el [marcado de microformatos](https://developers.google.com/search/docs/data-types/breadcrumbs)
    - ![Low][low_img] ¿Hay que añadir microformatos en otros contenidos? [http://schema.org](http://schema.org/docs/gs.html)
      - Videos
      - Paginación
      - etc.
  - [ ] ![Low][low_img] Hay un sitemap.xml

## Documentación

  - [ ] ![High][high_img] En el README del proyecto están todas las herramientas que se usan para el site.
    - Por ejemplo: ¿Se usa fontcustom? ¿Se usa IconMoon? ¿Donde está la configuración?

## Performace

  - [ ] ![Medium][medium_img] Echar un ojo en ChromeDev Tools **LightHouse**
  - [ ] ![Medium][medium_img] Echar un ojo en [PageSpeed Insights](https://developers.google.com/speed/pagespeed/insights/)
  - [ ] ![Low][low_img] HTML Minificado (esto es de nota)

[low_img]: https://rawgit.com/carloscabo/front-end-checklist/master/resources/img/low.svg
[medium_img]: https://rawgit.com/carloscabo/front-end-checklist/master/resources/img/medium.svg
[high_img]: https://rawgit.com/carloscabo/front-end-checklist/master/resources/img/hight.svg