# Real-time Meesho API 🛒🚀
The Meesho API provides access to Meesho's product catalog, search functionality, and detailed product information. This API enables developers to integrate Meesho's extensive marketplace data into their applications. 📱💻

## 💪 Why Use Realtime-Meesho API? 🌟

- Get instant updates on product prices, inventory, and availability
- Fast response times with 99.9% uptime
- Load balanced servers for handling high-volume requests
- Detailed product specifications
- Category-based product discovery
- Well-documented endpoints
- High-quality image URLs and product variations

## 👥 Who Should Use the API?

- Retail websites integrating Meesho products
- Web application creators
- Market research firms
- Price comparison platforms
- Trend analysis services
- Dropshipping businesses
- Social commerce platforms
- Price tracking services
- Investment analysis platforms
  
## Endpoints 🔗

1. Get Products by Category 📂
Retrieve products for a specific category from Meesho.
<pre><code>GET /products-by-category</code></pre>

### parameters
|       Name         |Type                          |Description|
|----------------|-------------------------------|-----------------------------|
|    page_id      |      string                   |The category ID to fetch product by category
|    page         |      integer                  |Page number for pagination


3. Product Search 🔎
Search for products using keywords.
<pre><code>GET /product-search</code></pre>

### parameters
|       Name         |Type                          |Description|
|----------------|-------------------------------|-----------------------------|
|    query      |      string                   |Search query term to fetch product by query
|    page         |      integer                  |Page number for pagination


4. Product Details 📦
Get detailed information about a specific product.
<pre><code>GET /product-details</code></pre>

### parameters
|       Name         |Type                          |Description|
|----------------|-------------------------------|-----------------------------|
|    product_id      |      string                   |Unique product identifier to fetch product details


## Authentication 🔑
Authentication is handled through RapidAPI. Include your RapidAPI key in the request headers:

- x-rapidapi-host: real-time-meesho-api.p.rapidapi.com
- x-rapidapi-key: your_rapid_api_key

## Features 🌟

- Real-time product data access
- Pagination support
- Category-based browsing
- Product search functionality
- Detailed product information
- Optional raw response format
- Error handling and logging

## Error Responses ⚠️

|   Status Code      |      Error Code                       |Description|
|--------------------|-------------------------------|-----------------------------|
|    400             |      INVALID_ID              |  Invalid Product ID/Invalid Category ID     
|    502             |      RELAY_SERVICE_ERROR      |  Temporary connection issue     
|    503             |      CONNECTION_ERROR         |  Unable to connect to Ahrefs   
|    500             |      INTERNAL_SERVER_ERROR    |  Unexpected server error
|    500             |      UNKNOWN_ERROR            |  Unhandled error condition

## Error Response Format

<pre><code>{
    "error": "ERROR_CODE",
    "details": "Error description message"
}
</code></pre>

## Notes 📝

All endpoints return beautified responses Proper error handling is implemented for all routes
Logging is enabled for debugging purposes

### This API provides comprehensive access to Meesho's marketplace data, perfect for building e-commerce applications, price comparison tools, or market analysis systems! 🚀🛍️
