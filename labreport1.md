# **Kevin Chen CSE 15L Lab Report 1**
We learned 3 terminal commands in the first week of CSE 15L. These are cd, ls and cat, which stand for "change directory", "list" and "concatenate".

I will cover 3 examples of using each Unix command.

**Using cd**

Using cd with no arguments
   
Command: cd

Working directory: /home

![image](https://github.com/kevinkchen1/cse15l-lab-reports/assets/108315438/8abad140-7b3b-4e81-a1fb-00a13f9b1dd2)

The output after I run cd is just /home, which is the home directory. This is because running cd will always switch back to home directory, regardless of the current directory. This output is correct, with no error, as running cd with no directory after should return to home.<br>


Using with a path to a directory as an argument
   
Command: cd lecture1/messages

Working directory: /home/lecture1/messages

![image](https://github.com/kevinkchen1/cse15l-lab-reports/assets/108315438/c8284048-eb6d-42bf-81a4-9e1067234e02)

The result is correct and there are no errors with this command with the given argument. The output of running this in the home directory is that the working directory is now switched to a directory called messages as a result of the given path to directory as an argument in the cd command.


Using with a path to a file as an argument
   
Command: cd lecture1/Hello.java

Working directory: /home

![image](https://github.com/kevinkchen1/cse15l-lab-reports/assets/108315438/0a696e53-99b1-4c3b-a670-aa0050f34327)

In the photo above, I also tried to cd using a path to a file as an argument, starting from the home directory with the path the file as cd lecture1/Hello.java. This causes an error because Hello.java is not a directory, but instead a Java file. cd can only switch into other directories.


**Using ls**

Using ls with no arguments

Command: ls

Working directory: /home

![image](https://github.com/kevinkchen1/cse15l-lab-reports/assets/108315438/86075145-ebaa-44da-8d62-b2a205b5b8c0)


Using ls with no arguments will list out the files and directories in the current working directory. This output is correct and is not an error. In this example, I'm currently in the home directory and ls will display all contents in home, which is just the lecture1 directory. 


Using ls with a path to a directory as an argument
   
Command: ls lecture1/messages

Working directory: /home

![image](https://github.com/kevinkchen1/cse15l-lab-reports/assets/108315438/cff186a7-40ad-4d6a-8d80-265b18200dcb)


Using ls with a path to a directory will list the contents of the directory that the path specifies and does not cause an error. In the picture above, when I type ls lecture1/messages, it lists the contents in messages which are the txt files.


Using ls with path to a file as an argument
   
Command: ls lecture1/Hello.java

Working directory: /home

![image](https://github.com/kevinkchen1/cse15l-lab-reports/assets/108315438/1e96c1eb-dfb8-421f-a8f6-ae79a1ee6698)


Using ls with a path to a file as an argument does not cause an error, and will output the path to that file. In the example above, ls lecture1/Hello.java outputs the file path of argument.


**Using cat**

Using cat with no arguments
   
Command: cat

Working directory: /home

![image](https://github.com/kevinkchen1/cse15l-lab-reports/assets/108315438/981e9899-dea4-4e15-8090-c1e51211ecd8)


Using cat without any arguments will result in nothing happening and a new input line below where, as the command will wait for input from the user. This itself is not an error yet because it is waiting for more input from the user. This is shown in the image above.


Using cat with a path to a directory as an argument

Command: cat lecture1/messages

Working directory: /home

![image](https://github.com/kevinkchen1/cse15l-lab-reports/assets/108315438/476e717d-6943-4847-894b-0858d686cdb7)


Using cat with a path to a directory will result in an error, because cat is used to display the content of files and this isn't possible when given a directory as an argument. This is shown in the picture above with cat messages, and there is an error after.


Using cat with a path to a file as an argument

Command: cat lecture1/messages/zh-cn.txt

Working directory: /home

![image](https://github.com/kevinkchen1/cse15l-lab-reports/assets/108315438/61e01679-a76a-4449-a3bd-99370921105e)


Using cat with a path to a file as an argument will display the contents of the file that is in the argument without any errors. This is shown with cat zh-cn.txt. Running cat on this file displays the text that the file contains.
