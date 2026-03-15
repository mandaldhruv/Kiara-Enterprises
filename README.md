Kiara Enterprises - Premium Real Estate Portfolio 🏢✨

A modern, high-conversion website built for Kiara Enterprises, a premier real estate agency based in Vasai–Palghar, Maharashtra.

The site uses a sophisticated Executive Dark UI designed for high-net-worth clients, corporate buyers, and NRIs searching for premium residential, commercial, and industrial properties.

🌐 Live Demo

Experience the live production site:

https://kiaraenterprises.com

🛠 Tech Stack












🌟 Key Features
Direct Google Sheets Lead Generation

Contact forms send leads directly to Google Sheets

Uses AJAX fetch() API

Includes loading state ("Sending…")

Displays success message without page reload

Client Reviews Section

Elegant testimonial layout

Premium gold accent styling

Material icon star ratings

Dynamic Property Filtering

Users can instantly filter property listings by:

Apartments

Villas

Commercial

All properties

Implemented using Vanilla JavaScript for fast performance.

Quick Inquiry Modal

Clicking Schedule Visit opens a blur-background modal that automatically captures the selected property name.

Smart Scroll-Spy Navigation

Navbar automatically highlights the current section while scrolling using:

getBoundingClientRect()
Floating WhatsApp Integration

A pulsing WhatsApp Floating Action Button allows users to send a pre-filled inquiry message.

Multi-Page Legal Architecture

Includes dedicated pages:

Privacy Policy

Terms of Service

All pages maintain consistent styling and navigation.

Fully Responsive Design

Mobile-first layout built using Tailwind CSS:

Fluid containers

Flexible grids

Optimized typography

Works from mobile screens to 4K displays

🚀 Local Development

This project requires no build tools.

Tailwind CSS is loaded via CDN, and the site uses Vanilla JavaScript.

Clone the repository
git clone https://github.com/mandaldhruv/Kiara-Enterprises.git
Open the project

Navigate to:

public/index.html

Open it in your browser or run VS Code Live Server.

🚀 Deployment (Firebase Hosting)

Install Firebase CLI:

npm install -g firebase-tools

Login to Firebase:

firebase login

Deploy the project:

firebase deploy --only hosting
⚙️ Google Sheets Backend Configuration

Forms send data to a Google Apps Script Web App that writes leads to a spreadsheet.

Example Code.gs:

function doPost(e) {
  try {
    var doc = SpreadsheetApp.getActiveSpreadsheet();
    var sheet = doc.getActiveSheet();
    var rowData = [];

    rowData.push(new Date());                                 // Timestamp
    rowData.push(e.parameter.interest || "N/A");               // Interest
    rowData.push(e.parameter.property_type || "N/A");          // Property Type
    rowData.push(e.parameter.name || "N/A");                   // Name
    rowData.push(e.parameter.phone || "N/A");                  // Phone
    rowData.push(e.parameter.message || "N/A");                // Message
    rowData.push(e.parameter.Inquired_Property || "General");  // Property

    sheet.appendRow(rowData);

    return ContentService
      .createTextOutput(JSON.stringify({result: "success"}))
      .setMimeType(ContentService.MimeType.JSON);

  } catch(error) {
    return ContentService
      .createTextOutput(JSON.stringify({
        result: "error",
        error: error.message
      }))
      .setMimeType(ContentService.MimeType.JSON);
  }
}
📁 Project Structure
KiaraEnterprises/
│
├── public/
│   ├── kiara-logo/        # Brand assets
│   ├── index.html         # Main website
│   ├── privacy.html       # Privacy policy
│   └── terms.html         # Terms of service
│
├── .firebaserc            # Firebase project config
├── .gitignore             # Git exclusions
├── firebase.json          # Hosting configuration
├── LICENSE                # Proprietary license
└── README.md              # Documentation
⚖️ License

© 2026 Dhruv Mandal / Kiara Enterprises

All Rights Reserved.

This repository and its contents are proprietary. No part of this repository may be copied, modified, distributed, or reused without prior written permission.

See the LICENSE file for full details.

<p align="center"> Crafted with 💛 by <strong>Dhruv Mandal</strong><br> O3GenAI IT Solutions </p>
