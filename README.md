### CakePHP API Flash

This plugin consists of only a component to be used in your controllers in order to set flash message in the serialized response.

## Usage

Load the component in the desired controller:

```php
# the initialize method

$this->loadComponent('ApiFlash');
```

Then just call the `ApiFlashComponent#set(key, message)` method from any controller method:

```php
$this->ApiFlash->set('success', 'You were successfully authenticated!')

```

It will simply add an array to the `flash` key in the response body:
```php
[
	'flash' => [
		'success' => 'You were successfully authenticated!'
	]
]
```

## Config

You can configure the key which the array will be set in the response. Simply add a `key` index to the config of `loadComponent` call:
```php
# the intialize method

$this->loadComponent('ApiFlash', ['key' => 'feedback']);
```
