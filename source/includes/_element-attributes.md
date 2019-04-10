# Element Attributes

## ajaxForm

> `ajaxForm` attribute *settings.json* file example:

```json
"widget": {
  "type": "ajaxForm",
  "access": "public",
  "value": {
    "key": "",
    "value": ""
  },
  "options": {
    "label": "",
    "action": "vcv:wpWidgets:form"
  }
}
```

Requests a form via an AJAX call. A form is constructed in the PHP controller file.

`value` is an `object` type.


## animateDropdown

> `animateDropdown` attribute *settings.json* file example:

```json
"buttonAnimation": {
  "type": "animateDropdown",
  "access": "public",
  "value": "fadeInLeft",
  "options": {
    "label": "Animate button"
  }
}
```

Although animation list is already available for each element in Design Options, this attribute allows adding an additional drop-down with a list of animation classes (e.g. animation for the nested element).

`value` is a `string` type.


## attachimage

> `attachimage` attribute *settings.json* file example:

```json
"image": {
  "type": "attachimage",
  "access": "public",
  "value": "image.jpg",
  "options": {
    "label": "Image",
    "defaultValue": "image.jpg"
  }
}
```

Allows adding an image from Media Library. The initial/default value is a file name which is located inside element's `public` folder.

`value` is a `string` type.


## attachvideo

> `attachvideo` attribute *settings.json* file example:

```json
"video": {
  "type": "attachvideo",
  "access": "public",
  "value": "",
  "options": {
    "label": "Video"
  }
}
```

Allows adding a video from Media Library.

`value` is a `string` type.

## autocomplete

> `autocomplete` attribute *settings.json* file example:

```json
"source": {
  "type": "autocomplete",
  "access": "public",
  "value": "",
  "options": {
    "action": "actionName",
    "validation": true,
    "label": "Search items",
    "single": true
  }
}
```
Allows searching for value through the list. Usually, this attribute is used in shortcode based elements.

`value` is a `string` type.


## buttonGroup

> `buttonGroup` attribute *settings.json* file example:

```json
"alignment": {
  "type": "buttonGroup",
  "access": "public",
  "value": "left",
  "options": {
    "label": "Alignment",
    "values": [
      {
        "label": "Left",
        "value": "left",
        "icon": "vcv-ui-icon-attribute-alignment-left"
      },
      {
        "label": "Center",
        "value": "center",
        "icon": "vcv-ui-icon-attribute-alignment-center"
      },
      {
        "label": "Right",
        "value": "right",
        "icon": "vcv-ui-icon-attribute-alignment-right"
      }
    ]
  }
}
```
> or

```json
"size": {
  "type": "buttonGroup",
  "access": "public",
  "value": "large",
  "options": {
    "label": "Size",
    "values": [
      {
        "label": "Small",
        "value": "small",
        "text": "S"
      },
      {
        "label": "Medium",
        "value": "medium",
        "text": "M"
      },
      {
        "label": "Large",
        "value": "large",
        "text": "L"
      },
    ]
  }
}
```

A set of buttons allowing to select one value out of multiple. Buttons may contain an icon or text. To set the desired view of a button just define icon or text property in the value object.

`value` is a `string` type.

List of default Visual Composer icon classes for `buttonGroup` attribute, class names are self-explanatory:

* vcv-ui-icon-attribute-vertical-alignment-top
* vcv-ui-icon-attribute-vertical-alignment-middle
* vcv-ui-icon-attribute-vertical-alignment-bottom
* vcv-ui-icon-attribute-alignment-left
* vcv-ui-icon-attribute-alignment-right
* vcv-ui-icon-attribute-alignment-center
* vcv-ui-icon-attribute-shape-square
* vcv-ui-icon-attribute-shape-rounded
* vcv-ui-icon-attribute-shape-round
* vcv-ui-icon-attribute-row-width-boxed
* vcv-ui-icon-attribute-row-width-stretched
* vcv-ui-icon-attribute-row-width-stretched-content
* vcv-ui-icon-attribute-background-position-left-top
* vcv-ui-icon-attribute-background-position-center-top
* vcv-ui-icon-attribute-background-position-right-top
* vcv-ui-icon-attribute-background-position-left-center
* vcv-ui-icon-attribute-background-position-center-center
* vcv-ui-icon-attribute-background-position-right-center
* vcv-ui-icon-attribute-background-position-left-bottom
* vcv-ui-icon-attribute-background-position-center-bottom
* vcv-ui-icon-attribute-background-position-right-bottom


## calendar

> `calendar` attribute *component.js* file example:

```javascript
render () {
  // some code ...
  const { datepicker } = this.props.atts
  datepicker = datepicker || new Date()
  // continue code ...
}
```

> `calendar` attribute *settings.json* file example:

```json
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
```
An attribute that allows selecting date and time. Attribute returns selected date as a `Date` object. The default value is an empty `string`. The attribute sets the field value to the current date.

`value` is a `Date` `object` type.


## checkbox

> `checkbox` attribute *settings.json* file example:

```json
"devices": {
  "type": "checkbox",
  "access": "public",
  "value": [],
  "options": {
    "label": "Devices",
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
```

A simple checkbox input.

`value` is an `array` of `string`s.


## color

> `color` attribute *settings.json* file example:

```json
"backgroundColor": {
  "type": "color",
  "access": "public",
  "value": "#b3a694",
  "options": {
    "label": "Background color",
    "cssMixin": {
      "mixin": "backgroundColor",
      "property": "backgroundColor",
      "namePattern": "[\\da-f]+"
    }
  }
}
```
Displays a custom colorpicker. Usually, `cssMixin` property must be listed inside options.

`value` is a `string` type.


## customId

> `customId` attribute *settings.json* file example:

```json
"metaCustomId": {
  "type": "customId",
  "access": "public",
  "value": "",
  "options": {
    "label": "Element ID",
    "description": "Apply unique ID to element to link directly to it by using #your_id (for element ID use lowercase input only)."
  }
}
```
String field used to add a custom id to the element.

`value` is a `string` type.


## designOptions

> `designOptions` attribute *settings.json* file example:

```json
"designOptions": {
  "type": "designOptions",
  "access": "public",
  "value": {},
  "options": {
    "label": "Design Options"
  }
}
```

Design options to set up margins, paddings, border, background color etc.

`value` is an `object` type.


## dropdown

> `dropdown` attribute *settings.json* file example:

```json
"videoSource": {
  "type": "dropdown",
  "access": "public",
  "value": "youtube",
  "options": {
    "label": "Video source",
    "values": [
      {
        "label": "Youtube",
        "value": "youtube"
      },
      {
        "label": "Vimeo",
        "value": "vimeo"
      }
    ]
  }
}
```

List of values in a select tag

`value` is a `string` type.


## element

> `element` attribute *settings.json* file example:

```json
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
},
"metaEditFormTabs": {
  "type": "group",
  "access": "protected",
  "value": [
    "editFormTab1",
    "button",
    "designOptions"
  ]
}
```

Allows inserting another element. The inserted element will be displayed as a separate section in the Edit Form, thus the attribute must be listed in the `metaEditFormTabs` attribute.

`value` is an `object` type.


## googleFonts

> `googleFonts` attribute *settings.json* file example:

```json
"font": {
  "type": "googleFonts",
  "access": "public",
  "value": {
    "fontFamily": "Lato",
    "fontStyle": {
      "weight": "400",
      "style": "regular"
    },
    "status": "active",
    "fontText": "The sky was cloudless and of a deep dark blue."
  },
  "options": {
    "label": "Font"
  }
}
```

List of available google fonts with weight.

`value` is an `object` type.


## group

> `group` attribute *settings.json* file example:

```json
"editFormTab1": {
  "type": "group",
  "access": "protected",
  "value": [
    "alignment",
    "color",
    "metaCustomId",
    "customClass"
  ],
  "options": {
    "label": "General"
  }
}
```
List of data values. Used to group edit form attributes in the Edit Form.

`value` is an `array` of `strings`.


## htmleditor

> `htmleditor` attribute *settings.json* file example:

```json
"output": {
  "type": "htmleditor",
  "access": "public",
  "value": "<h2>Hello there!</h2>\n<p>This is just some text.</p>",
  "options": {
    "label": "Content"
  }
}
```

WordPress Classic TinyMCE editor.

`value` is a `string` type.


## iconpicker

> `iconpicker` attribute *settings.json* file example:

```json
"iconPicker": {
  "type": "iconpicker",
  "access": "public",
  "value": {
    "icon": "vcv-ui-icon-material vcv-ui-icon-material-mode_edit",
    "iconSet": "material"
  },
  "options": {
    "label": "Icon"
  }
}
```

Icon picker allows selecting an icon from predefined libraries.

`value` is an `object` type.


## inputIcon

> `inputIcon` attribute *settings.json* file example:

```json
"desktopWidth": {
  "type": "inputIcon",
  "access": "public",
  "value": "600",
  "options": {
    "min": "1",
    "label": "Width on a desktop",
    "iconClasses": "vcv-ui-icon vcv-ui-icon-desktop",
    "inputType": "number"
  }
},
"mobileWidth": {
  "type": "inputIcon",
  "access": "public",
  "value": "200",
  "options": {
    "min": "1",
    "label": "Width on a mobile",
    "iconClasses": "vcv-ui-icon vcv-ui-icon-mobile-portrait",
    "inputType": "number"
  }
}
```

An input with an icon on the side. `inputType` property can be changed to `number` or `string` value.

`value` is a `string` type.


## inputSelect

> `inputSelect` attribute *settings.json* file example:

```json
"price": {
  "type": "inputSelect",
  "access": "public",
  "value": {
    "input": "19,95",
    "select": "$_"
  },
  "options": {
    "type": "currency",
    "label": "Price",
    "values": []
  }
}
```
Selector with a search to browse multi-data. Currently, only `currency` type value is available.

`value` is an `object` type.


## number

> `number` attribute *settings.json* file example:

```json
"width": {
  "type": "number",
  "access": "public",
  "value": "150",
  "options": {
    "label": "Width",
    "min": 1,
    "max": 300
  }
}
```

Input field with number type. Can take `min` and `max` properties inside `options` property.

`value` is a `string` type.


## paramsGroup

> `paramsGroup` attribute *settings.json* file example:

```json
"bars": {
    "type": "paramsGroup",
    "access": "public",
    "value": {
      "value": [
        {
          "title": "Web Design",
          "value": 80,
          "color": "#50E3C2"
        },
        {
          "title": "Marketing",
          "value": 50,
          "color": "#50E3C2"
        }, 
        {
          "title": "Social Media",
          "value": 60,
          "color": "#50E3C2"
        }
      ]
    },
    "options": {
      "label": "General",
      "title": "Progress bar",
      "groupDefaultTile": "Progress bar",
      "settings": {
        "title": {
          "type": "string",
          "access": "public",
          "value": "Progress bar",
          "options": {
            "label": "Title"
          }
        },
        "value": {
          "type": "range",
          "access": "public",
          "value": "70",
          "options": {
            "label": "Value",
            "cssMixin": {
              "mixin": "barValue",
              "property": "value",
              "namePattern": "[\\da-f]+"
            }
          }
        },
        "color": {
          "type": "color",
          "access": "public",
          "value": "#50E3C2",
          "options": {
            "label": "Bar color",
            "cssMixin": {
              "mixin": "barColor",
              "property": "color",
              "namePattern": "[\\da-f]+"
            }
          }
        },
        "_paramGroupEditFormTab1": {
          "type": "group",
          "access": "protected",
          "value": [
            "title",
            "value",
            "color"
          ],
          "options": {
            "label": "General"
          }
        },
        "metaEditFormTabs": {
          "type": "group",
          "access": "protected",
          "value": [
            "_paramGroupEditFormTab1"
          ]
        }
      }
    }
  }
  ```

> `paramsGroup` attribute *component.js* file example:

```javascript
import React from 'react'
import vcCake from 'vc-cake'
import classNames from 'classnames'
import ProgressBar from './progressBar'
const vcvAPI = vcCake.getService('api')
export default class ProgressBars extends vcvAPI.elementComponent {
  /**
   * getMixin method returns a PCSS mixin specific to the child element,
   * it uses VC native method getMixinData to get PCSS mixin.
   */
  getMixin (mixinName, i) {
    const elementMixins = this.getMixinData()
    return elementMixins['bars'][i][mixinName]
  }
  /**
   * getContent method returns an array of child elements,
   * from <ProgressBar /> component.
   * Proper attributes must be passed
   */
  getContent () {
    const { bars } = this.props.atts
    // All the necessary code for elements' child components
    ...
    const items = bars.value ? bars.value : bars
    return items.map((item, i) => {
      let key = `progressBar-${this.props.id}-${i}`
      let attributes = item.progressBar || item
      attributes.atts = {}
      // tag property is a must have, the system will recognize to which element it belongs
      attributes.atts.tag = this.props.atts.tag
      attributes.atts.title = item.title
      attributes.atts.value = item.value
      attributes.itemIndex = i
      attributes.getMixin = this.getMixin.bind(this)
      return <ProgressBar {...attributes} key={key} />
    })
  }
  render () {
    const { id, atts, editor } = this.props
    // All the necessary code to render element component
    ...
  
    return (
      <div {...editor} id={`el-${id}`} className={containerClasses} {...doAll}>
        <div className='vce-progress-bars' {...customProps}>
          {this.getContent()}
        </div>
      </div>
    )
  }
}
```

> `paramsGroup` attribute *childComponent.js* file example:

```javascript
import React from 'react'
import vcCake from 'vc-cake'
import classNames from 'classnames'
const vcvAPI = vcCake.getService('api')
export default class ProgressBar extends vcvAPI.elementComponent {
  render () {
    const { getMixin, itemIndex } = this.props
    const { title, value } = this.props.atts
    let containerClasses = [ 'vce-progress-bar-container' ]
    let mixin = getMixin('barValue', itemIndex)
    if (mixin) {
      containerClasses.push(`vce-progress-bar--value-${mixin.selector}`)
    }
    mixin = getMixin('barColor', itemIndex)
    if (mixin) {
      let colorClass = `vce-progress-bar--${colorType}-${mixin.selector}`
      containerClasses.push(colorClass)
    }
    containerClasses = classNames(containerClasses)
    // All the necessary code to render child element component
    ...
    return <div className={containerClasses}>
      <div className='vce-progress-bar-text'>
        <div className='vce-progress-bar-title'>{title}</div>
        <div className='vce-progress-bar-value' />
      </div>
      <div className='vce-progress-bar-wrapper'>
        <progress className='vce-progress-bar' value={value} max='100'>{value} %</progress>
      </div>
    </div>
  }
}
```

This attribute allows to contain and operate a certain set of attributes within a separate group. A group can be added, edited, removed, cloned and moved (relative to each other, up and down.) Initial groups are set within a *settings.json* file. Inside elements Edit Form `paramsGroup` attribute is displayed similar to Tree View, once clicked on edit, Edit Form will re-render with attributes bound to this group.

The options values within each group will affect the corresponding child element of the initial parent element (e.g. Bar in Progress Bars element.)

The code examples shows how Progress Bars element is built.

`value` is an `object` type.


## radio

> `radio` attribute *settings.json* file example:

```json
"device": {
  "type": "radio",
  "access": "public",
  "value": "xs",
  "options": {
    "label": "Device",
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
```

Input field with radio type.

`value` is a `string` type.


## range

> `range` attribute *settings.json* file example:

```json
"width": {
  "type": "range",
  "access": "public",
  "value": "60",
  "options": {
    "label": "Width",
    "min": 1,
    "max": 100
  }
}
```

Slider with a range of values.

`value` is a `string` type.


## rawCode

> `rawCode` attribute *settings.json* file example:

```json
"rawHtml": {
  "type": "rawCode",
  "access": "public",
  "value": "<p><strong>HyperText Markup Language (HTML)</strong> is the standard markup language for creating web pages and web applications.</p>",
  "options": {
    "label": "Raw HTML",
    "mode": "html"
  }
}
```

Raw code editor, `mode` property can be set to `html` or `javascript`.

`value` is a `string` type.


## string

> `string` attribute *settings.json* file example:

```json
"title": {
  "type": "string",
  "access": "public",
  "value": "Hello World!",
  "options": {
    "label": "Title"
  }
}
```

Input field with text type.

`value` is a `string` type.


## textarea

> `textarea` attribute *settings.json* file example:

```json
"text": {
  "type": "textarea",
  "access": "public",
  "value": "Lorem ipsum dolor sit amet...",
  "options": {
    "label": "Text"
  }
}
```

A simple Textarea input type.

`value` is a `string` type.


## toggle

> `toggle` attribute *settings.json* file example:

```json
"toggleTitle": {
  "type": "toggle",
  "access": "public",
  "value": true,
  "options": {
    "label": "Toggle title"
  }
}
```

Toggle switcher like a checkbox.

`value` is a `boolean` type.


## toggleSmall

> `toggleSmall` attribute *settings.json* file example:

```json
"darkTextSkin": {
  "type": "toggleSmall",
  "access": "public",
  "value": true
},
"description": {
  "type": "htmleditor",
  "access": "public",
  "value": "Lorem ipsum dolor sit amet...",
  "options": {
    "label": "Description",
    "skinToggle": "darkTextSkin"
  }
}
```
A small version of `toggle` attribute is used to toggle skin color of a tinyMCE editor.

`value` is a `boolean` type.


## treeView

> `treeView` attribute *settings.json* file example:

```json
"buttons": {
  "type": "treeView",
  "access": "public",
  "value": {},
  "options": {
    "label": "Buttons"
  }
}
```

Displays child elements as Tree View in Edit Form.

`value` is an `object` type.


## url

> `url` attribute *settings.json* file example:

```json
"buttonUrl": {
  "type": "url",
  "access": "public",
  "value": {
    "url": "",
    "title": "",
    "targetBlank": false,
    "relNofollow": false
  },
  "options": {
    "label": "Link selection"
  }
}
```

Link field which works via Link editor for WordPress.

`value` is an `object` type.


