![FullStack UI](logo-fullstack-ui.png)
[![FOSSA Status](https://app.fossa.io/api/projects/git%2Bgithub.com%2Fkaifaust%2Ffullstack-ui.svg?type=shield)](https://app.fossa.io/projects/git%2Bgithub.com%2Fkaifaust%2Ffullstack-ui?ref=badge_shield)

## What is FullStack UI?
FullStack UI is a SCSS framework built to make front end UI development fast and scalable. This project is no longer in active development and is not recommended for production.

## Architecture

* **CORE**: Framework core
* **TOOLS**: Mixins and functions
* **SETTINGS**: Site-wide settings
* **GENERIC**: Low-specificity, far-reaching rulesets and classless elements
* **OBJECTS**: Objects, abstractions, and design patterns (e.g. .media {})
* **COMPONENTS**: Discrete, complete chunks of UI (e.g. .carousel {})
* **UTILITIES**: High-specificity, very explicit selectors. Overrides and helper classes (e.g. .u-hidden {})


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

---

### License
MIT


[![FOSSA Status](https://app.fossa.io/api/projects/git%2Bgithub.com%2Fkaifaust%2Ffullstack-ui.svg?type=large)](https://app.fossa.io/projects/git%2Bgithub.com%2Fkaifaust%2Ffullstack-ui?ref=badge_large)