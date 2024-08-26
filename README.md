### Harvest Billing Widget Developer Guide

---

# Harvest Billing Widget Developer Guide

This guide provides developers with detailed instructions on how to integrate, customize, and publicly deploy the **Harvest Billing Widget** for Azure DevOps dashboards. The widget utilizes the Azure DevOps SDK and Harvest API to visually represent billable, non-billable, and R&D hours in a customizable chart. All source code and project details can be found in the [EirEvo/AzureDevOpsExtensions GitHub repository](https://github.com/EirEvo/AzureDevOpsExtensions).

## Table of Contents

- [Overview](#overview)
- [Prerequisites](#prerequisites)
- [Project Structure](#project-structure)
- [Setting Up Your Development Environment](#setting-up-your-development-environment)
- [Modifying the vss-extension.json File](#modifying-the-vss-extensionjson-file)
- [Building and Packaging the Widget](#building-and-packaging-the-widget)
- [Deploying to Azure DevOps](#deploying-to-azure-devops)
- [Making the Widget Public](#making-the-widget-public)
- [Creating a Publisher](#creating-a-publisher)
- [Contributing](#contributing)

## Overview

The Harvest Billing Widget is a versatile tool designed to be integrated into Azure DevOps dashboards to display time tracking data such as billable, non-billable, and R&D hours using the Harvest API. This guide will help you set up, customize, and deploy the widget, making it available on the Azure DevOps Marketplace.

## Prerequisites

Ensure you have the following installed and configured before starting:

- **Node.js** (v14 or later)
- **npm** (v6 or later)
- **Azure DevOps Account** with necessary permissions
- **Harvest Account** with API access
- **Visual Studio Code** or your preferred IDE
- **Azure DevOps Extension Tools (tfx-cli)**

  Install the Azure DevOps Extension Tools globally via npm:

  ```bash
  npm install -g tfx-cli

Project Structure
The widget project is structured as follows:

bash
Copy code
harvest-billing-widget/
│
├── docs/                         # Documentation and images
├── img/                          # Widget images (e.g., logo, preview)
├── scripts/                      # Custom JavaScript files for the widget
│   └── widget-configuration.js   # Handles widget configuration logic
├── sdk/                          # Azure DevOps SDK scripts
│   └── scripts/
│       ├── VSS.SDK.js            # Azure DevOps SDK
│       └── VSS.SDK.min.js        # Minified Azure DevOps SDK
├── widget.html                   # Main widget HTML file
├── widget-configuration.html     # Configuration HTML file
├── package.json                  # Node.js project file with dependencies
├── README.md                     # Project readme
└── vss-extension.json            # Azure DevOps extension manifest
Setting Up Your Development Environment
1. Clone the Repository
Start by cloning the repository to your local machine:

bash
Copy code
git clone https://github.com/EirEvo/AzureDevOpsExtensions.git
cd AzureDevOpsExtensions
2. Install Dependencies
Install the necessary Node.js dependencies:

bash
Copy code
npm install
3. Launch the Local Development Server
Use tools like http-server to serve the HTML files locally for testing:

bash
Copy code
npx http-server
Visit http://localhost:8080 to view the widget in your browser.

Modifying the vss-extension.json File
The vss-extension.json file is the core configuration file for your Azure DevOps extension. It defines the widget's metadata, including its ID, version, categories, and the resources it uses.

Key Modifications Required:
Publisher ID:

Replace the "publisher": "EirEvo-EvoLabs" with your own publisher ID.

Example:

json
Copy code
"publisher": "YourPublisherID",
Version:

Set the version to reflect your extension's versioning strategy.

Example:

json
Copy code
"version": "1.0.1",
Categories:

Ensure the "categories" field includes "Azure Boards" to make your widget compatible with Azure DevOps dashboards.

Example:

json
Copy code
"categories": ["Azure Boards"],
Gallery Flags:

To make the widget public, add the following "galleryFlags" field:

json
Copy code
"galleryFlags": [
  "Preview",
  "Public"
],
Resource Paths:

Ensure all paths to resources (e.g., images, scripts) are correctly defined. This includes the logo, preview image, and the SDK script.

Example for icons:

json
Copy code
"icons": {
  "default": "img/logo.png"
}
Widget Sizes:

Define the supported sizes for the widget in the "supportedSizes" field to ensure proper display on the dashboard.

Example:

json
Copy code
"supportedSizes": [
  { "rowSpan": 2, "columnSpan": 2 },
  { "rowSpan": 2, "columnSpan": 3 },
  { "rowSpan": 3, "columnSpan": 2 },
  { "rowSpan": 3, "columnSpan": 3 }
],
SDK Reference:

Ensure the Azure DevOps SDK script is correctly referenced in the vss-extension.json file:

json
Copy code
{
  "path": "sdk/scripts/VSS.SDK.min.js",
  "addressable": true
}
