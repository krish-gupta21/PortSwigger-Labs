Lab: DOM XSS in innerHTML sink using source location.search 

Description: This lab contains a DOM-based cross-site scripting vulnerability in the search blog functionality.
             It uses an innerHTML assignment, which changes the HTML contents of a div element, using data from location.search.
             To solve this lab, perform a cross-site scripting attack that calls the alert function.

1. As mentioned in description vulnerbaility is in the search function so on home page tested the search function by entering some text.

   <img width="500" height="533" alt="image" src="https://github.com/user-attachments/assets/339a7ff3-6e49-4685-921c-57dd80d7df1b" />

2. Then opened DEV tools to analyze where the input is reflecting in the code and analyzed that the input was reflected inside the span tag.

   <img width="500" height="551" alt="image" src="https://github.com/user-attachments/assets/41c1f590-fc10-490f-af8a-23121f9ab3aa" />

3. And in the script the .innerHTML sink was using the "query" parameter from function to get the input from search.

4. Then from my past experienced thought to use the basic payload -> <script>alert(1)</script> and to my surprise payload got injected into the code but do not get executed.

   <img width="500" height="659" alt="image" src="https://github.com/user-attachments/assets/975f7e83-66dc-4702-a2ab-540b04a237f0" />

5. After spending some time on google to search for this found that in "innerHTML" sink "script" tag do not gets executed.
   Note: Modern Browsers treat it as dead script.<br>
   So simply injecting <script> inside innerHTML does NOT run.

6. Then tried another payload -> <img_src=x onerror=alert()> . Here keeping the image source as "x" which is not a valid source and upon execution error message pops up.

   <img width="500" height="544" alt="image" src="https://github.com/user-attachments/assets/c8a34760-8e43-4ac7-9cfd-bb60fdbe3b26" />

   <img width="500" height="264" alt="image" src="https://github.com/user-attachments/assets/b82272b7-a90e-43a8-9fe1-2aacaf20c08f" />

