### Counter para Modelos Relacionados

Se puede usar el método `withCount('relation_name')` sobre un modelo para contar el número de registros devueltos por la consulta.

**Ejemplo:**

Definimos la relación en el modelo:

`public function replies(){
        return $this->hasMany(Reply::class);
    }`

Usamos el método `withCount()` colocando el nombre de la relación

`$threads = Thread::latest()->withCount('replies')->get();`

Esto crea el campo `{relation}_count` sobre el resultado de la consulta. Nos regresa el número de registros devueltos.
