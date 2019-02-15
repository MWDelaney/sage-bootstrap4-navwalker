# Sage 9 friendly Bootstrap 4 Navwalker

Sets up a Bootstrap 4 Navwalker for Sage 9-based themes.

To install, run the following in your Sage9-based theme directory:
```bash
composer require "mwdelaney/sage-bootstrap4-navwalker"
```

Include the navwalker in your `wp_nav_menu` function:

## As a [Controller](https://github.com/soberwp/controller) method (Recommended)
In your Controller, probably `app.php`
```php
/**
 * Primary Nav Menu arguments
 * @return array
 */
public function primarymenu() {
  $args = array(
    'theme_location'    => 'primary_navigation',
    'menu_class'        => 'navbar-nav',
    'walker'            => new \App\wp_bootstrap4_navwalker(),
    ...
  );
  return $args;
}
```

In your Blade file, probably `header.blade.php`
```php
@if (has_nav_menu('primary_navigation'))
  {!! wp_nav_menu($primarymenu) !!}
@endif
```

## Without Controller
If you're not setting up your template data with Controller, you'll need to fully reference the `\App\wp_bootstrap4_navwalker()`.
In your Blade file, probably `header.blade.php`
```php
@if (has_nav_menu('primary_navigation'))
  {!! wp_nav_menu(['theme_location' => 'primary_navigation', 'menu_class' => 'navbar-nav', 'walker' => new \App\wp_bootstrap4_navwalker()]) !!}
@endif
```
