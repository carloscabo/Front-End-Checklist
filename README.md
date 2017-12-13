# front-end-checklist

Lista de recursos y checklist para realizar comprobación de un site / proyecto antes de pasar a producción.

## Salida a producción

- [ ] Comprobar que están todos los [elementos del layout base](https://github.com/carloscabo/front-end-checklist/blob/master/resources/layout.html)
  - Favicon ( [convertico.com](http://convertico.com/) )
  - `lang` en el `head`
  - OpenGraph
  - Twitter Card
  - etc.
- [ ] Uso de elementos semanticos cuando sea posible ( `header`, `section`, `footer`, `main` )
- [ ] [Detectar IE con JS](https://gist.github.com/carloscabo/1b92432965e141d03f27771b6212b98f) porque IE [ya no soporta los comentarios condiconales](https://msdn.microsoft.com/en-us/library/hh801214(v=vs.85).aspx)
- [ ] [Valida en HTML en el W3C](https://validator.w3.org/)
  - Ayuda a detectar errores típicos de JS
  - Puede ayudar a prevenir errores graves como tener varios `id` o varios `h1` en la página
- [ ] Testear con el AdBlocker puesto
- [ ] Revisar la consola para enlaces rotos o errores de JS
- [ ] Hay un sistema que añada prefijos al CSS ( postCSS? )
- [ ] JS y el CSS concatenados y minificados
  - Idealmente un fichero de JS y uno de CSS
  - Tenmos puesto el linter de JS en el editor SIEMPRE
  - El JS al final del `body`
  - Si hay CSS crítico ponerlo _inline_ en el `head`

## Páginas

  - [ ] Pagína 404 / 500

## Responsive y crossbroser

- [ ] Revisar en: desktop ( 1920w ), tablet ( iPad, 768w ), mobile ( 360w )
  - Se adapata de forma fluida en resoluciones intermedias
- [ ] Revisar en small-desktop ( MacBook Air 11" 1366x600 )
  - ¿Elemenos importante que queden fuera del _fold_?
- [ ] Chrome
- [ ] Firefox
- [ ] Safari
- [ ] IE11
- [ ] Edge
- [ ] Simlador de iOS al menos para iPhone

## Imágenes

- [ ] optimizar imágenes estáticas
  - [ImageOptim](https://imageoptim.com/es.html)
  - [TinyPNG](https://tinypng.com/) para PNGs con zonas transparentes grandes que pesen mucho
  - [SVGO](https://github.com/svg/svgo) para optimzar los SVGs
- [ ] Alternativas para móviles
 - Usaremos `picture` si necesitamos que haya alternativas para mobile. Hay un [bonito _polyfill_ para IE10](http://scottjehl.github.io/picturefill/)
- [ ] Usaamos _lazyload_ para componentes / páginas que usen muchos elementos de imagen

## Contenido y SEO

- [ ] Todas las imágenes tienen `alt`  
  ```css
    /* Para resaltarlas en el navegador ;) */
    img[alt=""],
    img:not([alt]) {
      border: 5px dashed #c000;
    }
  ```
  - [ ] Echar un ojo a las [guidelines de Accesibildiad de WGAC 2.0](https://www.w3.org/TR/2006/WD-WCAG20-20060427/appendixB.html)
    - En organismos institucionales o grandes empresas puede ser obligatorio cumplir un `A` o incluso un `AA`.
  - [ ] los _breadcrumbs_ tienen el [marcado de microformatos](https://developers.google.com/search/docs/data-types/breadcrumbs)
    - ¿Hay que añadir microformatos en otros contenidos? [http://schema.org](http://schema.org/docs/gs.html)
      - Videos
      - Paginación
      - etc.
  - [ ] Los formularios se pueden nevagar con `tab`
  - [ ] Hay un sitemap.xml
  
## Performace

  - [ ] Echar un ojo en ChromeDev Tools **LightHouse**
  - [ ] Echar un ojo en [PageSpeed Insights](https://developers.google.com/speed/pagespeed/insights/)
  - [ ] HTML Minificado (esto es de nota)