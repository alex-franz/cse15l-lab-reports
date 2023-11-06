# Lab Report 3:
## Alexander Franz, A16816659

## Part 1:

The bug I'm choosing is form the revserseInPlace method, that takes in an array and reverses it. 

```
public void testReverseInPlace() {
  int[] input1 = {1,2,3,4,5};
  ArrayExamples.reverseInPlace(input1);
  assertArrayEquals(new int[]{5,4,3,2,1}, input1);
}
```
This test is designed to test the method with a very basic input, and to see if 
the method even works. In this case it is a failing input, as the actual output is `{5,4,3,4,5}`.

```
public void testReverseInPlace() {
  int[] input1 = {1,2,2,1};
  ArrayExamples.reverseInPlace(input1);
  assertArrayEquals(new int[]{1,2,2,1}, input1);
}
```
This test does not induce a failure because it is a symmetric array. So when the second half of the array is iterated through, when the method accidentally just reflects the first half, it creates the original array anyway. 

![Image 11-5-23 at 9 20 PM](https://github.com/alex-franz/cse15l-lab-reports/assets/146875191/8287411e-b4e6-4d95-8f06-29e83766b00b)

This screenshot shows the failing and successful inputs. The symptom is that the method is outputting 4 instead of the expected 2. 

## Before 

```
static void reverseInPlace(int[] arr) {
  for(int i = 0; i < arr.length; i += 1) {
  arr[i] = arr[arr.length - i - 1];
  }
}
```

## After 
```
static void reverseInPlace(int[] arr) {
  for(int i = 0; i < arr.length / 2; i += 1) {
    int temp = arr[i];
    arr[i] = arr[arr.length - i - 1];
    arr[arr.length - i - 1] = temp;
  }
}
```
This code initializes a temp int using i in the loop, then it swaps the element on the other side, then swaps the temp element with the associated element. Also it iterates through only half the list so the actual output doesn't just look like a reflected list. 

## Part 2:

## The find command

The find command is a very powerful tool to find specific files or directories. The `-type` option allows us to find items that are either directories (d), files (f), etc. 

If we run the command `find ./technical -type d`, we get a list of directories in `./technical`.

The output is 
```
./technical
./technical/government
./technical/government/About_LSC
./technical/government/Env_Prot_Agen
./technical/government/Alcohol_Problems
./technical/government/Gen_Account_Office
./technical/government/Post_Rate_Comm
./technical/government/Media
./technical/plos
./technical/empty
./technical/biomed
./technical/911report
```

Then, if we run `find ./technical type f` we get a huge output of files that are in `./technical`
. Here is a short snip. 

```
./technical/biomed/1471-2199-2-6.txt
./technical/biomed/bcr567.txt
./technical/biomed/gb-2002-3-10-research0055.txt
./technical/biomed/1471-2121-2-3.txt
./technical/biomed/1471-213X-1-11.txt
./technical/biomed/1472-684X-1-5.txt
./technical/biomed/1476-4598-1-6.txt
./technical/911report/chapter-13.4.txt
./technical/911report/chapter-13.5.txt
./technical/911report/chapter-13.1.txt
./technical/911report/chapter-13.2.txt
./technical/911report/chapter-13.3.txt
./technical/911report/chapter-3.txt
./technical/911report/chapter-2.txt
./technical/911report/chapter-1.txt
./technical/911report/chapter-5.txt
./technical/911report/chapter-6.txt
./technical/911report/chapter-7.txt
./technical/911report/chapter-9.txt
./technical/911report/chapter-8.txt
./technical/911report/preface.txt
./technical/911report/chapter-12.txt
./technical/911report/chapter-10.txt
./technical/911report/chapter-11.txt
```

It would be very useful to use this option as it can help us find directories within directories that have lots of files. 

The `-size` option allows us to find files or directories that are of the specified size. In this example below, I'm finding files of size less than 10kb in the `./technical` directory. 

The command ```% find ./technical/911report -size -10k ``` will give us the output 

```
./technical/911report
./technical/911report/preface.txt
```
This next example shows the files with less than 1MB, using the command ```% find ./technical/911report -size -1M```

The output is 

```
./technical/911report
./technical/911report/chapter-13.4.txt
./technical/911report/chapter-13.5.txt
./technical/911report/chapter-13.1.txt
./technical/911report/chapter-13.2.txt
./technical/911report/chapter-13.3.txt
./technical/911report/chapter-3.txt
./technical/911report/chapter-2.txt
./technical/911report/chapter-1.txt
./technical/911report/chapter-5.txt
./technical/911report/chapter-6.txt
./technical/911report/chapter-7.txt
./technical/911report/chapter-9.txt
./technical/911report/chapter-8.txt
./technical/911report/preface.txt
./technical/911report/chapter-12.txt
./technical/911report/chapter-10.txt
./technical/911report/chapter-11.txt
```
As we can see, the two outputs are different. Using this option can allow us to find huge files that take up too much space in a certain drive, which can allow the user to maintain a healthier file system.  

The `-empty` option gives users the ability to search for empty files/directories. This can be very useful in managing files and deleting unused files/directories. The screenshot below shows an example of using this option. I added a directory to the `./technical` directory called `/empty` that contains an empty file to show this command in action. 

The command ```% find ./technical -empty``` outputs 

```
./technical/empty/empty.txt
```

Which is the empty txt file I added to the empty directory I created

Then, if I delete the empty.txt file, we can use the command ```% find ./technical -empty``` again, but the output would be 

```
./technical/empty
```

This option could help us find empty files/directories that we would want to get rid if our file system is cluttered. 

The `-depth` option allows us to find files in a sorted list to the command line. It finds files at the farthest location then prints until it reaches the specified parent directory. 

```% find ./technical -depth```
This example uses depth in the `./technical` directory and prints out all the files and directories sorted. A short snip of the output is as follows.
```
./technical/biomed/bcr567.txt
./technical/biomed/gb-2002-3-10-research0055.txt
./technical/biomed/1471-2121-2-3.txt
./technical/biomed/1471-213X-1-11.txt
./technical/biomed/1472-684X-1-5.txt
./technical/biomed/1476-4598-1-6.txt
./technical/biomed
./technical/911report/chapter-13.4.txt
./technical/911report/chapter-13.5.txt
./technical/911report/chapter-13.1.txt
./technical/911report/chapter-13.2.txt
./technical/911report/chapter-13.3.txt
./technical/911report/chapter-3.txt
./technical/911report/chapter-2.txt
./technical/911report/chapter-1.txt
./technical/911report/chapter-5.txt
./technical/911report/chapter-6.txt
./technical/911report/chapter-7.txt
./technical/911report/chapter-9.txt
./technical/911report/chapter-8.txt
./technical/911report/preface.txt
./technical/911report/chapter-12.txt
./technical/911report/chapter-10.txt
./technical/911report/chapter-11.txt
./technical/911report
./technical
```

Another example, ```% find ./technical/911reports/chapter*.txt -depth``` will print out all the files with the specified pattern in the sorted order based on the directory structure. This could help us find the last files in a directory if the directory contains a lot of files.
```
./technical/911report/chapter-1.txt
./technical/911report/chapter-10.txt
./technical/911report/chapter-11.txt
./technical/911report/chapter-12.txt
./technical/911report/chapter-13.1.txt
./technical/911report/chapter-13.2.txt
./technical/911report/chapter-13.3.txt
./technical/911report/chapter-13.4.txt
./technical/911report/chapter-13.5.txt
./technical/911report/chapter-2.txt
./technical/911report/chapter-3.txt
./technical/911report/chapter-5.txt
./technical/911report/chapter-6.txt
./technical/911report/chapter-7.txt
./technical/911report/chapter-8.txt
./technical/911report/chapter-9.txt
```

The source I used to figure out how to use the options is below.

https://ss64.com/bash/find.html


