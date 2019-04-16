# Assets management

Visual Composer elements have an ability to include JS and CSS libraries out of the box. These libraries are called shared assets.

Assets are included to an element via the *settings.json* file. But it will only enqueue an asset if it is already available within a Visual Composer plugin. For instance, some other elements may contain assets, like Icon element. The Icon element contains multiple various icon libraries or assets, but these assets are available within a plugin only if the Icon element is downloaded.

A fresh installation of Visual Composer plugin comes only with a few basic elements, so some of the assets can only be available once particular elements are downloaded.

The *manifest.json* file allows to specify a particular asset and it will a download it without downloading an element.

## Include assets via settings.json

> Include assets via *settings.json* example:

```json
{
  "sharedAssetsLibrary": {
    "access": "protected",
    "type": "string",
    "value": {
      "libraries": [
        {
          "libsNames": [
            "slickSlider",
            "animate"
          ]
        }
      ]
    }
  }
}
```

To include an asset inside *settings.json* file a `sharedAssetsLibrary` meta attribute should be used.


## Download assets via manifest.json

> Download assets via *manifest.json* example:

```json
{
  "elements": {
    "textTest": {
      "settings": {
        "name": "Text Test",
        "metaThumbnailUrl": "[publicPath]/thumbnail-text-block.png",
        "metaPreviewUrl": "[publicPath]/preview-text-block.jpg",
        "metaDescription": "Simple (TEST) text editor for working with static text, including paragraphs, titles, bullets and even media. Simple text block is a copy of default WordPress editor."
      }
    }
  },
  "categories": {
    "Misc": {
      "elements": [
        "textTest"
      ]
    }
  },
  "assetsDependencies": [
    "asset/iconpicker",
    "element/Icon"
  ]
}
```

To download an asset inside *manifest.json* file a `assetsDependencies` property name should be used. This property accepts an array type value, where multiple assets can be specified.

The `assetsDependencies` property may store a particular asset or an element. Which means that if an element is specified as a dependency, this element will be downloaded along with all of its assets. Whereas the specified asset will download this particular asset.

In the example above there are two items listed under the `assetsDependencies` property. One is the asset and another is an element.

To download only a single asset `“asset/assetName”` value has to be specified.

To download only an element `“element/elementName”` value has to be specified.

Available shared asset list


Library name | Description | Element dependant
-------------|-------------|------------------
waypoints |	Uses <a href="http://imakewebthings.com/waypoints/" target="_blank">waypoints</a> library. Included in the Design Options attribute |	No
animate |	Uses <a href="https://daneden.github.io/animate.css/" target="_blank">animate.css</a> library. Included in the Design Options attribute |	No
iconpicker |	Uses a set of multiple various icon sets. Typicons, Material, Font Awesome, Entypo, etc. Bundled with an Icon element. |	Yes
imageFilter	| Uses <a href="https://una.im/CSSgram/" target="_blank">CSSgram</a> library. Bundled with image type elements like Single Image. |	Yes
lightbox |	Uses <a href="https://lokeshdhakar.com/projects/lightbox2/" target="_blank">lightbox</a> library. Bundled with image type elements like Single Image. |	Yes
photoswipe |	 Uses <a href="http://photoswipe.com/" target="_blank">photoswipe</a> library. Bundled with image type elements like Single Image |	Yes
slickSlider |	Uses <a href="http://kenwheeler.github.io/slick/" target="_blank">slick slider</a> library. Bundled with elements that have a sliding option like Simple Image Slider. |	Yes
zoom |	Uses <a href="http://www.jacklmoore.com/zoom/" target="_blank">jQuery zoom</a> library. Bundled with image type elements like Single Image | 	Yes
