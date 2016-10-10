# FullStack UI

This project is under active development and is not recommended for production use at this time.

## What is FullStack UI?
FullStack UI is a fork of InuitCSS maintained by FullStack Labs. It builds on the some of the core architectural principles of InuitCSS and introduces new paradigms that allow for greater extensibility and scalability.

## Goal
FullStack UI is our answer to the challenges we faced in our software consultancy. We needed the ability to start and complete projects quickly while keeping the codebase scalable. We wanted something as easy to get started with as Bootstrap, as themeable as Semantic UI and as dynamic as InuitCSS.

## Getting Started
The best way to start using FullStack UI is with NPM.

Download and install [Node](https://nodejs.org/en/download/).
Node comes with npm installed, so all you have to do is update it:
```
$ npm install npm@latest -g
```

Now you can install this framework:
```
$ npm install fullstack-ui --save
```

Navigate to `node_modules/fullsack-ui/`

Copy `index.scss` to your project's root CSS folder.

Update the import paths to point to the framework:
```
@import "node_modules/fullstack-ui/palettes/palettes.default";
```

You'll need something to compile the app. `node-sass` is an option.
```
$ npm install node-sass --save-dev
```

You can have `nodemon` watch for SCSS and compile on save.
```
$ npm install nodemon --save-dev
```

Add this to your `package.json`. The build script takes the first argument as the source directory and the second as the destination. Adjust these as needed:
```
"scripts": {
  "build:css": "node-sass src/scss/index.scss src/css/index.css",
  "watch:css": "nodemon -e scss -x \"npm run build:css\"",
}
```

Finally, run this:
```
$ npm run watch:css
```

Don't forget to `<link>` `index.css` in your project's `<head>` and you're ready to roll!

## Architecture
FullStack UI's killer feature is its generative qualities. It utilizes structured data (maps) and initializers (mixins) to generate classes and styles. This strategy allows you to build on the framework in a truly scalable way. To get the most out of this framework, you'll want to familiarize yourself with the following concepts.

### Palettes
A **Palette** is a Sass map with with one or more key-value pairs. FullStack UI comes with a default palette that will provide a minimal but effective supply of ready-to-go colors. This gets applied to the `$global-palette` which acts as our single source of our app's colors.
```
$global-palette: (
  "primary"   : rgb(33,150,243),
  "secondary" : rgb(39,49,68),
  "success"   : rgb(76,175,80),
  "alert"     : rgb(244,67,54),
  ...
);
```

**NOTE**: This will eventually fall under a higher-level `Themes` paradigm.

### Initializers
An *Initializer* is a Sass mixin that do one of two things:

1. Instantiate a Sass map if it has not already been instantiated

2. Add/overwrite existing global settings

Initializers come before settings because we use them to build our settings.

Right now, we only have two initializers, but this will soon grow to include typography, z-index, etc.

#### Color Initializers
`$global-palette`'s values can be added to or overwritten with `set-color($id, $color)`:
```
@include set-color("primary", #BADA55);
```

Sometimes it's helpful to apply a whole palette to `$global-palette`. You can do this with:
```
@include set-palette($palette-google-material);
```

#### Spacing Initializers
`$global-spacing` contains our app's single source of spacing units, which is quite helpful. Its default values are based on sensible sizes that make vertical rhythm easy:
```
$global-spacing: (
   null:   round($global-line-height),
  "nano":  round($global-line-height * 0.125),
  "micro": round($global-line-height * 0.25),
  "tiny":  round($global-line-height * 0.5),
  "small": round($global-line-height * 0.75),
  "large": round($global-line-height * 1.5),
  "huge":  round($global-line-height * 2),
) !default;
```

You can add or override these with `set-spacing-unit($name, $spacing)`:
```
set-spacing-unit("my-custom-spacing-unit": 100px);
```

# *The following topics will be covered soon...*


### Settings


### Tools


#### Debug
Sometimes its helpful to display the value of a variable at a specific point in compilation. For example, if you'd like to see what's in `$global-palette`.
```
@include debug($global-palette);
```
This embeds a pseudo element on `<body>` that includes the variable's value.


### Generic


### Elements


### Objects


### Components


### Utilities
