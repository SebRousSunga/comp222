### COMP 222


#### 10/05/2023



  1. Overview

    - Take home Quiz time!

    * Chapter 3
        - Practice with Booth's and IEEE floating point conversion
        - Do this friday alongside AVL trees
        - Saturday do part 1 of the Minesweeper

    - Cut off point mid-term
        - Digital logic review
        - Chapter 2
        - Chapter 3


   - Block Diagram
       - Cool litttle diagram of hardware/ storage
       - Highest level 
          - Accept address as input, giving back data as output, like pointesr you know
          - This be chapter 5


   * Floating point and weird output
       - See when you printf a float and it comes out 56.999999
       - Prescision can have a round off error if it can't be displayed as a sum of negative powers
       - 0.25 is a negative power
       - 0.1 decimal, as a floating point
         - You can't
         - Can do 0.1000000056739
         - 0.1 isn't represented as a sum of negative powers


    * Java strings/text vs C string
        - Java contains a class define for String
        - String {}
        - Dozens of built in string methods
        *** Java
          String s = new String("Hello")<- memory allocation of heap , like malloc
                             <- need a constructor too
                             class type tells us s is a reference variable, s contains address of the string, on heap
        ***
        - Objects have no value variable, can only influence objects through reference variables
        - Only value variables of built in types. Like Integers

        - C contains no string data type
           - Array of char
           - int x  = 5;  <- value variable, x has no addres of something, contains value itself
           - value variable or pointer variable
           - C gives more options, pointers of any type, values of any type

       * C strings
           - char datatype
           - char constants

             *** 
                char x;
             - char constants
               - any character typed on keyboard, surronded by single quotse <- important distinction
               - backed from ascii table, key pressed has code represented entered

               * treat liked string, despite no string datatype, does in C++

               * String constants
                  - in double quotes, "abcde" "123"


               * Special char constants
                  - '\n' also own numerical code
                  - '\0' null character ,terminating character

               * diff between string datatype, char constatn, single, double
                 - single double quotes affect context, can't mix and match

               * How to store strings in C
                 - Array of char
                   - could do pointer to char but this is more common
                 - char x[20]; <- string 20 characers long, need null terminator \0
                 - Make big for worst case, if not worst case, just leave empty space
               * how to store string

                 - initizalization expression, at type of declartaion
                     - char[20] = "ABCDE" ; <- Init expression

                 * Cpy content later
                     - Can't initization later
                     - char x[20];

                     x = "abcde" <- wrong, only works during declartoin of variable

                     - lbirary contains a cpy function, called strcpy(char array to cpy into, str_to_cpy)
                     - If you want to know strcpy, just basic character assignment



                  * in heap
                     - x is an array of size 20, one dimensional
                     - each char in string is a char constant, single quotes
                     - single quotes in x
                     - Strings aren't objects, so no properties, no length proptery
                        - Find length by terminator characters
                        - Every string constant contains a null character at the end

                        - Cool trick, copy a 20 constant string into a char x[20] will overflow
                        - as the null character makes the string 21 characters
                     - Can't really directly modify a string char constant
                       - in java

                     - x[0] = 'A';
                     - can modify string one character at a time
                     - well in the array of char
                     - 

                   * Build that string
                     - char y[20];
                     - y[0] = 'p';
                     - y[1] = 'g';
                     - y[2] = 'r';
                     - y[3] = '\0';

                        - terminate string yourself
                        - if no terminator, function like strlen will just keep going, as it never reaches a terminator and end

                        - strcmp sees which string goes first, 0 if both are same


                  * <string.h>

                  	  - special header file
                  	  - C compilier for visual studio implicit includes string.h

                  * Weird ass tokenize function
                      - Java has split function, based on character combinatino, split
                      - string tokenizer , strtok
                      - new 10 20 50
                      - strtok break this apart based on location of spaces

                      - multiple strings in a array
                      - need a matrix, 2d diminesnional array for strings, 
                      - one dim array for single string taht user imputs
                      - 2d for tokenss
                      - Pick sizes for worst case scenerio
                        - remember that arrays are static

                 * Single Precision Format

                     - -127 to 127
                     - 2 to powerof -127, or 2 ^127
                     - exponents to a base of 2

                     - take positive half of number line
                     - 0 then least positive number < than zero
                     - Postiive infinity in front of msp number less than infinite

                     - 2 -127 is a very, very close number to zero
                     - 2 ^127 is very very large number close to infinite- 
                     - limited by bits of exponents
                     - reach whatever 2^127 is
                     - goes larger overflows to infinity, vice versa with 2 ^ -127


                     * denormalized fraction

                        1.....  2 ^-127
                          - no relief from underflow
                          - relax restrictoin of normalized fraction
                          - to 0.1
                          - to 0.01
                          - keep div by 2, can't make exponent anymore negative, but denormalized fraction
