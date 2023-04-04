A continuación se detallarán los problemas encontrados junto a sus respectivas soluciones del software proporcionado:


## 1 El método addEventListener fue escrito de forma errónea.

Al ejecutar el programa se presentaba el siguiente mensaje en consola: guessSubmit.addeventListener is not a function at load
Esto se daba debido a que el método addEventListener llamado para la inicialización del programa fue escrito incorrectamente como "addeventListener".
La correción fue colocar en mayúscula la Inicial de la palabra event.

## 2 El elemento lowOrHi se selecciona incorrectamente.

En la declaración de variables no se estaba llamando al elemento CSS que mostraba si el número ingresado por el usuario era mayor o menor.
Se corrigió llamando correctamente al elemento en la declaración de variables, cambiando:

const lowOrHi = document.querySelector('lowOrHi');
por:
const lowOrHi = document.querySelector('.lowOrHi');

## 3 La cantidad de intentos era incorrecta.

Se habían establecido 5 intentos para el usuario cuando el requerimiento es de 10 intentos.

La variable donde se establecían los intentos fue modificada para aceptar 10 intentos.

## 4 La variable que obtiene el número aleatorio se le daba un valor erróneo

El valor que se le dió 2 veces a la variable randomNumber fue hecho de forma incorrecta, ya que el rango de números era de 0 a 9 y se estaban usando números decimales
Se modificaron ambas líneas de código por el siguiente:
randomNumber = Math.floor(Math.random() * 100) + 1;
Así ahora el rango de números es de 1 a 100 tomando en cuenta solo los enteros.

## 5 Los mensajes al ganar, perder u obtener número incorrecto muestran de forma incorrecta.

El formato de fondo para el mensaje de número incorrecto y al ganar están al contrario, mostrando negro al ganar y verde al tener número incorrecto.
El mensaje de victoria y derrota están al contrario, mostrando mensaje de victoria al acabarse todos los intentos y mensaje de derrota al acertar el número.
Se corrigieron los formatos en base a los requerimientos proporcionados.

## 6 La condición de victoria no se cumple

Al ingresar el número necesario para obtener el mensaje de victoria se mostraba el mensaje de "número incorrecto", esto debido a que dentro del código se usaba un operador de igualdad estricta y no se convertía a tipo Integer la variable que contenía el dato proporcionado por el usuario. 
Dentro de la condición "if" donde se realizaba dicha igualdad se procedió a realizar la conversión dejandola de la siguiente forma:
 if(parseInt(userGuess) === randomNumber)

 ## 7 No existe validación para números enteros

 En ninguna parte del código se creó un método de validación para permitir solamente números enteros por lo que se creó dicha validación de la siguiente forma:
  
  let userGuess = Number(guessField.value);
 

 if (!Number.isInteger(userGuess)) {
    alert("Por favor, ingrese un número entero.");
    return;
  }

Se convirtió el dato de entrada "guessField" a Number para luego entrar en una condicionante donde si el dato es diferente a un número entero se mostrara una alerta en el navegador y finalizara el recorrido de la función en esa parte para evitar que ese intento sea tomado en cuenta. Si el dato agregado por el usuario es un número entero se ejecuta el demás código de la función.

## 8 La variable ATTEMPS fue escrita incorrectamente

Este problema no afectaba la funcionalidad del programa, sin embargo a futuro puede causar problemas de referencia debido a que la palabra correcta es ATTEMPTS, si un programador nuevo revisa el código superficialmente y no detecta el nombre de la variable, al querer referenciarla notará que dicha variable no existe hasta que lea el código.

## 9 El mensaje de derrota fue escrito incorrectamente

Este problema no afectaba la funcionalidad del programa, solamente era error de escritura ya que el mensaje original era "Perdistes", se corrigió por la forma correcta siendo "Pérdiste"

## 10 El mensaje de la etiqueta y el botón daban confusión al leerlos

Este problema no afectaba la funcionalidad del programa, sino que daba confusión al leerlos ya que el texto original de la etiqueta era : "Ingresa el número a adivinar"
Dando a entender que el usuario debía de ingresar un número que luego él quiera adivinar lo cuál es incorrecto. Se cambió el texto a : "Ingresa el número"
La razón es porque el título es "Juego Adivina tu número" y luego están las instrucciones que especifican lo que se debe de hacer.
Luego se cambió el texto del botón ya que el texto original era: "Ingresar el número aleatorio" que puede generar confusión al usuario. 
Se cambió por: "Ingresa el número" que da una idea más generalizada de lo que el botón hace.