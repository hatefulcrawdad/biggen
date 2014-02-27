##Biggen: Modal Menus##
Create beautiful full-screen modal menus with the ease and customization of Sass.

#### Markup Structure ####
To make your first Biggen menu, you'll need to follow the simple markup structure provided below. There are only a few requires elements and class names are all up to you since the entire extension is built with mixins, giving you ultimate flexibility.

_Note: Any class name surrounded by brackets means use whatever class you want, just apply the appropriate mixin._

##### Menu Icon #####
```
<input type="radio" id="biggen-open" name="biggen-toggle">
<label class="[biggen-open]" for="biggen-open"><span>&#9776;</span> Menu</label>
```

##### Modal Menu #####
```
<div class="[biggen-overlay]">
  <div class="[biggen-container]">
    <input type="radio" id="biggen-close" name="biggen-toggle">
    <label for="biggen-close" class="[biggen-close]"><span>&times;</span></label>
    <ul class="[biggen-list]">
      <li class="[biggen-list-item]"><a class="[biggen-list-item-link]" href="#">Menu Item 1</a></li>
      <li class="[biggen-list-item]"><a class="[biggen-list-item-link]" href="#">Menu Item 2</a></li>
      ...
    </ul>
  </div>
</div>
```
