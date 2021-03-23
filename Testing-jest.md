```json
"scripts": {
    "start": "cross-env NODE_ENV=production node index.js",
    "start:dev": "cross-env NODE_ENV=development nodemon index.js",
    "test": "cross-env NODE_ENV=test jest --verbose --detectOpenHandles --testTimeout=30000",
    "test:watch": "npm run test -- --watch"
}
```
```si queremos indicarle un test en especifico podemos usar```

```json
"test": "cross-env NODE_ENV=test jest --verbose --detectOpenHandles --testTimeout=30000" tests/notes.test.js,
```
```o usar en la consola el comando de ademas de usar el script le indicamos el test especifico```
```el titulo no hace falta que sea exacto```

```shell
npm run test -- -t "titulo del it de la prueba"
```
