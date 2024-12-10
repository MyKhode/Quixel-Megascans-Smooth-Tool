![image](https://github.com/user-attachments/assets/a37d0b80-0715-4f77-bb8a-8319f9dc9173)

# Human Mimicking Script for Asset Handling

This script is designed to interact with an API to acquire assets by adding them to your account. It mimics human behavior by introducing randomized delays between requests to avoid triggering anti-bot protections.

## Features

- **Acquiring Assets**: The script adds non-acquired assets to your account.
- **Human-like Delays**: It introduces random delays between 0.5 to 1 second between requests, with a slight progressive delay for each page to avoid detection.
- **Error Handling**: In case of failed requests, it logs errors and continues execution.
- **Auth Token Validation**: The script checks for a valid authentication token stored in cookies.

## Setup

1. **Prerequisites**:
   - A valid authentication token.
   - Ensure you're logged in and the `auth` cookie is available.

2. **Install Dependencies**:
   - There are no external dependencies. The script uses `fetch()` and other native browser methods.

3. **Usage**:
   - Open the script in your browser's developer console.
   - The script will check if you're authenticated and begin fetching items, mimicking human behavior by waiting for random durations between requests.
   - You can specify the starting page and whether to clear the console after each page with the `startPage` and `autoClearConsole` parameters.

4. **Execution**:
   - The script loops through multiple pages of assets and attempts to add non-acquired assets to your account.
   - The delay between requests is randomized between 0.5s and 1s, with slight progression for each page.

## Configuration

You can customize the following options:

- **startPage** (default: 7231): The starting page index to begin adding assets from.
- **autoClearConsole** (default: `true`): Whether to clear the console after each page.

## Code Explanation

- **getCookie(name)**: This function retrieves the value of the specified cookie.
- **callCacheApi(params)**: This function interacts with the cache API to fetch asset data.
- **callAcl({ id, name })**: This function adds an asset to the account by sending a POST request to the ACL API.
- **callAcquired()**: This function fetches the list of assets already acquired.
- **Delay Logic**: The delay between requests is randomly calculated between 500ms and 1000ms, with a slight progressive increase for each page processed.

## Example Usage

```javascript
(async (startPage = 7231, autoClearConsole = true) => {
  // Your script here
})();
