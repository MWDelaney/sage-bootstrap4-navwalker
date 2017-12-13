# Sage 9 friendly Bootstrap 4 Navwalker

Sets up a Bootstrap 4 Navwalker for Sage 9-based themes.

To install, run the following in your Sage9-based theme directory:
```bash
composer require "mwdelaney/sage-bootstrap4-navwalker": "1.0"
```

Include the navwalker in your `wp_nav_menu` function:
```
wp_nav_menu( array(
  'menu'              => 'primary',
  'theme_location'    => 'primary',
  ...
  'walker'            => new wp_bootstrap4_navwalker())
); 
```