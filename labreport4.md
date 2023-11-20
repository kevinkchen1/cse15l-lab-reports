# Kevin Chen CSE 15L Lab Report 4

## Step 1: Connect to ieng6

Command: `ssh cs15lfa23pe@ieng6.ucsd.edu`

**Keys Pressed:** *`<up> <up> <up> <up> <up> <up> <up> <up> <Enter>` 
The `ssh cs15lfa23pe@ieng6.ucsd.edu` command was used 8 commands ago so I pressed the up arrow 8 times to get to that command and then ran it to connect to ieng6.


![image](https://github.com/kevinkchen1/cse15l-lab-reports/assets/108315438/2e59424e-ac9d-4752-abcc-7db540500a9c)


## Step 2: Clone repository with SSH url

Command: `git clone git@github.com:kevinkchen1/cse15llab7.git` `cd lab7`


**Keys Pressed:** *`Ctrl-C: git@github.com:kevinkchen1/cse15llab7.git` `Typed on command line: git clone` `Ctrl-V` `<Enter>`*
I used `Ctrl-C` to copy the ssh clone URL from my forked lab7 Github repository and then `Ctrl-V` to paste it into the command line after `git clone`. Then I pressed enter to run the completed command to clone the forked repository. Then I `cd lab7` to change the directory to the lab7 respository.


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






