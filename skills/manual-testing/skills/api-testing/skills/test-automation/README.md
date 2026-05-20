# Test Automation Skill

## 📋 Overview

Test automation uses code to automatically execute tests. This skill covers Selenium/Python automation, Page Object Model pattern, and best practices for maintainable test suites.

## 🎯 When to Use This Skill

Use test automation when:
- Regression testing repetitive scenarios
- Need continuous integration/deployment
- Testing large feature sets
- Smoke testing before releases
- Cross-browser testing

## 📚 What You'll Learn

- Selenium WebDriver fundamentals
- Python test frameworks (pytest)
- Page Object Model pattern
- Locator strategies
- Wait strategies
- Assertion techniques
- CI/CD integration
- Test reporting

## 🔄 Related Skills

- **Manual Testing** - Basis for automation
- **API Testing** - API automation with code
- **Test Data** - Data for automated tests
- **Performance Testing** - Performance automation

## 📖 Framework

### 1. Selenium Basics

**Setup:**
```python
from selenium import webdriver
from selenium.webdriver.common.by import By

driver = webdriver.Chrome()
driver.get("https://example.com")
```

**Locators:**
```python
# ID
element = driver.find_element(By.ID, "login-button")

# Class
element = driver.find_element(By.CLASS_NAME, "input-field")

# XPath
element = driver.find_element(By.XPATH, "//button[@id='submit']")

# CSS Selector
element = driver.find_element(By.CSS_SELECTOR, "input[type='email']")
```

### 2. Page Object Model

**Structure:**
```python
class LoginPage:
    def __init__(self, driver):
        self.driver = driver
    
    def login(self, email, password):
        self.driver.find_element(By.ID, "email").send_keys(email)
        self.driver.find_element(By.ID, "password").send_keys(password)
        self.driver.find_element(By.ID, "submit").click()
```

### 3. Waits

**Implicit Wait:**
```python
driver.implicitly_wait(10)
```

**Explicit Wait:**
```python
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC

wait = WebDriverWait(driver, 10)
element = wait.until(
    EC.presence_of_element_located((By.ID, "success"))
)
```

## 💡 Examples

### Example 1: Login Test

```python
import pytest
from selenium import webdriver
from selenium.webdriver.common.by import By

class TestLogin:
    def setup_method(self):
        self.driver = webdriver.Chrome()
        self.driver.get("https://example.com/login")
    
    def test_valid_login(self):
        """TC-AUTO-001: Login with valid credentials"""
        username = self.driver.find_element(By.ID, "username")
        password = self.driver.find_element(By.ID, "password")
        submit = self.driver.find_element(By.ID, "submit")
        
        username.send_keys("student")
        password.send_keys("Password123")
        submit.click()
        
        assert "Dashboard" in self.driver.title
    
    def test_invalid_login(self):
        """TC-AUTO-002: Login with wrong password"""
        username = self.driver.find_element(By.ID, "username")
        password = self.driver.find_element(By.ID, "password")
        submit = self.driver.find_element(By.ID, "submit")
        
        username.send_keys("student")
        password.send_keys("WrongPassword")
        submit.click()
        
        error = self.driver.find_element(By.ID, "error")
        assert error.is_displayed()
    
    def teardown_method(self):
        self.driver.quit()
```

### Example 2: Page Object Model

```python
# pages/login_page.py
class LoginPage:
    def __init__(self, driver):
        self.driver = driver
        self.username_field = (By.ID, "username")
        self.password_field = (By.ID, "password")
        self.login_button = (By.ID, "submit")
    
    def login(self, username, password):
        self.driver.find_element(*self.username_field).send_keys(username)
        self.driver.find_element(*self.password_field).send_keys(password)
        self.driver.find_element(*self.login_button).click()

# tests/test_login.py
from pages.login_page import LoginPage

def test_login():
    driver = webdriver.Chrome()
    driver.get("https://example.com/login")
    
    login_page = LoginPage(driver)
    login_page.login("student", "Password123")
    
    assert "Dashboard" in driver.title
    driver.quit()
```

## 🧪 Test Types

### Regression Tests
- Run after code changes
- Ensure features work
- Automated suite

### Smoke Tests
- Quick checks
- Core functionality
- Fast execution

### Integration Tests
- Multiple components
- Full workflows
- End-to-end

## 📊 Metrics

Track:
- Test count: 50
- Pass rate: 96%
- Execution time: 10 minutes
- Flaky tests: 2
- Coverage: 85%

## 🛠️ Tools

- **Selenium** - Browser automation
- **pytest** - Test framework
- **Allure** - Reporting
- **Jenkins** - CI/CD

## ✅ Checklist

- [ ] Page Object Model implemented
- [ ] Proper wait strategies
- [ ] Clear locators
- [ ] Meaningful assertions
- [ ] Test data management
- [ ] Error handling
- [ ] Logging implemented
- [ ] Reports generated

## 🚀 Next Steps

1. Create 10+ automated tests
2. Implement Page Object Model
3. Set up pytest fixtures
4. Integrate with CI/CD
5. Generate test reports

---

**Last Updated:** Mayo 2026
**Difficulty:** Advanced
**Time to Master:** 3-4 weeks
