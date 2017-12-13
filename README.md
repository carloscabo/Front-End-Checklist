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

## Responsive y crossbroser

- [ ] Revisar en: desktop ( 1920w ), tablet ( iPad ), mobile ( 360w )
- [ ] Revisar en small-desktop ( MacBook Air 11" 1366x600 )
  - ¿Elemenos importante que queden fuera del _fold_?
- [ ] Chrome
- [ ] Firefox
- [ ] Safari
- [ ] IE11
- [ ] Edge
