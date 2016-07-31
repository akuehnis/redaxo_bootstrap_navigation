# redaxo_bootstrap_navigation
Create a Bootstrap navigation in Redaxo

## Installation

Create the file bootstrap_navigation.php on your server, I suggest here:

/redaxo/data/bootstrap_navigation.php

## Usage

In your template, create the navigation using this code:

```
<nav class="navbar">
    <div class="container-fluid">
        <div class="navbar-header">
            <button type="button" class="navbar-toggle" data-toggle="collapse" data-target="#myNavbar">
                <span class="icon-bar"></span>
                <span class="icon-bar"></span>
                <span class="icon-bar"></span> 
            </button>
            <a class="navbar-brand" href="<?php echo rex_getUrl(rex_article::getSiteStartArticleId());?>"><?php echo rex::getServerName();?></a>
        </div>
        <div class="collapse navbar-collapse" id="myNavbar">
            <?php 
            include_once rex_path::data('bootstrap_navigation.php');
            $nav = rex_bootstrap_navigation::factory();
            $category_id = 0;
            $depth = 4;
            $open = true;
            $ignore_offlines = true;
            echo $nav->get($category_id, $depth, $open, $ignore_offlines);
            ?>
        </div>
    </div>
</nav>
```
