# Kevin Chen CSE 15L Lab Report 3

## Part 1 - Bugs
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


**Method with Bug (reverseInPlace):**

```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```
**Output when Running JUnit test with bug in method:**

![image](https://github.com/kevinkchen1/cse15l-lab-reports/assets/108315438/b797141d-0f5c-4a4d-b49c-db20da0057dc)


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



**How I debugged:**

For the reverseInPlace method, a failure inducing input was any input array that had more than one value in it. In my example failure inducing input array, {7, 8, 9} has 3 values, which led to errors when running the test reverseInPlace2. The problem with the method when running the ReverseInPlace2 is that the array doesn’t sort properly in place because it will end up reusing values that have been sorted. The first error message states that 7 was expected in the 3rd element, but 9 was present. This is because when the method reversing the array and assigning the last value, it uses the first element in the almost sorted in place array which is 9, when it’s supposed to be using the first element from the original array, 7. The way that I debugged this method is I used two pointers for indices of the array, where one starts at the 0th index and the second starts at the last index. I then proceed to swap these two values by saving the value of the left pointer in a variable, setting the value of left pointer to the right one, and then updating the right pointer with the saved left value. I then increase left pointer by 1 and decrease right pointer by 1, moving them closer to the center of the array. This loop continues until the two pointers reach the middle, meaning the entire array has been reversed.


## Part 2 - Researching Commands

**Command:** grep

**4 Interesting Command Line Options:**
1. `-i`
2. `-r`
3. `-w`
4. `-l`


**Examples with `-i`:**

```
grep -i "six" */*/1468-6708-3-1.txt

Six large controlled population-based studies of
          examining health status over time, we added a sixth
```

![image](https://github.com/kevinkchen1/cse15l-lab-reports/assets/108315438/f72b76c5-6bec-4e16-93b9-738251049e05)


```
grep -i "heart" technical/*/1468-6708-3-10
.txt
        Prevent Heart Attack Trial (ALLHAT) is a randomized,
        Heart, Lung, and Blood Institute (NHLBI). A double-blind,
        compare the rate of fatal coronary heart disease (CHD) or
        National Heart, Lung, and Blood Institute accepted a
        outpatient], heart failure [HF/treated in the hospital or
          Heart Failure Diagnosis
          nocturnal dyspnea, dyspnea at rest, New York Heart
          either of these alone, without other indications of heart
          Heart Failure Diagnostic Criteria
        1) New York Heart Classification functional class III:
        Assessment of Patients with Diseases of the Heart: AHA
```

<img width="727" alt="image" src="https://github.com/kevinkchen1/cse15l-lab-reports/assets/108315438/a55085d1-1620-4bdb-8e3a-ce55b333e061">

When grep is used with `-i` as an option, it indicates that grep will search for lines in the file(s) for the given string, but case insensitive. It's usefulness can be seen in the example, the string being searched for is "six" and if a line in a file has "Six" or any other variation of capitlization, that line will still be matched. This can be very convinient for the user, as they don't have to worry about including multiple variations of the string when searching for matching lines.


**Examples with `-r`:**
```
grep -r "nocturnal" technical/biomed
technical/biomed/1468-6708-3-10.txt:          nocturnal dyspnea, dyspnea at rest, New York Heart
technical/biomed/1471-2202-3-20.txt:          sleep-wake distribution typical for this nocturnal
technical/biomed/1471-2202-3-20.txt:        arrhythmic by lesioning of the SCN. In nocturnal roden
ts,
technical/biomed/1471-2202-3-20.txt:        nocturnal and diurnal species, 
technical/biomed/1472-6793-2-18.txt:          illustrates coordination preferences during the noct
urnal
technical/biomed/1472-6882-1-10.txt:          nocturnal and enter water when chased [ 5 ] . They are
technical/biomed/1472-6882-1-10.txt:          are nocturnal, living in hollow fallen trees during the
technical/biomed/1476-511X-1-2.txt:          not removed the night before, and since nocturnal mice
technical/biomed/rr37.txt:          or nocturnal), use of systemic corticosteroids, use of
```

<img width="939" alt="Screenshot 2023-11-05 at 9 37 03 PM" src="https://github.com/kevinkchen1/cse15l-lab-reports/assets/108315438/b621cbaa-59ad-4ce4-8c48-6736ec1b8484">


```
grep -r "dyspnea" technical/plos  
technical/plos/pmed.0010008.txt:        bronchodilation to relieve dyspnea, antibiotics for intercurrent respiratory tract
technical/plos/pmed.0020017.txt:          physicians and manifested by lessened dyspnea and cancer-related pain. However, this
```

<img width="939" alt="Screenshot 2023-11-05 at 9 37 03 PM" src="https://github.com/kevinkchen1/cse15l-lab-reports/assets/108315438/c9bcec1b-7a6a-44b2-86bd-7487e4789ff5">

When grep is used with `-r` as an option, it indicates that grep will search for lines in the file(s) for the given string in a recursive manner. This means it will search the all the files in the directory in the argument and files in all subdirectories too and return matching line. In the example, the string grep is searching for is "noctural" and it will recursiverly search for this in biomed directory and any subdirectories. The process is the same for searching "dyspnea" as well.


**Examples with `-w`:**

```
grep -w "all" technical/plos/journal.pbio.0020001.txt
        88% of all scientific and technical publications registered by the Science Citation Index
        Canada across all subject areas in
```

<img width="877" alt="image" src="https://github.com/kevinkchen1/cse15l-lab-reports/assets/108315438/946c8cc0-740f-4cfc-8915-658b7409d9a2">


```
grep -w "for" technical/plos/journal.pbio.0020010.txt
        JSTOR is successful for reasons its founders did not intend. Bill Bowen's inspired
        vision was of a solution to libraries' ever-voracious demands for space to house paper
        bold decision at the time, but the future for access to journal literature lies in
        Learned’, many of which are relevant to current access initiatives. The need for grant
        provides a model for others. Much of the credit must go to JSTOR's enterprising president,
        for easy access to high-quality content was the key to the fulfilment of that promise.
        adaptation of the JSTOR purchasing model for selling outside the United States, the United
        of research to provide opportunities for high-quality research conducted outside North
```

<img width="890" alt="image" src="https://github.com/kevinkchen1/cse15l-lab-reports/assets/108315438/2efd3d85-8001-4084-98d1-3fb813266ff2">

When grep is used with `-w` as an option, it indicates that grep will search for lines where there is an occurance of only the string provided. This means it will not return lines where the string is part of a larger word, but only lines where the string is a full word or phrase itself. In the examples, the strings are "all" and "for" which can both be found in larger words. If the user wants to look for lines with specifically these words by themselves, but doesn't use `-w`, then the output might have unwanted results. Using `-w` and then providing the string will ensure that the lines returned have exactly the string in the command.


**Examples with `-l`:**

```
grep -l "Air Force One" *.txt         
  chapter-1.txt
  chapter-10.txt
  chapter-13.2.txt
  chapter-13.4.txt
  chapter-13.5.txt
  chapter-3.txt
```

<img width="616" alt="image" src="https://github.com/kevinkchen1/cse15l-lab-reports/assets/108315438/897aa909-a30c-4840-b86c-a32af34189f1">


```
grep -l "nocturnal" technical/biomed/*.txt            
technical/biomed/1468-6708-3-10.txt
technical/biomed/1471-2202-3-20.txt
technical/biomed/1472-6793-2-18.txt
technical/biomed/1472-6882-1-10.txt
technical/biomed/1476-511X-1-2.txt
technical/biomed/rr37.txt
```

<img width="732" alt="image" src="https://github.com/kevinkchen1/cse15l-lab-reports/assets/108315438/c35ddec3-a608-43d5-b44d-cfaeaae04534">

When grep is used with `-l` as an option, it returns a list of files that contain the string in the command. In the examples above, the first output is all the files that contain the string "Air Force One", second output has all the files that contain the string "nocturnal". This is helpful if the user wants to know which files contain a keyword or relevant phrase they want to filter by, so they can have a smaller list of files to work with. 
