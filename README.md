# Kiara Enterprises - Premium Real Estate Portfolio 🏢✨

A modern, high-conversion, single-page website built for **Kiara Enterprises**, a premier real estate agency based in Vasai-Palghar, Maharashtra. Designed with a sophisticated "Executive Dark" theme, it caters to high-net-worth individuals, corporate clients, and NRIs seeking residential, commercial, and industrial properties.

![HTML5](https://img.shields.io/badge/html5-%23E34F26.svg?style=for-the-badge&logo=html5&logoColor=white)
![TailwindCSS](https://img.shields.io/badge/tailwindcss-%2338B2AC.svg?style=for-the-badge&logo=tailwind-css&logoColor=white)
![JavaScript](https://img.shields.io/badge/javascript-%23323330.svg?style=for-the-badge&logo=javascript&logoColor=%23F7DF1E)
![Google Apps Script](https://img.shields.io/badge/Google%20Apps%20Script-4285F4?style=for-the-badge&logo=google&logoColor=white)

## 🌟 Key Features

* **Direct Google Sheets Lead Generation:** Both the main contact form and the popup inquiry form submit leads *directly* to a Google Sheet using an AJAX `fetch` API. Features a seamless "Sending..." state and a clean, inline green success message without jarring page reloads or browser alerts.
* **Dynamic Property Filtering:** Users can filter the "Curated Properties" section by categories (All, Apartments, Villas, Commercial) instantly using vanilla JavaScript.
* **Quick Inquiry Modal:** Clicking "Schedule Visit" or any specific property card opens a centered, blurred-background inquiry modal that automatically captures the specific property the user is interested in.
* **Scroll-Spy Navigation:** The fixed dark-glass navbar automatically highlights the currently viewed section as the user scrolls down the page.
* **Intersection Observer Animations:** An animated stats counter triggers precisely when the user scrolls the "About" section into view.
* **Floating WhatsApp Integration:** A pulsing WhatsApp Floating Action Button (FAB) that opens the user's app with a pre-filled, URL-encoded inquiry message.
* **Custom Map Experience:** A sleek, grayscale Google Maps iframe wrapped in an interactive overlay that redirects users directly to Google Maps for exact directions on click.
* **Fully Responsive UI/UX:** Mobile-first design leveraging Tailwind CSS container queries, ensuring perfect scaling and grid adjustments from mobile phones to 4K desktops.

## 🛠️ Technologies Used

* **HTML5:** Semantic and accessible structure.
* **Tailwind CSS (via CDN):** Rapid, utility-first styling with a custom configuration inside the `<head>` for specific brand colors (Matte Gold `#eccb13` and Deep Charcoal `#121212`).
* **Vanilla JavaScript:** Lightweight DOM manipulation for the mobile menu, scroll spy, filtering, modal logic, and AJAX form submissions. No heavy frontend frameworks required.
* **Google Apps Script:** Acts as the backend API to parse POST requests from the website and append them as new rows in a private Google Sheet.
* **Google Fonts & Material Symbols:** *Playfair Display* (elegant serif), *Inter* (clean sans-serif), and scalable vector icons.

## 🚀 Setup & Installation

Because this project uses the Tailwind CSS CDN and Vanilla JavaScript, there is no build process or `npm install` required!

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/mandaldhruv/Kiara-Enterprises.git](https://github.com/mandaldhruv/Kiara-Enterprises.git)
Open the project folder.

Run the site: Double-click index.html inside the public/ folder to open it in your default web browser, or use a tool like VS Code Live Server for a better development experience.

⚙️ Google Sheets Backend Configuration
This website is hardcoded to send leads to a Google Sheet. If you need to recreate or modify the backend, here is how the data maps.

The HTML forms use the following name attributes, which must be handled by your Code.gs Google Apps Script:

interest (Buying, Renting, etc.)

property_type (Apartment, Villa, etc.)

name (Full Name)

phone (Phone Number)

message (Optional Message)

Inquired_Property (Hidden field capturing the specific property clicked via the modal)

Required Google Apps Script (Code.gs):

JavaScript
function doPost(e) {
  try {
    var doc = SpreadsheetApp.getActiveSpreadsheet();
    var sheet = doc.getActiveSheet();
    var rowData = [];
    
    // Push the data exactly matching the HTML form names
    rowData.push(new Date());                                     
    rowData.push(e.parameter.interest || "N/A");                  
    rowData.push(e.parameter.property_type || "N/A");             
    rowData.push(e.parameter.name || "N/A");                      
    rowData.push(e.parameter.phone || "N/A");                     
    rowData.push(e.parameter.message || "N/A");                   

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
├── public/
│   ├── index.html            # Main application file
│   └── kiara-logo/           # Brand assets (logo, favicon)
└── README.md                 # Project documentation
<div align="center">
<p>Crafted with 💛 by - <strong>Dhruv Mandal</strong></p>
</div>
