# training

## Setup
- Vagrant-ScotchBox
- HTML-Starter
- Gulp-Builder
- Gulpfile.js
  - Notify()
  - Listen()

## SASS
- @import
- /setup/
- _grid.scss
  - _name
  - /** Comments */
  - $variables

```
$grid-small: 500px;
$grid-large: 1000px;
```

```
/**
 * OUTER CONTAINER
 */
.outer-container {
    margin: auto;
}

@media (min-width: $grid-small) {
    .outer-container {
        max-width: $grid-small;
    }
}

@media (min-width: $grid-large) {
    .outer-container {
        max-width: $grid-large;
    }
}
```
```
.outer-container {
    margin: auto;

    @media (min-width: $grid-small) {
        max-width: $grid-small;
    }

    @media (min-width: $grid-large) {
        max-width: $grid-large;
    }
}
```
- @mixins
```
/**
 * BREAKPOINT
 */
@mixin breakpoint($size) {
    // Small
    @if $size == small {
        @media (min-width: $grid-small) {
            @content;
        }
    }

    // Large
    @if $size == large {
        @media (min-width: $grid-large) {
            @content;
        }
    }
}

/**
 * OUTER CONTAINER
 */
.outer-container {
    margin: auto;

    @include breakpoint(small) {max-width: $grid-small;}
    @include breakpoint(large) {max-width: $grid-large;}
}
```
- BEM
```
<div class="product-list outer-container">
    <div class="product-list__product">
        <p><img src="//placehold.it/250" alt=""></p>
    </div>
    <div class="product-list__product">
        <p><img src="//placehold.it/250" alt=""></p>
    </div>
    <div class="product-list__product">
        <p><img src="//placehold.it/250" alt=""></p>
    </div>
    <div class="product-list__product">
        <p><img src="//placehold.it/250" alt=""></p>
    </div>
</div>
```
`modules/_product-list.scss`
```
/**
 * PRODUCT LIST
 */
.product-list {

}

    
    .product-list__product {
        padding: 15px;

        @include breakpoint(small) {
            float: left;
            width: 50%;
        }

        @include breakpoint(medium) {
            width: 25%;
        }
    }
``` 
`setup/_mixins.scss`
```
/**
 * MIXINS & UTILITIES
 */


/**
 * CLEARFIX
 */
@mixin clearfix() {
    &:after {
        content:"";
        display:table;
        clear:both;
    }
}





/**
 * UNLIST
 */
@mixin unlist {
    list-style: none;
    margin: 0;
    padding: 0;
}
```

