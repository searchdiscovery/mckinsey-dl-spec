# UI Item Clicked

These HTML attributes should be added to items that do not qualify as CTAs, but that still need to be tracked. Examples include expanding a UI accordion, clicking on a tab, or clicking on an interactive component.

## Data Attributes HTML Code

```html
  <a href="<linkDestination>"
    data-layer-event-prefix="UI Item"
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
  "event": "UI Item Clicked",
  "linkInfo": {
    "category": "<category>",
    "subcategory": "<subcategory>"
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