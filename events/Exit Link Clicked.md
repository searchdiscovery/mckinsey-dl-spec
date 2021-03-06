# Exit Link Clicked

Exit link clicks will be automatically detected by comparing the list of domains within Adobe Launch. This spec is for manually adding exit links if necessary in the future.

## Data Attributes HTML Code

```html
  <a href="<linkDestination>"
    data-layer-event-prefix="Exit Link"
    data-layer-action="click"
    data-layer-category="<category>"
    data-layer-subcategory="<subcategory?>"
    data-layer-subcategory2="<subcategory2?>"
    data-layer-text="<text?>"
  >
```

Items with a ? are optional

## Generated Javascript Code

```js
window.appEventData = window.appEventData || [];
appEventData.push({
  "event": "Exit Link Clicked",
  "linkInfo": {
    "category": "<category?>",
    "subcategory": "<subcategory?>",
    "subcategory2": "<subcategory2?>",
    "region": "<region?>",
    "text": "<text>",
  }
});
```

Items with a ? may not be generated depending on what attributes are present and the ancestry of the clicked item.

### Variable Definitions

|Field|Type|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|category|string|Category of the link|chat, ecommerce, learn more, share, subscribe, visit|
|subcategory|string|Subcategory of the link|buy now, email, print, social|
|subcategory2|string|Subcategory tier 2 of the link. Often used for service names, such as with a share > social.|facebook, twitter|
|region|string|Pipe-delimited list of all regions in ancestry of clicked item. Automatically generated.|
|text|string|Text contents of the item clicked on, or an alternative text label to use instead|Chat with us, Visit our Twitter Page|