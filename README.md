##Biggen: Sass modal menus##
Create beautiful full-screen modal menus with the ease and customization of Sass.

#### Markup Structure ####
To make your first Biggen menu, you'll need to follow the simple markup structure provided below. There are only a few requires elements and class names are all up to you since the entire extension is built with mixins, giving you ultimate flexibility.

_Note: Any class name surrounded by [brackets] means use whatever class you want, just apply the appropriate mixin._

```
<!-- Biggen Toggle -->
<label class="[biggen-toggle]" for="[biggen-toggle]" onclick><span>&#9776;</span> Menu</label>
<input type="checkbox" id="[biggen-toggle]">

<!-- Biggen Menu -->
<div class="[biggen-overlay]">
  <div class="[biggen-container]">
    <ul class="[biggen-list]">
      <li><a href="#">Menu Item 1</a></li>
      ...
    </ul>
  </div>
</div>
```

##### Required Elements #####
Biggen relies on a handy (:checked trick)[http://css-tricks.com/almanac/selectors/c/checked/] to create the states that we need for the menu. This means that you'll need to pay close attention to how you structure the markup used to create the menu. The order is **always** `<label>` follow by `<input>` followed by `<div class="[overlay]">`.

1. Create an `<label class="[biggen-toggle]" for="[biggen-toggle]">`
2. Add an `<input type="checkbox" id="[biggen-toggle]">` right below that, with nothing in between. Make sure the id matches the class you used for the label
3. Add your `<div class="[biggen-overlay]">...</div>` and its contents right after that checkbox, the order is important!
