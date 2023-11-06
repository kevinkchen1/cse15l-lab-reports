# Kevin Chen CSE 15L Lab Report 3


**Failure Inducing Input for Buggy Program:**
```
  @Test
  public void testReverseInPlace2() {
    int[] input2 = {7, 8 ,9};
    ArrayExamples.reverseInPlace(input2);
    assertArrayEquals(new int[]{9, 8 ,7}, input2);
  }
```
  

Non Failure Inducing Input:

```
@Test 
public void testReverseInPlace() {
    int[] input1 = { 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3 }, input1);
  }
```

**Image of symptom:**

![image](https://github.com/kevinkchen1/cse15l-lab-reports/assets/108315438/b797141d-0f5c-4a4d-b49c-db20da0057dc)


**Method with Bug (reverseInPlace):**

```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```
**Output when Running JUnit test with bug in method:**

![image](https://github.com/kevinkchen1/cse15l-lab-reports/assets/108315438/42da3e76-02eb-45b3-ae22-c416cf571af4)


**Corrected Code:**

```
static void reverseInPlace(int[] arr) {
    int left = 0;
    int right = arr.length - 1;
    while (left < right) {
        int val = arr[left];
        arr[left] = arr[right];
        arr[right] = val;
        left++;
        right--;
    }
}
```

**Output when Running JUnit test with corrected method:**

<img width="827" alt="Screenshot 2023-11-05 at 8 05 29 PM" src="https://github.com/kevinkchen1/cse15l-lab-reports/assets/108315438/893a2450-374a-4fa6-b4a5-316667219bd0">



## How I debugged:
For the reverseInPlace method, a failure inducing input was any input array that had more than one value in it. In my example failure inducing input array, {7, 8, 9} has 3 values, which led to errors when running the test reverseInPlace2. The problem with the method when running the ReverseInPlace2 is that the array doesn’t sort properly in place because it will end up reusing values that have been sorted. The first error message states that 7 was expected in the 3rd element, but 9 was present. This is because when the method reversing the array and assigning the last value, it uses the first element in the almost sorted in place array which is 9, when it’s supposed to be using the first element from the original array, 7. The way that I debugged this method is I used two pointers for indices of the array, where one starts at the 0th index and the second starts at the last index. I then proceed to swap these two values by saving the value of the left pointer in a variable, setting the value of left pointer to the right one, and then updating the right pointer with the saved left value. I then increase left pointer by 1 and decrease right pointer by 1, moving them closer to the center of the array. This loop continues until the two pointers reach the middle, meaning the entire array has been reversed.


