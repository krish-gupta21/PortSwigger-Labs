Lab: Reflected DOM XSS

Description: This lab demonstrates a reflected DOM vulnerability. 
             Reflected DOM vulnerabilities occur when the server-side application processes data from a request and echoes the data in the response. 
             A script on the page then processes the reflected data in an unsafe way, ultimately writing it to a dangerous sink.
             To solve this lab, create an injection that calls the alert() function.

1. The lab is about a reflected DOM xss in the website.

   <img width="1893" height="917" alt="image" src="https://github.com/user-attachments/assets/141073ba-f901-441b-b5d0-f1ddb1f87c97" />

2. Firstly testing the search functionality in the homepage and checking for input reflection in the source code.
   Here, it showed that our input got reflected inside the "h1" tag. And also one other thing to be noticed here is that this lab uses a separate .js file and not a internal js script.

   <img width="1893" height="832" alt="image" src="https://github.com/user-attachments/assets/1a7aaf0f-fd48-4b9f-b3b5-d109f34236ef" />

4. We can view the js file from the "Sources" section in the DevTools. In the js file its using an "eval()" function to evaulate the search query which could be our way in to find the xss.
   So it takes the input from search whether its a js code and executes it.

   <img width="1893" height="819" alt="image" src="https://github.com/user-attachments/assets/068eb647-0bda-42d5-b709-40fbec0a2a91" />

5. From the "Network" tab also we can see that our input is inside the json format so if we can escape it we would be able to execute our malicious script on the site.

   <img width="1893" height="610" alt="image" src="https://github.com/user-attachments/assets/fda8e0cd-3965-4dd0-9d85-e1307572acbb" />

6. So the basic sense to escape from double quotes would be to use " . After that can use -alert() and check for the response.
   And Here we can see that "alert()" function was still not able to escape the string as backslash was inserted before " to keep the whole input
   abcd123"-alert() as a string.

   <img width="1893" height="630" alt="image" src="https://github.com/user-attachments/assets/ead92048-9428-467b-b00f-bacb4f613b36" />

7. But by in inserting a backslash manually we can see that our "alert()" function was able to escape the string but still didn't got executed as there was still a quote(") after the alert function.

   <img width="1893" height="623" alt="image" src="https://github.com/user-attachments/assets/117a5cee-4795-43a5-96ba-4ded2b63504f" />

8. So now what we can do is comment whatever is after the alert function to make our "alert()" function execute using the comments(//). And close the curly brace before the quote.
   And as a result our "alert()" function gets exectuted and we can see a popup shown on the screen.

   <img width="1893" height="592" alt="image" src="https://github.com/user-attachments/assets/04add7b2-9218-4e80-b522-5959e6661dbe" />

   <img width="1893" height="272" alt="image" src="https://github.com/user-attachments/assets/6e65fd40-b81a-4081-920b-e2d455d4e506" />

