# Products Objects

The products API allows you to view a individual, or a batch, of products.

## Product Object FULL

The product Object Full have all the data of the product used in the client, with the nested `Product Objects` in simple format

> Example of product object FULL:

```json-doc
{
  "id": 987,
  "sku": "5678-DFGHJ-345",
  "urls": {
    "permalink": "/permalink-url-product",
    "cannonical": "/cannonical-url-product"
  },
  "slug": "nice-red-pillow",
  "status": "",
  "title": "Red Pillow",
  "short_description": "Red organic cotton",
  "has_size_guide": true,
  "price": {
    "current": 55.87,
    "original": 60,
    "currency": "EUR"
  },
  "availability": {
    "status" '"InStock",
    "quantity": 20
  },
  "wait_and_save": {
    "status": true,
    "discount_value": 5,
    "discount_type": "%"
  },
  "badge": {
    "id": 678,
    "src": "/folder/file.png",
    "title": "Name of image",
    "alt": "Description of image",
  },
  "images": [
    {
      "id": 678,
      "src": "/folder/file.png",
      "title": "Name of image",
      "alt": "Description of image",
    }
    {Image Object},
    {Image Object},
  ],
  "related_groups": [
    {
      "title": "Duvet Cover",
      "products": [
        {Product Object Simple},
        {Product Object Simple},
        {Product Object Simple},
      ]
    },
  ]
  "colors": [
    {Product Object Simple},
    {Product Object Simple}
  ],
  "details": [
    {
      "title": "Overview",
      "content": "<h1>Overview</h1><p>Clean and simple...</p>",
      "badge": {Image Object},
      "image": {Image Object}
    },
    {
      "title": "Details & Care",
      "content": "<ul><li><b>Exterior</b>: 100 cotton</li><li>...",
      "badge": {Image Object},
      "image": {Image Object}
    },
    {Product Details Simple},
  ]
}
```


|            Attribute            |   Type  | Description                                                                                                         |
| ------------------------------- | ------- | ------------------------------------------------------------------------------------------------------------------- |
| `id`                            | integer | Product ID (post ID)                                                                                                |
| `sku`                           | string  | SKU refers to a Stock-keeping unit, a unique identifier for each distinct product and service that can be purchased |
| `url.permalink`                 | string  | Product URL                                                                                                         |
| `url.cannonical`                | string  | Product Cannonical URL                                                                                              |
| `slug`                          | string  | Product slug                                                                                                        |
| `status`                        | string  | Product status (post status). @todo list possible status                                                            |
| `title`                         | string  | Product name                                                                                                        |
| `short_description`             | string  | Product short description                                                                                           |
| `has_size_guide`                | Boolean | If the product has styleguide                                                                                       |
| `price`                         | Object  | Price Object. See [Price Properties](#price-object)                                                                 |
| `availability`                  | Object  | Availability Object. See [Product Availability Properties](#availability-object)                                    |
| `wait_and_save`                 | Object  | Wait and Save Object. See [Wait and Save Object](#wait-and-save-object)                                             |
| `badge`                         | Object  | Image. See [Images Properties](#images-object)                                                                      |
| `images`                        | Array   | List of products images. See [Images Properties](#images-object)                                                    |
| `related_groups`                | Array   | Array of Objects of type Product Simple with title                                                                  |
| `colors`                        | Array   | @todo colors                                                                                                        |
| `details`                       | Array   | List of products images. See [Images Properties](#product-details-object)                                           |


## Product Object SIMPLE ##

The Product Object Simple have only the basicof the product used in the client, without the nested `Product Objects` in simple format

> Example of product object SIMPLE:

```json-doc
{
  "id": 987,
  "sku": "5678-DFGHJ-345",
  "urls": {
    "permalink": "/permalink-url-product",
    "cannonical": "/cannonical-url-product"
  },
  "slug": "nice-red-pillow",
  "status": "",
  "title": "Red Pillow",
  "short_description": "Red organic cotton",
  "price": {
    "current": 55.87,
    "original": 60,
    "currency": "EUR"
  }
  "availability": {Product Availability Object},,
  "wait_and_save": {Product Wait and Save Object},,,
  "badge": {
    "id": 678,
    "src": "/folder/file.png",
    "title": "Name of image",
    "alt": "Description of image",
  },
  "images": [
    {
      "id": 678,
      "src": "/folder/file.png",
      "title": "Name of image",
      "alt": "Description of image",
    }
    {Image Object},
    {Image Object},
  ]
}
```

|            Attribute            |   Type  | Description                                                                                                         |
| ------------------------------- | ------- | ------------------------------------------------------------------------------------------------------------------- |
| `id`                            | integer | Product ID (post ID)                                                                                                |
| `sku`                           | string  | SKU refers to a Stock-keeping unit, a unique identifier for each distinct product and service that can be purchased |
| `url.permalink`                 | string  | Product URL                                                                                                         |
| `url.cannonical`                | string  | Product Cannonical URL                                                                                              |
| `slug`                          | string  | Product slug                                                                                                        |
| `status`                        | string  | Product status (post status). @todo list possible status                                                            |
| `title`                         | string  | Product name                                                                                                        |
| `short_description`             | string  | Product short description                                                                                           |
| `price`                         | Object  | Price Object. See [Price Properties](#price-object)                                                                 |
| `availability`                  | Object  | Availability Object. See [Product Availability Properties](#availability-object)                                    |
| `wait_and_save`                 | Object  | Wait and Save Object. See [Wait and Save Object](#wait-and-save-object)                                             |
| `badge`                         | Object  | Image. See [Images Properties](#images-object)                                                                      |
| `images`                        | Array   | List of products images. See [Images Properties](#images-object)                                                    |


## Product Details Object ##

> Example of product details object:

```json-doc
{
  "title": "Name of image",
  "content": "<h1>title</h1><p>Content</p>",
  "badge": {},
  "image": {},
}
```

|  Attribute   |   Type   | Description.                                              |
| ------------ | -------- | --------------------------------------------------------- |
| `title`      | string  | Text used for the tab                                      |
| `content`    | string  | Text or HTML                                               |
| `badge`      | Object  | Images object. See [Images Properties](#images-properties) |
| `image`      | Object  | Images object. See [Images Properties](#images-properties) |



## Product Availability Object ##

> Example of product availability object:

```json-doc
{
  "status" '"InStock",
  "quantity": 20
}
```

The availability of this item. Possible values.
The values should be the same as listed in [schema.org/ItemAvailability](http://schema.org/ItemAvailability)

<aside class="notice">
  <p>
    The <code>quantity</code> will return maximum threshold limit of the quantity, not the real total quantity-
  </p>
  <p>
    Examples: 
  </p>
  <p>
    If the product has 190 items avaliable, but the limit is 20, will return 20.
  </p>
  <p>
    If the product has 8 items avaliable, and the limit is 20, will return 8 with the <code>status</code> as <code>LimitedAvailability</code>.
  </p>
</aside>

| Value.               | Description                                                                                          |
| -------------------- | ---------------------------------------------------------------------------------------------------- |
| Discontinued         | Indicates that the item has been discontinued.                                                       |
| InStock              | Indicates that the item is in stock.                                                                 |
| InStoreOnly          | Indicates that the item is available only at physical locations.                                     |
| LimitedAvailability  | Indicates that the item has limited availability.                                                    |
| OnlineOnly           | Indicates that the item is available only online.                                                    |
| OutOfStock           | Indicates that the item is out of stock.                                                             |
| PreOrder             | Indicates that the item is available for pre-order, but will be delivered when generally available.  |
| PreSale              | Indicates that the item is available for ordering and delivery before general availability.          |
| SoldOut              | Indicates that the item has sold out.                                                                |


### Product Wait and Save Object ###

> Example of Wait and Save Object:

```json-doc
{
  "status": true,
  "discount_value": 5,
  "discount_type": "%"
}
```

|  Attribute.      | Type    | Description.                                                |
| ---------------- | ------- | ----------------------------------------------------------- |
| `status`         | Boolean | Text used for the tab                                       |
| `discount_value` | Float   | value of discount                                           |
| `discount_type`  | String  | Text with the type of discount (`percentual` or `absolute`) |



# Product Endpoints

## Retrieve a product

This API helps you to create a new product.

### HTTP Request ###

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-post">GET</i>
    <h6>/api/product-by-slug/{product-slug}</h6>
  </div>
</div>

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-post">GET</i>
    <h6>/api/product-by-id/{product-id}</h6>
  </div>
</div>

## Retrieve multiple products

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-post">GET</i>
    <h6>/api/products-by-id/{product-id-1},{product-id-2},{product-id-3},...</h6>
  </div>
</div>