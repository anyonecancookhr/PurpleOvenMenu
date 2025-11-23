# PurpleOvenMenu

Purple Oven Web App - Comprehensive Editing Guide

This document provides full instructions on how to modify the content of the purple_oven_app.html file. You can edit these values using any text editor (Notepad, TextEdit, VS Code, etc.).

1. How to Edit Menu Items (Products)

The list of cakes, pastries, and prices is stored in a variable called purpleOvenMenuData.

Steps to Edit:

Open purple_oven_app.html.

Search for const purpleOvenMenuData.

You will see a structure that looks like this:

const purpleOvenMenuData = [
    {
        category: "Cakes",
        subCategories: [
            {
                name: "Light Cakes (8 In)",
                items: [
                    { name: "Honeycomb Crunch Cake - Whole" },
                    { name: "Pistachio Stardust - Whole" }
                ]
            },
            // ... more categories
        ]
    }
];


Common Tasks:

Change a Product Name/Price/Unit:
Edit the text inside the quotes. Note that the unit (e.g., "Whole", "PC") is separated by a dash -.

Change: { name: "Honeycomb Crunch Cake - Whole" }

To: { name: "Honeycomb Crunch Cake - P1200" }

Add a New Item:
Add a new line inside the items bracket [...]. Ensure you add a comma , after the previous item.

items: [
    { name: "Existing Cake - Whole" },
    { name: "New Chocolate Cake - Whole" } // New Item
]


Remove an Item:
Simply delete the line containing the item you want to remove.

2. How to Edit Menu Images (The "See Menu" View)

The menu images displayed when clicking "See Our Menu" are controlled by the brands variable.

Search for const brands.

Look for the menuFiles line:

// Option A: Automatic numbering (0 to 9)
menuFiles: Array.from({ length: 10 }, (_, i) => `PO_Menu-images-${i}.jpg`)


To use specific filenames:

Replace the entire line with your list of filenames:

menuFiles: [
    "page1.jpg",
    "page2.jpg",
    "page3.jpg"
]


Note: Ensure these image files are saved in the exact same folder as the HTML file.

3. How to Edit Dropdown Menus (Locations & Time)

These options are found near the top of the <script> section.

A. Pick Up Locations

Search for const pickUpLocations. You can add, remove, or rename locations here.

const pickUpLocations = [
    'Temple Drive (QC)',
    'My New Branch (Makati)', // You can add new ones here
    'Alabang (MM)'
];


B. Time Slots

Search for const timeSlots. Currently, it uses a formula. To customize it manually, replace the existing code with a simple list:

const timeSlots = [
    "9:00 AM",
    "10:00 AM",
    "11:00 AM",
    "1:00 PM",
    "5:00 PM"
];


4. How to Edit Contact Information

To update the phone numbers or email address displayed in the footer and the "Call Us" section:

Email Address: Search for const ORDER_EMAIL.

const ORDER_EMAIL = "orderonline@purpleoven.com.ph";


Phone Numbers:

Search for the phone number itself in the code (e.g., 8631 4221) and replace the text.

Important: You must update both the display text (what the user sees) and the href="tel:..." link (what the phone dials).

Example:

<!-- Edit the number after tel: and the number in white text -->
<a href="tel:+63288889999">+632 8888 9999</a>
