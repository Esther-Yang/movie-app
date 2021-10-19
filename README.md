# Movie App

A React App which can add movie and fetch movie from database.

# Feature

- A form to add movie with its title, opening text and release date.
- A "Fetch Movie" button to fetch movie from database.
- Displays the list of movies.
- Use Realtime Database from Firebase.

# Procedure

## Sending a `GET` Request

- With fetch api which return a `promise` object.

```
function fetchMovieHandler(){
    fetch("url")
        .then(()=>{

        })
        .then(()=>{

        });
}
```

- Addtional: use `async/await`

```
async function fetchMovieHandler(){
    const response = await fetch('url');
    const data = await response.json;
    //...
}
```

## Handling Http Errors

- Using `then()`

```
catch()
```

- Using `async/await`

```
try{
    if(!response.ok){
        throw new Error("Something went wrong");
    }
}catch(error){
    setError(error.message);
}
```

## Use `useEffect()` and `useCallback()`

- To automatically run the function when the component is loaded.

```
useEffect(()=>{
    fetchMovieHandler();
},[fetchMovieHandler]);
```

- To prevent function recreation everytime.

```
const fetchMovieHandler = useCallback(async()=>{

},[]);
```

## Sending a `POST` Request

```
async function addMovieHandler(movie){

    const response = await fetch("<Firebase URL>/<node name>.json, {
        method: "POST", //default is "GET"
        body: JSON.stringify(movie), //transform JSON to JS object
        headers : {"Content-Type":"application/json"},
    }
);

const data = await response.json;

}
```
