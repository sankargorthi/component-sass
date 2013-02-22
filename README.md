# component-sass

  Transpile Sass files for your component builds.

## Install

    $ npm install component-sass

## Usage
  
  Add your `.sass` or `.scss` files to the `styles` array in your `component.json`:

  ```js
  {
    "styles": [
      "base.sass",
      "button.scss"
    ]
  }
  ```

  Use the plugin during your build process:

  ```js
  var fs            = require('fs')
    , Builder       = require('component-builder')
    , componentSass = require('component-sass');

  var builder = new Builder(__dirname);

  builder.use(componentSass);

  builder.build(function(err, res){
    if (err) throw err;
    fs.writeFileSync('build/build.js', res.require + res.js);
    fs.writeFileSync('build/build.css', res.css);
  });
  ```