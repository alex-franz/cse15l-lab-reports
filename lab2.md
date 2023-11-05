# Lab Report 2;
## Alexander Franz, A16816659

## Part 1:

Here is the code I wrote for my StringServer.
![image](https://github.com/alex-franz/cse15l-lab-reports/assets/146875191/98b8e24f-990c-4283-9e69-d83ed47c4ce2)

Here are the screenshots of StringServer at work. 
![image](https://github.com/alex-franz/cse15l-lab-reports/assets/146875191/85d82666-b08f-4151-a2ba-d99ed8cbbce5)
In this screenshot the methods called in order are the main method in the StringServer class, then the start method in the Server class is called and the server is created. Then handleRequest is called with the URL as the argument and when /add-message?s=Hello is added to the end of the URL, then "Hello" is printed to the screen numbered 1. The relevant arguments are the path and the query of the URL. The field `Array<String> lst` is changed during this becasue Hello is added to the list. No values in specific were changed.

![image](https://github.com/alex-franz/cse15l-lab-reports/assets/146875191/3498268f-3371-47af-84f8-e882fb9dbf3c)
Similarly to the previous screenshot, the method called is handleRequest which takes in the URL as an arugment again. The relevant arguments in this case are the path and the query. It detects the same query and adds the String "How are you" 
to the field `Array<String> lst`, which changes it. Then the string is decoded to prevent the method from showing "How+are+you" 
instead of "How are you", and then shown on the page as number 2. With other requests that aren't /add-message, the server will return 404 Not Found! because I did not include support for other requests.  

## Part 2:




![image](https://github.com/alex-franz/cse15l-lab-reports/assets/146875191/cee7e43c-ba02-4ff6-96e0-97ddd37820ee)

In this screenshot, we can see using ls, the path of my private ssh key would be C:/Users/afran/.ssh/id_rsa

![image](https://github.com/alex-franz/cse15l-lab-reports/assets/146875191/b812d202-50c1-4243-a391-0ac335b6f11a)

On ieng6, the path to the key would be /home/.ssh/id_rsa. 

![image](https://github.com/alex-franz/cse15l-lab-reports/assets/146875191/67e9772e-2650-4ced-8b26-3c6aba859205)

Here we can see I can log into ieng6 without providing any password. 

During weeks 2 and 3 I learned how to log into a remote server and create a key that allows me to login without a password.

