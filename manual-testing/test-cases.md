# Test Cases (Web UI + API)

## Web UI — Sauce Demo

### Authentication
**TC-UI-001 — Login with valid credentials**
- Preconditions: User is on login page
- Steps:
  1. Enter valid username
  2. Enter valid password
  3. Click **Login**
- Expected:
  - User is redirected to Products page
  - Products list is displayed

**TC-UI-002 — Login with invalid credentials**
- Preconditions: User is on login page
- Steps:
  1. Enter invalid username/password
  2. Click **Login**
- Expected:
  - Error message is displayed
  - User stays on login page

**TC-UI-003 — Login with empty fields**
- Preconditions: User is on login page
- Steps:
  1. Leave username empty
  2. Leave password empty
  3. Click **Login**
- Expected:
  - Validation / error message is displayed

### Product Listing & Sorting
**TC-UI-004 — Products page loads and shows items**
- Preconditions: User is logged in
- Steps:
  1. Open Products page
- Expected:
  - List of products is displayed
  - Each item shows name, price, and Add to cart button

**TC-UI-005 — Sort products (e.g., Price low to high)**
- Preconditions: User is logged in on Products page
- Steps:
  1. Change sort option to “Price (low to high)”
- Expected:
  - Products are reordered accordingly

### Cart
**TC-UI-006 — Add item to cart**
- Preconditions: User is logged in on Products page
- Steps:
  1. Click **Add to cart** for any product
  2. Open Cart
- Expected:
  - Selected product appears in cart
  - Cart badge increments

**TC-UI-007 — Remove item from cart**
- Preconditions: At least one item is in cart
- Steps:
  1. Click **Remove** for an item in cart
- Expected:
  - Item is removed
  - Cart badge decreases (or disappears)

### Checkout (basic flow)
**TC-UI-008 — Start checkout**
- Preconditions: At least one item is in cart
- Steps:
  1. Open Cart
  2. Click **Checkout**
- Expected:
  - Checkout information page opens

**TC-UI-009 — Checkout with valid customer data**
- Preconditions: User is on Checkout information page
- Steps:
  1. Fill First Name, Last Name, Zip/Postal Code with valid data
  2. Click **Continue**
- Expected:
  - Checkout overview page is displayed

**TC-UI-010 — Finish checkout**
- Preconditions: User is on Checkout overview page
- Steps:
  1. Click **Finish**
- Expected:
  - Confirmation page is displayed (order completed)


## API — Reqres

** TC-API-USER-001 — Get existing user by valid ID (strict body match)

- **Method:** GET  
- **Endpoint:** `/api/users/1`

**Steps:**
1. Send request

**Expected:**
- Status code: **200**
- Response is **JSON**
- Response contains `data` object
- `data` strictly equals:
  - `id` = 1
  - `email` = `george.bluth@reqres.in`
  - `first_name` = `George`
  - `last_name` = `Bluth`
  - `avatar` = `https://reqres.in/img/faces/1-image.jpg`
- Response contains `support` object:
  - `support.url` exists
  - `support.text` exists
- Response contains `_meta` object:
  - `_meta.powered_by` exists
  - `_meta.docs_url` exists
  - `_meta.context` exists

---

** TC-API-USER-002 — Get non-existing user returns 404 with empty JSON object

- **Method:** GET  
- **Endpoint:** `/api/users/99`

**Steps:**
1. Send request

**Expected:**
- Status code: **404**
- Response is **JSON**
- Response body is **empty object `{}`** (strict match)

---

** TC-API-USER-003 — Get user with invalid ID format returns error JSON

- **Method:** GET  
- **Endpoint:** `/api/users/aaaa` *(invalid ID format)*

**Steps:**
1. Send request

**Expected:**
- Status code: **404**
- Response is **JSON**
- Response body is **NOT** empty object (contains at least one key)
- Response contains `error` field
- `error` is a **string**

