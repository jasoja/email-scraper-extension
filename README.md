## Email Scraper Chrome Extension

### Description:
This Chrome extension allows users to extract email addresses from any webpage they visit.

### Components:

1. **Popup UI**: 
   - Provides a simple popup UI with a single button labeled "Scrape Email" and a list below it to display the extracted email addresses.

2. **Content Script**: 
   - Injects a content script into the currently active tab.
   - Parses the HTML content of the page using a regular expression to extract email addresses.

3. **Message Passing**: 
   - Enables communication between the content script and the popup script using Chrome's messaging API.
   - Sends the extracted email addresses back to the popup script.

4. **Popup Script**: 
   - Listens for clicks on the "Scrape Email" button.
   - Queries the active tab to get its ID and executes the content script to extract email addresses from that page.

5. **Manifest File (`manifest.json`)**: 
   - Defines the metadata and permissions for the extension, including the name, description, version, popup HTML file, and required permissions (such as accessing active tabs and executing scripts).

### Usage:
1. Install the extension in Chrome.
2. Click on the extension icon to open the popup.
3. Click on the "Scrape Email" button to extract email addresses from the currently active webpage.

### Manifest File (`manifest.json`):
```json
{
  "manifest_version": 3,
  "name": "Email Scraper",
  "description": "Scrape emails from any webpage",
  "version": "1.0",
  "action" : {
    "default_popup": "popup.html"
  },
  "permissions": ["activeTab", "scripting"]
}
