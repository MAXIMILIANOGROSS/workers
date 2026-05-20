# API Testing Skill

## 📋 Overview

API testing validates that APIs work correctly. This skill covers REST API testing with Postman, assertions, and validation strategies.

## 🎯 When to Use This Skill

Use API testing when:
- Testing backend endpoints
- Validating data flows between systems
- Testing microservices
- Checking error handling
- Load testing APIs
- Integration testing

## 📚 What You'll Learn

- REST API fundamentals
- HTTP methods and status codes
- Postman collections
- Request/response validation
- Assertion writing
- Error handling testing
- Performance validation

## 🔄 Related Skills

- **Test Automation** - API automation with code
- **Performance Testing** - API load testing
- **Test Data** - Test data for APIs
- **Manual Testing** - Manual API testing

## 📖 Framework

### 1. API Basics

**HTTP Methods:**
- GET - Retrieve data
- POST - Create data
- PUT - Update data
- DELETE - Remove data

**Status Codes:**
- 200 - OK
- 201 - Created
- 400 - Bad Request
- 404 - Not Found
- 500 - Server Error

### 2. Test Request

**Structure:**
### 3. Response Validation

**Check:**
- Status code
- Response time (< 500ms)
- Headers
- JSON structure
- Field values

### 4. Assertions

**Examples:**
```javascript
pm.expect(pm.response.code).to.equal(200);
pm.expect(pm.response.responseTime).to.be.below(500);
pm.expect(jsonData.name).to.equal("John");
```

## 💡 Examples

### Example 1: GET User
