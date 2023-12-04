# Kevin Chen CSE 15L Lab Report 5

## Part 1: EdStem Post from Student


**Student Post:**

List Reverse Method:

<img width="418" alt="image" src="https://github.com/kevinkchen1/cse15l-lab-reports/assets/108315438/0e8deaef-5e46-49fa-a08d-97de3fcc3344">

Test Output:

<img width="893" alt="Screenshot 2023-12-01 at 3 06 32 PM" src="https://github.com/kevinkchen1/cse15l-lab-reports/assets/108315438/a9a6c6f6-7447-4137-abb5-80f755f52396">


Hi,

I'm a student in CSE 15L and I'm running into issues when trying to test my method that is supposed to reverse an array in place. When running a Java file with JUnit tests, it outputs what's shown in the screenshot above, stating that at the second index of the reversed array, the expected value was 7 but the actual value was 9, meaning that the method returned the wrong result. I'm assuming that the input array is not being sorted properly because the last value of the original array is also the last value of the sorted array, which isn't correct. I think the failure inducing input is when there is an array of length greater than 1 and the bug it that when the method is sorting in place, it's reusing values that have already been sorted at a particular index.


**TA Response:**

Hello,

I'd recommend that you run through a simulation of your ReverseInPlace method with an input array that has 2 or more values. Manually, running your method and keeping track of the values of the array you are reversing will help you understand what is going wrong. Additionally, you could add some print statements to show what value is being swapped during each iteration of the loop and see if that is the correct value that should be placed at the corresponding index.


**Student Response:**

<img width="698" alt="image" src="https://github.com/kevinkchen1/cse15l-lab-reports/assets/108315438/0bf89a6a-3520-40aa-aece-71e99066fd78">

<img width="504" alt="image" src="https://github.com/kevinkchen1/cse15l-lab-reports/assets/108315438/9da4addf-cf58-40d1-ac16-42cc43240d68">

Thank you for your help. I decided to use print statements to see what was being replaced during the reversing of the list using the input {7, 8, 9}. I see that everything is being reversed correctly except in the last iteration where the code is swapping out 9 for 9, which is the symptom. The list that is returned is {9, 8, 9} and is incorrect as the input list reversed should be {9, 8, 7}. The bug is that the array is sorting incorrectly because it ends up reusing indices that have been sorted. When debugging it says "swaping 9 for 9" because when the code  is at the last index, it uses the first element in the same sorted array being sorted which is 9, when it’s supposed to be using the first element from the original array, 7. 


**Information About Setup:**

File and directory structure needed:

<img width="801" alt="image" src="https://github.com/kevinkchen1/cse15l-lab-reports/assets/108315438/e64efb8f-8da2-4f0c-a030-97a476ffe6c2">

Inside of my lab3 directory, I had the test.sh file containing the commands to run JUnit tests that would run the ArrayTests.java file. I also had the ArrayTests.java file which contained the code to tests my ReverseInPlace method. The ReverseInPlace method is located in the ArrayExamples.java file. 

Content of Method File before fixing bug:

<img width="418" alt="image" src="https://github.com/kevinkchen1/cse15l-lab-reports/assets/108315438/0e8deaef-5e46-49fa-a08d-97de3fcc3344">

Command I ran to trigger the bug:

`bash test.sh`

bash.sh contains: 

<img width="835" alt="image" src="https://github.com/kevinkchen1/cse15l-lab-reports/assets/108315438/ee1a15ba-023c-471c-bc4a-1ee89b728a8f">


How to fix bug:


The way that I debugged this method is I used two pointers for indices of the array, where one starts at the 0th index and the second starts at the last index. I then proceed to swap these two values by saving the value of the left pointer in a variable, setting the value of left pointer to the right one, and then updating the right pointer with the saved left value. I then increase left pointer by 1 and decrease right pointer by 1, moving them closer to the center of the array. This loop continues until the two pointers reach the middle, meaning the entire array has been reversed.

`static void reverseInPlace(int[] arr) {
    int left = 0;
    int right = arr.length - 1;
    while (left < right) {
        int val = arr[left];
        arr[left] = arr[right];
        arr[right] = val;
        left++;
        right--;
    }
}`

## Part 2: Reflection:


A topic I found very valuable from my lab experience in the second half of this quarter is learning what vim is and how to use. I found it very helpful that I can open up vim on essentially and computer and that it is a very standard tool that all developers use. I found it particularly useful when trying to edit files when logged onto ieng6 because there was no vscode or IDE application that I could open up the files on when on the remote computer.  One insightful aspect I discovered is the power of Vim's editing modes, allowing users to seamlessly switch between different modes (normal, insert, visual, etc.). This flexibility enhances efficiency in text editing tasks.

