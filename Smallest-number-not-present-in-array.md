# CodilityPerformSolution
This is the solution for smallest number which is not present in array.
Example : 
1. arr[]={1,2,4,5};
   output : 3

2. arr[]={1,2,3,4,5};
   output : 6

3. arr[]={-1,-2};
   output : 1

```java
import java.util.Arrays;
import java.util.stream.IntStream;
public class Solution {

	public static void main(String[] args) {

		int arr[] = { -3, -1, 3, 5, -4 };
		int smallNumber = 1;

		Arrays.sort(arr);
		for (int i : arr) {

			if (i < 0) {
				smallNumber = 1;
			}
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
