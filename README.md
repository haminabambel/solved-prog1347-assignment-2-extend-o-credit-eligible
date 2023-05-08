Download Link: https://assignmentchef.com/product/solved-prog1347-assignment-2-extend-o-credit-eligible
<br>
<strong>Objectives:</strong>

<ul>

 <li>Creation and use of functions</li>

 <li>Passing arguments into parameters</li>

 <li>Splitting your code into modular functions</li>

 <li>Making appropriate design decisions</li>

 <li>Following stated requirements</li>

</ul>

<strong>Overview of Requirements</strong>

<ul>

 <li>Write a program that uses a function to calculate the result of raising one number to the power of another.</li>

 <li>Use an on-screen menu to prompt for user input.

  <ul>

   <li>The menu must look like this:</li>

  </ul></li>

</ul>

Power Menu:

<ol>

 <li>Change base</li>

 <li>Change exponent</li>

 <li>Display base raised to exponent</li>

 <li>Exit program</li>

</ol>

Option?

For example, the function should be able to compute the fact that 10 to the power 3 is 1000 and that 20 to the power 4 is 160000. Test your program with more than the above two sets of values.

<strong>Detailed Functional Requirements</strong>

<strong>Actions:</strong>

<ul>

 <li>The user must be prompted for the base or exponent whenever they choose that option. The result must be calculated and displayed on user request through a menu option (as above).</li>

 <li>The program <strong>must loop and must only exit</strong> when the appropriate menu item is chosen.</li>

</ul>

<strong>Calculation:</strong>

The power calculation must be done using a function that you create. Requirements for this function:

<ul>

 <li>It must be called calculatePower.</li>

 <li>It must take two parameters (the base and exponent).</li>

 <li>It must return the calculated value to the calling function.</li>

 <li>It must use a loop to calculate the power. Multiple if-else statements are not permitted in this function!</li>

</ul>

<strong>Values:</strong>

<ul>

 <li>Initial values for the base and exponent must be 1.</li>

 <li>The base and exponent values are always integers.</li>

 <li>The base number (that is, the number which is being raised to the exponent) must only be in the range 1 to 25.</li>

 <li>The exponent must only be in the range 1 to 5.</li>

 <li>You can assume that the user will not be hostile and won’t try to enter a number that is larger than the largest possible int.</li>

 <li>Range checking for the base and exponent must be done using a function that you create. This is one function that is called twice, once for checking the base, once for checking the exponent.  Requirements for this function:

  <ul>

   <li>It must be called checkRange.</li>

   <li>It must take at least three parameters (value to check, minimum acceptable value, maximum acceptable value). You can have more parameters if you wish (but you really should be very sure about your design if you add more).

    <ul>

     <li>This implies that you should not create one range checking function for the base and a second one for the exponent <strong>unless </strong>all those functions do is have a single line that calls checkRange with the appropriate arguments.</li>

    </ul></li>

   <li>It must return 0 if the value is out of range and 1 if the value is within the specified range.</li>

   <li>It must <strong>not </strong>display any output. The calling function must print an error message if the value is out of range.</li>

  </ul></li>

 <li>Out-of-range bases and exponents must restore the previous value.

  <ul>

   <li>Do <strong>not</strong> reprompt the user for a valid base or exponent if they enter one that is out of range.</li>

   <li>As stated in an earlier requirement, display an error message if the value is out of range (but not in calculatePower).</li>

  </ul></li>

</ul>

<strong>Other Requirements</strong>

<ul>

 <li>It must not use scanf() or fscanf(). Using cin is discouraged unless you handle the issues associated with using cin (which you should be aware of already if you’re thinking of using cin).</li>

 <li>It must not use global variables (covered in the Scope and Style lecture).</li>

 <li>It must not use goto.</li>

 <li>It must not use the pow() function.</li>

 <li>You must not call the main() function recursively (in other words, don’t have a call to main() within any of your functions).</li>

 <li>Appropriate programming style as discussed in class and in the Course Notes must be used.</li>

 <li>Function prototypes for all functions you create (except main()) must be used.</li>

</ul>

<strong>File Requirements:</strong>

<ul>

 <li>Call your project cA2.</li>

 <li>You must call your source file cA2.c or cA2.cpp to generate cA2.exe.</li>

 <li>Call your ZIP file cA2.zip.</li>

</ul>

<strong>getNum():</strong>

You can (and should) use a function such as the following to get input:




#pragma warning(disable: 4996)

int getNum(void)

{

/* the array is 121 bytes in size; we’ll see in a later lecture how we can improve this code */

char record[121] = {0}; /* record stores the string */

int number = 0;

/* NOTE to student: indent and brace this function consistent with your others */

/* use fgets() to get a string from the keyboard */

fgets(record, 121, stdin);

/* extract the number from the string; sscanf() returns a number

* corresponding with the number of items it found in the string */

if( sscanf(record, “%d”, &amp;number) != 1 )

{

/* if the user did not enter a number recognizable by

* the system, set number to -1 */

number = -1;

}

return number;

}

This function should be put at the end of your source file.

Make sure that you create a function comment and prototype for getNum(). Reformat the bracing and indentation of getNum if required to match your own style.


