Lab: DOM XSS in document.write sink using source location.search inside a select element

Description: This lab contains a DOM-based cross-site scripting vulnerability in the stock checker functionality. It uses the JavaScript document.write function, which writes data out to the page.
             The document.write function is called with data from location.search which you can control using the website URL. The data is enclosed within a select element.
             To solve this lab, perform a cross-site scripting attack that breaks out of the select element and calls the alert function.

1. After accessing the PortSwigger lab the homepage was of a shoppin site with various items listed.

   <img width="500" height="312" alt="image" src="https://github.com/user-attachments/assets/247d8e3e-75f2-48bf-90a1-58438e892f42" />

2. On checking one product there was no functionality accept one which was list stock options.

   <img width="500" height="899" alt="image" src="https://github.com/user-attachments/assets/e8c9177d-591e-4555-a671-6a6131362289" />

3. Then i opened DEV tools where it showed that all "Check Stock" options were inside the "select" statement which has a "name" of "storeId".

   <img width="500" height="839" alt="image" src="https://github.com/user-attachments/assets/a8dc3618-b1e6-466b-915c-ef5757614807" />

4. Then took a look at the URL and tried changing the "productId" in the URL but it showed "Invalid product ID".

   <img width="500" height="546" alt="image" src="https://github.com/user-attachments/assets/e4e2c277-1261-47ae-8829-7fe3045d17d2" />

5. After that i took a look at the "storeId" Again and thought to add it in the URL. And the new product got added into the "select" tag list among other options.

   <img width="500" height="930" alt="image" src="https://github.com/user-attachments/assets/15af6d37-7797-40a2-bcb7-c46e658dcbd9" />

6. Now it's time to test this "storeId" parameter by adding our payloads. One of the paylaod i tested was a basic -> <script>alert(1)</script> -> which worked.
   Then i tried another payload for the -> </select><svg onload=alert()> -> this one also got executed and a popup was displayed on the screen.

   <img width="500" height="829" alt="image" src="https://github.com/user-attachments/assets/047d9c22-03e8-49df-a9e4-5823cdce9682" />

   <img width="500" height="306" alt="image" src="https://github.com/user-attachments/assets/af73f2b6-6d6d-400c-928c-96d55d747a5e" />



   
