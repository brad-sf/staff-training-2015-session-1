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

    @include breakpoint(small) {
        max-width: $grid-small;
    }

    @include breakpoint(large) {
        max-width: $grid-large;
    }
}
```



$variables
@mixins
BEM
cssguidelin.es
Modules
