## -pseudo Elementos (No son seleccionables)
Al igual que las pseudo-classes, los pseudo-elementos se añaden a los selectores, pero en cambio, no describen un estado especial sino que, permiten añadir estilos a una parte concreta del documento. Por ejemplo, el pseudoelemento ::first-line selecciona solo la primera línea del elemento especificado por el selector.

!!Recuerde que hereda las caracteriscas del padre pero requieren de ciertas propiedades para ser visibles
Ademas no son seleccionables como las etiquetas

selector::pseudo-elemento { propiedad: valor; }

## Los mas conocidos son AFTER/BEFORE
Como lo indican sus nombres son pseudo elementos que se colocan antes y despues de la etiqueta seleccionada,
por lo general son utilizados para agregar estilos especificos sin tener que recurrir a otra etiqueta, tambien en ciertas animaciones como las lineas inferiores en algunas palabras

<p>señor</p>
<style>
    p::after{
        content:"buen dia";  Esta propiedad es necesaria sino jamas se veran algun efecto
    }
</style>

OUTPUT: señorbuen dia ----> el content: es un valor preformateado significa que toma todo valor dentro de las comillas incluso los espacios
<p>que tal</p>
<style>
    p::before{
        content:"hola ";
        display:inline-block;
    }
</style>
OUTPUT: hola que tal ---> aqui agregue espacio luego del hola y lo toma igual

En el Caso de que no aparezca algun resultado esperado puede deberse que la etiqueta posee algun display,
tambien los display generales afectan a este pseudo-elemento, por lo tanto puede agregarle display: block u inline-block para lograr verlo antes u despues

## ::first-letter
El pseudo-elemento ::first-letter aplica estilos a la primera letra de la primera línea un elemento de bloque, sólo cuando no es precedido de otro contenido (como imágenes o tablas).

<p><p class='ejemplo'>H</p>ola</p>
<style>
    p::first-letter{
        text-transform:uppercase;
        color:red;
        font-size:25px;
    }
</style>
Output ---> Hola  h de color rojo y 25px de tamaño

## ::first-line
El Pseudoelemento ::first-line aplica estilos a la primera línea de un elemento de bloque. Nótese que la longitud de la primera línea depende de muchos factores, incluyendo el ancho del elemento, el ancho del documento y el tamaño de fuente del texto.
<div>
<p>hola como estas en este nuevo curso</p>
</div>
<style>
    div{
        width:20px;
        height:25px;
    }
    p::first-line{
        color:red;
    }
</style>

## ::placeholder
El pseudo-elemento CSS ::placeholder representa el texto provisional (en-US) en un elemento <input> o un elemento <textarea>.

<input type='text' placeholder='buenas' saludar="buen dia">
<style>
    input::placeholder{
        color:red;
        font-size:12px;
    }
</style>

## Tipos de content:"" en after y before

string : "hola como estas" --> añade el texto
attr(saludar) --> añade la url dentro del href, el atributo puede ser cualquiera incluso uno inventado
IMAGE url(./direccion_de_la_img.jpg)
GRADIENT linear-gradient(red,blue)
COUNTER counter(item)



