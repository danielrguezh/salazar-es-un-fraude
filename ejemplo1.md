# Ejercicio 15 tarea 3 (ficheros) AED
## 15) Lista de chistes (rotativos)
 * Enunciado: Muestra un chiste distinto en cada ejecución desde chistes.txt.
### Codigo del defraudador
```php
<?php
    $chistes = file("chistes.txt");
    $random = array_rand($chistes);
    echo $chistes[$random];
```

### Codigo de alguien con un minimo de decencia
```php
<?php
$content = explode("\n", file_get_contents("resources/ejercicio15/chistes.txt"));

function chisteRandom(): string {
    global $content;

    if (empty($content)) {
        return null;
    }

    $index = array_rand($content);
    $chiste = $content[$index];
    unset($content[$index]);
    return $chiste;
}
for ($i=0; $i=sizeof($content);$i++){
    echo chisteRandom() . "\n";
}
?>
```
