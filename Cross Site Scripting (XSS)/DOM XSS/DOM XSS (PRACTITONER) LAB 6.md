Lab: DOM XSS in AngularJS expression with angle brackets and double quotes HTML-encoded

Description: This lab contains a DOM-based cross-site scripting vulnerability in a AngularJS expression within the search functionality. 
             AngularJS is a popular JavaScript library, which scans the contents of HTML nodes containing the ng-app attribute (also known as an AngularJS directive).
             When a directive is added to the HTML code, you can execute JavaScript expressions within double curly braces.
             This technique is useful when angle brackets are being encoded. To solve this lab, perform a cross-site scripting attack that executes an AngularJS expression and calls the alert function.

1. So the lab is about a xss vulnerbility in the angular js expression in the search functionlity of the lab.
   It contains a ng-app attribute which is used in angular js which marks the root element of angular js application and tells the framework from where to start compiling and processing Angular expressions.
   
2. So the basic homepage with a search feature and some posts. In the search feature entered an alphanumeric input.

   <img width="1878" height="957" alt="Screenshot 2025-11-26 215454" src="https://github.com/user-attachments/assets/2dfc5695-63e2-4dde-b5b5-a371fff3b95a" />

2. In the source the input got reflected inside the section tag. And also the "ng-app" attribute was used inside the body tag which tells the code to start compiling and processing Angular expressions.

   <img width="1899" height="894" alt="Screenshot 2025-11-26 215930" src="https://github.com/user-attachments/assets/421d468e-8dfc-493c-a80b-f83f08fa56de" />

3. As given a hint in the description that in angular js framework when a directive is added we can directly execute JS expressions directly inside double curly braces {{ }}.
   So tried a basic expression inside search feature and got the result.

   <img width="1053" height="482" alt="Screenshot 2025-11-26 230908" src="https://github.com/user-attachments/assets/5a81e108-63fc-455c-ae31-227f05ab3ce4" />

4. But on using an alert function it does not get exectuted.
   
   <img width="979" height="356" alt="Screenshot 2025-11-26 231155" src="https://github.com/user-attachments/assets/3b36ca85-cbae-4d99-9e21-2614ec96fbe8" />

5. Alert function does not get executed as AngularJS allows only functions/variables inside the current scope and prevents global functions for security purposes to prevent from attacks like XSS.
   So in order for function like alert() to work it must be defined as a part of scope so that it can get evaluated. Some of AngularJS scope methods are:

   <img width="1045" height="814" alt="Screenshot 2025-11-26 231638" src="https://github.com/user-attachments/assets/da0e0668-97a8-4bb9-a7e7-64e2bd47457c" />

6. So with the use of scope methods we can create a payload which can help us to execute the alert() function.<br>
   The payload we can use -> {{ $eval.constructor('alert(1)')() }} <br>
   Here,<br>
   $eval -> one of scope methods used to execute methods on current scope.<br>
   .constructor -> points to the global JavaScript Function constructor<br>
   alert() -> function we want to get executed<br>
   () -> to call the created function

   <img width="1117" height="306" alt="Screenshot 2025-11-26 232842" src="https://github.com/user-attachments/assets/fd088211-cab3-40a0-a5a7-fb040d1946d8" />

   <img width="1087" height="308" alt="Screenshot 2025-11-26 232856" src="https://github.com/user-attachments/assets/be201ccb-c636-435b-a1a1-cce0e49d9c3c" />
