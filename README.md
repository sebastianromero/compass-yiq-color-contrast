# YIQ Color Contrast Sass function

El ojo humano es más sensible a los cambios en el rango naranja-azul que en el rango violeta-verde, por lo tanto, la luminosidad percibida de un color puede variar de acuerdo a su longitud de onda.

El modelo de espacio de color YIQ fue diseñado para tener en cuenta este sesgo.
El modelo toma en cuenta las distintas partes del color de acuerdo al impacto en nuestra percepción de la luminosidad del color. Al utilizar este espacio de color cuando se hacen comparaciones de contrastes de color, se logran pares de colores de apariencia más natural.

La extensión de Compass original: https://github.com/timhettler/compass-yiq-color-contrast

Para más información sobre color, contraste y el espacio de color YIQ:

* [**24 Ways:** Calculating Color Contrast](http://24ways.org/2010/calculating-color-contrast/)
* [**W3C:** Ensure that foreground and background color combinations provide sufficient contrast when viewed by someone having color deficits or when viewed on a black and white screen](http://www.w3.org/TR/AERT#color-contrast)
* [**Wikipedia:** YIQ](http://en.wikipedia.org/wiki/YIQ)

## Uso

  ```scss
  @import 'yiq-color-contrast'
  ```

### Variables configurables

Todas las variables están asignadas con `!default`, así que se las puede reemplazar en tu nuevo proyecto.

El color de texto que se usa cuando el color de fondo es "light" (claro)

  ```scss
  $yiq-contrasted-dark-default: #000;
  ```

El color de texto que se usa cuando el color de fondo es "dark" (oscuro)

  ```scss
  $yiq-contrasted-light-default: #fff;
  ```

A a value between 0 and 255. It determines when the lightness of color changes from "dark" to "light".

  ```scss
  $yiq-contrasted-threshold: 128;
  ```

Toggles diagnostic messages.

  ```scss
  $yiq-debug: false;
  ```

### Functions

Returns `true` if the color is "light" or `false` if it is "dark".

  ```scss
  yiq-is-light($color, [$threshold])
  ```
Returns the `$light` color when the `$color` is dark and the `$dark` color when the `$color` is light. The `$threshold` is a value between 0 and 255 and it determines when the lightness of `$color` changes from "dark" to "light".

  ```scss
  yiq-contrast-color($color, [$dark], [$light], [$threshold])
  ```

### Mixins

Sets the specified background color and calculates a dark or light contrasted text color. The arguments are passed through to the `yiq-contrast-color function`.

  ```scss
  @include yiq-contrasted($background-color, [$dark], [$light], [$threshold])
  ```

### Demo

Check out how the YIQ color contrast compares to the default Compass color contrast: http://timhettler.github.io/compass-yiq-color-contrast/

##Licencia
Licenciado bajo la licencia MIT.

Copyright &copy; 2015 Tim Hettler

Traducción Sebastian Romero
