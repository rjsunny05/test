# ✅ React Dependency Scanning POC

| Author        | Created on | Version   | Last updated by | Last edited on | Internal reviewer | L0              | L1          | L2              |
| ------------- | ---------- | --------- | --------------- | -------------- | ----------------- | --------------- | ----------- | --------------- |
| Rajeev Ranjan | 17-05-2025 | version 1 | N/A             | N/A            | Priyanshu         | Khushi Malhotra | Mukul Joshi | Piyush Upadhyay |

---

## 1. Introduction

In React apps, dependencies are primarily managed using npm or yarn. Scanning for vulnerabilities is crucial since npm packages often include third-party code which can be compromised or outdated.

---

## 2. POC: Scanning a React App

### 🔧 Step 1: Clone or Create a React App

```bash
npx create-react-app react-dependency-scan
cd react-dependency-scan
```

---

### 🧪 Step 2: Run npm audit

```bash
npm audit
```

You will receive a list of vulnerabilities (if any) along with severity, path, and suggested fixes.

> 🔁 To auto-fix:

```bash
npm audit fix
```

> 🔍 To deeply fix and update transitive dependencies:

```bash
npm audit fix --force
```

---

### 🔒 Step 3: Scan with Snyk

**Install Snyk CLI:**

```bash
npm install -g snyk
```

**Authenticate (opens browser):**

```bash
snyk auth
```

**Run scan:**

```bash
snyk test
```

**Optional: monitor project on snyk.io:**

```bash
snyk monitor
```

> Snyk will list vulnerabilities, licenses, and even create monitoring dashboards.

---

### 🤖 Step 4: Enable Dependabot in GitHub

In your project repo, create the file:

`.github/dependabot.yml`

```yaml
version: 2
updates:
  - package-ecosystem: "npm"
    directory: "/"
    schedule:
      interval: "weekly"
```

> GitHub will automatically scan and open PRs to update dependencies.

---

### ✅ Step 5: CI Integration Example (GitHub Actions)

Create `.github/workflows/dependency-scan.yml`:

```yaml
name: Dependency Scan

on: [push]

jobs:
  audit:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout Code
        uses: actions/checkout@v2

      - name: Install Dependencies
        run: npm install

      - name: Run npm audit
        run: npm audit --audit-level=high
```

---

## 3. Contact

| Name          | Email Address                                                                     |
| ------------- | --------------------------------------------------------------------------------- |
| Rajeev Ranjan | [rajeev.rajan.snaatak@mygurukulam.co](mailto:rajeev.rajan.snaatak@mygurukulam.co) |

---

## 4. References

1. [Snyk for JavaScript](https://snyk.io/languages/javascript/)
2. [npm audit docs](https://docs.npmjs.com/cli/v9/commands/npm-audit)
3. [Dependabot GitHub Docs](https://docs.github.com/en/code-security/supply-chain-security/keeping-your-dependencies-updated-automatically)
