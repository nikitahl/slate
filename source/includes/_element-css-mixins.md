# Element CSS Mixins

## CSS Mixins

> CSS Mixins *settings.json* example:

```json
{
 "color": {
   "type": "color",
   "access": "public",
   "value": "#fff",
   "options": {
     "label": "Title color",
     "cssMixin": {
       "mixin": "basicColor",
       "property": "color",
       "namePattern": "[\\da-f]+"
     }
   }
 }
}
```

> CSS Mixins *componentName/cssMixins/basicColor.pcss* example:

```css
.vce-button {
 &--color-$selector {
   color: $color;
   &:hover {
     color: color($color shade(10%));
   }
 }
}
```

> CSS Mixins *index.js* example:

```javascript
// ...
'mixins': {
  'basicColor': {
    'mixin': require('raw-loader!./cssMixins/basicColor.pcss')
  }
}
// ...
```

> CSS Mixins *component.js* example:

```javascript
// This code goes inside render() method
// get mixins data
let mixinData = this.getMixinData('basicColor')
if (mixinData) {
  classes += ` vce-button--color-${mixinData.selector}`
}
```

There is an option to use mixins for generated styles such as *color* or *size*. Mixins are prepared and formatted CSS code designed to generate unique style for an element.

In the example shown a mixin change the color of the button, created setting named `color` has an option field `cssMixin` with properties mixin to give file name where mixin is stored `basicColor` and property to name variable to store attribute value `color`.

Inside *basicColor.pcss* file example:

`$selector` is auto-generated variable with unique mixin selector

`$color` is variable where the attribute value is stored. Its name matches with `options.cssMixin.property` value.

PostCSS file must be included in the *index.js* file.

Also, it is possible to get mixin data in *component.js* file by using a helper `getMixinData()`


## PostCSS

> PostCSS *styles.scss* example:

```css
$bodyColor: #fff;
@media (--md-only) {
  body {
    background: $bodyColor;
  }
}
```

It is possible to use some POSTCSS features in CSS mixins and *styles.css* file

A complete list of POSTCSS plugins what are in use is:

* <a href="https://www.npmjs.com/package/postcss-advanced-variables" target="_blank">postcss-advanced-variables</a>: PostCSS plugin to convert Sass-like variables and conditionals into CSS;
* <a href="https://www.npmjs.com/package/postcss-custom-properties" target="_blank">postcss-custom-properties</a>: PostCSS plugin to transform W3C CSS Custom Properties for cascading variables syntax to more compatible CSS;
* <a href="https://www.npmjs.com/package/postcss-color-function" target="_blank">postcss-color-function</a>: PostCSS plugin to transform W3C CSS color function to more compatible CSS;
* <a href="https://www.npmjs.com/package/postcss-nested" target="_blank">postcss-nested</a>: PostCSS plugin to unwrap nested rules like how Sass does it;
* <a href="https://www.npmjs.com/package/postcss-custom-media" target="_blank">postcss-custom-media</a>: PostCSS plugin to transform W3C CSS Custom Media Queries syntax to more compatible CSS.

Complete list of custom media queries:

* all, all-only: all available devices;
* xs, mobile-portrait: mobile portrait and above;
* xs-only, mobile-portrait-only: mobile portrait only;
* sm, mobile-landscape: mobile landscape and above;
* sm-only, mobile-landscape-only: mobile landscape only;
* md, tablet-portrait: tablet portrait and above;
* md-only, tablet-portrait-only: tablet portrait only;
* lg, tablet-landscape: tablet landscape and above;
* lg-only, tablet-landscape-only: tablet landscape only;
* xl, desktop: desktop and above;
* xl-only, desktop-only: desktop only.

