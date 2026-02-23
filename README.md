# Kiara Enterprises - Premium Real Estate Portfolio 🏢✨

A modern, high-conversion, single-page website built for **Kiara Enterprises**, a premier real estate agency based in Vasai East, Palghar. Designed with a sophisticated "Executive Dark" theme, it caters to high-net-worth individuals, corporate clients, and NRIs seeking residential, commercial, and industrial properties.

## 🌟 Key Features

* **Premium UI/UX:** "Executive Dark" aesthetic utilizing Deep Charcoal backgrounds with Matte Gold (`#eccb13`) accents.
* **Parallax Hero Section:** Smooth, immersive background scrolling effect on the hero image.
* **Dynamic Scroll-Spy Navigation:** The navbar automatically updates to highlight the currently viewed section (Home, About, Projects, Services, Contact) and stays persistently highlighted.
* **Intersection Observer Animations:** An animated counter (`0` to `2021`, `50+`, `500+`) that triggers only when the user scrolls the Stats Strip into view.
* **Interactive Budget Slider:** A real-time JavaScript-powered range slider that updates Indian real estate pricing formats (e.g., ₹20L to ₹5Cr+) as the user drags the handle.
* **Working Contact Form:** Fully functional frontend form integrated with [FormSubmit](https://formsubmit.co/), sending leads directly to the configured email without needing a backend server.
* **Floating WhatsApp Integration:** A pulsing WhatsApp Floating Action Button (FAB) that opens the user's app with a pre-filled, URL-encoded inquiry message.
* **Custom Map Experience:** A sleek, grayscale Google Maps iframe wrapped in an interactive overlay that redirects users to Google Maps for exact directions on click.
* **Fully Responsive:** Mobile-first design leveraging Tailwind CSS container queries and flexbox/grid layouts.

## 🛠️ Technologies Used

* **HTML5:** Semantic and accessible structure.
* **Tailwind CSS (via CDN):** Rapid, utility-first styling with custom theme configuration in the `<head>`.
* **Vanilla JavaScript:** Lightweight DOM manipulation for the mobile menu, scroll spy, dynamic slider, parallax, and counter animations (No heavy frameworks like React/jQuery).
* **Google Fonts:** *Playfair Display* (elegant serif for headings) and *Inter* (clean sans-serif for body text).
* **Google Material Symbols:** Scalable, lightweight vector icons.

## 🚀 Setup & Installation

Because this project uses the Tailwind CSS CDN and Vanilla JS, there is no build process or `npm install` required!

1.  **Clone or Download** the repository.
2.  Open the project folder.
3.  Double-click `index.html` to open it in your default web browser.

## ⚙️ Configuration & Customization

If you need to update business details in the future, here is where to look in the `index.html` code:

* **Email Forwarding (FormSubmit):**
    Locate the `<form action="https://formsubmit.co/YOUR_EMAIL_HERE" ...>` tag in the Contact section and replace the email with your desired receiving address. *(Note: You will need to confirm the email address once via FormSubmit on the very first submission).*
* **WhatsApp Number & Message:**
    Locate the floating `<a>` tag at the bottom of the HTML (`<a href="https://wa.me/917977651751?text=..." ...>`). Change the phone number (keep the country code) or alter the URL-encoded text.
* **Direct Call Button:**
    Locate the "Contact Us" button in the Hero section (`href="tel:+917977651751"`) to update the phone dialer link.
* **Google Maps Link:**
    Locate the map container in the Contact section and update the `href` on the overlay `<a>` tag to your specific Google Maps share link.

## 📁 File Structure

```text
├── index.html       # The main single-page application containing all HTML, Tailwind config, and JS scripts
└── README.md        # Project documentation
📝 License
© 2026 Kiara Enterprises. All rights reserved. Design and code strictly for the Kiara Enterprises brand.
