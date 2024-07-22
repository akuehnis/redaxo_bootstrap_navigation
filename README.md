# redaxo\_bootstrap\_navigation
Create a Bootstrap navigation in Redaxo

## Installation

Create the file bootstrap\_navigation.php on your server, I suggest here:

/redaxo/src/addons/project/lib/bootstrap\_navigation.php

## Usage

In your template, create the navigation using this code:

```
<nav class="navbar navbar-expand-md bg-dark navbar-dark">
  <!-- Brand -->
  <a class="navbar-brand" href="#">Navbar</a>

  <!-- Toggler/collapsibe Button -->
  <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#collapsibleNavbar">
    <span class="navbar-toggler-icon"></span>
  </button>

  <!-- Navbar links -->
  <div class="collapse navbar-collapse" id="collapsibleNavbar">
    <?php 
    $nav = rex_bootstrap_navigation::factory();
    $category_id = 0;
    $depth = 4;
    $open = true;
    $ignore_offlines = true;
    echo $nav->get($category_id, $depth, $open, $ignore_offlines);
    ?>
  </div>
</nav>
```
