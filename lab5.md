# Lab Report 5
## Alexander Franz, A16816659



## Part 1: Debugging Scenario

**Scenario Instructions**

The student is assigned a short in class exercise that requires them to implement a Selection Sort algorithm for a int list. They also must write a basic test that shows the algorithms works with basic cases. 

They are also required to write a bash script to compile and run the program.

**Student Post/Question**

Hello, I'm trying to implement my sort algorithm but I keep getting this weird output where my sorted array is all the same. I'm not sure why it's doing this but I have a feeling it has to do with my swapping section because the first value is 1, which is the expected value for the sorted array at index 0. Here's my code below and the bash script I made to run it. The first file is named Sort.java and the bash script is named test.sh.

```
import java.util.ArrayList;

public class Sort{
	
	public static int[] selection(int[] lst) {
		for ( int i = 0; i < lst.length - 1; i++) {
			int min = i; 
			for ( int j = i; j < lst.length; j++ ) {
				if ( lst[min] >=  lst[j] ) {
					min = j;
				}
			}
			lst[i] = lst[min];
		}		
		return lst;
	}
	


	public static void main(String[] args) {
		
		
		int[] testArr = {6,5,4,3,2,1};
		int[] expectedArr = {1,2,3,4,5,6};
		System.out.println("Test Array:");
		System.out.print("[ ");
		for (int j = 0; j < testArr.length; j++) {
			System.out.print(testArr[j]);
			System.out.print(" ");

		}
		System.out.println("]");
		int[] newArr = selection(testArr);
		for ( int i = 0; i < newArr.length; i ++ ) {
			if ( newArr[i] != expectedArr[i] ) {
				System.out.println("Error! Did not match expected array! ");
				break;
			} 
		}
		System.out.println("Sorted Array:");
		System.out.print("[ ");
		for (int i = 0; i < newArr.length; i++ ) {
			System.out.print(newArr[i]);
			System.out.print(" ");

		}
		System.out.println("]");


	
	}
}
```
```
javac Sort.java 
java Sort 
```

I ran the test I made using `bash test.sh` at the command line and the resulting output is below.
```
Test Array:
[ 6 5 4 3 2 1 ]
Error! Did not match expected array! 
Sorted Array:
[ 1 1 1 1 1 1 ]
```



**TA Response**

Hi student! This is a great start to your algorithm. The method correctly identifies the minumum value, however, it does seem like your swapping portion is incorrect. Do you think your swap is actually swapping the values?

**Student Fix/ Explanation of Bug**

I inspected the algorithm and realized my swap wasn't actually swapping the values. I was just reassigning the current element to the minimum value and losing the current value. Since the minimum value is at the end of the list, it's reassigning all the values to 1, which obviously does not sort the list. I added two lines of code to prevent this. First, I added a temporary variable labeled `temp` that is assigned to the current value, then reassigned that value to the minimum value, and finally reassigned the value at the min index to the temp variable, which effectively swaps the values without losing the current value. Here is a code snippet of my selection method. I didn't alter my bash script. 
```
public static int[] selection(int[] lst) {
	for ( int i = 0; i < lst.length - 1; i++) {
		int min = i; 
		for ( int j = i; j < lst.length; j++ ) {
			if ( lst[min] >=  lst[j] ) {
				min = j;
			}
		}
		int temp = lst[i];
		lst[i] = lst[min];
		lst[min] = temp;
	}		
	return lst;
}
```
Now, after running it my output is as expected! After running `bash test.sh`, the output shows as below.

```
Test Array:
[ 6 5 4 3 2 1 ]
Sorted Array:
[ 1 2 3 4 5 6 ]
```

## Part 2: Reflection

I learned a lot of cool things in the second half of the quarter, but I think the most useful thing was learning how to use Git and Github. Talking to our TA Alon, he noted that Git and Github are used super widely in the industry so it is really important to learn it. After hearing this, I started making my own repositories for my CSE 12 PAs so I can edit my PAs from my laptop or my Home Desktop much more efficiently. Another thing I learned was Vim, which is super complicated for no reason but it is so cool to be able to do everything from the command line. Learning the basics of Vim can allow me to do everything form the command line, but mastering Vim would allow me to do it all efficiently. Our TA also gave us really useful tips when searching for internships. I really enjoyed this course and I feel like I learned some really valuable information!

