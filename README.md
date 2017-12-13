# front-end-checklist

Lista de recursos y checklist para realizar comprobación de un site / proyecto antes de pasar a producción.

## Salida a producción

- [ ] Comprobar que están todos los [elementos del layout base](https://github.com/carloscabo/front-end-checklist/blob/master/resources/layout.html)
- [ ] Uso de elementos semanticos cuando sea posible ( `header`, `section`, `footer`, `main` )
- [ ] Valida en HTML en el W3C
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

## Contenido

- [ ] Todas las imágenes tienen `alt`  
  ```css
    img[alt=""],
    img:not([alt]) {
      border: 5px dashed #c000;
    }
  ```