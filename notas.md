# Notas del Curso Expresiones Regulares

Las expresiones regulares son las formas con las que podemos buscar gran cantidades de datos puestos en una forma.

Se puede buscar de diferentes formas, casi en todas las formas que se puede escribir un texto.

## Herammientas de las Expresiones Regurales:

Las herramientas que se pueden usar en las expresiones regualres son:

- Caracter (.):

Obtiene cualquier caracter y ya. Es bueno pero tambien es bueno no abusar de él, ya que siempre va a encontrar algo y si vamos a 
borrar algo, pues puede salir todo muy mal en muy poco tiempo.

- Clases

Son busquedas de caracteres especificos

Pueden ser predefinidas, en general los tipos de los caracteres:
	- digitos: \d
	- palabras: \w
	- espacios: \s

O pueden ser definidas por nosotros, para hacerlas es:
[] // Clase
[1] // Donde va a iniciar, generalmente de un tipo de dato
[1-9] // Que busque hasta x rango, del mismo tipo de dato
[1-9a-b] // Se agrega otro rango de otro tipo de dato
[1-9a-b_] // Se puede agregar otros caracteres sin necesidad de ponerlos en un rango

- Delimitadores:

Son formas de buscar unos tipos de datos, teniendo 3 tipos

	- * Greedy, 0 o más caracteres pedidos: [rango]P* rangoPerro
	- + Uno o mas, 1 o más caracteres pedidos: [rango]P+ rangoPerro
	- ? cero o uno, 0 o un caracter pedido: [rango]P? rangoP

- Contadores:

Son los que nos va permitir repetir un caracter varias veces, siendo de esta forma:

char{num_repetir} 

En algunos lenguajes de programación se nos pide poner dos número dentro de los corchetes, siendo

char{num_char_min, num_char_max} // Si queremos dejarlo cómo el de arriba, solo ponemos dos veces el mismo número

- ? a profundidad:

Se pude usar para delimitar las busquedas, haciendo que no busque y encuentre lineas enteras, si no que encuentre de agrupaciones más 
pequeñas.

.+?, // Nos busca todos los caracteres que tengan uno o más seguidos hasta una coma y ahí se rompe o termina la busqueda, delimitandose

- ^ Negaciones:

Se pueden negar las clases predeterminadas, simplemente poniendo las letras de cada tipo de caracter en mayusculas

	- \D
	- \W
	- \S

O se puede usar en clases con ^, o en la misma expresión regular. Los rangos negados van a ser igual a su contraparte.

- Lineas Enteras ^ ... $

Se pueden buscar expresiones regulares dentro de toda una linea usando los operadores:

^ expresion $

Evitando que se repita un match varias veces en una linea.

- Agrupación de Expresiones Regulares

Cómo en la aritmetica, es un poco dificil seguir de largo con toda la operación, para eso se puede hacer el uso de 
parenstesis, pero esto nos puede dar un super poder al reemplazar datos. Llamado grupos.

## Find and Reemplace

Al hacer una busqueda, obviamente vamos a poder cambiar el contenido encontrado, un super truco que podemos usar es dividir la expresión 
en parentesis, así para poder tener diferentes grupos. Para usar cada grupo vamos a nombrarlos con $ y el número de este:

(RegExp)(RegExp)

$1 $2
