# Kevin Chen CSE 15L Lab Report 3


Failure Inducing Input for Buggy Program: 

`@Test
  public void testReverseInPlace2() {
    int[] input2 = {7, 8 ,9};
    ArrayExamples.reverseInPlace(input2);
    assertArrayEquals(new int[]{9, 8 ,7}, input2);
  }`
  

Non Failure Inducing Input:

`@Test 
	public void testReverseInPlace() {
    int[] input1 = { 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3 }, input1);
  }`

Image of symptom:

![image](https://github.com/kevinkchen1/cse15l-lab-reports/assets/108315438/b797141d-0f5c-4a4d-b49c-db20da0057dc)


Method with Bug:

`static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }`
![image](https://github.com/kevinkchen1/cse15l-lab-reports/assets/108315438/42da3e76-02eb-45b3-ae22-c416cf571af4)

Corrected Code:

`static void reverseInPlace(int[] arr) {
    int[] newArr = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArr[i] = arr[arr.length - i - 1];
    }
  }`
  


![image](https://github.com/kevinkchen1/cse15l-lab-reports/assets/108315438/51e1a7f3-71b5-4731-8b40-7975cea8072b)

