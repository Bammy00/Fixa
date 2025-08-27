
```markdown
# Fixa E2E Test Suite

This repository contains automated end-to-end tests for the **Fixa Employee Management System**, built with **Playwright** and **TypeScript**.

The suite validates core workflows such as authentication and partial employee onboarding.  
_Onboarding coverage is partial due to limited time for setup and test implementation._

---

## 📁 Project Structure

```

fixa-e2e-tests/
├── tests/                  # Organized test specs
│   ├── auth/               # Login and authentication tests
│   │   ├── login.spec.ts
│   │   └── invalid-login.spec.ts
│   └── employees/          # Employee dashboard and onboarding tests
│       └── add-employee.spec.ts
├── pages/                  # Page Object Models for reusable selectors
│   ├── login.page.ts
│   └── employee.page.ts
├── mocks/                  # Mock API responses
│   └── employees.mock.ts
├── utils/                  # Test data and helper functions
│   └── test-data.ts
├── playwright.config.ts    # Playwright configuration
└── README.md               # Project documentation

````

---

## 🚀 Getting Started

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-username/fixa-e2e-tests.git
   cd fixa-e2e-tests
````

2. **Install dependencies**

   ```bash
   npm install
   ```

3. **Install Playwright browsers**

   ```bash
   npx playwright install
   ```

---

## ▶️ Running Tests

* Run **all tests**

  ```bash
  npx playwright test
  ```

* Run a **specific test file**

  ```bash
  npx playwright test tests/employees/add-employee.spec.ts
  ```

* Run only **authentication tests**

  ```bash
  npx playwright test tests/auth
  ```

* Run in **headed mode** (visible browser)

  ```bash
  npx playwright test --headed
  ```

* View **HTML report**

  ```bash
  npx playwright show-report
  ```

---

## 🔐 Authentication Coverage

Authentication flows are located in `tests/auth/`:

* **login.spec.ts** → Valid login with correct credentials
* **invalid-login.spec.ts** → Invalid login and error handling

**Credentials (staging only):**

* Email: `wouldhavelovedtousegithubsecrets@fixing.com`
* Password: `nottoberevealed`

⚠️ *These credentials are for testing only. Do **not** use in production.*

---

## 👥 Employee Dashboard Coverage

Employee-related tests are in `tests/employees/`:

* **add-employee.spec.ts** → Adds a new employee manually via the onboarding flow

  * Includes form validation
  * Gender selection
  * Submission logic
  * Uses **mock API responses** for consistency

---

## 🕒 CI Integration

To run tests daily via **GitHub Actions**, use the workflow:

```
.github/workflows/playwright-daily.yml
```

This workflow:

* Runs the full suite **every day at 8:00 AM UTC**
* Uploads the Playwright **HTML report as an artifact**

---


