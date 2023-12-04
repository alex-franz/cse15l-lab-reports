# Lab Report 5
## Alexander Franz, A16816659

**Scenario Instructions**

The student is assigned a short in class exercise that requires them to implement an Insertion Sort algorithm for a int list. They also must write a basic test that shows the algorithms works with basic cases. 

They are also required to write a bash script to compile and run the program within JDB. 

**Student Post/Question**

Hello, I'm trying to implement my sort algorithm but I keep getting this weird output where my array is sorted except for the last elemetn. I'm so close and I can;t figure out why it's doing this. Here's a screenshot of my code. 

```
	public static int[] insertion(int[] lst) {
		for ( int i = 0; i < lst.length - 1; i++) {
			int min = i; 
			for ( int j = 0; j < lst.length; j++ ) {
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
