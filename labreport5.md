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

<img width="504" alt="image" src="https://github.com/kevinkchen1/cse15l-lab-reports/assets/108315438/9da4addf-cf58-40d1-ac16-42cc43240d68">





The original post from a student with a screenshot showing a symptom and a description of a guess at the bug/some sense of what the failure-inducing input is. (Don’t actually make the post! Just write the content that would go in such a post)
A response from a TA asking a leading question or suggesting a command to try (To be clear, you are mimicking a TA here.)
Another screenshot/terminal output showing what information the student got from trying that, and a clear description of what the bug is.
At the end, all the information needed about the setup including:
The file & directory structure needed
The contents of each file before fixing the bug
The full command line (or lines) you ran to trigger the bug
A description of what to edit to fix the bug


Command: `git clone git@github.com:kevinkchen1/cse15llab7.git` `cd lab7`


**Keys Pressed:** *`Ctrl-C: git@github.com:kevinkchen1/cse15llab7.git` `Typed on command line: git clone` `Ctrl-V` `<Enter>`*
I used `Ctrl-C` to copy the ssh clone URL from my forked lab7 Github repository and then `Ctrl-V` to paste it into the command line after `git clone`. Then I pressed enter to run the completed command to clone the forked repository. Then I `cd lab7` to change the directory to the lab7 repository.


![image](https://github.com/kevinkchen1/cse15l-lab-reports/assets/108315438/abf77b5a-449a-4b60-aca1-a83c358e1fe9)


## Step 3: Running JUnit Tests with ListExampleTests

Commands:
1. `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar`

**Keys Pressed:** *`<up> <up> <up> <up> <up> <Enter>`* The `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` command was used 5 commands ago so I pressed the up arrow 5 times to get to that command and then ran it.

2. `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests`
   
**Keys Pressed:** *`<up> <up> <up> <up> <up> <Enter>`* Similarily, after running the previous command to compile the JUnit Test, the `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests` was used 5 commands ago, so once again I pressed the up arrow 5 times to get to that command and then ran it to run the ListExamplesTests.

   
![image](https://github.com/kevinkchen1/cse15l-lab-reports/assets/108315438/925f05be-c5a9-491e-83d2-41c64f960242)

## Step 4: Edit the code to fix the failing test

**Keys Pressed:** from cursor at top, left of the file: `329w`, `e`, `x`, `i`, `"2"`, `<esc>` `:wq`
After opening the ListExamples.java file in vim, my cursor was at the top, left of the file and I wanted to move the cursor to the line with the bug in the fastest way possible. To do this, I moved the cursor forward by 329 words with `329w`, moved to the end of the current word "index" with `e` to land on "1" of `index1`. Then I pressed `x` to delete the "1", pressed `i` to enter insert mode and entered "2" to change the variable to `index2`. I then pressed `<esc>` to go back to normal mode and then used the command `:wq` to save and exit the file.

![image](https://github.com/kevinkchen1/cse15l-lab-reports/assets/108315438/5dfc1daa-622a-4419-bc93-57443ec02b50)


## Step 5: Run the tests to show that they now succeed

Commands: 
1. `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java`

**Keys Pressed:** `<up> <up> <up>` `<Enter>`
The `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` command was used 3 commands ago so I pressed the up arrow 3 times to get to that command and then ran it. 


2. `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests` 

**Keys Pressed:** `<up> <up> <up>` `<Enter>`
After running the previous command to compile the JUnit Test, the `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests` was used 5 commands ago, so once again I pressed the up arrow 5 times to get to that command and then ran it to run the ListExamplesTests.

<img width="565" alt="image" src="https://github.com/kevinkchen1/cse15l-lab-reports/assets/108315438/9f247606-3854-49bd-bbf7-dc8b4e15a324">


## Step 6: Commit and push changes to Github

**Keys Pressed:** `git add ListExamples.java` `<enter>` `git commit -m"changed var"` `<enter>` `git push` `<enter>`
After debugging and making edits to ListExamples.java, I want to have these changes reflected on the remote repository on Github. To do this, I do `git add` from the command line to add `ListExamples.java` as a file to be included for the commit. After that, I can create the commit with a message "changed var" through `git commit -m"changed var"`. With the commit created, I can now push changes to my Github repository with `git push`, and the edits I commited will now show up on Github.

<img width="760" alt="image" src="https://github.com/kevinkchen1/cse15l-lab-reports/assets/108315438/94e2c300-1a55-4bd5-a845-75b27cf2a191">

<img width="693" alt="image" src="https://github.com/kevinkchen1/cse15l-lab-reports/assets/108315438/ba105c4c-f63b-40cd-96b9-8d724e011604">







