##Biggen: Sass Modal Menus##
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

```scss
.[biggen-toggle] { @include biggen-toggle; }
.[biggen-overlay] { @include biggen-overlay; }
.[biggen-container] { @include biggen-container; }
.[biggen-list] { @include biggen-list; }
```

#### Biggen Toggle Mixin ####
A Biggen menu must contain a toggle, this is what enables it to open. You can run with the defaults provided or pass in a few arguments to make things your own.

```scss
@include biggen-toggle($font-size, $font-color, $font-weight, $font-style, $text-transform, $toggle-name, $overlay-class);

// The mixin arguments explained.
//
// - $font-size: Default is `16px`. Control the font-size property, accepts any size
// - $font-color: Default is `black`. Color for default menu toggle
// - $font-color-hover: Default is `rgba(black, .7)`. Color for default menu toggle while hovering
// - $font-weight: Default is `normal`. Control the font-weight property
// - $font-style: Default is `null`. Control the font-style property
// - $text-transform: Default is `null`. Control the text-transform property
// - $toggle-name: Match your toggle name, match your checkbox "id" and label "class" and "for"
// - $overlay-class: Match the class name for your biggen overlay
```

#### Biggen Overlay Mixin ####
Since Biggen is a modal menu, we need to have some sort of overlay to cover the original site a bit.

```scss
@include biggen-overlay($bg1, $bg2);

// The mixin arguments explained.
//
// - $bg1: Default is `darken(lightblue, 25%)`. Control default background color for page overlay
// - $bg2: Default is `false`. If true: adds linear gradient between $bg1 and $bg2
```

#### Biggen Container Mixin ####
A default Biggen menu contains a background container that can be styled with the following mixin.

```scss
@include biggen-container($bg1, $bg2, $margin-top, $padding, $width);

// The mixin arguments explained.
//
// - $bg1: Default is `darken(lightblue, 15%)`. Set the background color for container element
// - $bg2: Default is `false`. Creates a linear gradient between $bg1 and $bg2
// - $margin-top: Default is `10%`. Control how far away from the top of the page you want your menu to be
// - $padding: Default is `40px`. Control padding around the inside of a Biggen menu
// - $width: Default is `50%`. Control the non-mobile width of a Biggen menu
```

#### Biggen List Mixin ####
This mixin styles up the unordered list used to hold all the links inside a Biggen menu.

```scss
@include biggen-list($list-count, $font-size, $link-color, $link-color-hover, $text-decoration, $text-transform, $text-padding);

// The mixin arguments explained.
//
// - $list-count: Default is `1`. Control how many link lists. 1, 2, 3?
// - $font-size: Default is `12px`. Control the font-size property of links
// - $link-color: Default is `#fff`. Control the color for links
// - $link-color-hover: Default is `darken(lightblue, 40%)`. Set the :hover, :focus and :active color for links
// - $text-decoration: Default is `none`. You can control the text-decoration property.
// - $text-transform: Default is `uppercase`. You can control the text-transform property of links.
// - $text-padding: Default is `20px`. Control the padding around links in the list.
```