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
### Example 2: POST Create User
### Example 3: Error Handling
## 🧪 Test Types

### Positive Testing
- Valid requests return correct data
- Status codes correct

### Negative Testing
- Invalid requests return errors
- Error messages helpful

### Performance Testing
- Response times acceptable
- Handle concurrent requests

### Security Testing
- Authentication required
- Authorization checked

## 📊 Metrics

Track:
- Total tests: 50
- Passed: 48 (96%)
- Failed: 2 (4%)
- Average response time: 150ms

## 🛠️ Tools

- **Postman** - Collections and testing
- **Insomnia** - REST client
- **Thunder Client** - VS Code extension

## ✅ Checklist

- [ ] All endpoints covered
- [ ] Positive and negative tests
- [ ] Error codes tested
- [ ] Response time validated
- [ ] Authentication tested
- [ ] Status codes verified
- [ ] Data validation checked

## 🚀 Next Steps

1. Create 20+ API tests
2. Document with assertions
3. Create Postman collection
4. Run against staging
5. Learn Test Automation

---

**Last Updated:** Mayo 2026
**Difficulty:** Intermediate
**Time to Master:** 1-2 weeks
