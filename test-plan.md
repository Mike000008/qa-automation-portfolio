# Test Plan

## 1. Introduction
This test plan describes the testing strategy and scope for the QA portfolio project.
The goal is to validate the functionality, usability, and API behavior of the selected applications.

## 2. Applications Under Test
- Web UI: Sauce Demo (e-commerce demo application)
- REST API: Reqres (public REST API)

## 3. Testing Scope

### In Scope
- User authentication (login)
- Product listing and filtering
- Shopping cart functionality
- Basic checkout flow
- REST API endpoints for user management (login, register, users)
- Positive and negative test scenarios

### Out of Scope
- Performance and load testing
- Security testing
- Payment processing validation
- Cross-browser testing

## 4. Test Types
- Smoke testing
- Functional testing
- Exploratory testing
- API testing

## 5. Test Environment
- OS: Windows
- Browser: Chrome (latest)
- API Tool: Postman
- Automation: Python (pytest, requests, Playwright)

## 6. Entry and Exit Criteria

### Entry Criteria
- Application is accessible
- Test environment is available

### Exit Criteria
- All critical test cases are executed
- Critical defects are documented

## 7. Risks and Assumptions
- Demo applications may be unstable or change behavior
- Limited control over test data
- No access to backend logs
