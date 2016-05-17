Gravatar Tools for CakePHP 2.0
==========================================================================================

This project separates the url generation from the CakePHP image tag
generation in the helper.  It provides the same url generation capability
as a component if you need to build avatar urls outside of the view context.

Installation
------------------------------------------------------------------------------------------

at the root level of your cakephp project

assuming you are using "app" as your app folder and you plan to use the name "Gravatar" for the Plugin

git submodule add https://simkimsia@github.com/simkimsia/cakephp-gravatar.git app/Plugin/Gravatar


Helper Usage
------------------------------------------------------------------------------------------

### In your controller:
```php
<?php
class MyController extends AppController {
  public $helpers = array('Gravatar.Gravatar');
...
}
```
### In your view:

```php
<?php echo $this->Gravatar->image('guest@example.com', array('size' => 98), array('alt' => 'Gravatar')); ?>
```

Component Usage
------------------------------------------------------------------------------------------
### In your controller:
```php
<?php
class MyController extends AppController {
  public $components = array('Gravatar.Gravatar');
...
}
```
### In some function:

```php
<?php
if($this->Gravatar->accountExists('email@example.com')) {
	$this->Gravatar->download('email@example.com', '/webroot/img/users/avatar.jpg');
}
```
