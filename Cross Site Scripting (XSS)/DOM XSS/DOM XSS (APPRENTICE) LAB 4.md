Lab: DOM XSS in jQuery anchor href attribute sink using location.search source

Description: This lab contains a DOM-based cross-site scripting vulnerability in the submit feedback page.
             It uses the jQuery library's $ selector function to find an anchor element, and changes its href attribute using data from location.search.
             To solve this lab, make the "back" link alert document.cookie.

1. As clearly mentioned that the vulnerbility is in the submit feedback page so on starting the lab jumped directly into the submit feedback page.

   <img width="500" height="441" alt="image" src="https://github.com/user-attachments/assets/8a75974f-f477-4fc5-84b0-9158fa41de42" />

   <img width="500" height="873" alt="image" src="https://github.com/user-attachments/assets/ee88f9cd-1e42-4a55-8d14-e7ac92c9b09b" />

2. On the feedback page we have only two buttons "submit feedback" and the back button. Then opened the DEV tools for source code review. And in the script tag function was using "Back" buttons id to take
   the "href" attributes input and a new object was created to get the "returnPath" parameter from URL which was inititally a forward-slash(/).

   <img width="500" height="681" alt="image" src="https://github.com/user-attachments/assets/2aae8d49-b540-4fdb-9a45-742a7fe9b089" />

   <img width="500" height="45" alt="image" src="https://github.com/user-attachments/assets/749a66df-8864-40ef-87ed-125d6e902118" />

3. Then tested the "returnPath" parameter with random input and after reviewing in source code the input got appended after the forward slash inside the anchor tag.

   <img width="500" height="672" alt="image" src="https://github.com/user-attachments/assets/9a863545-41f2-4a56-be72-62e18819d1cf" />

   <img width="500" height="36" alt="image" src="https://github.com/user-attachments/assets/a4dd3342-3561-4446-b1a5-8f03fced0aef" />

4. Then as we can use "javascript" directly into the "anchor" tag i tried the payload in the returnPath parameter -> javascript:alert(document.cookie).<br>
   And upon submitting the payload the lab got solved notification showed up but no popup was shown as part of alert function.

   <img width="500" height="838" alt="image" src="https://github.com/user-attachments/assets/3650eb93-30c0-493f-84e1-df5e61162be7" />

5. As the payload got stored in anchor tag for back button so i tried pressing the back button and then the payload got executed and a popup alert showed up.

   <img width="500" height="961" alt="image" src="https://github.com/user-attachments/assets/b0967bed-85b0-42be-a6f7-716f2d4319dc" />
