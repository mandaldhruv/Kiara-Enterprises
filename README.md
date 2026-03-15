# Kiara Enterprises - Premium Real Estate Portfolio 🏢✨

A modern, high-conversion website built for **Kiara Enterprises**, a premier real estate agency based in Vasai-Palghar, Maharashtra. Designed with a sophisticated "Executive Dark" theme, it caters to high-net-worth individuals, corporate clients, and NRIs seeking residential, commercial, and industrial properties.

![HTML5](https://img.shields.io/badge/html5-%23E34F26.svg?style=for-the-badge&logo=html5&logoColor=white)
![TailwindCSS](https://img.shields.io/badge/tailwindcss-%2338B2AC.svg?style=for-the-badge&logo=tailwind-css&logoColor=white)
![JavaScript](https://img.shields.io/badge/javascript-%23323330.svg?style=for-the-badge&logo=javascript&logoColor=%23F7DF1E)
![Google Apps Script](https://img.shields.io/badge/Google%20Apps%20Script-4285F4?style=for-the-badge&logo=google&logoColor=white)
![Firebase](https://img.shields.io/badge/firebase-%23039BE5.svg?style=for-the-badge&logo=firebase)
![License](https://img.shields.io/badge/License-Proprietary-red.svg?style=for-the-badge)

## 🌐 Live Demo
Experience the live production site here: **[kiaraenterprises.com](https://kiaraenterprises.com)**

---

## 🌟 Key Features

* **Direct Google Sheets Lead Generation:** Both the main contact form and the popup inquiry form submit leads *directly* to a secure Google Sheet using an AJAX `fetch` API. Features a seamless "Sending..." state and an inline success message without jarring page reloads.
* **Client Reviews Section:** A beautifully integrated, grid-aligned testimonials section featuring premium gold-accented styling and solid material-icon star ratings.
* **Dynamic Property Filtering:** Users can effortlessly filter the "Curated Properties" portfolio by categories (All, Apartments, Villas, Commercial) instantly using vanilla JavaScript.
* **Quick Inquiry Modal:** Clicking "Schedule Visit" or any specific property card triggers a centered, blurred-background inquiry modal that automatically captures the specific property the user is interested in.
* **Smart Scroll-Spy Navigation:** The fixed dark-glass navbar uses `getBoundingClientRect()` to perfectly highlight the currently viewed section as the user scrolls through the page.
* **Floating WhatsApp Integration:** A pulsing WhatsApp Floating Action Button (FAB) that routes the user to a pre-filled, URL-encoded inquiry chat.
* **Multi-Page Legal Architecture:** Seamless navigation between the main landing page and dedicated, uniformly styled `privacy.html` and `terms.html` legal pages.
* **Fully Responsive UI/UX:** Mobile-first design leveraging Tailwind CSS container queries and Flexbox, ensuring perfect scaling, stacked grids, and readable typography from mobile screens to 4K desktops.

## 🛠️ Technologies Used

* **Frontend:** HTML5, Tailwind CSS (via CDN for rapid utility-first styling).
* **Logic:** Vanilla JavaScript (ES6+). No heavy frontend frameworks required, ensuring lightning-fast load times.
* **Database / API:** Google Apps Script (`Code.gs`) acts as a serverless backend API to parse `POST` requests and append them as new rows in a private Google Sheet.
* **Hosting & Deployment:** Firebase Hosting, configured with clean URLs and mapped to a custom domain.
* **Typography & Iconography:** *Playfair Display* (serif), *Inter* (sans-serif), and Google Material Symbols.

## 🚀 Local Development & Deployment

Because this project relies on Tailwind CSS CDN and Vanilla JavaScript, local development requires no build tools.

**Local Setup:**
1. Clone the repository: `git clone https://github.com/mandaldhruv/Kiara-Enterprises.git`
2. Navigate to the `public/` directory and open `index.html` in your browser (or use VS Code Live Server).

**Firebase Deployment:**
To push updates to the live custom domain, ensure you have the Firebase CLI installed:
```bash
firebase deploy --only hosting
⚙️ Google Sheets Backend Configuration
The HTML forms use specific name attributes mapped to a Google Apps Script. To recreate the backend, use the following Code.gs structure:

JavaScript
function doPost(e) {
  try {
    var doc = SpreadsheetApp.getActiveSpreadsheet();
    var sheet = doc.getActiveSheet();
    var rowData = [];
    
    // Data pushes must map to HTML 'name' attributes
    rowData.push(new Date());                                     // Timestamp
    rowData.push(e.parameter.interest || "N/A");                  // Interest
    rowData.push(e.parameter.property_type || "N/A");             // Property Type
    rowData.push(e.parameter.name || "N/A");                      // Full Name
    rowData.push(e.parameter.phone || "N/A");                     // Phone Number
    rowData.push(e.parameter.message || "N/A");                   // Optional Message
    rowData.push(e.parameter.Inquired_Property || "General");     // Hidden Modal Field

    sheet.appendRow(rowData);
    
    return ContentService
      .createTextOutput(JSON.stringify({ "result": "success" }))
      .setMimeType(ContentService.MimeType.JSON);
      
  } catch(error) {
    return ContentService
      .createTextOutput(JSON.stringify({ "result": "error", "error": error.message }))
      .setMimeType(ContentService.MimeType.JSON);
  }
}
📁 File Structure
Plaintext
KiaraEnterprises/
├── public/
│   ├── kiara-logo/           # Brand assets (logo, favicon)
│   ├── index.html            # Main single-page application
│   ├── privacy.html          # Privacy Policy page
│   └── terms.html            # Terms of Service page
├── .firebaserc               # Firebase project target
├── .gitignore                # Git exclusion rules (cache/logs)
├── firebase.json             # Firebase hosting configuration
├── LICENSE                   # Proprietary Legal License
└── README.md                 # Project documentation
⚖️ License
© 2026 Dhruv Mandal / Kiara Enterprises. All Rights Reserved.

This repository and its contents are proprietary. No part of this repository may be reproduced, distributed, copied, modified, or transmitted in any form without prior written permission. See the LICENSE file for full details.

<p align="center">Crafted with 💛 by - <strong>Dhruv Mandal</strong> (O3GenAI IT Solutions)</p>
