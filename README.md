# KMaps Typeahead

This repository contains a JQuery plugin which allows SHANTI's KMaps Solr index to be searched using [Typeahead plug-in](https://github.com/corejavascript/typeahead.js).

Please visit the project's [documentation](https://github.com/rderik/shanti_kmaps_typeahead/wiki) for examples and use cases.

# Basic usage

Markup:
```HTML
  <input type="text" id="kmaps-search-source" class="kmaps-search-term form-control form-text text-full" placeholder="Search source by text..." autocomplete="off">
```
Script
```javascript
$("#kmaps-search-source").kmapsTypeahead({
    term_index: "URL_SOLR_TERM_INDEX",
    domain: "sources",
    filters_domain: "subjects",
    root_kmap_path: null,
    features_path: "/features/",
    autocomplete_field: "title",
    filters: "asset_type:sources"
  });
  $("#kmaps-search-source").bind('typeahead:select', function(ev, suggestion) {
  console.log('Selection: ' + JSON.stringify(suggestion));
  $("#citation_info_source_id").val(suggestion.id);
});
```
