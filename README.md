# PurpleOvenMenu

Purple Oven Web App - Menu Editing Guide

This guide explains how to update the product menu in the index.html file. The menu data is stored in a JavaScript structure, allowing you to easily add categories, subcategories, and individual items.

Purple Oven App: Maintenance Guide

This guide explains how to easily update the prices and images in your Purple Oven web application. All of these changes happen within the index.html file.

PART 1: Updating Prices

All the items and their prices are stored in JavaScript arrays inside the <script> tag, starting around line 170.

1. Standard Menu Items

Look for the const purpleOvenMenuData = [ section. This contains the categories (Cakes, Bars, Cookies, etc.).

To change a price:

Search (Ctrl+F or Cmd+F) for the name of the item, e.g., "Classic Sans Rival".

You will see a line like this:
{ name: "Classic Sans Rival - whole", price: 1230 }

Simply change the number next to price:. Do not add commas or currency symbols.

Correct: price: 1300

Incorrect: price: "1,300" or price: ₱1300

2. Assorted Boxes (Base Price)

Inside purpleOvenMenuData, assorted boxes have an extra type attribute.
Example:
{ name: "Assorted Little Cakes/Pies - box of 6", price: 1320, type: "assorted_box_6" }

Change the price: 1320 to update the base/minimum price of the box.

3. Items inside Assorted Dropdowns (Assorted Pools)

The individual items inside the assorted dropdowns get their prices from two specific lists located right above purpleOvenMenuData:

const assortedPool = [...] (For Little Cakes & Pies)

const cookiePool = [...] (For Cookies)

To update pool prices:
Find the pool and change the price number.

const assortedPool = [
    { name: "Little Carrot Cake", price: 220 }, // Change 220 to your new price
    // ...
];


PART 2: Updating Menu Images

The app currently displays a gallery of menu images when the user clicks "See Our Menu".

How the current setup works

If you scroll down to the function renderMenu() (around line 348), you will see this line of code:

const menuFiles = Array.from({ length: 10 }, (_, i) => `PO_Menu-images-${i}.jpg`);


This automatically looks for 10 images named sequentially in the same folder as your website:

PO_Menu-images-0.jpg

PO_Menu-images-1.jpg
...all the way to PO_Menu-images-9.jpg.

Option A: The Easiest Way (Replace the files)

If you want to update the menu images without touching the code:

Save your new menu images as .jpg.

Name them exactly PO_Menu-images-0.jpg, PO_Menu-images-1.jpg, etc.

Upload and replace the old files in your web hosting folder.

Option B: Change the code for new filenames

If you have new images with different names (e.g., menu_page1.png, menu_page2.png), you can change the code to explicitly list your new files.

Change this:

const menuFiles = Array.from({ length: 10 }, (_, i) => `PO_Menu-images-${i}.jpg`);


To a manual list like this:

const menuFiles = [
    "menu_page1.png",
    "menu_page2.png",
    "promo_banner.jpg"
];


(Make sure to put quotes around each filename and separate them with a comma).

💡 Important Tips for Coding:

Always keep a backup of index.html before making changes. If you accidentally delete a comma or a bracket }, the menu might stop loading.

No Commas in Prices: Javascript needs raw numbers for math (e.g., 1200 not 1,200).

Clear your Cache: After updating the code or images, remember to clear your browser cache (or open an Incognito window) to see the changes applied immediately.
