# ClickPesa API Development General Guideline - Version 1.0

1. Use kebab-case for URLs
> Example:
> ```js
> GET /system-orders
> ```



2. Use camelCase for Parameters
> Example:
> ```js
> PATCH /system-orders/{orderId}
> ```



3. Plural Name to Point to a resource / collection
> Example:
> ```js
> GET /system-orders
> ```



4. URL Starts With a Collection and Ends With an Identifier
> Example:
> ```js
> // Bad - points to a property instead of a resource
> GET /shops/:shopId/category/:categoryId/price 
>
>//Good
>GET /shops/:shopId/ or GET /category/:categoryId
> ```



5. Use proper HTTP methods to describe an operation
> Example:
> ```js
> //Bad
> POST /update-user/{userId} or GET /getusers
>
>//Good
>PUT /user/{userId}
>
>//HTTP Methods for CRUD Functions
> GET  // To retrieve a representation of a resource
> POST // To create new resources and sub-resources
> PUT  // To update existing resources
> PATCH // To update existing resources. It only updates the fields that were supplied, leaving the others alone
> DELETE // To delete existing resources
> ```
6. Don’t use database's table_name / collection as a resource name

7. Accept limit and offset Parameters GET operations
> Example:
> ```js
> GET /shops?offset=5&limit=5
> ```


8. Take fields Query Parameter
> Example: 
> ```js
> // Only return the name, address, and contact of the shops
> GET /shops?fields=id,name,address,contact
> ```


9. Use the Relation in the URL For Nested Resources
> Example: 
> ```js
> //  Get the list of all products from shop 2
> GET /shops/2/products
> 
> //  Get the details of product 31, which belongs to shop 2
> GET /shops/2/products/31
> ```

10. Use Verbs for Non CRUD operations
> Example: 
> ```js
> // resend the alert to a user
> POST /alerts/245743/resend
> ```
