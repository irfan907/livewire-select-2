# Pre Requisites
* You have installed [livewire/livewire](https://github.com/livewire/livewire).
* You have [alpine.js](https://alpinejs.dev/) scripts included in your project.

* You have [select2](https://select2.org/) scripts included in your project.

# Setup
> **Note**
> This does not support multiselect and defer updates.

1. Copy `select2.blade.php` to path `your-project/resources/views/components`

2. Include the component wherever to use in **.blade** file

```html
    <x-select2 class="" wire:model="filters.selectedUser"   dataArray="users" id="select_user"/>
```

3. Now in livewire component format the **dataArray="users"** as follows

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

4. Whenever your users data change and you want to **re-render the select2** to reflect new users , simply dispatch the browser event as follows

```phps
$this->dispatchBrowserEvent('re-init-select-2-component');
```