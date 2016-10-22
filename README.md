# Polymer Global Variables Demo

This is a demo of Polymer Global Variables hack, based on Polymer Starter Kit.

You can see the result [here](https://polymer-global-variables-a8281.firebaseapp.com).

The localization is implemented using Polymer Global Variables API. `my-language` component changes the locales object using `Polymer.globalsManager`.

*my-language.html*
```javascript
...

properties: {
  locales: {
    type: Object,
    value: {
      english: { ... },
      spanish: { ... }
},

 ...

changeLanguage: function(event) {
  var language = event.target.value;
  // Load selected locales
  Polymer.globalsManager.set('locales', this.locales[language]);
}
```

Every element created has access to the `globals` property, so you don't need to bind the locales to every element where you need them:

*my-view1.html*
```html
<div class="card">
  <div class="circle">1</div>
  <h1>[[globals.locales.view1.title]]</h1>
  <p>[[globals.locales.view1.description]]</p>
  <p>[[globals.locales.view1.extended]]</p>
</div>
```
