# CSE100_PA2_Tester
UCSD CSE100 Spring 2016 PA2 Self-Tester for Students. 

WARNING: THIS SCRIPT DOES NOT COME WITH ANY GUARANTEE. IT IS YOUR RESPONSIBILITY TO MAKE SURE YOUR CODE WORKS CORRECTLY. 

Before you use it, please read the script and make sure you understand what it is doing. I have done extensive commenting so that the script is more understandable. 

** Being able to write these scripts is a skill that we expect you to develop and will make you a much stronger programmer. **

The tester assumes you have the following PA2 directory sturcture: 
```
.
|-- BitInputStream.cpp
|-- BitInputStream.hpp
|-- BitOutputStream.cpp
|-- BitOutputStream.hpp
|-- HCNode.cpp
|-- HCNode.hpp
|-- HCTree.cpp
|-- HCTree.hpp
|-- Makefile
|-- compress.cpp
|-- ty_tester.sh
|-- pa2_input_files
|   `-- (exact files inside this directory does not matter)
|-- refcompress
|-- refuncompress
`-- uncompress.cpp
```

##  What does the tester do?
1. The tester use `make` to compile your code;
  * The tester will exit if `make` fails.
2. It generates a random binary input file and a random text input file for testing using `openssl rand`;
  * On ieng6, the two files will be 5 [MiB](https://en.wikipedia.org/wiki/Mebibyte) in size to keep the running time reasonable;
  * On non-ieng6 machines, the two files will be 10 [MiB](https://en.wikipedia.org/wiki/Mebibyte) in size.
3. The tester will loop through all the input files found in `pa2_input_files` to test them;
  * Accuracy test: For each file, the tester will perform a `compress` and `uncompress` and compare the result with the original file;
    * The tester will exit if an accuracy test fails. 
  * Size test: On ieng6, the tester will also  perform a `refcompress` and compare the sizes to make sure your version beats the reference version in compression ratio. 
    * The tester will continue even if an size test fails. 
4. Temporary files generated by the tester will be deleted upon exit. 

## How to use
1. [Download](https://github.com/tommyang/CSE100_PA2_Tester/raw/master/ty_tester.sh) the script and place it in the correct location (see above).
2. Read the script and make sure you understand what it is doing. * Being able to write these scripts is a skill that we expect you to develop and will make you a much stronger programmer. *
3. Usage information is inside the script. 

Good luck on this PA!

## Credit

This was originally written and used by me a few quarters ago. I made some changes that are inspired by [Raymond's script](https://github.com/cwscx/cse100_pa2_raymond_test) from last quarter. 
