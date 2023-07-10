# Pre Requisites
* You have installed [livewire/livewire](https://github.com/livewire/livewire).
* You have [alpine.js](https://alpinejs.dev/) included in your project.

# Setup
1. Copy `select2.blade.php` to path `your-project/resources/views/components`

2. Include the component in view file

```html
<x-select2 class="" wire:model="filters.selectedUser" dataArray="users" id="select_user"/>
```

3. Now in livewire component format the dataArray as follows

```php
$users=[
    [
        'id'=>'1',
        'text'=>"John"
    ],
    [
        'id'=>'2',
        'text'=>"John Doe"
    ],
]
```

4. Whenever your users data change and you want to re-reder the select2 to reflect new users , simply dispatch the browser event as follows

```phps
$this->dispatchBrowserEvent('re-init-select-2-component');
```