# Clever Project Readme

This project is class scheduling developed by python.

## Installation

Use the package manager [pip](https://pip.pypa.io/en/stable/) to install python. My python version is Python 3.7.0.



## Build Executable and Run
First we create a bash script file names "scheduler", then enter the following into script file.
```bash
#!/bin/bash

if [ $# -ne 1 ]; then
    python ClassScheduler.py
else
python ClassScheduler.py "$1"
```
Then we can run our bash script in the terminal.
```bash
./scheduler test1.json
```

## Design
First, I read data from JSON file and parse it into JSON type.  
Secondly, in this project I used one directory (which works like map) to store the relationship between name and prerequisites. Key is name, value is prerequisites.  
Thirdly, I used two lists, one is to store the courses that already been taken, one is to store the courses haven't been taken.  
For each non-taken courses. If there is no prerequisite or all prerequisites already been taken, then add this course to taken list and delete it from haven't taken list.
 Otherwise, that means the current course can not be took yet, skip it and check for other courses. Repeat this process until all courses are taken.  
 The order we put courses in course taken list is the order we should select courses.  
 Finally, I print all elements in taken list.

## Time Complexity
In this project, the time complexity is O(n^2)

## Space Complexity
In this project, the space complexity is O(n)
