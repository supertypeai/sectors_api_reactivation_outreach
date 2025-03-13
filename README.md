# sectors_api_reactivation_outreach

This repository contains a GitHub Actions workflow that triggers the Sectors API reactivation outreach endpoint. The workflow is designed to run daily and securely call the API to send reactivation emails to inactive users based on the configured outreach schedule.

## Overview

The GitHub Action in this repository uses cURL to trigger the reactivation endpoint of your Sectors API. It is built to:
- Run on a daily schedule.
- Securely use secrets (such as `ACTION_SECRET_KEY`) to call the API.
- Help automate the process of sending reactivation emails to inactive users.

## Setup

### 1. Repository Secrets

Before using the workflow, add the following secrets to your GitHub repository:

- **ACTION_SECRET_KEY:**  
  The secret key that the API endpoint expects to authenticate the request.


To add a secret:
1. Navigate to your GitHub repository.
2. Click on **Settings**.
3. Go to **Secrets and variables** > **Actions**.
4. Click **New repository secret** and add the secret name and value.

### 2. Workflow File

The workflow file is located at `.github/workflows/email_reactivation.yml`. It is configured to run daily via a cron job and can also be manually triggered.

## Workflow Details

The workflow performs the following steps:
1. Checks out the repository.
2. Uses `curl` to send a POST request to the reactivation API endpoint.
3. Includes the secret `ACTION_SECRET_KEY` in the header for secure access.
