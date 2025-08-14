# Gearo E-commerce API Documentation

This repository contains the API documentation and Postman collection for the Gearo E-commerce platform.

## 📋 Table of Contents

- [Overview](#overview)
- [Getting Started](#getting-started)
- [Authentication](#authentication)
- [API Endpoints](#api-endpoints)
- [Postman Collection](#postman-collection)
- [Environment Variables](#environment-variables)
- [Response Formats](#response-formats)

## 🌟 Overview

The Gearo E-commerce API provides endpoints for managing customers, products, orders, payments, and store operations. This API follows RESTful principles and uses JSON for data exchange.

**Base URL:** `https://ecom.techworlds.my`
**API Version:** v1/v2 (varies by endpoint)

## 🚀 Getting Started

### Prerequisites
- Valid store slug (e.g., `my-store`)
- API credentials (product key & secret key for signature-based authentication)
- Bearer token for authenticated endpoints

### Quick Start
1. Import the Postman collection into your Postman workspace
2. Set up environment variables (see below)
3. Test the endpoints starting with authentication

## 🔐 Authentication

The API supports multiple authentication methods:

### 1. Bearer Token Authentication
For customer-specific operations:
```
Authorization: Bearer {access_token}
```

### 2. Signature-Based Authentication
For enhanced security, some endpoints require MD5 signature validation using:
- Product Key
- Secret Key
- Request parameters

### 3. Store Slug Parameter
Most endpoints require a store slug parameter:
```
?slug=my-store
```

## 📚 API Endpoints

### Customer Management
- `POST /api/customer/login` - Customer login
- `POST /api/customer/register` - Customer registration
- `GET /api/customer/profile` - Get customer profile
- `POST /api/customer/profile` - Update customer profile
- `POST /api/customer/logout` - Customer logout

### Product Catalog
- `GET /api/product/list` - Get products by category
- `GET /api/product/product` - Get single product details
- `GET /api/product/get-products-variant-quantity` - Get variant quantities
- `POST /api/product/taxes` - Calculate product taxes

### Homepage Content
- `GET /api/slides` - Get homepage slides/banners
- `GET /api/homepage/categories` - Get homepage categories
- `GET /api/v2/homepage/feature` - Get featured products and hot deals

### Navigation & Menus
- `GET /api/header` - Get navigation menu structure
- `GET /api/footer` - Get footer menu structure

### Orders & Shopping
- `GET /api/customer/order/list` - Get customer order history
- `GET /api/customer/order/detail` - Get order details
- `POST /api/customer/order/refund` - Request order refund
- `POST /api/customer/order/receive` - Mark order as received

### Shipping & Location
- `GET /api/orders/locations` - Get available shipping locations
- `POST /api/orders/shipping-fee` - Calculate shipping costs
- `POST /api/orders/apply-coupon` - Apply discount coupon

### Payment Processing
- `POST /api/payment/cod` - Cash on delivery payment
- `POST /api/payment/ipay88` - iPay88 payment gateway
- `POST /api/payment/scpayment` - SCPayment gateway

### Store Information
- `GET /api/branches` - Get store branches
- `GET /api/stores/setting` - Get store settings
- `GET /api/stores/payment-setting` - Get payment configuration

## 📦 Postman Collection

The included Postman collection (`Ecom - Client API.postman_collection.json`) contains:
- Pre-configured requests for all endpoints
- Environment variables setup
- Authentication helpers
- Example responses

### Import Instructions
1. Open Postman
2. Click "Import" button
3. Select the JSON file
4. Configure environment variables

## 🔧 Environment Variables

Set up these variables in your Postman environment:

```json
{
  "url": "ecom.techworlds.my",
  "token": "your_bearer_token_here",
  "slug": "my-store",
  "product_key": "your_product_key",
  "secret_key": "your_secret_key"
}
```

## 📄 Response Formats

### Success Response
```json
{
  "data": {
    // Response data here
  }
}
```

### Authentication Response
```json
{
  "access_token": "9|pVYZQxsJI1DCqe7RFI2kFr2O7hwEF7PVQBEBmZPAd622b2b2",
  "token_type": "Bearer"
}
```

### Error Response
```json
{
  "error": "Error message here"
}
```

## 🛠️ Rate Limiting

The API implements rate limiting:
- **Limit:** 60 requests per time window
- **Headers:** Check response headers for rate limit status

## 🤝 Contributing

1. Fork this repository
2. Create a feature branch
3. Update documentation as needed
4. Submit a pull request

## 📞 Support

For API support and questions:
- Create an issue in this repository
- Contact the development team

## 📝 License

This documentation is provided under the MIT License.

---

**Last Updated:** $(date +'%Y-%m-%d')
**API Version:** v1/v2
**Maintained by:** Gearo Development Team
