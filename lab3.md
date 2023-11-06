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

## The find command

The find command is a very powerful tool to find specific files or directories. The `-type` option allows us to find items that are either directories (d), files (f), etc. The screenshot below shows us how this is used using `-type` to find all directories within the `./technical` directory. 

![Image 11-5-23 at 9 47 PM](https://github.com/alex-franz/cse15l-lab-reports/assets/146875191/633cb9e3-93a6-47f5-967b-079fd95dc100)

The `-size` option allows us to find files or directories that are of the specified size. In this example below, I'm finding files of size less than 10kb in the `./technical` directory. 

![Image 11-5-23 at 9 53 PM](https://github.com/alex-franz/cse15l-lab-reports/assets/146875191/74171ee7-e94b-436f-91c5-63380dcc8e81)

The `-empty` option gives users the ability to search for empty files/directories. This can be very useful in managing files and deleting unused files/directories. The screenshot below shows an example of using this option. I added an empty directory to the `./technical` directory to show this command in action. 

![Image 11-5-23 at 9 58 PM](https://github.com/alex-franz/cse15l-lab-reports/assets/146875191/eac9615f-ab6a-4357-ab2f-d2f079c9f31a)

The `-print` option allows us to print the contents of a directory to the command-line. In this example below we use find, then specify the path and then use `-print`. Which then prints all its contents to the command line. 

![Image 11-5-23 at 10 06 PM](https://github.com/alex-franz/cse15l-lab-reports/assets/146875191/16943f60-42dc-4a39-878f-a115103e2bb6)

The source I used to figure out how to use the options is below.

https://ss64.com/bash/find.html


