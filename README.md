# Alternative select element with input and search functional

This script registers a new element `select-search` in the browser. To ensure that the data from the element is sent from the form, when rendering, a hidden element (`input[type="hidden"]`) is added after the element, which tracks the value of the `select-search`.

***
**Attention!**
Do not forget that this element will not be correctly displayed in a browser with scripts disabled.
Consider this information when developing
***

## Installation

To use the element, connect the file in the end of document, e.g.

```html
<script src="https://your-site.com/js/select-search.js"></script>
```

## Using

Syntax of `select-search` is similar to `select` element syntax. Instead of the `option` element, the element `s-option` is used, e.g.

```html
<select-search name="test" placeholder="input to search" required>
    <s-option value="1">First item</s-option>
    <s-option value="2" selected>Second item</s-option>
    <s-option value="3">Third item</s-option>
</select-search>
```

## Customizing

Element `select-search` can be customized through special properties, e.g.

```css
select-search {
    --select-search-border: 1px solid red;
    --select-search-arrow-background: linear-gradient(0deg, #858585 0%, #dedede 100%);
    --select-search-item-hover-background: #888888;
}
```

### CSS-properties of element


Property name                               |  CSS property type  |  Default value  |
--------------------------------------------|---------------------|-----------------|
**CSS general properties:**                 |                     |                 |
--select-search-border                      |     border          |  1px solid #aaa |
--select-search-border-radius               |     border-radius   |       2px       |
--select-search-background                  |     background      |      initial    |
--select-search-color                       |     color           |      initial    |
--select-search-font                        |     font            |      initial    |
**CSS properties of arrow block:**          |                     |                 |
--select-search-arrow-symbol                |     unicode string  |     '\2304'     |
--select-search-arrow-width                 |     width           |       20px      |
--select-search-arrow-background            |     background      |    transparent  |
**CSS properties of input field:**          |                     |                 |
--select-search-input-padding               |     padding         |        4px      |
--select-search-input-color                 |     color           |      initial    |
--select-search-input-font                  |     font            |      initial    |
**CSS properties of input field - result not found:**|            |                 |
--select-search-notvalued-border            |     border          |  1px solid #aaa |
--select-search-notvalued-background        |     background      |    transparent  |
--select-search-notvalued-color             |     color           |      initial    |
**CSS properties of input field - required is empty:**|           |                 |
--select-search-errored-border              |     border          |  1px solid #aaa |
--select-search-errored-background          |     background      |    transparent  |
--select-search-errored-color               |     color           |      initial    |
**CSS properties of items list:**           |                     |                 |
--select-search-list-background             |     background      |      #ffffff    |
--select-search-list-height <br>*Maximal value of list height*|     height          |       200px     |
--select-search-list-border                 |     border          |  1px solid #aaa |
--select-search-list-border-radius          |     border-radius   |       2px       |
**CSS properties of items:**               |                     |                 |
--select-search-item-padding                |     padding         |     4px 2px     |
--select-search-item-hover-background <br>*Background of mouse hover item*|     background      |     #eeeeee     |
--select-search-item-focus-background <br>*Background of focused item*|     background      |     #eeeeee     |
--select-search-item-selected-background <br>*Background of selected item*    |     background      |     #f5f5f5     |

## JavaScript events und properties

**Tracked events:**

`change`

**Available properties**

* `value` - current value of element (default `s-option[selected]`)
* `displayVale` - current displayed value

E.g.:

```js
document.querySelector('select-search').addEventListener('change',function(e){
  console.log(e.target.displayValue);
  console.log(e.target.value);
});
```
