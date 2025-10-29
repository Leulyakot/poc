# MuleSoft CI/CD to Anypoint GovCloud (GitHub Actions)

This guide helps you set up a complete CI/CD pipeline using **GitHub Actions**, **Maven**, and a **Connected App** to deploy a MuleSoft application to **Anypoint GovCloud**.

---

## 🧩 Prerequisites

- Mule application managed with **Maven**
- Access to **Anypoint GovCloud**
- A **Connected App** with Client Credentials grant type
- Mule app source code hosted in **GitHub**

---

## 🔐 Create Connected App in Anypoint GovCloud

1. Log in to [Anypoint GovCloud](https://gov.anypoint.mulesoft.com/).
2. Go to **Access Management → Connected Apps → Create App**.
3. Choose **Grant Type:** `Client Credentials`.
4. Add scopes:
   - `Design Center Developer`
   - `Exchange Contributor`
   - `Runtime Manager Deployer`
   - `CloudHub Admin`
5. Copy the **Client ID** and **Client Secret**.

---

## 🧰 Add Secrets to GitHub Repository

In **GitHub → Settings → Secrets and Variables → Actions**, add:

| Secret Name | Description |
|--------------|--------------|
| `ANYPOINT_CLIENT_ID` | Connected App Client ID |
| `ANYPOINT_CLIENT_SECRET` | Connected App Client Secret |
| `ANYPOINT_ENV` | Environment name (e.g., Sandbox, Prod) |
| `ANYPOINT_ORG_ID` | Organization ID |
| `ANYPOINT_BUSINESS_GROUP_ID` | Business Group ID |
| `ANYPOINT_PLATFORM_URL` | Usually `https://gov.anypoint.mulesoft.com` |

---

## ⚙️ Mule Maven Plugin Configuration (pom.xml)

```xml
<plugin>
  <groupId>org.mule.tools.maven</groupId>
  <artifactId>mule-maven-plugin</artifactId>
  <version>3.9.0</version>
  <configuration>
    <deploymentType>cloudHub</deploymentType>
    <cloudHubDeployment>
      <uri>${anypoint.platform.url}</uri>
      <muleVersion>4.5.2</muleVersion>
      <environment>${anypoint.env}</environment>
      <businessGroup>${anypoint.businessGroupId}</businessGroup>
      <applicationName>${project.artifactId}</applicationName>
      <workers>1</workers>
      <workerType>Micro</workerType>
    </cloudHubDeployment>
  </configuration>
</plugin>
```

---

## 🚀 GitHub Action Workflow

Create a file at `.github/workflows/mule-cicd.yml`:

```yaml
name: MuleSoft Multi-Env CI/CD (GovCloud)

on:
  push:
    branches: [ develop ]
  pull_request:
    types: [closed]
    branches: [ staging, master ]

jobs:
  build:
    name: 🏗️ Build Mule Application
    runs-on: ubuntu-latest
    if: github.event.pull_request.merged == true || github.ref == 'refs/heads/develop'

    steps:
      - name: Checkout Repository
        uses: actions/checkout@v4

      - name: Set up JDK 8
        uses: actions/setup-java@v4
        with:
          distribution: 'temurin'
          java-version: '8'

      - name: Cache Maven Dependencies
        uses: actions/cache@v4
        with:
          path: ~/.m2
          key: ${{ runner.os }}-maven-${{ hashFiles('**/pom.xml') }}
          restore-keys: |
            ${{ runner.os }}-maven-

      - name: Build Mule App
        run: mvn clean package -DskipTests

      - name: Upload Build Artifact
        uses: actions/upload-artifact@v4
        with:
          name: mule-app
          path: target/*.jar


  deploy:
    name: 🚀 Deploy to Anypoint GovCloud
    runs-on: ubuntu-latest
    needs: [build]
    if: github.event.pull_request.merged == true || github.ref == 'refs/heads/develop'
    environment: production

    steps:
      - name: Download Build Artifact
        uses: actions/download-artifact@v4
        with:
          name: mule-app

      - name: Set up JDK 8
        uses: actions/setup-java@v4
        with:
          distribution: 'temurin'
          java-version: '8'

      - name: Determine Target Environment
        id: envmap
        run: |
          # Determine target Mule environment based on branch or PR target
          if [[ "${GITHUB_REF##*/}" == "develop" ]]; then
            echo "env_name=Development" >> $GITHUB_OUTPUT
          elif [[ "${GITHUB_BASE_REF}" == "staging" ]]; then
            echo "env_name=Staging" >> $GITHUB_OUTPUT
          elif [[ "${GITHUB_BASE_REF}" == "master" ]]; then
            echo "env_name=Production" >> $GITHUB_OUTPUT
          else
            echo "Unknown environment for ${GITHUB_REF##*/}"
            exit 1
          fi

      - name: Deploy to MuleSoft GovCloud
        env:
          ANYPOINT_CLIENT_ID: ${{ secrets.ANYPOINT_CLIENT_ID }}
          ANYPOINT_CLIENT_SECRET: ${{ secrets.ANYPOINT_CLIENT_SECRET }}
          ANYPOINT_BUSINESS_GROUP_ID: ${{ secrets.ANYPOINT_BUSINESS_GROUP_ID }}
          ANYPOINT_PLATFORM_URL: ${{ secrets.ANYPOINT_PLATFORM_URL }}
          ANYPOINT_ENV: ${{ steps.envmap.outputs.env_name }}
        run: |
          echo "Deploying to $ANYPOINT_ENV environment..."
          mvn mule:deploy \
            -Danypoint.platform.clientId=${ANYPOINT_CLIENT_ID} \
            -Danypoint.platform.clientSecret=${ANYPOINT_CLIENT_SECRET} \
            -Danypoint.platform.url=${ANYPOINT_PLATFORM_URL} \
            -Danypoint.env=${ANYPOINT_ENV} \
            -Danypoint.businessGroup=${ANYPOINT_BUSINESS_GROUP_ID}
```

---

## ✅ Pipeline Overview

| Step | Description |
|------|--------------|
| Checkout | Clone the repo |
| Setup Java | Install JDK 8 |
| Cache Maven | Reuse local Maven packages |
| Build | Compile and package Mule app |
| Test | Run unit tests |
| Deploy | Deploy to Anypoint GovCloud |

---

## 🧭 Verify Deployment

1. Go to [Runtime Manager](https://gov.anypoint.mulesoft.com/runtime-manager/).
2. Check that the application has been deployed.
3. View logs under **Monitoring → Applications**.

---

## 🧪 Optional: Split Build and Deploy Workflows

You can create two workflows:
- **build.yml** – triggered on PR for testing
- **deploy.yml** – triggered on merge to `main` for controlled release

---

## 🏁 Summary

✅ End-to-end automated MuleSoft CI/CD pipeline on GitHub Actions  
🔒 Secure Connected App authentication (GovCloud compliant)  
🚀 Auto-deploys on push to `main` branch  
🧠 Ready for expansion into multi-env deployments (Dev → UAT → Prod)

---
