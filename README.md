# Bulma Clone

## Instructions

The goal is to create a copy-cat of https://mythril.io/ with [Bulma CSS Framework](https://bulma.io).

To start, you can either clone the project (if you are a Git master) or [download the Zip](https://github.com/mc100s/bulma-clone/archive/master.zip).


## First steps

### Start the project

Create an `index.html` file and take the starter template from: https://bulma.io/documentation/overview/start/

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Hello Bulma!</title>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/bulma/0.7.0/css/bulma.min.css">
  <script defer src="https://use.fontawesome.com/releases/v5.0.7/js/all.js"></script>
</head>
<body>
  <section class="section">
    <div class="container">
      <h1 class="title">
        Hello World
      </h1>
      <p class="subtitle">
        My first website with <strong>Bulma</strong>!
      </p>
    </div>
  </section>
</body>
</html>
```

Open the project and check if you have the same thing as below, with the same font.

![](https://i.imgur.com/bxhI8QM.png)


### Include the navbar 

Now we are going to add the navbar. To start, we can copy the code from the [Bulma Transparent navabar](https://bulma.io/documentation/components/navbar/#transparent-navbar) and change a little the text.

This is the code you can have just after the opening `<body>` tag.

```html
<nav class="navbar is-transparent">
  <div class="navbar-brand">
    <a class="navbar-item" href="https://bulma.io">
      <img src="https://bulma.io/images/bulma-logo.png" alt="Bulma: a modern CSS framework based on Flexbox" width="112" height="28">
    </a>
    <div class="navbar-burger burger" data-target="navbarExampleTransparentExample">
      <span></span>
      <span></span>
      <span></span>
    </div>
  </div>

  <div id="navbarExampleTransparentExample" class="navbar-menu">
    <div class="navbar-start">
      <div class="navbar-item has-dropdown is-hoverable">
        <a class="navbar-link" href="#">
          Games
        </a>
        <div class="navbar-dropdown is-boxed">
          <a class="navbar-item" href="#">
            Browse games
          </a>
          <hr class="navbar-divider">
          <a class="navbar-item" href="#">
            Reviews
          </a>
          <a class="navbar-item" href="#">
            Recommendations
          </a>
        </div>
      </div>
      <div class="navbar-item has-dropdown is-hoverable">
        <a class="navbar-link" href="#">
          Community
        </a>
        <div class="navbar-dropdown is-boxed">
          <a class="navbar-item" href="#">
            User
          </a>
          <hr class="navbar-divider">
          <a class="navbar-item" href="#">
            Staf
          </a>
        </div>
      </div>
    </div>

    <div class="navbar-end">
      <div class="navbar-item">
        <div class="field is-grouped">
          <p class="control">
            <a class="bd-tw-button button" data-social-network="Twitter" data-social-action="tweet" data-social-target="http://localhost:4000" target="_blank" href="https://twitter.com/intent/tweet?text=Bulma: a modern CSS framework based on Flexbox&amp;hashtags=bulmaio&amp;url=http://localhost:4000&amp;via=jgthms">
              <span class="icon">
                <i class="fas fa-sign-in-alt"></i>
              </span>
              <span>
                Login
              </span>
            </a>
          </p>
          <p class="control">
            <a class="button is-primary" href="https://github.com/jgthms/bulma/releases/download/0.7.0/bulma-0.7.0.zip">
              <span class="icon">
                <i class="fas fa-user-plus"></i>
              </span>
              <span>Download</span>
            </a>
          </p>
        </div>
      </div>
    </div>
  </div>
</nav>
```

And this is what it should look like:

![](https://i.imgur.com/llaHqc1.png)


### Make the navbar responsive

If your screen is small, you will see a burger menu appearing and hidding the links from the navbar. But if you click on it, nothing happens.

The reason is we need to make the website interactive with JavaScript and the Bulma package does not come with any JavaScript. If we follow the instructions from the [navbar menu documentation](https://bulma.io/documentation/components/navbar/#navbar-menu), we just need to add the following javascript, for example in `script.js` file.

```js
document.addEventListener('DOMContentLoaded', function () {

  // Get all "navbar-burger" elements
  var $navbarBurgers = Array.prototype.slice.call(document.querySelectorAll('.navbar-burger'), 0);

  // Check if there are any navbar burgers
  if ($navbarBurgers.length > 0) {

    // Add a click event on each of them
    $navbarBurgers.forEach(function ($el) {
      $el.addEventListener('click', function () {

        // Get the target from the "data-target" attribute
        var target = $el.dataset.target;
        var $target = document.getElementById(target);

        // Toggle the class on both the "navbar-burger" and the "navbar-menu"
        $el.classList.toggle('is-active');
        $target.classList.toggle('is-active');

      });
    });
  }

});
```

Don't forget to link the JavaScript file in your `index.html` by adding the following tag in your `<head>` tag:

```html
<script src="script.js"></script>
```

Now you have a responsive navbar!

![](https://i.imgur.com/obMJKqx.png)


### Fit the navbar in a container

If you have a deep look on the original website, you will see the navbar has some padding left and right. To solve that, you can add a div with the class container inside your navbar, like this:

```html
<nav class="navbar is-transparent">
  <div class="container">
    ...
  </div>
</nav>
```

![](https://i.imgur.com/5NpcUQh.png)


### Welcome section

Now we will create the first section, without the background image.

To do that, you can replace your current section with the following one.


```html
<section class="hero is-primary is-medium">
  <div class="hero-body">
    <div class="container">
      <h1 class="title">
        Welcome to my website
      </h1>
      <h2 class="subtitle">
        Track, discover, review and recommend video games.
      </h2>
    </div>
  </div>
</section>
```

### Trending section

For that section, you will need to use:
- [Bulma Columns responsivness](https://bulma.io/documentation/columns/responsiveness/)


### Recent Game Reviews section

For that section, you will need to use:
- [Bulma notification](https://bulma.io/documentation/elements/notification/)
- [Bulma tag](https://bulma.io/documentation/elements/tag/)


### Recent Game Recommendations section

For that section, you will need to use:
- [Bulma Columns basics](https://bulma.io/documentation/columns/basics/)
- [Bulma buttons](https://bulma.io/documentation/elements/button/)


### Statistics section

For that section, you will need to use:
- [Bulma Hero](https://bulma.io/documentation/layout/hero/)
- [Bulma Columns responsivness](https://bulma.io/documentation/columns/responsiveness/)


### Add your own CSS file

For that part, you can just create a `style.css` file and link it in your `index.html`:

```html
<link rel="stylesheet" href="style.css">
```

