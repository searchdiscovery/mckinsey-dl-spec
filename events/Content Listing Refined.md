# Content Listing Refined

Fire whenever a user clicks on a search feature that refines or otherwise modifies the search results.

## Javascript Code

```js
window.appEventData = window.appEventData || [];
appEventData.push({
  "event": "Content Listing Refined",
  "listingRefined": {
    "refinementType": "<refinementType",
    "searchType": "<searchType>"
  }
});
```
## Variable Definitions

|Field|Type|Description|Example|Pattern|Min Length|Max Length|Minimum|Maximum|Multiple Of|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|refinementType|string|Describes the type of refinement performed.|filter, sort|
|searchType|string|Describes the type of search performed.|article, content, job, people, etc.|