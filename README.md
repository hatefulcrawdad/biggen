##Biggen: Sass modal menus##
Create beautiful full-screen modal menus with the ease and customization of Sass.

### Markup Structure ###
To make your first Biggen menu, follow the markup below. There's only a few required elements. _Note: Any class name surrounded by [brackets] means use whatever class you want, just apply the appropriate mixin._

```html
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

Biggen relies on the handy [:checked trick](http://css-tricks.com/almanac/selectors/c/checked/) to create the "states" of the menu. This means that you'll need to pay close attention to how you structure your markup. The order is **always** `<label> + <input> + <div class="[overlay]">`.

1. Create an `<label class="[biggen-toggle]" for="[biggen-toggle]">`
2. Add an `<input type="checkbox" id="[biggen-toggle]">` right below that, with nothing in between. Make sure the id matches the class you used for the label
3. Add your `<div class="[biggen-overlay]">...</div>` and its contents right after that checkbox, the order is important!


### Built With Mixins ###
After defining your markup, we'll get styles in place. Biggen relies on Sass to compile, but feel free to still use Compass, Bourbon or any other library without any problems.

The basic Sass needed to get up and running with default styles, just match your class names:

```css
.[biggen-toggle] { @include biggen-toggle; }
.[biggen-overlay] { @include biggen-overlay; }
.[biggen-container] { @include biggen-container; }
.[biggen-list] { @include biggen-list; }
```

#### Biggen Toggle Mixin ####
A Biggen menu must contain a toggle, this is what enables it to open. You can run with the defaults provided or pass in a few arguments to make things your own.

```scss
// The mixin and arguments
@include biggen-toggle($font-size, $font-color, $font-weight, $font-style, $text-transform, $toggle-name, $overlay-class);

// The mixin arguments explained.
//
// - $font-size: Default is 16px. Control the font-size property, accepts any size
// - $font-color: Default is black. Color for default menu toggle
// - $font-color-hover: Default is rgba(black, .7). Color for default menu toggle while hovering
// - $font-weight: Default is normal. Control the font-weight property
// - $font-style: Default is null. Control the font-style property
// - $text-transform: Default is null. Control the text-transform property
// - $toggle-name: Match your toggle name, match your checkbox "id" and label "class" and "for"
// - $overlay-class: Match the class name for your biggen overlay
```