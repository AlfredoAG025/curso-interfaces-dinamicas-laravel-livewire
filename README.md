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
3. Ejecutar el comando `php artisan migrate:refresh --seed`: Refresca "Borra datos sin borrar las estructuras" las migraciones con los datos del DatabaseSeeder

# Configuración de datos falsos

`\App\Models\Category::factory(10)
            ->hasThreads(20)
            ->create();`

Para que funcione el método `hasThreads(n)` hay que configurar la relación en el modelo de categorias.

`Category.php`

`public function threads()
    {
        return $this->hasMany(Thread::class);
    }`

Despúes se ejecuta el comando de migración `php artisan migrate:refresh --seed`

# Comando para borrar las estructuras, tablas, de la base de datos y volverlas a crear
### Además genera los datos falsos

`php artisan migrate:fresh --seed`
