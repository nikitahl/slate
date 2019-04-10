# Attributes Options

Each attribute has a type and options. Options property is an object that may contain multiple properties which can extend an attribute.


## Common options

<aside class="notice">
Following attributes options are common for all attributes.
</aside>

### label

> label option example:

```json
{
  "text": {
    "type": "textarea",
    "access": "public",
    "value": "Lorem ipsum dolor sit amet...",
    "options": {
      "label": "Text"
    }
  }
}
```

A label which will be displayed in the Edit Form right before the attribute field.


### description

> description option example:

```json
{
  "width": {
    "type": "number",
    "access": "public",
    "value": "",
    "options": {
      "label": "Width",
      "description": "Set the width of a button in pixels."
    }
  }
}
```

A description which will be displayed in the Edit Form right after the attribute field.


### descriptionHTML

> descriptionHML option example:

```json
{
  "width": {
    "type": "number",
    "access": "public",
    "value": "",
    "options": {
      "label": "Width",
      "descriptionHTML": "<p class='description'>Set the <b>width</b> of a button in pixels.</p>"
    }
  }
}
```

A description which will be displayed in the Edit Form right after the attribute field and allows HTML tags.


### values

> values option example:

```json
{
  "verticalAlignment": {
    "type": "dropdown",
    "access": "public",
    "value": "top",
    "options": {
      "label": "Vertical alignment",
      "values": [
        {
          "label": "Top",
          "value": "top",
        },
        {
          "label": "Middle",
          "value": "middle",
        },
        {
          "label": "Bottom",
          "value": "bottom",
        }
      ]
    }
  }
}
```

An `array` of `objects`. Usually, each `object` consists of `label` and `value` properties. This property is used for attributes that have multiple values like `buttonGroup` or `dropdown`.


### cssMixins

> cssMixins option example:

```json
{
  "color": {
    "type": "color",
    "access": "public",
    "value": "#fff",
    "options": {
      "label": "Title color",
      "cssMixin": {
        "mixin": "titleColor",
        "property": "color",
        "namePattern": "[\\da-f]+"
      }
    }
  }
}
```

Defines which POST CSS mixin to use, mixin variable and pattern. `cssMixin` property is an `object` that has several properties:

* `mixin` defines the name of POST CSS file with the mixin;
* `property` defines the name of the property inside POST CSS file;
* `namePattern` defines the pattern of how input data will be verified via RegExp.


### onChange

> onChange option example:

```json
{
  "title": {
    "type": "string",
    "access": "public",
    "value": "Hello World",
    "options": {
      "label": "Title",
      "onChange": {
        "rules": {
          "titleType": {
            "rule": "value",
            "options": {
              "value": "custom"
            }
          }
        },
        "actions": [
          {
            "action": "toggleVisibility"
          }
        ]
      }
    }
  },
  "titleType": {
    "type": "dropdown",
    "access": "public",
    "value": "default",
    "options": {
      "label": "Title type",
      "values": [
        {
          "label": "Default title",
          "value": "default"
        },
        {
          "label": "Custom title",
          "value": "custom"
        }
      ]
    }
  }
}
```

Defines how to react to another attribute value change. It is defined as an `object` inside an attribute `options` property and must hold `rules` and `actions` properties. Learn more about rules and actions.

## Custom options
<aside class="notice">
Following attributes options are custom and each is used in a specific attribute.
</aside>

### multiple

> multiple option example:

```json
{
  "image": {
    "type": "attachimage",
    "access": "public",
    "value": "sample-background.png",
    "options": {
      "label": "Background image",
      "multiple": false
    }
  }
}
```

Used in the `attachimage` and `attachvideo` attributes. Has a `boolean` value type and defines the ability to select multiple images.


### defaultValue

> defaultValue option example:

```json
{
  "image": {
    "type": "attachimage",
    "access": "public",
    "value": "sample-background.png",
    "options": {
      "label": "Background image",
      "defaultValue": "sample-background.png"
    }
  }
}
```

Used in the `attachimage` attribute. Has a `string` value type and defines the image set by default. Images for this property should be located in the *elementName/elementName/public* folder.


### imageFilter

>imageFilter option example:

```json
{
  "image": {
    "type": "attachimage",
    "access": "public",
    "value": "sample-background.png",
    "options": {
      "label": "Background image",
      "imageFilter": true
    }
  }
}
```

Used in the `attachimage` attribute. Has a `boolean` value type and defines whether Instagram like filters should be enabled for the image.


### url

> url option example:

```json
{
  "image": {
    "type": "attachimage",
    "access": "public",
    "value": "sample-background.png",
    "options": {
      "label": "Background image",
      "url": false
    }
  }
}
```

Used in the `attachimage` attribute. Has a `boolean` value type and defines whether link selector should be enabled.


### action

> action option example:

```json
{
  "atts_category": {
    "type": "autocomplete",
    "access": "public",
    "value": [],
    "options": {
      "action": "woocommerceCategory",
      "label": "Category ID or Slug",
    }
  }
}
```

Used in the `autocomplete` attribute. Has a `string` value type and defines the action for AJAX request.


### labelAction

> labelAction option example:

```json
{
  "atts_category": {
    "type": "autocomplete",
    "access": "public",
    "value": [],
    "options": {
      "action": "woocommerceCategory",
      "labelAction": "product_cat",
      "label": "Category ID or Slug"
    }
  }
}
```

Used in the `autocomplete` attribute. Has a `string` value type and defines the label action for AJAX request.


### returnValue

> returnValue option example:

```json
{
  "atts_category": {
    "type": "autocomplete",
    "access": "public",
    "value": "",
    "options": {
      "action": "woocommerceCategory",
      "labelAction": "product_cat",
      "returnValue": "slug",
      "label": "Category ID or Slug",
    }
  }
}
```

Used in the `autocomplete` attribute. Has a `string` value type and defines the return value for AJAX request.


### validation

> validation option example:

```json
{
  "atts_category": {
    "type": "autocomplete",
    "access": "public",
    "value": "",
    "options": {
      "action": "woocommerceCategory",
      "labelAction": "product_cat",
      "returnValue": "slug",
      "validation": true,
      "label": "Category ID or Slug",
    }
  }
}
```

Used in the `autocomplete` attribute. Has a `boolean` value type and defines whether validation should be enabled for the `autocomplete` field.


### single

> single option example:

```json
{
  "atts_category": {
    "type": "autocomplete",
    "access": "public",
    "value": "",
    "options": {
      "action": "woocommerceCategory",
      "labelAction": "product_cat",
      "returnValue": "slug",
      "validation": true,
      "label": "Category ID or Slug",
      "single": true
    }
  }
}
```

Used in the `autocomplete` attribute. Has a `boolean` value type and defines whether a single available options should be enabled.


### global

> global option example:

```json
{
  "source": {
    "type": "dropdown",
    "access": "public",
    "value": "",
    "options": {
      "label": "Envira Gallery source",
      "global": "vcvWpEnviraGallery"
    }
  }
}
```

Used in the `dropdown`, `checkbox`, `radio`, `buttonGroup` attributes, usually in conjunction with WordPress plugins. Has a `string` value type and represents a JavaScript global variable.


### category

> category option example:

```json
{
  "button": {
    "type": "element",
    "access": "public",
    "value": {
      "tag": "basicButton"
    },
    "options": {
      "category": "Button"
    }
  }
}
```

Used in the `element` attribute. Has a `string` value type and is used to define child element category.


### tabLabel

> tabLabel option example:

```json
{
  "button": {
    "type": "element",
    "access": "public",
    "value": {
      "tag": "basicButton"
    },
    "options": {
      "category": "Button",
      "tabLabel": "Button"
    }
  }
}
```

Used in the `element` attribute. Has a `string` value type and is used to define child element section label in the Edit Form.


### merge

> merge option example:

```json
{
  "button": {
    "type": "element",
    "access": "public",
    "value": {
      "tag": "basicButton"
    },
    "options": {
      "category": "Button",
      "tabLabel": "Button",
      "merge": {
        "attributes": [
          {
            "key": "alignment",
            "type": "string"
          },
          {
            "key": "buttonText",
            "type": "string"
          },
          {
            "key": "buttonUrl",
            "type": "object"
          }
        ]
      }
    }
  }
}
```

Used in the `element` attribute. Has an `object` value type and is used to define which element attributes should be merged on element replace. It has attributes property which itself is an `array`.


### exclude

> exclude option example:

```json
{
  "icon": {
    "type": "element",
    "access": "public",
    "value": {
      "tag": "icon"
    },
    "options": {
      "category": "Icon",
      "tabLabel": "Image view icon",
      "exclude": [
        "iconUrl"
      ]
    }
  }
}
```

Used in the `element` attribute. Has an `array` value type and is used to define which attributes should be excluded for child element.


### listView

> listView option example:

```json
{
  "devices": {
    "type": "checkbox",
    "access": "public",
    "value": [],
    "options": {
      "label": "Devices",
      "listView": true,
      "values": [ 
        {
          "label": "Desktop",
          "value": "xl"
        },
        {
          "label": "Mobile",
          "value": "xs"
        }
      ]
    }
  }
}
```

Used in the `radio` and `checkbox` attributes. Has a `boolean` value type, and is used to define whether radios or checkboxes should be displayed inline or as a list. If the property is not defined radios and checkboxes will be displayed as inline.


### inline

> inline option example:

```json
{
  "description": {
    "type": "htmleditor",
    "access": "public",
    "value": "Lorem ipsum dolor sit amet...",
    "options": {
      "label": "Description",
      "inline": true
    }
  }
}
```

Used in the `htmleditor` and `string` attributes. Has a `boolean` value type and is used to define whether inline editing should be enabled for the attribute.


### inlineMode

> inlineMode option example:

```json
{
  "title": {
    "type": "string",
    "access": "public",
    "value": "Lorem ipsum",
    "options": {
      "label": "Title",
      "inline": true,
      "inlineMode": "text"
    }
  }
}
```

Used in the `string` attribute. Has a `string` value type and is used to handle inline editing in regular `string` type attributes.

Currently only available value is `text`.


### skinToggle

> skinToggle option example:

```json
{
  "description": {
    "type": "htmleditor",
    "access": "public",
    "value": "Lorem ipsum dolor sit amet...",
    "options": {
      "label": "Description",
      "skinToggle": "darkTextSkin"
    }
  }
}
```

Used in the `htmleditor` attribute. Has a `string` value type and is used in conjunction with `toggleSmall` attribute to switch tinyMCE editor to a dark theme.

### inputClasses

Used in the `inputIcon` attribute. Has a `string` value type and is used to define classes for an icon.


### inputType

> inputType and inputClasses option example:

```json
{
  "heightxl": {
    "type": "inputIcon",
    "access": "public",
    "value": "400",
    "options": {
      "label": "Height on desktop (px)",
      "iconClasses": "vcv-ui-icon vcv-ui-icon-desktop",
      "inputType": "number",
  },
}
```

Used in the `inputIcon` attribute. Has a `string` value type and is used to define the input type.


### type

> type option example:

```json
{
  "price": {
    "type": "inputSelect",
    "access": "public",
    "value": {
      "input": "89,00",
      "select": "$_"
    },
    "options": {
      "type": "currency",
      "label": "Price",
      "values": []
    }
  }
}
```

Used in the `inputSelect` attribute. Has a `string` value type and is used to define the type. 

Currently, only `currency` type is available.


### min

> min option example:

```json
{
  "autoPlayDelay": {
    "type": "number",
    "access": "public",
    "value": "1",
    "options": {
      "label": "Autoplay delay",
      "min": 1
    }
  }
}
```

Used in the `number` and `range` attributes. Has a `number` value type and is used to define the minimum input value.


### max

> max option example:

```json
{
  "autoPlayDelay": {
    "type": "number",
    "access": "public",
    "value": "1",
    "options": {
      "label": "Autoplay delay",
      "max": 100
    }
  }
}
```

Used in the `number` and `range` attributes. Has a `number` value type and is used to define the maximum input value.


### measurement

> measurement option example:

```json
{
  "width": {
    "type": "range",
    "access": "public",
    "value": "60",
    "options": {
      "label": "Width",
      "description": "Enter width in percents (Example: 60).",
      "measurement": "%"
    }
  }
}
```

Used in the `range` attribute. Has a `string` value type and is used to define measurement units for the `range` attribute field.


### mode

> mode option example:

```json
{
  "rawHtml": {
    "type": "rawCode",
    "access": "public",
    "value": "<p>Lorem ipsum dolor sit amet...</p>",
    "options": {
      "label": "HTML",
      "mode": "html"
    }
  }
}
```

Used in the `rawCode` attribute. Has a `string` value type and is used to define code editor’s mode. 

Currently, only `html` and `javascript` are available.


### height

> height option example:

```json
{
  "rawHtml": {
    "type": "rawCode",
    "access": "public",
    "value": "<p>Lorem ipsum dolor sit amet...</p>",
    "options": {
      "label": "HTML",
      "mode": "html",
      "height": "30vh",
    }
  }
}
```

Used in the `rawCode` attribute. Has a `string` value type and is used to define code editor’s height.


### time

> time option example:

```json
{
  "datepicker": {
    "type": "calendar",
    "access": "public",
    "value": "",
    "options": {
      "label": "Date",
      "time": true,
      "timeIntervals": 15
    }
  }
}
```

Used in the `calendar` attribute. Has a `boolean` value type and is used to enable time selection.


### timeIntervals

> timeIntervals option example:

```json
{
  "datepicker": {
    "type": "calendar",
    "access": "public",
    "value": "",
    "options": {
      "label": "Date",
      "time": true,
      "timeIntervals": 15
    }
  }
}
```

Used in the `calendar` attribute. Has a `number` value type and is used to define time interval. If this option is not specified, the default time interval will be set to `10`.

