<h1> sistema de registro</h1>

-estado de proyecto; en construccion.

para ejecutar el sistema, debes poner:

```npm install react``
// Array para almacenar los nombres de amigos
let amigos = [];

// Función para agregar un amigo 
function agregarAmigo() {
    // Capturar el valor del campo de entrada
    const inputAmigo = document.getElementById("amigo"); // Obtiene el elemento del DOM con id "amigo" (un campo de entrada).
    const nombreAmigo = inputAmigo.value.trim(); // Obtiene el texto ingresado en el campo, eliminando espacios al inicio y al final.

    // Validar que el campo no esté vacío 
    if (nombreAmigo === "") { // Verifica si el campo de entrada está vacío.
        alert("Por favor, inserte un nombre."); // Muestra una alerta si no hay texto ingresado. 
        return; // Detiene la ejecución de la función 
    }

    // Validar que el nombre no esté duplicado
    if (amigos.includes(nombreAmigo)) { // Comprueba si el nombre ya existe en el array "amigos". 
        alert(`El nombre "${nombreAmigo}" ya está en la lista.`); // Usa comillas invertidas para interpolar el nombre.
        return; // Detiene la ejecución de la función.
    }

    // Agregar el nombre al array de amigos 
    amigos.push(nombreAmigo); // Agregar el nombre al array "amigos".

    // Limpiar el campo de entrada
    inputAmigo.value = ""; // Borra el texto del campo de entrada para que quede vacío después de agregar el nombre.

    // Actualizar la lista en el HTML
    actualizarLista(); // Llama a la función "actualizarLista" para reflejar los cambios en la interfaz de usuario
}

// Función para actualizar la lista de amigos en la interfaz
function actualizarLista() {
    const listaAmigos = document.getElementById("listaAmigos");

    // Limpiar el contenido actual de la lista 
    listaAmigos.innerHTML = ""; // Borra cualquier contenido previo dentro del contenedor de la lista 

    // Recorrer el array con un ciclo for
    for (let i = 0; i < amigos.length; i++) { // Itera sobre cada elemento en el array "amigos".
        const li = document.createElement("li"); // Crea un nuevo elemento <li> (elemento de lista).
        li.textContent = amigos[i]; // Asigna el texto del elemento <li> al nombre del amigo actual en el array.
        listaAmigos.appendChild(li); // Agrega el elemento <li> al contenedor de la lista en el DOM
    }
}

// Función para seleccionar un amigo aleatorio
function sortearAmigo() {
    // Validar que haya amigos disponibles 
    if (amigos.length === 0) { // Comprueba si el array "amigos" está vacío.
        alert("No hay amigos disponibles para sortear. Agrega al menos uno."); // Muestra una alerta si no hay amigos en la lista
        return; // Detiene la ejecución de la función.         
    }

    // Genera un índice aleatorio 
    const indiceAleatorio = Math.floor(Math.random() * amigos.length); // Genera un número aleatorio entre 0 y la longitud del array menos uno
    
    // Obtener el nombre sorteado
    const amigoSorteado = amigos[indiceAleatorio]; // Usa el índice aleatorio para obtener un nombre del array.

    // Mostrar el resultado en el HTML
    const resultado = document.getElementById("resultado"); // Obtiene el elemento de DOM con id "resultado" (donde se muestra el nombre).
    resultado.textContent ='Amigo sorteado: misael'; // Actualiza el contenido del elemento con el nombre sorteado.
}



