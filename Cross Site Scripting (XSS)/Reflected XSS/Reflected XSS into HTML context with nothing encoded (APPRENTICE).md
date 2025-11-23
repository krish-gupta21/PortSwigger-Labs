Lab: Reflected XSS into HTML context with nothing encoded

Description: This lab contains a simple reflected cross-site scripting vulnerability in the search functionality.
             To solve the lab, perform a cross-site scripting attack that calls the alert function.

1. After accessing lab i tested the search feature.
2. Entered Hello in search feild.

   <img width="500" height="312" alt="image" src="https://github.com/user-attachments/assets/3bc1ffbd-34ad-45da-83d0-ad02c053d921" />


4. Search query looks like this -> https://0aae003504f56d8884c450b2008e0027.web-security-academy.net/?search=Hello
5. Then entered the payload in search field -> <script>alert(1)</script>

   <img width="500" height="312" alt="image" src="https://github.com/user-attachments/assets/fc66b1bd-6943-4524-ab1e-2b32f0ab27d4" />
   
6. Modified Url -> https://0aae003504f56d8884c450b2008e0027.web-security-academy.net/?search=%3Cscript%3Ealert%281%29%3C%2Fscript%3E
7. Finally popup shown on the screen.

   <img width="500" height="312" alt="image" src="https://github.com/user-attachments/assets/21aa61f2-0244-4da4-af78-b7bad45b4f4f" />
