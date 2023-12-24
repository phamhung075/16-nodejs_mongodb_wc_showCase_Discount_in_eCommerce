# Node.js MongoDB Showcase Projects
This is a personal project series based on the lessons by @anonystick ([https://github.com/anonystick](https://github.com/anonystick)).
## 1. [Authentication and API Key Management (HS256)](https://github.com/phamhung075/2-nodejs_mongodb_wc_showCase_Dynamic_for_ApiKey_and_Permissions_HS256/tree/master)

## 2. [ErrorHandler ApiResponse](https://github.com/phamhung075/3-nodejs_mongodb_wc_showCase_ErrorHandler_API)

## 3. [Success Handler ApiResponse](https://github.com/phamhung075/4-nodejs_mongodb_wc_showCase_ApiResponseUseClass/tree/master?tab=readme-ov-file)

## 4. [SignUp and Login Public Access](https://github.com/phamhung075/5-nodejs_mongodb_wc_showCase_SignUpLogin)

## 5. [Logout Authentication](https://github.com/phamhung075/6-nodejs_mongodb_wc_showCase_LogoutAuthentication)
## 6. [Refresh Token and Token Verification](https://github.com/phamhung075/7-nodejs_mongodb_wc_showCase_RefreshToken_verifyToken)
## 7. [Schema for Products in E-commerce](https://github.com/phamhung075/8-nodejs_mongodb_wc_showCase_Schema_Products_Ecommerce)
## 8. [API for Products Using Factory Pattern](https://github.com/phamhung075/11-nodejs_mongodb_wc_showCase_Api_Service_use_Factory_Pattern_Products_Senior_lv)

## 9. [API Service for Product Draft, Publish, and Unpublish](https://github.com/phamhung075/12-nodejs_mongodb_wc_showCase_Api_Service_Products_isDraft_isPublish_unPublish)
## 10. [API Service for Product Data Retrieval](https://github.com/phamhung075/13-nodejs_mongodb_wc_showCase_Api_Service_Products_findAll_findOne_selectData_unSelectData)
## 11. [API Service for Products: POST, PUT, PATCH](https://github.com/phamhung075/14-nodejs_mongodb_wc_showCase_Api_Service_Products_POST_PUT_PATCH)
## 12. [Inventories Model and Services Showcase](https://github.com/phamhung075/15-nodejs_mongodb_wc_showCase_InventoriesModel_vs_Services)
## 13. Discount Management in E-commerce


### Introduction

`16-nodejs_mongodb_wc_showCase_Discount_in_eCommerce` is a Node.js application that demonstrates the implementation of discount management in an e-commerce context using MongoDB. This project focuses on creating, managing, and applying discounts to products, an essential feature in modern e-commerce platforms.

### Installation

- Clone the repository:

    `git clone https://github.com/phamhung075/16-nodejs_mongodb_wc_showCase_Discount_in_eCommerce.git`
    
- Change to the directory:

    `cd 16-nodejs_mongodb_wc_showCase_Discount_in_eCommerce`
    
- Install dependencies:

    `npm install`
    

### Features

- **Discount Service** (`./services/discount.service.js`): Manages the business logic for creating and applying discounts.
- **Discount Controller** (`./controllers/discount.controller.js`): Handles API requests related to discount operations.
- **Discount Repository** (`./repositories/discount.repo.js`): Performs database operations for discount data.
- **Product Repository** (`./repositories/product.repo.js`): Integrates discount application into product data.
- **Router and Utilities** (`./routes/index.js`, `./utils/utils.js`): Organizes routing and provides utility functions to support discount operations.

### Usage

- Provides an end-to-end solution for managing discounts in e-commerce, from creation to application on products.
- Demonstrates how discounts can dynamically affect product pricing and promotions.

### MongoDB Connection

- Connect to MongoDB using: `mongodb://localhost:27017/yourDatabase`

### Additional Notes

- This project is a practical guide for developers aiming to implement discount features in e-commerce applications.
- The architecture and design patterns used in this project can be adapted to various e-commerce scenarios and requirements.
### Postman Examples


- **Signup**, **Login**, **Logout** examples as in the previous project.
- **Token Refresh** examples as in the previous project.
- **Create Product** examples as in the previous project.
- **Publish Product** examples as in the previous project.
- **UnPublish Product** examples as in the previous project.
- **get all Draft Products** examples as in the previous project.
- **get all Published Products** examples as in the previous project.
- **Find Product** examples as in the previous project.
- **Find All Products** examples as in the previous project.
- **Search Products by name** examples as in the previous project.
- **Modify Product** examples as in the previous project.
- **create new Discount By shop** examples
``` 
@url_dev=http://localhost:3052/v1/api/discount

### create new Discount By shop
POST {{url_dev}}
Content-Type: application/json
x-api-key: [API_KEY]
x-client-id: [SHOP_ID]
authorization: [ACCESS_TOKEN]

{
    "nameDiscount": "name fix amount",
    "description":  "description",
    "type": "fixed_amount",
    "value": 10000,
    "max_value": 30000,
    "code": "SHOP-10k",
    "start_date": "2023-12-20 09:00:00",
    "end_date": "2023-12-29 09:00:00",
    "max_uses":100,
    "uses_count": 0,
    "users_used": [],
    "max_uses_per_user": 1,
    "min_order_value": 200000,
    "created_by": {},
    "is_active": true,
    "applies_to": "specific",
    "product_ids" : ["6582b907ab506c927e56fc4b","6582b8b878683ca9b7b01094","658072bbd2a51865255c9990"]
}
```

- **get Product for Discount code** examples
``` 
@url_dev=http://localhost:3052/v1/api/discount

### get Product for Discount code
GET {{url_dev}}/list_product_code?code=[discountCode]&shopId=[shopId]&limit=[limit]&page=[page]
Content-Type: application/json
x-api-key: [API_KEY]

```

- **get list discount by Shop** examples
``` 
@url_dev=http://localhost:3052/v1/api/discount

### get list discount by Shop
GET {{url_dev}}?shopId=[shopId]&limit=[limit]&page=[page]
Content-Type: application/json
x-api-key: [API_KEY]
x-client-id: [SHOP_ID]
authorization: [ACCESS_TOKEN]
```

- **get amount discount** examples
``` 
@url_dev=http://localhost:3052/v1/api/product

### get amount discount
POST {{url_dev}}/amount
Content-Type: application/json
x-api-key: [API_KEY]
x-client-id: [SHOP_ID]
authorization: [ACCESS_TOKEN]

{
    "codeId": "SHOP-10k",
    "userId": 2,
    "shopId": "658071d2d2a51865255c9980",
    "products":[{
        "productId": "658072bbd2a51865255c9990",
        "quantity": 5,
        "price": 120000
    }]
}
```
For more detailed examples, refer to see [README.png](./README.png).
