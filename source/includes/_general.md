# Common Formats

Some types of information will be repeated across endpoints, with the same format, listed below:

Common formats describe the content of a object, not the name of this object property in the parent object.

## Images Object ##

> Example of image object:

```json-doc
{
  "id": 678,
  "src": "/folder/file.png",
  "title": "Name of image",
  "alt": "Description of image",
}
```

All the images in the API shuld be described by the format:

| Attribute    | Type    | Description     |
| ------------ | ------- | --------------- |
| `id`         | integer | Image ID        |
| `src`        | string  | Image URL.      |
| `title`      | string  | Image title     |
| `alt`        | string  | Image alt text  |

## Price Object ##

> Example of price object full:

```json-doc
{
  "current": 55.87,
  "original": 60,
  "currency": "EUR"
}
```

> Example of price object without promotional price:

```json-doc
{
  "current": 55.87,
  "original": null,
  "currency": "EUR"
}
```

The prices values should be delivered in the final format to avoid price transformation in client side

| Attribute    | Type    | Description                            |
| ------------ | ------- | -------------------------------------- |
| `current`    | float   | Price value, final                     |
| `original`   | float   | Price value, final                     |
| `currency`   | String  | 3 letters code in [ISO_4217][ISO_4217] |


[ISO_4217]: https://en.wikipedia.org/wiki/ISO_4217#Active_codes