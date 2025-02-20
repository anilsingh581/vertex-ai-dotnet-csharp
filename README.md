# Vertex AI Setup in C#

This repository provides a guide to set up and use Google Cloud's Vertex AI in a C# project. Follow the steps below to configure your environment and integrate Vertex AI functionality.

## Prerequisites

Before you begin, ensure you have the following:

1. **Google Cloud Account**: An active Google Cloud account is required.
2. **Project**: Create a project in the [Google Cloud Console](https://console.cloud.google.com/) (e.g., `ocrai-selfbill`).
3. **Billing**: Enable billing for your Google Cloud project.
4. **Visual Studio**: Install any recent version (e.g., 2019 or 2022) with the .NET workload.

---

## Step 1: Enable Vertex AI API

1. Navigate to the [Google Cloud Console](https://console.cloud.google.com/).
2. Select your project (e.g., `ocrai-selfbill`).
3. Go to **APIs & Services** > **Library**.
4. Search for **Vertex AI API**.
5. Click **Enable** to activate the API for your project.

---

## Step 2: Set Up Authentication

Vertex AI requires authentication via a service account. Follow these steps:

### 1. Create a Service Account
- In the Google Cloud Console, go to **IAM & Admin** > **Service Accounts**.
- Click **Create Service Account**.
- Name it (e.g., `vertex-ai-service-account`).
- Grant it the **Vertex AI User** role (or a custom role with appropriate permissions).
- Click **Create and Continue**, then **Done**.

### 2. Generate a Key
- From the Service Accounts list, click on your new service account.
- Go to the **Keys** tab, then click **Add Key** > **Create New Key**.
- Select **JSON** as the key type and download the file (e.g., `ocrai-selfbill-123456789.json`).

### 3. Set Environment Variable
- Place the JSON key file in a secure location on your machine.
- Set the `GOOGLE_APPLICATION_CREDENTIALS` environment variable to point to this file:

  **Windows:**
  ```cmd
  set GOOGLE_APPLICATION_CREDENTIALS=C:\path\to\your\service-account-key.json

  
