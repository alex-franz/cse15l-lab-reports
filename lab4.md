# Lab Report 4

## Alexander Franz, A16816659

## Vim and Git Tasks


**Step 1: Log into ieng6.**

Keys Pressed: In this step, I entered `ssh cs15lfa23jg@ieng6.ucsd.edu` then pressed `<enter>`. 

Summary: This successully logged me into ieng6 wihtout using a password since my ssh key bypassed the login. 

![image](https://github.com/alex-franz/cse15l-lab-reports/assets/146875191/63945e19-9978-4c64-b9da-f17abd31cfee)

___

**Step 2: Git Clone into ieng6.**

Keys Pressed: In this step, I used the command `git clone` then used `<cmd C>` and `<cmd V>` to copy the SSH URL from my lab7 fork to the command line. Then 
I pressed `<enter>` to run the command.

Summary: I used these commands to clone the repository into ieng6 so I can inspect files, run tests, and debug them in ieng6. 

<img width="706" alt="image" src="https://github.com/alex-franz/cse15l-lab-reports/assets/146875191/2a62ef46-cb22-40b9-9237-28ee3145ae8a">

___

**Step 3: Running the test, demonstrating failure.**

Keys Pressed: My first step was to use `ls` to see the contents of ieng6. Then I navigated to lab7 using `cd l` then `<tab>` to fill in the rest, and pressed `<enter>` to execute. Then I used `ls` again and `bash t` + `<tab>` to fill in the rest and pressed `<enter>` to run the tests. 

Summary: I used these commands so I can run the JUnit tests and demonstrate the test failed. I used some shortcuts liek `<tab>` in order to reduce keystrokes and make my testing process more efficient. 

<img width="712" alt="image" src="https://github.com/alex-franz/cse15l-lab-reports/assets/146875191/5a80a21c-0b96-4191-b8ca-d50de9a93e08">

___

**Step 4: Edit the code file to fix the failing test**

Keys Pressed: First I want to edit the error inducing file, which is ListExamples.java. To do this I used `vim ListExamples.java` which I typed out by hand because there is another file with the ListExamples string. Then after typing in this command I pressed `<enter>` to execute it and enter vim. Then once entering vim, I pressed `<i>` to enter insert mode. From insert mode, I pressed `<down>` 43 times, then `<right>` 12 times to reach the part of the code that needs to be fixed. Then, while in insert mode I pressed `<backspace>` to delete the 1 in `index1` and replaced it with a `2` by pressing `<2>`. Then I pressed `<esc>` to exit insert mode and entered the command `:wq` to save and exit the file. The screenshots are below. 

Summary: I used basic vim commands to navigate through the file and fix the bug. My approach is not the most efficient as there are other commands I can use to naviagte to a specific line, however, my approach was very simple and straightforward.

Entering vim

<img width="366" alt="image" src="https://github.com/alex-franz/cse15l-lab-reports/assets/146875191/1912b1e9-30a5-4d27-ab0b-e311db73ef5b">

In vim before navigating to bug

<img width="548" alt="image" src="https://github.com/alex-franz/cse15l-lab-reports/assets/146875191/b5aaea2f-a5aa-421d-82df-f3f21218f42f">

After navigating to bug and fixing it.

<img width="522" alt="image" src="https://github.com/alex-franz/cse15l-lab-reports/assets/146875191/68338f7d-5c96-42df-b3bb-299f55354025">

___

**Step 5: Run the tests, demonstrating they now succeed**

Keys Pressed: After exiting vim, I pressed `<up>` `<up>` to recover the `bash test.sh` command I ran earlier and pressed `<enter>` to run the tests again. Which showed the test passed. 

Summary: This step was almost exactly like step 3, except I used `<up>` arrows to recover the bash command I previously used, which made my process much more efficient.  

<img width="389" alt="image" src="https://github.com/alex-franz/cse15l-lab-reports/assets/146875191/9cf1c58b-2826-4d3e-8b99-d988e9a15278">

___

**Step 6: Commit and push the resulting change to your Github account**

Keys Pressed: During this step, I typed out `git add .` then pressed `<enter>` to stage the file for a commit. This command stages all files added or modified for a new commit to the current branch. Then, on the next command I typed out `git commit -m "bug fixed"` and `<enter>` to run the command. This commits the added files to the main branch of my forked repository with the following message after the `-m` option. Then I typed out the command `git push` and `<enter>` to run it. This command pushes the commit to the remote server. Finally, the output shows how many files were modified as well as how many insertions and deletions that were made, and some other output after `git push`.

Summary: Using the git commands, I was able to add, commit, and push my changes to my repository. Here I used a shortcut in `git commit -m "big fixed"` to input the message without having to enter vim and make more  keystrokes. I did this to make my process more efficient and streamlined. 

<img width="500" alt="image" src="https://github.com/alex-franz/cse15l-lab-reports/assets/146875191/0f5a3bed-832b-4fb1-8f5e-6e2b23432a6c">



