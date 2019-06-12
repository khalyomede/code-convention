# Code convention

Set of guidelines I built from my developper experience. Gathered here to remind me how to keep my code scalable over time.

![GitHub tag (latest SemVer)](https://img.shields.io/github/tag/khalyomede/code-convention.svg) ![GitHub](https://img.shields.io/github/license/khalyomede/code-convention.svg)

## Summary

- [Function naming](#function-naming)
- [Variable naming](#variable-naming)

## Function naming

- [Function updating a boolean property](#function-updating-a-boolean-property)
- [Function returning the value of a boolean property](#function-returning-the-value-of-a-boolean-property)
- [Function returning an array](#function-returning-an-array)
- [Function checking if has element](#function-checking-if-has-element)

### Function updating a boolean property

- Use kebab case
- Prefixed by `enable` or `disable` keywords to update a boolean value

```javascript
class Response {
	static enableFetchingFromCache() {
		Response.fetchFromCache = true;
	}

	static disableFetchingFromCache() {
		Response.fetchFromCache = false;
	}
}
```

### Function returning the value of a boolean property

- Use kebab case
- Name is positive
- Suffixed by `enabled`

```javascript
class Response {
	static fetchingFromCacheEnabled() {
		return Response.fetchFromCache === true;
	}
}
```

### Function returning an array

- Use kebab case
- Prefixed by `get`
- Plural

```javascript
const Router {
    static _routes = [];

    static getRoutes() {
        return Router._routes;
    }
}
```

### Function checking if has element

- Use kebab case
- Name positive
- Prefixed by `has`

```javascript
class Router {
	static _routes = [];

	static hasRoute(route) {
		return Router._routes.includes(route);
	}
}
```

## Variable naming

- [Arrays](#arrays)
- [Booleans](#booleans)
- [Looping on an array](#looping-on-an-array)
- [Number of items in an array](#number-of-items-in-an-array)

### Array

- Use kebab case
- Plural

```javascript
const repositories = ["rs-json", "browser-worker", "JUR"];
```

- If not pluralizable, suffix it by `list`

```javascript
const fluxList = ["incoming", "outgoing"];
```

### Booleans

- Use kebab case
- Name positive

```javascript
class Response {
	static fetchFromCache = true;
}
```

### Looping on an array

- Use kebab case
- `for ... of` or `foreach ... as` variable loop should have singular form

```javascript
const buttons = document.querySelectorAll("button");

for (const button of buttons) {
	// ...
}
```

- regular `for` index name should be named `index`

```javascript
for (let index = 0; index < 5; index++) {
	// ...
}
```

### Number of items in an array

- Use kebab case
- Suffixed with `count`

```javascript
const languages = ["php", "c#", "nodejs"];
const languagesCount = languages.length;
```
