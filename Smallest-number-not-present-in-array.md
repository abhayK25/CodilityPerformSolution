# Codility-Solution
This is the solution for smallest number which is not present in array.
Example : 
1. arr[]={1,2,4,5};
   output : 3

2. arr[]={1,2,3,4,5};
   output : 6

3. arr[]={-1,-2};
   output : 1

4. arr[]={4,2,1,5};
   output : 3   

```java
import java.util.Arrays;
import java.util.stream.IntStream;
public class Solution {

	public static void main(String[] args) {

		int arr[] = {1,2,4,5};
		int smallNumber = 1;

		Arrays.sort(arr);
		for (int i : arr) {
			boolean contains = IntStream.of(arr).anyMatch(x -> x == (i + 1));
			if (contains == false) {
				smallNumber = i + 1;
				if (smallNumber < 0) {
					smallNumber = 1;
				}
				break;
			}
		}

	}

}
```
