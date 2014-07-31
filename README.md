## theon

Sass/CSS library to give you an indexed set of neutral colors derived from a central base color.
Mixing a bit of color into the greys looks nicer than the stark greys (#eee, #999, etc).

By default it has 15 shades, indexed by lightness. If you use the Sass version you can
customise the lighness and saturation, and/or build custom CSS.

![Theon greys](https://raw.githubusercontent.com/jjt/theon/master/theon-screen.png)

####Bower:
```shell
bower install --save theon
```

####CSS for declarative styles:

```html
<link rel="stylesheet" href="/path/to/theon.min.css">
...
<body class="theonBg-12">
    <h2 class="theon-4">Theon</h2>
    <svg>
      <rect class="theonFill-5 theonStroke-2"></rect>
    </svg>
```

####Sass functions/placeholders:
```scss
@import 'theon';

// Basic usage is through theon($index)
body {
  background: theon(14);
}

svg {
  @extend %theonFill-8;
  @extend %theonStroke-4;
}
```

#### Customise with Sass

```scss
// Can set custom base, lightnesses, and saturation variables before @importing theon
$theonBase: #7a7a79; // Default
$theonLgts: 4 10 16 22 29 36 43 50 57 64 71 78 84 89 95; // Defaults
$theonSats: 3 3  3  3  3  4  5  5  5  5  5  6  7  9  10; // Defaults 

@import 'theon';

// Can also configure by calling theonConfig() with positional config options
// This has the same effect as the above configuration
$customLgts: 4 10 16 22 29 36 43 50 57 64 71 78 84 89 95;
$customSats: 3 3  3  3  3  4  5  5  5  5  5  6  7  9  10;
theonConfig(#7a7a79, $customLgts, $customSats); 
```

#### Outputting CSS classes with Sass

```scss
// Set these vars to customise
$theonBase: #f00;
$theonLgts: 10, 30, 50, 70, 90
$theonSats: 10, 10, 20, 30, 40

// Then import this file
@import 'theon-css';
```

#### Enjoy

![Wigglewigglewigglewiggle](http://img.pandawhale.com/112961-Ramsay-Snow-sausage-gif-Imgur-aNM9.gif)
