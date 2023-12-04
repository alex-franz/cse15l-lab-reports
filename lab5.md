# Lab Report 5
## Alexander Franz, A16816659

**Scenario Instructions**

The student is assigned a short in class exercise that requires them to implement an Insertion Sort algorithm for a int list. They also must write a basic test that shows the algorithms works with basic cases. 

They are also required to write a bash script to compile and run the program within JDB. 

**Student Post/Question**

Hello, I'm trying to implement my sort algorithm but I keep getting this weird output where my sorted array is all the value one. I'm not sure why it's doing this but I have a feeling it has to do with my swapping section because the first value is 1, which is the expected value for the sorted array at index 0. Here's my code below and the bash script I made to run it. 

```
public static int[] insertion(int[] lst) {
	for ( int i = 0; i < lst.length - 1; i++) {
		int min = i; 
		for ( int j = 0; j < lst.length; j++ ) {
			if ( lst[min] >=  lst[j] ) {
				min = j;
			}
		}
		lst[i] = lst[min];
	}		
	return lst;
}
```

When I input the array `{6,5,4,3,2,1}`, my test method outputs `{1,1,1,1,1,1}`. 
