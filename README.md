# SimpleAutoCompleteJS
Simple auto-complete server-side 100% javascript

## How to use:

```Javascript

const fetchPokemons = async (arg) =>{
    url = "https://pokeapi.co/api/v2/type/grass"
    const arr = await fetch(url);

    const data = await arr.json();

    var pokes = [];
    data.pokemon.forEach(element => {
        pokes.push(element.pokemon.name);
    });
    return pokes;
}

new AutoComplete("input-find", "input-find-list", {
    src : fetchPokemons,
    onSelect : (element) =>{
        console.log(element);
    }
});
```
