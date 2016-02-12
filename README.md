# Angular Selector

[![MIT License](http://img.shields.io/badge/license-MIT-blue.svg?style=flat)](LICENSE)
[![Gitter](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/indrimuska/angular-selector?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge)

*Angular Selector* is a native AngularJS directive that transform a simple `<select>` box into a full html select with typeahead.

Check out the examples page to learn more: [http://indrimuska.github.io/angular-selector](http://indrimuska.github.io/angular-selector).

![Angular Selector](http://indrimuska.github.io/angular-selector/img/angular-selector.png)

### Features

* **No-jQuery Required**<br>
  Angular Selector is a full native Angular directive, so you can use it without have to include any other library (except AngularJS, of course!).
* **Skinnable**<br>
  You can define a template for the items in the dropdown list and a template for selected items.
* **RTL Support**<br>
  To use it in with any kind of text direction.
* **Remote Resource Loading**<br>
  Fetch your data from an external source and use it in your application.
* **From HTML `<option>` to JS `object`**<br>
  Fill your `<select>` from server-side ad use data-attributes for every option you have, then *Angular Selector* performs for you the conversion to a simple array of objects.
* **Custom Option Creation**<br>
  You can create new options and add them to the list, just by hitting <kbd>Enter</kbd>.
* **Keyboard support**<br>
  Move up and down the dropdown list using keyboard arrows. Select highlighted item pressing <kbd>Enter</kbd>. Remove last selected item with <kbd>Del</kbd> key.
* **Responsive**<br>
  Perfect for use in mobile environments.

### Dependencies

* Just [AngularJS](https://angularjs.org/)!

### Installation

```
jspm i github:palecek/angular-selector.js
```

Load stylesheet and scripts into your app:

```html
<script src="//ajax.googleapis.com/ajax/libs/angularjs/1.4.3/angular.min.js"></script>
<script src="//cdn.rawgit.com/palecek/angular-selector/master/angular-selector.js"></script>
<link href="//cdn.rawgit.com/palecek/angular-selector/master/angular-selector.css" rel="stylesheet">
```

Add the dependency to your module:
```javascript
var app = angular.module('MyApp', ['selector']);
```

### Examples

Look at [these](http://indrimuska.github.io/angular-selector/).

### Options

Parameter | Type | Default | Description
---|---|---|---
model | `Property` | | Two-way binding property that models the `select` view.
name | `String` | | Input name attribute.
disable | `Boolean` | `false` | Enable/disable the select. Note the name is `disable` not `disabled` to avoid collisions with the HTML5 multiple attribute.
multi | `Boolean` | `false` | Allows to select more than one value. Note the name is `multi` not `multiple` to avoid collisions with the HTML5 multiple attribute.
placeholder | `String` | | Optional placeholder text to display if input is empty.
options | `Array` | `[]` | Set of options to display.<br><br>If you don't use a custom template (`viewItemTemplate` and `dropdownItemTemplate`) and you don't change the default values of `valueAttr` and `labelAttr`, each option in this array must contain a `label` key and a `value` key.
valueAttr | `String` | `null` | Name of the value key in options array. This also sets the type of result for the model: if you don't set this attribute (`null` by default) the entire object option is returned, otherwise it will be returned only the selected property.
labelAttr | `String` | `"label"` | Name of the label key in options array.
groupAttr | `String` | `"group"` | Name of the `optgroup` label key in options array. It allows to group items by the selected key. Items have to be already sorted to see the groups just one time.
rtl | `Boolean` | `false` | Two-way bindable attribute to set a Right-To-Left text direction.
api | `Object` | `{}` | This object is equipped with the methods for interacting with the selector. Check out the ["APIs" example](http://indrimuska.github.io/angular-selector/).
create | `Boolean` or `Function` | | Allows users to type the label of their own options and push them into the list. You can pass a function that returns the full format of the option, using `input` as parameter, or set it to `true` to let Angular Selector create an object with the default properties given by `valueAttr` and `labelAttr`.
change | `Function` | | Callback fired every time the selected values change. It provides two parameters: `newValue` and `oldValue`.
remote | `Object` | <pre>{<br>  method: 'GET',<br>  cache: true,<br>  params: {}<br>}</pre> | Configuration object to pass to the native `$http` service ([docs](https://docs.angularjs.org/api/ng/service/$http#usage)).
remoteParam | `String` | `"q"` | Name of the query key in the remote parameter object. You should use this parameter to perform server-side filtering.
removeButton | `Boolean` | `true` | Two-way bindable attribute to see the remove button (cross icon).
viewItemTemplate | `String` | `"selector/item-default.html"` | Template URL of selected item(s).
dropdownItemTemplate | `String` | `"selector/item-default.html"` | Template URL of each item in the dropdown list.
dropdownGroupTemplate | `String` | `"selector/group-default.html"` | Template URL of each group (header) in the dropdown list.

### Contributions

For personal support requests, please use [Gitter](https://gitter.im/indrimuska/angular-selector), otherwise create first a live example (with [Plunker](http://plnkr.co/)) then describe your problem using [GitHub issue tracker](https://github.com/indrimuska/angular-selector/issues/new).

### License

Copyright (c) 2015 Indri Muska. Licensed under the MIT license.
