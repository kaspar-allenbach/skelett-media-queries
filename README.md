# Skelett Media-Queries
A barebones (German: Skelett) media query library without any styling.

Used by [skelett-flexbox-grid](https://github.com/kaspar-allenbach/skelett-flexbox-grid) and [sekelett-container](https://github.com/kaspar-allenbach/skelett-container).


## The Skelett
- The Skelett repos are a bunch of standalone scss libraries without any styling so they don't interfere with your very beautiful project.
- No padding
- No margin
- no colors
- no nothing
- ITCSS naming to prevent style injections


| Size           | px      | Example Selector      | Example Selector (downwards) |
| -------------- |:-------:| ---------------------:| ----------------------------:|
| Extra small    | ≥320px  | `@include xs__up { … }` | `@include xs__down { … }`      |
| Small          | ≥576px  | `@include sm__up { … }` | `@include sm__down { … }`      |
| Medium         | ≥768px  | `@include md__up { … }` | `@include md__down { … }`      |
| Large          | ≥992px  | `@include lg__up { … }` | `@include lg__down { … }`      |
| Extra large    | ≥1200px | `@include xl__up { … }` | `@include xl__down { … }`      |


# Example of usage

#### foo.scss
```
@include sm__up {
  body {
    background: red;
  }
};
```
#### Compiles to
```
@media (min-width: 576px) {
  body {
    background: red;
    }
};
```

# Visibility Classes
There are visibility Extends as well:
```
.hidden-sm__down { @include sm__down { display: none; } }
```
This would hide an element on Lg size and below.


## Extend, Mixin, HTML
You can now add Visibility Classes as a `extend`, as a `Mixin` or as a class directly in your `HTML`:

#### As a Extend:

```
.yourThing { @extend %hidden-sm__down; }
```

#### As a Mixin:
```
.yourThing { @include hidden-sm__down; }
```

#### Or directely in HTML:

```
<li class="hidden-sm__down">Gugus Dada</li>
```
