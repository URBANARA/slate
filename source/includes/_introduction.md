# Introduction

Welcome to the Urbanara API documentation. This is the API used by the web interface, public.


## Conventions

> Do and don't do

```js
// Bad
{ 
  "detailTitle": "Example",
  "detailContent": "My content"
}

// Good
{ 
  "detail_title": "Example" ,
  "detail_content": "My content"
}

// Better
{ 
  "detail": {
    "title": "Example",
    "content": "My content"
  }
}
```

- URLs endpoints, parameters and object properties will use `snake_case` to avoid mistakes.
  - use `detail_title` over `detailTitle`
- properties should have a descritive name, as simple as possible, with nested types of data
  - Prefer `detail.title` over `detail_title` (never `detailTitle`)
- If some attribute will be used in a HTML property, use the same name convention
  - `img.src` for image urls, intead of `img.url`
  - `img.alt` for image ALT attribute, intead of `img.description`
- All the values that are NOT content to display to the user, should be a code, to be used in front end
  - `data.error` should be a code  like `404` instead of a error message
  - `availability.status` should be a code like `OnlineOnly` instead of "Product sold online only"

## Making Requests

> Example with channel in body OR headers


```js
fetch('/any-api-endpoint', {
  method: 'GET',
  body: JSON.stringify({channel: 'MOBILE_DE'}), 
  // or
  headers: new Headers({
    'Content-Type': 'application/json'
    'channel': 'MOBILE_DE'
  })
})
.then(res => res.json())
.catch(error => console.error('Error:', error))
.then(response => console.log('Success:', response));
```

You need to send the channel of the current web interface

- MOBILE_DE
- DESKTOP_DE
- MOBILE_UK
- DESKTOP_UK

## Response Format

- Responses will be returned in JSON format.
- Repeated `objects` will be nested inside a `Array` where the order received will be used to display on the client.


### Common Attributes

> Example of success request:

```json-doc
{
	"meta": {
		"error": null,
	},
	"data": {
		...
	}
}
```

> Example of error request:

```js
{
	"meta": {
		"error": 404,
	},
	"data": null
}
```


All the responses will have two root properties `meta` and `data`, so we can take actions based on the response type instead of take actions inside the components

The basic fields of `meta` property should exists even if there is no data, to avoid add logic in frontend to check id some propertie exists or no before acess

Attribute      | Format   | Description
-------------- | -------- | -----------
**meta**       | `Object` | Information about the request, like redirects, errors
**meta.error** | `Object` | The <code>error</code>  code should be based on the error list.
**data**       | `Object` | The data of the request, specifiv from each endpoint