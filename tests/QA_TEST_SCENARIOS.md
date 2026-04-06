# QA Test Scenarios - Shoplane E-Commerce Website

## Project Overview
Shoplane is a responsive e-commerce website that sells clothing and accessories. The application features product browsing, shopping cart functionality, and a checkout process with data persistence using localStorage.

---

## Test Scenarios

### **TS-001: Product Catalog Load and Display**
**Objective:** Verify that all products are loaded correctly from the API and displayed on the home page.

**Steps:**
1. Launch the homepage (index.html)
2. Wait for product data to load from the API endpoint
3. Verify both "Clothing" and "Accessories" sections are populated with product cards
4. Verify each product card displays: product image, name, brand, and price
5. Verify product count matches API response

**Expected Result:** All products load without errors, product cards display complete information, and page layout is responsive across devices (desktop, tablet, mobile).

---

### **TS-002: Banner Carousel Functionality**
**Objective:** Verify the product banner carousel auto-plays and navigation works correctly.

**Steps:**
1. Load the homepage and wait for page to fully render
2. Observe the banner carousel at the top of the page
3. Verify the carousel auto-plays (slides change every 2 seconds)
4. Verify navigation dots are visible at the bottom of the carousel
5. Click on different navigation dots to manually switch slides
6. Verify carousel loops infinitely

**Expected Result:** Carousel slides automatically, manual navigation via dots works, smooth transitions occur, and carousel loops without errors.

---

### **TS-003: Navigation and Menu Toggle (Responsive)**
**Objective:** Verify the responsive navbar works correctly on different screen sizes.

**Steps:**
1. Load the homepage on desktop view (1920x1080)
2. Verify menu items "Home", "Clothings", and "Accessories" are visible
3. Resize browser to mobile view (375x667)
4. Verify the burger menu icon appears
5. Click the burger icon to toggle the menu
6. Verify the menu expands and all navigation links are clickable
7. Click a navigation link and verify it navigates correctly
8. Resize back to desktop and verify burger menu disappears

**Expected Result:** Menu displays correctly based on screen size, burger menu toggle works without lag, navigation links function properly on all screen sizes.

---

### **TS-004: Product Details Page Navigation**
**Objective:** Verify that clicking a product navigates to the product detail page with correct product information.

**Steps:**
1. Open the homepage and wait for products to load
2. Click on any product card (image or details area)
3. Verify the URL changes to "product.html?product_id=[id]"
4. Verify the product detail page loads successfully
5. Verify the product details (name, brand, price, image) match the clicked product
6. Verify the "Add to Cart" button is present and visible

**Expected Result:** Product detail page loads with correct product information, URL parameter is passed correctly, and all product details match the product card clicked.

---

### **TS-005: Add to Cart and Cart Count Update**
**Objective:** Verify that adding products to cart updates the cart count and stores data in localStorage.

**Steps:**
1. Navigate to a product detail page
2. Note the initial cart count (should be 0 or previous count)
3. Click "Add to Cart" button
4. Verify the cart count increases by 1
5. Verify the cart count updates in localStorage ("cart-count")
6. Add the same product multiple times
7. Verify the count increments correctly
8. Refresh the page and verify cart count persists

**Expected Result:** Cart count updates immediately, localStorage reflects correct cart-count and product-list data, cart persists after page refresh.

---

### **TS-006: Checkout Page with Multiple Items**
**Objective:** Verify the checkout page displays all cart items correctly with accurate calculations.

**Steps:**
1. Add 3-4 different products to cart from the product pages
2. Vary the quantity of items added (add some products multiple times)
3. Navigate to the checkout page (checkout.html)
4. Verify all added items are displayed with correct product details
5. Verify the product count (quantity "x#") is displayed correctly for each item
6. Verify the per-item amount is calculated correctly (quantity × price)
7. Verify the total amount is calculated correctly (sum of all items)

**Expected Result:** All items display correctly, individual item amounts are accurate, total amount matches the sum of all items, no calculation errors occur.

---

### **TS-007: Place Order and Cart Clearing**
**Objective:** Verify that placing an order clears the cart and navigates to order confirmation.

**Steps:**
1. Add products to cart and navigate to checkout page
2. Verify cart items are displayed
3. Click the "Place Order" button
4. Verify the page navigates to the order confirmation page (orderconfirm.html)
5. Return to the homepage
6. Verify the cart count has been reset to 0
7. Verify localStorage "product-list" has been cleared
8. Verify localStorage "cart-count" is set to 0

**Expected Result:** Order placement triggers cart clearing, cart count resets to 0, localStorage is cleared of cart items, order confirmation page displays, and cart remains empty after refresh.

---

### **TS-008: Responsive Design and Cross-Device Compatibility**
**Objective:** Verify the website is responsive and displays correctly on different devices and screen sizes.

**Steps:**
1. Test on Desktop (1920x1080)
   - Verify layout is optimized for large screens
   - Verify all elements are properly aligned
   - Verify carousel displays with full height
2. Test on Tablet (768x1024)
   - Verify layout adjusts for medium screens
   - Verify content is readable without scrolling excessively
   - Verify product cards stack appropriately
3. Test on Mobile (375x667)
   - Verify burger menu appears and functions
   - Verify all elements fit without horizontal scroll
   - Verify touch interactions work correctly
   - Verify product images scale properly
4. Test on various browsers (Chrome, Firefox, Safari, Edge)

**Expected Result:** Website displays correctly on all screen sizes without distortion, text remains readable, navigation functions on all devices, and styling is consistent across browsers.

---

### **TS-009: Section Filtering and Navigation**
**Objective:** Verify that filtering by sections (Clothing and Accessories) works correctly.

**Steps:**
1. Load the homepage and observe all products
2. Click on "Clothings" link in navigation menu or scroll to the Clothing section
3. Verify only clothing products are visible on the page
4. Click on "Accessories" link in navigation menu or scroll to the Accessories section
5. Verify only accessories products are visible on the page
6. Verify the page jumps/scrolls to the correct section

**Expected Result:** Section filtering works correctly, products are properly categorized, navigation links correctly scroll/jump to intended sections, and section filtering is reflected in the UI.

---

### **TS-010: API Failure and Error Handling**
**Objective:** Verify the application handles API failures gracefully.

**Steps:**
1. Load the homepage with internet connection enabled
2. Wait for products to load successfully
3. Disconnect internet connection or block the API endpoint
4. Try to refresh the page
5. Observe the page behavior (check for error messages, fallback content, or console errors)
6. Reconnect internet and refresh
7. Verify products load again successfully
8. Check browser console for any JavaScript errors

**Expected Result:** Application handles network failures gracefully, displays user-friendly error messages or fallback content, no JavaScript errors in console, and products reload when connection is restored.

---

## Testing Priority
1. **Critical:** TS-001, TS-005, TS-006, TS-007, TS-008
2. **High:** TS-002, TS-004, TS-009
3. **Medium:** TS-003, TS-010

---

## Test Execution Notes
- Use Playwright or Selenium for automated testing
- Test across multiple browsers and devices
- Verify localStorage data persistence
- Monitor network requests and API responses
- Check console for JavaScript errors and warnings
- Validate responsive design at breakpoints (320px, 768px, 1024px, 1920px)

---

**Document Created:** April 6, 2026  
**Project:** Shoplane E-Commerce Website  
**Tested Features:** Navigation, Product Catalog, Shopping Cart, Checkout Process, Responsive Design
