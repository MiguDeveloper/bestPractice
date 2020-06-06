
## Reglas generales de formato
- Espacios en blanco al final: eliminar los espacios en blanco al final ya que son innecesarios y pueden complicar las diferencias, recordemos que podemos eliminar estos espacios configurando nuestros IDEs luego de guardar el archivo

```javascript
// No se recomienda
const name = 'Miguel';__

// Recomendado
const name = 'Miguel';
```

- Identación: El uso de las sangrias debe ser coherente en todo el archivo. Ya sea que uses tabs o espacios

- TODO: resalte tareas por hacer con ```TODO``` y no use otros marcadores. Agregue el comentario luego de los dos puntos
```javascript
// TODO: revisar tipo de variable
```

## Reglas lenguaje Javascript

- Declaración de variables: las tres formas que conocemos son las siguientes, ```const```, ```let```, ```var```. comencemos declarando nuestras variables con ```const``` si está necesita ser reasignada mas adelante usemos ```let```, recordemos que ya no existe buenas razones para usar ```var```.

- Punto y coma: siempre usemosla. El punto y coma debe incluirse al final de las expresiones de función, pero no al final de las declaraciones  de función.
```javascript
// No recomendado
const foo = () => {
    return true // sin ;
}
// No recomendado
function foo() {
    return true;
}; // ; extra

// Recomendado
const foo = () => {
    return true;
};
// Recomendado
function foo() {
    return true;
}
```

## Ciclos: ```for```, ```for-in``` y ```foreach```

- Se prefiere ```forEach``` y ```for``` sobre ```for-in``` cuando vamos iterar sobre un array

```javascript
myArray = ['a', 1, 'etc'];
// No recomendado
for(const indexNum in myArray){
    console.log(myArray[indexNum])
}

const clubAlianza = {
    'jugadores': [
        {
            'name': 'Waldir',
            'nro': 10
        },
        {
            'name': 'Jeferson F.',
            'nro': 10
        }
    ]
};

// No recomendado
for(const i in clubAlianza){
    console.log(clubAlianza.jugadores[i].name);
    console.log(clubAlianza.jugadores[i].nro);
}

// Recomendado
myArray.forEach(item => console.log(item));

// Recomendado
clubAlianza.jugadores.forEach(item => {
    console.log(item.name + ' ' + item.nro)
})

// Recomendado
const jugador = {'name': 'Paolo', 'apellido': 'Guerrero'};
for(const key in jugador){
    if(jugador.hasOwnProperty(key)){
        console.log(jugador[key]);
    }
}
```

## Array y Objetos literales

- Utilice array y objetos literales y no constructores.

```javascript
// No recomendado
const myArray = new Array(1,2,3);
const myObject = new Object();
myObject.a = 0;

// Recomendado
const myArray = [1, 2, 3];
const myObject = {a: 1, b: 2, c: 3};
```

## Tips and Tricks

- Retorna siempre ```false```: null, undefined, '', 0
- Retorna siempre ```true```: '0', [], {}
- Usar siempre que se pueda el condicional ternario
```javascript
// No recomendado
if(val){
    return foo();
} else {
    return bar();
}

// Recomendado
return val ? foo() : bar();
```

- && y || 
```javascript
// No recomendado
const foo = name => {
    const theName;
    if(name){
        theName = name;
    }else{
        theName = 'Miguel';
    }
}

// Recomendado
const foo = (name) => {
    const theName = name || 'Miguel';
}

// No recomendado
if(node){
    if(node.kids){
        console.log(node.kids);
    }
}

// Recomendado
if(node && node.kids){
    console.log(node.kids);
}
```