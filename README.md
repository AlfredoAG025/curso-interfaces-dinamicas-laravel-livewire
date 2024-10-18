# Instalar Livewire

`composer require livewire/livewire`

# Crear un componente en Livewire

`php artisan make:livewire component-name`

## Archivos de Livewire

1. `app/Livewire/ComponentName.php` -> Lógica
2. `resources/views/livewire/component-name.blade.php` -> Vista

## Crear Modelo Laravel con Migración y Factory

`php artisan make:model ModelName -mf`

## Archivos de Laravel Migración y Factory

1. `database/migrations/date_create_model_name_table.php`
2. `database/factories/ModelNameFactory.php`

## Migrar con datos falsos

1. Modificar Factory regresando en el arreglo asociativo las claves y valores con valores falsos. Se puede usar `fake()`
2. Modificar el DatabaseSeeder indicando la cantidad de registros a generar.
3. Ejecutar el comando `php artisan migrate:refresh --seed`: Refresca las migraciones con los datos del DatabaseSeeder

