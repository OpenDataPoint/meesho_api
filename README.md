# Meesho API Documentation 🚀🌟
Welcome to the Meesho API documentation! This guide provides details on how to interact with the Meesho API to perform health checks, fetch products by category, search products, and retrieve product details. this API offers functionalities to check health, fetch products by category, search products, and retrieve product details. this API is secure, reliable, and easy to use. 🚀 Let's dive in! 🌟

## Table of Contents
- Overview 📦
- Why Our API? 🌟
- Why Use Meesho API? 🛍️
- Who Should Use the API? 👥
- Getting Started 🔧
- Endpoints 🛠️
  - Health Check 🩺
  - Products by Category 🛍️
  - Product Search 🔍
  - Product Details 📦
- Error Handling ⚠️
- Contributing 🤝
- Important Notes 📋
- Support 📞
  
## Overview 📦
The Meesho API allows developers to interact with Meesho's product catalog programmatically. Key features include:
- Checking API health status 
- Fetching products by category ID 
- Searching products by query string 
- Retrieving detailed product information by product ID

## Why Our API? 🌟
The Meesho API stands out for its simplicity, reliability, and developer-friendly design. Whether you're building an e-commerce platform, a price comparison tool, or a product discovery app, our API provides the tools you need to succeed. With clear documentation, we make integration a breeze.

## Why Use Meesho API? 🛍️
- **Access a Vast Product Catalog**: Retrieve products by category, search with keywords, or dive into detailed product information.
- **Flexible Responses**: Choose between processed or raw responses to suit your needs.
- **Developer-Friendly**: Clear endpoints, pagination support, and comprehensive error handling make development smooth.
- **Real-Time Interaction**: Stay updated with the latest product data from Meesho’s platform.

## Who Should Use the API? 👥
The Meesho API is perfect for:
- **E-commerce Developers**: Integrate Meesho’s product catalog into your online store or marketplace.
- **Price Comparison Platforms**: Fetch product details to compare prices and features.
- **Content Creators**: Build apps or websites showcasing trending products.
- **Data Analysts**: Access product data for market research or trend analysis.
- **Startups and Businesses**: Enhance your platform with Meesho’s extensive product offerings.

## Getting Started 🔧
To start using the Meesho API:
- **Review Documentation**: Explore the endpoints below to understand available functionalities.
- **Test the API**: Use tools like `curl` or Postman to make your first request.
- **Integrate**: Add the API to your application for seamless product data access.

## Endpoints 🛠️

### 1. Health Check 🩺
Check the API's health status to ensure it's up and running.
- **Endpoint:** `GET /health`
- **Summary**: Checks the API's health status.
- **Description**: Verify if the API is operational.
- **Operation ID**: `health_check_health_get`
#### Parameters
None required. Just send the request! 
#### Responses
200: Successful response indicating the API is healthy.
```
'json'
{}
```
#### Example Request:
```
'bash'
curl -u https://meesho-api.p.rapidapi.com/health
```
#### Example Response:
```
'json'
{
  status: healthy
}
```
### 2. Products by Category 🛍️
Retrieve a list of products filtered by a specific category.
- **Endpoint:** `GET /products-by-category`
- **Summary**: Fetches products by category ID.
- **Description**: Retrieve products for a specific category. Supports pagination and raw response options.
- **Operation ID**: `products_by_category_products_by_category_get`
#### Parameters
| Name     | Type    | Required | Description                  | Default |
|----------|---------|----------|------------------------------|---------|
| page_id  | String  | Yes      | The ID of the category page  | -       |
| page     | Integer | No       | Page number (minimum: 1)     | 1       |

#### Responses
- 200: Successful Response
  - Content: JSON object containing products
  - Example:
    ```
    'json'
      {}
    ```
- 400: Bad Request.
  - Content: Error details
- 404: Not Found.
  - Content: Error details
- 500: Internal Server Error.
  - Content: Error details
- 422: Validation Error.
  - Content: Detailed validation error

#### Example Request:
```
'bash'
curl -u https://meesho-api.p.rapidapi.com/products-by-category?page_id=cat123&page=1
```
#### Example Response:
```
'json'
{
  "success": true,
  "productsInPage": 20,
  "products":[]
}
```
### 3. Product Search 🔍
Search for products using a query string.
- **Endpoint:** `GET /product-search`
- **Summary**: Searches products by query string.
- **Description**: Search products by providing a query string. Supports pagination.
- **Operation ID**: `product_search_product_search_get`
#### Parameters
| Name  | Type    | Required | Description                  | Default |
|-------|---------|----------|------------------------------|---------|
| query | String  | Yes      | The search query string      | -       |
| page  | Integer | No       | Page number (minimum: 1)     | 1       |

#### Responses
- 200: Successful Response
  - Content: JSON object containing products
  - Example:
    ```
    'json'
      {}
    ```
- 400: Bad Request.
  - Content: Error details
- 404: Not Found.
  - Content: Error details
- 500: Internal Server Error.
  - Content: Error details
- 422: Validation Error.
  - Content: Detailed validation error

#### Example Request:
```
'bash'
curl -u https://meesho-api.p.rapidapi.com/product-search?query=shoes&page=1
```
#### Example Response:
```
'json'
{
  "success": true,
  "productsInPage": 20,
  "products":[]
}
```
### 4. Product Details 📦
Fetch detailed information about a specific product.
- **Endpoint:** `GET /product-details`
- **Summary**: Fetches product details by product ID.
- **Description**: Retrieve details for a product by providing its ID.
- **Operation ID**: `product_details_product_details_get`
#### Parameters
| Name       | Type   | Required | Description            |
|------------|--------|----------|------------------------|
| product_id | String | Yes      | The ID of the product  |

#### Responses
- 200: Successful Response
  - Content: JSON object containing product details.
  - Example:
    ```
    'json'
      {}
    ```
- 400: Bad Request.
  - Content: Error details
- 404: Not Found.
  - Content: Error details
- 500: Internal Server Error.
  - Content: Error details
- 422: Validation Error.
  - Content: Detailed validation error

#### Example Request:
```
'bash'
curl -u https://meesho-api.p.rapidapi.com/product-details?product_id=prod123
```
#### Example Response:
```
'json'
{
  "success": true,
  "product":{}
}
```
## Error Handling ⚠️
The API uses standard HTTP status codes and provides detailed error responses when something goes wrong.
### Common Errors
- 400 Bad Request:
  ```
  'json'
  {
    "success": false,
    "error": "ERROR_CODE",
    "details": "Error description message"
  }
  ```
- 404 Not Found:
  ```
  'json'
  {
    "success": false,
    "error": "ERROR_CODE",
    "details": "Error description message"
  }
  ```
- 500 Internal Server Error:
  ```
  'json'
  {
    "success": false,
    "error": "ERROR_CODE",
    "details": "Error description message"
  }
  ```
- 422 Validation Error:
  ```
  'json'
  {
    "detail": [
      {
        "loc": ["query", "param_name"],
        "msg": "Error message",
        "type": "error_type"
      }
    ]
  }
  ```
## Contributing 🤝
We welcome feedback and contributions! To suggest improvements:
1. Open an issue on our repository (link TBD).
2. Submit a pull request with your changes.
3. Follow our code of conduct (TBD).

## Important Notes 📝
- All endpoints expect query parameters as specified.
- Ensure required parameters (like page_id, query, or product_id) are included to avoid 422 validation errors.
- Responses may vary based on the data available; the examples above assume empty JSON for simplicity.

## Support 📞
For help with the Meesho API:
- Documentation: Refer to this README or the OpenAPI schema (openapi.json).
- Contact: Reach out to the Meesho API team (contact details TBD).
- Community: Join our developer community (link TBD).

#### The Meesho API empowers developers to interact with product data effortlessly. With endpoints for health checks 🩺, fetching products by category 🛍️, searching products 🔍, and retrieving product details, it provides a robust interface for building applications. Use query parameters to customize requests and handle responses in JSON format. Dive in, explore, and create something amazing! 🚀

### [Check Meesho API](#)
