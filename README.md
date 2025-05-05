# 📚 Book Reservation API - Postman Test Collection

This repository contains an automated test suite for the Book Reservation API, built using [Postman](https://www.postman.com/) and executed in CI using [Newman](https://www.npmjs.com/package/newman) via GitHub Actions.

---

## 🚀 How It Works

- 🧪 Postman collection: `BookReservationSystem.postman_collection.json`
- 🌍 Environment file: `BookReservationSystemEnvironment.postman_environment.json`
- ⚙️ CI: [GitHub Actions](https://docs.github.com/en/actions) runs Newman on every push or PR to the `main` branch.
- 📄 HTML reports are generated with each test run and uploaded as a downloadable artifact.

---

## 🧪 Running Locally with Newman

### Prerequisites

- [Node.js](https://nodejs.org/) installed
- Install Newman and the HTML reporter globally:

```bash
npm install -g newman newman-reporter-html
```

### Run the Tests

```bash
newman run BookReservationSystem.postman_collection.json \
  -e BookReservationSystemEnvironment.postman_environment.json \
  --reporters cli,html \
  --reporter-html-export newman-report.html
```

This will:
- Run the API tests
- Print results in the terminal
- Generate a `newman-report.html` file for visual reporting

---

## ⚙️ GitHub Actions CI

On each push or pull request to `main`, the workflow:

1. Installs Node.js and Newman
2. Installs the HTML reporter
3. Runs the Postman tests
4. Generates an HTML report
5. Uploads the report as a downloadable artifact

You can find it under the **Artifacts** section in your GitHub Actions run:

📁 `newman-html-report → newman-report.html`

---

## 📁 Files in This Repository

| File                                         | Description                            |
|----------------------------------------------|----------------------------------------|
| `BookReservationSystem.postman_collection.json` | The Postman API test collection         |
| `BookReservationSystemEnvironment.postman_environment.json`           | Postman environment variables           |
| `.github/workflows/newman.yml`               | GitHub Actions workflow for CI testing |
| `README.md`                                  | This file                               |

---
