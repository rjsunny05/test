# Detailed Documentation Of React Dependency Scanning

| Author        | Created on | Version   | Last updated by | Last edited on | Internal reviewer | L0              | L1          | L2              |
| ------------- | ---------- | --------- | --------------- | -------------- | ----------------- | --------------- | ----------- | --------------- |
| Rajeev Ranjan | 17-05-2025 | version 1 | N/A             | N/A            | Priyanshu         | Khushi Malhotra | Mukul Joshi | Piyush Upadhyay |

---

##  Table of Contents

1. [Introduction](#1-introduction)
2. [Why Dependency Scanning is Important](#2-why-dependency-scanning-is-important)
3. [Workflow](#3-workflow)
4. [Different Tools for React Dependency Scanning](#4-different-tools-for-react-dependency-scanning)
5. [Comparison of Dependency Scanning Tools](#5-comparison-of-dependency-scanning-tools)
6. [Advantages of React Dependency Scanning in CI](6-#advantages-of-react-dependency-scanning-in-ci)
7. [Disadvantages of React Dependency Scanning in CI](#7-disadvantages-of-react-dependency-scanning-in-ci)
8. [Best Practices for Dependency Scanning](#8-best-practices-for-dependency-scanning)
9. [Recommendations](#9-recommendations)
10. [Conclusion](#10-conclusion)
11. [Contact Information](#11-contact-information)
12. [References](#12-references)

---

## 1. Introduction

In modern frontend development, React projects heavily rely on third-party libraries via npm. These dependencies can introduce vulnerabilities or compatibility issues if not regularly scanned. Dependency scanning helps ensure security, stability, and compliance in your React codebase.

---

## 2. Why Dependency Scanning is Important

| Reason      | Explanation                                                                       |
| ----------- | --------------------------------------------------------------------------------- |
| Security    | Prevent known vulnerabilities in third-party packages from compromising your app. |
| Stability   | Prevent broken builds or production issues due to incompatible libraries.         |
| Compliance  | Ensure usage of only approved licenses in OSS libraries.                          |
| Performance | Eliminate unnecessary or bloated packages.                                        |

---

## 3. Workflow

![Screenshot 2025-05-18 163301](https://github.com/user-attachments/assets/7a0f61c9-5b87-43da-8757-aea725888ca7)


---


## 4. Different Tools for React Dependency Scanning

| Tool                       | Description                                                             |
| -------------------------- | ----------------------------------------------------------------------- |
| **npm audit**              | Native npm tool to find known vulnerabilities.                          |
| **Snyk**                   | Monitors and patches security issues in npm dependencies.               |
| **OWASP Dependency-Check** | Checks for vulnerabilities in JavaScript dependencies via CVE database. |
| **Retire.js**              | Scans JavaScript libraries for known vulnerable versions.               |
| **Dependabot**             | GitHub-integrated bot to scan and update outdated/insecure packages.    |

---

## 5. Comparison of Dependency Scanning Tools

| Tool           | Key Feature                        | Integration           | Free Tier | Ease of Use |
| -------------- | ---------------------------------- | --------------------- | --------- | ----------- |
| npm audit      | Native vulnerability scan          | npm, CI/CD            | Yes       | High        |
| Snyk           | Auto PRs & deep vulnerability scan | GitHub, GitLab, npm   | Yes       | High        |
| Dependabot     | Auto PRs for outdated deps         | GitHub                | Yes       | High        |
| OWASP DepCheck | CVE-based checks                   | Manual/CI Integration | Yes       | Medium      |
| Retire.js      | JavaScript lib scan                | CLI/CI/CD             | Yes       | Medium      |

---

## 6. Advantages of React Dependency Scanning in CI

| Advantage                     | Description                                                    |
| ----------------------------- | -------------------------------------------------------------- |
| Early vulnerability detection | Find and patch issues during development phase itself.         |
| Continuous monitoring         | Auto-updates and alerts prevent long-term risk accumulation.   |
| Compliance enforcement        | Detect and flag disallowed licenses or libraries.              |
| Lightweight and fast          | npm audit, Snyk, and Dependabot are efficient in CI pipelines. |

---

## 7. Disadvantages of React Dependency Scanning in CI

| Disadvantage                | Explanation                                               |
| --------------------------- | --------------------------------------------------------- |
| False Positives             | Some tools may report low-priority or fixed issues.       |
| CI pipeline slowdown        | Full scans might slightly delay builds.                   |
| Breaking changes in updates | Auto updates (like Dependabot) can introduce regressions. |

---

## 8. Best Practices for Dependency Scanning

| Practice                 | Description                                                            |
| ------------------------ | ---------------------------------------------------------------------- |
| Automate with CI         | Add dependency scanning in CI (GitHub Actions, Jenkins, etc).          |
| Use multiple tools       | Combine **npm audit**, **Snyk**, and **Dependabot** for full coverage. |
| Review auto PRs manually | Check each dependency bump for breaking changes.                       |
| Schedule weekly scans    | Run regular audits to keep up with CVE disclosures.                    |
| Lock dependency versions | Use `package-lock.json` to freeze working versions.                    |

---

## 9. Recommendations

| Recommendation        | Description                                          |
| --------------------- | ---------------------------------------------------- |
| Use **npm audit**     | Start with `npm audit` for simple baseline scanning. |
| Integrate **Snyk**    | For deeper CVE checks and auto-fixing via PRs.       |
| Enable **Dependabot** | Keep dependencies auto-updated on GitHub.            |
| CI Scanning           | Add a scan stage in Jenkins or GitHub Actions.       |

---

## 10. Conclusion

We will be using **npm audit** tool for dependency scanning for our frontend which is used in our Employee API in OT-Microservice. **npm audit** is a simple, fast, and built-in tool that helps you quickly find and fix known security issues in your React project's dependencies. It requires no extra setup and works directly with your existing package-lock.json. **npm audit** is built directly into npm, making it the easiest and fastest way to scan for vulnerabilities without needing extra setup. It integrates seamlessly into any Node.js project and works out-of-the-box with CI/CD. Unlike other tools, it doesn’t require third-party accounts or configuration, making it ideal for quick and native security checks.

---

## 11. Contact Information

| Name          | Email Address                                                                     |
| ------------- | --------------------------------------------------------------------------------- |
| Rajeev Ranjan | [rajeev.rajan.snaatak@mygurukulam.co](mailto:rajeev.rajan.snaatak@mygurukulam.co) |

---

## 12. References

1. [Snyk for JavaScript](https://snyk.io/languages/javascript/)
2. [npm audit docs](https://docs.npmjs.com/cli/v9/commands/npm-audit)
3. [Dependabot GitHub Docs](https://docs.github.com/en/code-security/supply-chain-security/keeping-your-dependencies-updated-automatically)
4. [Retire.js GitHub](https://github.com/RetireJS/retire.js)
5. [OWASP Dependency Check](https://owasp.org/www-project-dependency-check/)

---

