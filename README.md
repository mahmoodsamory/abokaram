# Captin Gate Admin Access Control

Captin Gate Admin Access Control is an internal administration tool used to manage access to the Captin Gate rider portal.

The tool allows an authorized administrator to switch the connected rider portal between private access and public link access. It is built with Google Apps Script and uses the Google Apps Script API to update the deployment settings of the rider portal.

## What this app does

This app is used to:

- Check the current access status of the rider portal deployment.
- Change the rider portal web app access setting.
- Create a new Apps Script project version after a deployment setting change.
- Update the target rider portal deployment to use the new version.

## What this app does not do

This admin app does not:

- Read Gmail.
- Send emails.
- Access Google Drive files.
- Access payment information.
- Access personal files outside the configured Apps Script project.
- Sell or share user data.
- Read rider spreadsheet data directly.

The rider portal itself is a separate Apps Script project.

## Google OAuth scopes used

This admin app requests the following Google OAuth scopes:

### `https://www.googleapis.com/auth/script.scriptapp`

Used so the Apps Script project can obtain an OAuth token for the current authorized administrator.

### `https://www.googleapis.com/auth/script.external_request`

Used to call the Google Apps Script API through `UrlFetchApp`.

### `https://www.googleapis.com/auth/script.projects`

Used to read and update the target Apps Script project content, including the project manifest, and to create new project versions.

### `https://www.googleapis.com/auth/script.deployments`

Used to read and update the target rider portal deployment.

## Why these permissions are required

The app needs these permissions only to manage the deployment configuration of the connected rider portal Apps Script project.

The app changes deployment access settings such as:

- Private access
- Anyone with the link / public access
- Deployment version used by the web app

## Data handling

This app only processes configuration data related to the Apps Script deployment that it manages.

The app may process:

- Apps Script project ID
- Deployment ID
- Deployment access status
- Deployment version number
- Deployment description
- Administrator action timestamp

This app does not store user passwords in an external database.

## Privacy Policy

Privacy Policy: [PRIVACY.md](./PRIVACY.md)

## Terms of Service

Terms of Service: [TERMS.md](./TERMS.md)

## Contact

For support or questions, contact:

**Support Email:** your-email@example.com

## App owner

**Organization:** شركة ابشر بعلامة الفهد  
**App Name:** Captin Gate Admin Access Control

## Security note

This administration tool is intended only for authorized administrators. The public rider portal should remain in a separate Apps Script project from this admin control panel.
