# Commerce Demo GraphQL

## TODO

* Add images to results


## Example

```
/graphql?query=query{
 searchAPISearch(
   index_id: "products", 
   range: {start: 0, end: 10},
   fulltext: {keys: "Print", fields: ["title"]}
   conditions: [
     {operator: "=", name: "special_name", value: ""}
   ]
   facets: [
     {operator: "=", field: "brand_name", limit: 0, min_count: 1, missing: false},
     {operator: "=", field: "category_name", limit: 0, min_count: 1, missing: false}
     {operator: "=", field: "special_name", limit: 0, min_count: 1, missing: false}
   ]
 ) {
   documents {
     ... on ProductsDoc {
       title,
       product_id
       brand_name
       category_name
       special_name
     }
   }
   facets {
     name
     values {
       count
       filter
     }
   }
 }
}
```

Returns

```json
{
  "data": {
    "searchAPISearch": {
      "documents": [
        {
          "title": "36\" x 24\" Fawkestrooper Print",
          "product_id": 11,
          "brand_name": "Unsplash",
          "category_name": [
            "Print Shop"
          ],
          "special_name": [
            "Bildstein Approved",
            "Featured"
          ]
        },
        {
          "title": "24\" x 36\" Flowers Print",
          "product_id": 12,
          "brand_name": "Unsplash",
          "category_name": [
            "Print Shop"
          ],
          "special_name": []
        },
        {
          "title": "24\" x 36\" Foggy Forest Print",
          "product_id": 13,
          "brand_name": "Unsplash",
          "category_name": [
            "Print Shop"
          ],
          "special_name": []
        },
        {
          "title": "24\" x 30\" Hiding Goat Print",
          "product_id": 14,
          "brand_name": "Unsplash",
          "category_name": [
            "Print Shop"
          ],
          "special_name": [
            "Bildstein Approved",
            "Clearance"
          ]
        },
        {
          "title": "24\" x 36\" Moon Over Mountains Print",
          "product_id": 16,
          "brand_name": "Unsplash",
          "category_name": [
            "Print Shop"
          ],
          "special_name": []
        },
        {
          "title": "24\" x 36\" Night City Print",
          "product_id": 17,
          "brand_name": "Unsplash",
          "category_name": [
            "Print Shop"
          ],
          "special_name": []
        },
        {
          "title": "24\" x 36\" Palms Print",
          "product_id": 18,
          "brand_name": "Unsplash",
          "category_name": [
            "Print Shop"
          ],
          "special_name": []
        },
        {
          "title": "36\" x 24\" Seagulls Print",
          "product_id": 19,
          "brand_name": "Unsplash",
          "category_name": [
            "Print Shop"
          ],
          "special_name": []
        },
        {
          "title": "24\" x 36\" Splatter Print",
          "product_id": 20,
          "brand_name": "Unsplash",
          "category_name": [
            "Print Shop"
          ],
          "special_name": [
            "Clearance"
          ]
        }
      ],
      "facets": [
        {
          "name": "brand_name",
          "values": [
            {
              "count": 9,
              "filter": "Unsplash"
            }
          ]
        },
        {
          "name": "category_name",
          "values": [
            {
              "count": 9,
              "filter": "Print"
            },
            {
              "count": 9,
              "filter": "Shop"
            }
          ]
        },
        {
          "name": "special_name",
          "values": [
            {
              "count": 2,
              "filter": "Approved"
            },
            {
              "count": 2,
              "filter": "Bildstein"
            },
            {
              "count": 2,
              "filter": "Clearance"
            },
            {
              "count": 1,
              "filter": "Featured"
            }
          ]
        }
      ]
    }
  }
}
```
