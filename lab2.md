# Lab Report 2;
## Alexander Franz, A16816659

## Part 1:

Here is the code I wrote for my StringServer.
![image](https://github.com/alex-franz/cse15l-lab-reports/assets/146875191/98b8e24f-990c-4283-9e69-d83ed47c4ce2)

Here are the screenshots of StringServer at work. 
![image](https://github.com/alex-franz/cse15l-lab-reports/assets/146875191/85d82666-b08f-4151-a2ba-d99ed8cbbce5)
In this first screenshot, the method that is called is the handleRequest method, which takes in the specified query and extracts the 
String parameter and adds it to the field `Array<String> lst`. Then, the string is decoded and printed to the page as number 1. The 
value of `lst` is changed as the String "Hello" is added. 

![image](https://github.com/alex-franz/cse15l-lab-reports/assets/146875191/3498268f-3371-47af-84f8-e882fb9dbf3c)
Similarly to the previous screenshot, the method called is handleRequest. It detects the same query and adds the String "How are you" 
to the field `Array<String> lst`, which changes it. Then the string is decoded to prevent the method from showing "How+are+you" 
instead of "How are you", and then shown on the page as number 2. 

## Part 2:




![image](https://github.com/alex-franz/cse15l-lab-reports/assets/146875191/cee7e43c-ba02-4ff6-96e0-97ddd37820ee)

In this screenshot, we can see using ls, the path of my private ssh key would be C:/Users/afran/.ssh/id_rsa

![image](https://github.com/alex-franz/cse15l-lab-reports/assets/146875191/b812d202-50c1-4243-a391-0ac335b6f11a)

On ieng6, the path to the key would be /home/.ssh/id_rsa. 

![image](https://github.com/alex-franz/cse15l-lab-reports/assets/146875191/67e9772e-2650-4ced-8b26-3c6aba859205)

Here we can see I can log into ieng6 without providing any password. 

During weeks 2 and 3 I learned how to log into a remote server and create a key that allows me to login without a password.

