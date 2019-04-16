# Meta Attributes

Protected meta attributes of the Visual Composer available for use via the API.

## tag

> `tag` attribute *settings.json* file example:

```json
"tag": {
  "access": "protected",
  "type": "string",
  "value": "basicButton"
}
```

This unique tag which is used to identify and find element components and settings.

`value` is a `string` type.


## relatedTo

> `relatedTo` attribute *settings.json* file example:

```json
"relatedTo": {
  "type": "group",
  "access": "protected",
  "value": [
    "General",
    "Buttons"
  ]
}
```

Relation to groups. Used for drag&drop and Add Element panel. The default value is `“General"`.

`value` is an `array` of `string`s.


## editFormTab1

> `editFormTab1` attribute *settings.json* file example:

```json
"editFormTab1": {
  "type": "group",
  "access": "protected",
  "value": [
    "title",
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

List of edit form attributes in General section of the edit form.

`value` is an `array` of `string`s.


## metaEditFormTabs

> `metaEditFormTabs` attribute *settings.json* file example:

```json
"metaEditFormTabs": {
  "type": "group",
  "access": "protected",
  "value": [
    "editFormTab1",
    "designOptions"
  ]
}
```

List of sections in editForm. A section can be a group like “editFormTab1” or attribute like “designOptions”.

`value` is an `array` of `string`s.


## containerFor

> `containerFor` attribute *settings.json* file example:

```json
"containerFor": {
  "type": "group",
  "access": "protected",
  "value": [
    "Buttons"
  ]
}
```

> or

```json
"containerFor": {
  "type": "group",
  "access": "protected",
  "value": [
    "Tab"
  ],
  "options": {
    "elementDependencies": {
      "tag": "tab"
    }
  }
}
```

Defines what child elements can be inside the container element.

`value` is an `array` of `string`s.


## initChildren

> `initChildren` attribute *settings.json* file example:

```json
"initChildren": {
  "access": "protected",
  "type": "object",
  "value": [
    {
      "tag": "outlineButton",
      "titleColor": "#fff"
    },
    {
      "tag": "basicButton",
      "titleColor": "#fff"
    }
  ]
}
```

Used to initiate child elements. Each child object must hold a tag attribute and optional attribute names with values for initialization.

`value` is an `array` of `object`s.


## metaPublicJs

> `metaPublicJs` attribute *settings.json* file example:

```json
"metaPublicJs": {
  "access": "protected",
  "type": "string",
  "value": {
    "libraries": [
      {
        "libPaths": [
          "public/dist/customSlider.min.js",
          "public/dist/customGallery.min.js"
        ]
      },
      {
        "rules": {
          "toggleResponsiveMode": {
            "rule": "toggle"
          }
        },
        "libPaths": "public/dist/responsive.min.js"
      }
    ]
  }
}
```

A list of custom JavaScript libraries which will be used by and related to a particular element. Libraries may be included on conditions, a `rule` property must be set in order to enqueue a library. `libPaths` property may contain a `string` or an `array` type value.

`value` is an `object` type.


## sharedAssetsLibrary

> `sharedAssetsLibrary` attribute *settings.json* file example:

```json
"sharedAssetsLibrary": {
  "access": "protected",
  "type": "string",
  "value": {
    "libraries": [
      {
        "libsNames": [
          "slickSlider"
        ]
      },
      {
        "rules": {
          "clickableOptions": {
            "rule": "value",
            "options": {
              "value": "lightbox"
            }
          }
        },
        "libsNames": [
          "lightbox"
        ]
      },
    ]
  }
}
```

A list of JS libraries that are provided by the system which can be included by elements. Libraries may be included on conditions, a rule must be set in order to include a library. Learn how to include assets via the manifest.json file.

`value` is an `object` type.


Available shared library list:

Library name | Description
------------ | -------
waypoints  | Uses <a href="http://imakewebthings.com/waypoints/" target="_blank">waypoints</a> library. Included in the Design Options attribute
animate    | Uses <a href="https://daneden.github.io/animate.css/" target="_blank">animate.css</a> library. Included in the Design Options attribute
iconpicker | Uses a set of multiple various icon sets. Typicons, Material, Font Awesome, Entypo, etc.
imageFilter| Uses <a href="https://una.im/CSSgram/" target="_blank">CSSgram</a> library.
lightbox	 | Uses <a href="https://lokeshdhakar.com/projects/lightbox2/" target="_blank">lightbox</a> library.
photoswipe | Uses <a href="http://photoswipe.com/" target="_blank">photoswipe</a> library.
slickSlider| Uses <a href="http://kenwheeler.github.io/slick/" target="_blank">slick slider</a> library.
zoom       | Uses <a href="http://www.jacklmoore.com/zoom/" target="_blank">jQuery zoom</a> library.

## groups

> `groups` attribute *settings.json* file example:

```json
"groups": {
  "type": "string",
  "access": "protected",
  "value": "Buttons"
}
```

Used to assign an element to a group of elements. Can be used for replacing elements. Possible values: Content, Containers, Buttons, Separators.

`value` is a `string` type.



