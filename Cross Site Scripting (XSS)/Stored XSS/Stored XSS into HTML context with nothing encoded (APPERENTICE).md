Lab: Stored XSS into HTML context with nothing encoded

Description: This lab contains a stored cross-site scripting vulnerability in the comment functionality.
             To solve this lab, submit a comment that calls the alert function when the blog post is viewed.

1. After Entering lab analyzed the posts on homepage.
   
   <img width="500" height="312" alt="image" src="https://github.com/user-attachments/assets/226429e9-9034-41ae-9686-718f4d05c263" />

   
3. Posts contained a comment section where user can write a comment.

   <img width="500" height="312" alt="image" src="https://github.com/user-attachments/assets/dff4bc53-93ff-4778-a9b8-12e75d1d33c3" />


4. Entered the payload in the comment section -> <script>alert(1)</script>

   <img width="500" height="312" alt="image" src="https://github.com/user-attachments/assets/ce79e462-168c-4619-abab-49c9a71e3b84" />
  
5. After submitting the comment go back to the post page on which comment was submitted.

   <img width="500" height="312" alt="image" src="https://github.com/user-attachments/assets/108370b5-2869-4181-8cc0-0872e9c9e0d5" />

6. Now the popup is shown on the screen.

   <img width="500" height="312" alt="image" src="https://github.com/user-attachments/assets/1c47c7fd-4418-4979-95d9-2e5eb72f40f6" />
