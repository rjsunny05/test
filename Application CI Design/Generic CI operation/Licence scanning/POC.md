# Licence scanning POC: FOSSA


| Author      | Created on  | Version    | Last updated by | Last edited on | Internal reviewer |   L0     |    L1     |    L2   |
|-------------|-------------|------------|-----------------|----------------|-------------------|----------|-----------|-----------|
| Rajeev Ranjan    |     | version 1  | N/A        |     N/A   |     Priyanshu         | Khushi Malhotra  | Mukul Joshi     | Piyush Upadhyay  | 


## Table Of Contents
 1. [Pre-requisites](#1-Pre-requisites)
 2. [Setup and Configuration](#2-Setup-and-Configuration)
 3. [FOSSA in all three api (attedance-api, employee-api and salary-api) ](FOSSA-in-all-three-api (attedance-api, employee-api and salary-api))
 4. [Contacts Information](#4-contacts-information)
 5. [References](#5-references)





## 1. Pre-requisites

  - Access to FOSSA:    
        Sign up for a FOSSA account if you don’t have one.
        Access to the FOSSA dashboard and API token.
   
  - Project Repository:             
        Ensure the project source code is hosted on a supported version control system (GitHub, GitLab, Bitbucket, etc.).
   
  - System Requirements:
        FOSSA CLI installed:

   Access to the internet from your development environment.

## 2. Setup and Configuration

  - Install FOSSA CLI:
        Open a terminal and install the FOSSA CLI. On Ubuntu, use curl to install:
```
    curl -H 'Cache-Control: no-cache' https://raw.githubusercontent.com/fossas/fossa-cli/master/install-latest.sh | bash

    fossa --version
```

![Screenshot 2025-05-13 224613](https://github.com/user-attachments/assets/b72b9493-a24f-413f-87f3-fd7666a60b72)


  - Authenticate the CLI:

    Obtain an API token from the FOSSA dashboard: Settings → API Keys.
    Authenticate the CLI using the token:


```
    fossa login --token <your-api-token>
```
  ![Screenshot 2025-05-13 224823](https://github.com/user-attachments/assets/991a341e-2e37-4bee-818f-d48b399563a1)

## 3. FOSSA in all three api (attedance-api, employee-api and salary-api)

 ### (a) Integrate License Scanning 

  - Initialize FOSSA in the Project:
  - Navigate to the project directory and initialize FOSSA:
```
    fossa init
```
 #### (i) attendance-api
    
  ![Screenshot 2025-05-13 225033](https://github.com/user-attachments/assets/4aa4bea2-9e36-443f-8ae1-277b3de331e8)

 #### (ii) employee-api

  ![Screenshot 2025-05-13 231850](https://github.com/user-attachments/assets/27952cc6-f3c2-49bd-b12f-4738d20d3079)

  
 #### (iii) salary-api

 ![Screenshot 2025-05-13 233142](https://github.com/user-attachments/assets/91831d50-a8fd-4060-8098-e068bc594a8d)



   This will create a .fossa.yml file with default configurations.

Edit .fossa.yml (Optional):

  Modify the .fossa.yml file if needed to include/exclude specific paths or dependencies.

### (b) Run FOSSA Analysis

  - Execute the CLI to analyze your project dependencies:
```
fossa analyze
```

 #### (i) attendance-api

 ![Screenshot 2025-05-13 225118](https://github.com/user-attachments/assets/991a0aa1-e72f-462e-856e-9ee0e0a4777c)


 #### (ii) employee-api

 ![Screenshot 2025-05-13 231909](https://github.com/user-attachments/assets/f2e60fdd-7933-417d-8086-92c6178ca326)


 #### (iii) salary-api

 ![Screenshot 2025-05-13 233226](https://github.com/user-attachments/assets/de86f27a-48bd-4059-bc78-181f53a8cc5b)


### (c) Run FOSSA Test

- Execute the CLI to Runs license compliance checks:
```
fossa test
```

 #### (i) attendance-api

 ![Screenshot 2025-05-13 225622](https://github.com/user-attachments/assets/8e73518d-6fe2-4d6b-a7b6-dc9834f582e8)

 ![Screenshot 2025-05-13 225702](https://github.com/user-attachments/assets/57f2ac82-f3fb-4d83-88c7-4064e19c0e22)

 ![Screenshot 2025-05-13 225712](https://github.com/user-attachments/assets/3374252d-4d5b-4ff9-9a13-df81deb34f02)


 #### (ii) employee-api

 ![Screenshot 2025-05-13 231947](https://github.com/user-attachments/assets/9aff039a-cb2e-44a2-af56-d68f46aa2f5c)

 ![Screenshot 2025-05-13 232002](https://github.com/user-attachments/assets/2a3d6b6b-2b87-45f3-925a-15430d1c7d56)



 #### (iii) salary-api
 
 ![Screenshot 2025-05-13 233318](https://github.com/user-attachments/assets/5e65575e-c0e5-42d6-b430-87eaedff2f8c)






### (d) FOSSA dashboard.

 #### (i) attendance-api

 ![Screenshot 2025-05-13 225811](https://github.com/user-attachments/assets/d46562e2-1ea5-4a48-b281-1e6437f3ea38)

 #### (ii) employee-api

 ![Screenshot 2025-05-13 232041](https://github.com/user-attachments/assets/e1fcba9b-4774-4cd9-83a2-f87366a46851)

 #### (iii) salary-api

 ![Screenshot 2025-05-13 233349](https://github.com/user-attachments/assets/ad05ef52-a7d9-41f1-96d0-aafe756f9d06)




## 4. Contacts Information

| Name| Email Address      |
|-----|--------------------------|
| Rajeev Ranjan          |     rajeev.rajan.snaatak@mygurukulam.co |

## 5. References

| Tool        | Link                                                                   |
|-------------|------------------------------------------------------------------------|
| FOSSA       | [FOSSA Documentation](https://fossa.com)                                 |




