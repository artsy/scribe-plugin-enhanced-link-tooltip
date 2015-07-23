# scribe-plugin-enhanced-link-tooltip

A [Scribe](https://github.com/guardian/scribe) plugin for doing a Medium/Google Docs style tooltip UI instead of a prompt for inserting links.
Inspired by [artsy/scribe-plugin-link-tooltip](https://github.com/artsy/scribe-plugin-link-tooltip) and [ePages](https://github.com/ePages-de/scribe-plugin-enhanced-link-tooltip), but with a few modifications, namely:
* custom template (think of l10n)
* custom namespace for CSS classes and events
* pluggable link sanitizer
* tested with multiple Scribe instances
* links open in new tab/window

## Example

````javascript
var scribe = new Scribe(scribeElement);
scribe.use(scribePluginLinkTooltip());
````

These few CSS styles are more or less required to make the plugin work:
````css
.scribe-plugin-link-tooltip-hidden {
  visibility: hidden;
}

.scribe-plugin-link-tooltip {
  z-index: 1;
  white-space: nowrap;
}

.scribe-plugin-link-tooltip > * {
  display: inline-block;
}

.scribe-plugin-link-tooltip-state-edit .scribe-plugin-link-tooltip-show-on-view,
.scribe-plugin-link-tooltip-state-view .scribe-plugin-link-tooltip-show-on-edit {
  display: none;
}
````

## Positioning

The tooltip will prepend itself to the scribe element's parent element and use `position: absolute`, `top`, and `left` to position itself close to the text you're highlighting.
Therefore that element will get `position: relative` if (and only if) its current position is `static`.

## TODO

* Tests

# License

MIT
