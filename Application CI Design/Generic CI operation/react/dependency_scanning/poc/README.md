

# Dependency Scanning POC





| Author      | Created on  | Version    | Last updated by | Last edited on | Internal reviewer |   L0     |    L1     |    L2   |
|-------------|-------------|------------|-----------------|----------------|-------------------|----------|-----------|-----------|
| Rajeev Ranjan    | 17-05-2025    | version 1  | N/A        |     N/A   |     Priyanshu         | Khushi Malhotra  | Mukul Joshi     | Piyush Upadhyay  |  


---

## Table of Contents

1. [Introduction](#1-introduction)
2. [POC: Scanning a React App](#2-poc-scanning-a-react-app)

   * [Step 1: Clone or Create a React App](#step-1-clone-or-create-a-react-app)
   * [Step 2: install npm](#step-2-install-npm)
   * [Step 3: Run npm audit](#step-3-run-npm-audit)
   * [Step 4: Run npm audit](#step-4-run-npm-audit-fix)
3. [Contact](#3-contact)
4. [References](#4-references)

---

## 1. Introduction

In React apps, dependencies are primarily managed using npm or yarn. Scanning for vulnerabilities is crucial since npm packages often include third-party code which can be compromised or outdated.

---

## 2. POC: Scanning a React App

### Step 1: Clone or Create a React App

```bash
git clone https://github.com/OT-MICROSERVICES/frontend.git
cd frontend/

```
![Screenshot 2025-05-17 204647](https://github.com/user-attachments/assets/59385162-9078-4c52-9802-b33c3b8cb75c)


### Step 2: install npm

```bash
sudo apt install npm
```
![Screenshot 2025-05-17 204722](https://github.com/user-attachments/assets/72a676e3-5a4f-4c94-8867-5b9f747611f4)



### Step 3: Run npm audit

```bash
npm i ---package-lock-only
```

![Screenshot 2025-05-17 204830](https://github.com/user-attachments/assets/d9bf23c6-e3f1-4c8f-ac0b-e2f7032b0d17)


### Step 4: Run npm audit fix

```bash
npm audit fix
```
To deeply fix and update transitive dependencies:

```bash
npm audit fix --force
```

You will receive a list of vulnerabilities (if any) along with severity, path, and suggested fixes.


![Screenshot 2025-05-17 205214](https://github.com/user-attachments/assets/f67a733f-7183-4b73-be46-ec5b6e8f5c71)

![Screenshot 2025-05-17 205225](https://github.com/user-attachments/assets/297f5d3e-8a66-42cf-88ff-3a5703ba7673)





## 3. Contact

| Name          | Email Address                                                                     |
| ------------- | --------------------------------------------------------------------------------- |
| Rajeev Ranjan | [rajeev.rajan.snaatak@mygurukulam.co](mailto:rajeev.rajan.snaatak@mygurukulam.co) |

---

## 4. References

* [Snyk for JavaScript](https://snyk.io)
* [npm audit docs](https://docs.npmjs.com/cli/v9/commands/npm-audit)
* [Dependabot GitHub Docs](https://docs.github.com/en/code-security/supply-chain-security/keeping-your-dependencies-updated-automatically)

---

Let me know if you want this converted to a downloadable format (PDF, Markdown, or Word).

