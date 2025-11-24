Lab: DOM XSS in document.write sink using source location.search (APPRENTICE)

Description: This lab contains a DOM-based cross-site scripting vulnerability in the search query tracking functionality. It uses the JavaScript document.write function, which writes data out to the page.
             The document.write function is called with data from location.search, which you can control using the website URL.
             To solve this lab, perform a cross-site scripting attack that calls the alert function.

1. After accessing the lab firstly tested the search function on home page.

   <img width="500" height="312" alt="image" src="https://github.com/user-attachments/assets/ae4bcc18-5a30-4ea1-9afc-36fe7cdbb45d" />

2. Tested with any random text say - Hacker0xinvader

   <img width="500" height="312" alt="image" src="https://github.com/user-attachments/assets/3a57be05-b622-490f-b442-d8195e09b818" />

3. Then looked into the source code using the DEV Tools as to see where the entered text reflects in the code. Here the text reflected in 2 places firstly indside the "h1" tag and other inside the "img" tag.

   <img width="1905" height="861" alt="image" src="https://github.com/user-attachments/assets/c95d99bc-427d-40d7-a1e7-0f44658f8b7d" />

4. After reviewing the source code i then tested a payload -> Hacker0xinvader"><script>alert()</script>

   <img width="500" height="312" alt="image" src="https://github.com/user-attachments/assets/c7e23a24-7e71-440b-aa98-f65fd157122e" />
   
5. On the execution the payload got executed and a popup alert was shown on the screen. And after reviewing the source code again it showed that the "img" tag got closed and a new script tag
   was inserted into the code due to which the popup was successful.'

   <img width="1889" height="653" alt="image" src="https://github.com/user-attachments/assets/bfdcaf82-496e-48d5-9f41-c09715013802" />

   <img width="1065" height="287" alt="image" src="https://github.com/user-attachments/assets/9303e876-8f2b-485a-ae29-82f50de23860" />
