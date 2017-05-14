# sass
Personal SASS framework 

This is a simple framework that I have been building throughout my projects. I will make updates as needed for each project, keeping the structure already implemented.

Feel free to use it.

### Instalation

Clone or download all the files to your project

Watch the app.scss witch contains the output from all the framework

### Usage

basic structure

```
| --- components/
|     | -- _font-face.scss
|     | -- _project-vars.scss
|     | -- _project-colors.scss
| --- core/
|     | -- modules/
|          | - _functions.scss
|          | - _media-queries.scss
|          | - _mixins.scss
|     | -- _bootstrap-modules.scss
| --- partials/
|     | -- _home.scss
| --- _theme.scss
| --- app.scss
```

The `_theme.scss` file is where you will write your custom styles, register partials and components

I Already leave an example of Components and Partials. Feel free to use this structure as you want, but I believe this is a nice starting point to organize your var files, components and other assets files.

### About the queries
_This mini app was built under the MOBILE FIRST concept._ 

This means that all the styles are first created for mobile, like the standard. If you want to change the apearence for larger screens, then you can use the queries provided, witch are:

_media-tablet_ `@media screen and (min-width: 600px)`

_media-laptop_ `@media screen and (min-width: 1025px)`

_media-desktop_ `@media screen and (min-width: 1680px)`

*example*

```
h2.main-title {
  color: #999;
  font-size: 16px;
  @include media-tablet {
    font-size: 18px;
  }
  @include media-laptop {
    font-size: 22px;
  }
}
```


### Mixins

```
@mixin transition ($element, $duration, $animation) {
    transition: $element $duration $animation;
    -webkit-transition: $element $duration $animation;
    -moz-transition: $element $duration $animation;
    -o-transition: $element $duration $animation;
}
@mixin delay ($duration) {
    transition-delay: $duration;
    -webkit-transition-delay: $duration;
    -moz-transition-delay: $duration;
}

@mixin border-radius($all: 0) {
    @if $all {
        border-radius: $all;
        -webkit-border-radius: $all;
        -moz-border-radius: $all;
    }
}

@mixin box-shadow($value) {
    box-shadow: $value;
    -webkit-box-shadow: $value;
    -moz-box-shadow: $value;
}

@mixin appearance($value) {
    appearance: $value;
    -webkit-appearance: $value;
    -moz-appearance: $value;
    &::-ms-expand { /* for IE 11 */
        display: none;
    }
}

@mixin translate($x, $y) {
    transform: translate($x, $y);
    -webkit-transform: translate($x, $y);
    -moz-transform: translate($x, $y);
    -o-transform: translate($x, $y);
    -ms-transform: translate($x, $y);
}
@mixin rotate($value) {
    transform: rotate($value);
    -webkit-transform: rotate($value);
    -ms-transform: rotate($value);
    -moz-transform: rotate($value);
}

@mixin img-scale($value) {
    -webkit-transform:scale($value); /* Safari and Chrome */
    -moz-transform:scale($value); /* Firefox */
    -ms-transform:scale($value); /* IE 9 */
    -o-transform:scale($value); /* Opera */
     transform:scale($value);
}

@mixin input-placeholder($element) {
    #{$element}::-webkit-input-placeholder { /* Chrome/Opera/Safari */
      @content;
    }
    #{$element}::-moz-placeholder { /* Firefox 19+ */
      @content;
    }
    #{$element}:-ms-input-placeholder { /* IE 10+ */
      @content;
    }
    #{$element}:-moz-placeholder { /* Firefox 18- */
      @content;
    }
}

@mixin img-scale($value) {
    transform: scale($value);
    -webkit-transform: scale($value);
    -moz-transform: scale($value);
    -ms-transform: scale($value);
    -o-transform: scale($value);
}
```


