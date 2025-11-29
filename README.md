# PurpleOvenMenu

Purple Oven Web App - Menu Editing Guide

This guide explains how to update the product menu in the index.html file. The menu data is stored in a JavaScript structure, allowing you to easily add categories, subcategories, and individual items.

📍 Where to Edit

Open index.html in a text editor (VS Code, Notepad++, etc.).

Scroll down to the <script> section at the bottom.

Look for the variable constant named purpleOvenMenuData.

It looks like this:

const purpleOvenMenuData = [
    {
        category: "Cakes",
        subCategories: [ ... ]
    },
    // ...
];


1. How to Add a New Item

Items are listed inside the items array of a specific subcategory.

Syntax: { name: "Product Name - Unit" }

Example:
To add a "New Chocolate Cake" to an existing list:

items: [
    { name: "Existing Cake - whole" }, 
    { name: "New Chocolate Cake - whole" } // <--- Add this line (don't forget the comma above!)
]


Note: The text after the hyphen - (e.g., whole, pc, box) is automatically styled as the "unit" in the order form.

2. How to Add a Subcategory

Subcategories are groups within a main Category (e.g., "Cheesecakes" inside "Cakes").

Find the subCategories array of the parent Category.

Add a new object with name and items.

Example:

subCategories: [
    {
        name: "Existing Subcategory",
        items: [ ... ]
    }, 
    // New Subcategory Block
    {
        name: "New Delicious Section (8 In)",
        items: [
            { name: "New Item A - pc" },
            { name: "New Item B - pc" }
        ]
    }
]


3. How to Add a Main Category

To add a completely new section (like "Drinks" or "Merchandise"), add a new object to the main purpleOvenMenuData array.

Example:

const purpleOvenMenuData = [
    // ... existing categories ...
    
    {
        category: "New Category Name",
        subCategories: [
            {
                name: "Optional Subheader", 
                items: [
                    { name: "New Product - pc" }
                ]
            }
        ]
    }
];


4. Advanced Layout: Collapsible vs. Flat

The app displays categories in two ways:

Nested (Standard): Clicking the Category reveals Subcategory folders. (Used for "Cakes", "Bread and Pastries").

Flattened: Clicking the Category immediately shows the items (No subcategory folders). (Used for "Bars", "Cookies").

To control this, look for the categoriesToFlatten array in the code:

const categoriesToFlatten = ["Bars", "Cookies", "Loaves", "Snack Packs", "Reusable Bag"];


To make a category flat: Add its name to this list. Ensure the subcategory name in your data is empty "".

To make a category nested: Remove its name from this list.

⚠️ Important Syntax Tips

Commas: Always put a comma , after an item or bracket } if there is another one following it.

Quotes: Always use double quotes "" or single quotes '' around text.

Backups: Before editing, save a backup copy of your .html file just in case!
