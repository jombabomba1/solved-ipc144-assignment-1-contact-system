Download Link: https://assignmentchef.com/product/solved-ipc144-assignment-1-contact-system
<br>
The two (2) assignments this semester will revolve around building a Contact system that is searchable and efficient.

In the first assignment, you will build a Contact structure that contains other structures representing the contact Name, Address and phone Numbers.

<h1>Introduction to C Strings</h1>

The section of the notes regarding C strings is not completely covered until week 11, however you will need to know some very simple facts about string handling in C for this assignment.  If you wish, you can read more about string handling here: <a href="http://scs.senecacollege.ca/%7Eipc144/pages/content/strin.html">http://scs.senecacollege.ca/~ipc144/pages/content/strin.html</a>

A C string is an array of type char with a special terminator character called the null byte. When declaring a C string array it is necessary to always make the array <u>one character larger than the</u> <u>maximum</u> number of characters it needs to be able to store.

If we need to be able to store up to <strong>30 characters</strong>, this is the declaration of the array:

char firstName[31]; // the size is 31!

To read a C string (user input), code the following:

scanf(“%30s”, firstName);

<strong><em>Note</em></strong><em>: There is no ampersand (&amp;) before firstName, the name of an array is its address. 30 specifies the max number of characters to be read </em>

To print a C string, code the following:

printf(“%s
”, firstName);

Here is a code sample that reads and writes a C string:

#include&lt;stdio.h&gt;

#define NAME_SIZE 30 int main(void)

{      char firstName[NAME_SIZE + 1];

printf(“Enter the contact’s first name, maximum 30 characters: “);  scanf(“%30s”, firstName); //user enters: Fred

printf(“You entered: %s.
”, firstName); //outputs: You entered: Fred.




return 0;

}

<h1>Milestone 1</h1>

Download or clone Assignment 1 (<strong>A1</strong>) from <a href="https://github.com/Seneca-144100/IPC-Project">https://github.com/Seneca-144100/IPC-Project</a>

Open the project file for MS1 and look inside. You will find a file named contacts.h. The .h extension identifies this file as a header file. Header files contain declarations of structs and function prototypes. In this header file, the struct Name is already declared.

Structure Name has three (3) members:  <strong>firstName</strong>, a C string that can hold up to 30 characters <strong>middleInitial</strong>, a C string that can hold up to 6 characters, and <strong>lastName</strong>, a C string that can hold up to 35 characters.

struct Name

{

char firstName[31];       char middleInitial[7];

char lastName[36];

};

Declare two (2) more structures named Address, and Numbers, in the header file, <strong>contacts.h</strong>

Structure Address has five (5) members:  <strong>streetNumber, street</strong>, <strong>apartmentNumber</strong>, <strong>postalCode</strong>, and <strong>city</strong>.

streetNumber:  int, (<strong><u>logic</u></strong> for this field should enforce values greater than 0)  street:         C string, up to 40 characters

apartmentNumber:  int, (<strong><u>logic</u></strong> for this field should enforce values greater than 0)

postalCode:        C string, up to 7 characters city:                 C string, up to 40 characters

Structure Numbers has three (3) members:  <strong>cell</strong>, <strong>home</strong>, and <strong>business</strong>. These are all C strings that can hold up to 10 characters.

<strong>Milestone 1 Submission </strong>

Milestone 1 is to be done in the lab and shown to your instructor, there is no need to submit on matrix.

<strong>Milestone 2 </strong>

<h1>Application Logic</h1>

Open the project file for MS2 and look inside. You will find a source file named <strong>a1ms2.c</strong>. Use this file and in it code the main() function by implementing the following. Make sure that your project contains the <strong>contacts.h</strong> header file from milestone 1:

<ul>

 <li>Declare a variable of type Name (use a self-describing variable name) to be used for storing a contact’s full name

  <ul>

   <li>Initialize each member to an empty C string</li>

  </ul></li>

 <li>Declare a variable of type Address (use a self-describing variable name) to be used for storing a contact’s address information

  <ul>

   <li>Initialize the members so numeric values are set to zero and char arrays are set to an empty C string</li>

  </ul></li>

 <li>Declare a variable of type Numbers (use a self-describing variable name) to be used for storing a contact’s phone(s) information

  <ul>

   <li>Initialize each member to an empty C string</li>

  </ul></li>

 <li>Display to the screen a welcome message:</li>

</ul>

&gt;Contact Management System&lt;

&gt;————————-&lt;  (25 dashes followed by a single newline)

<table width="622">

 <tbody>

  <tr>

   <td width="622"><u>Note</u>:Structure member’s <strong>middleInitial</strong>, <strong>apartmentNumber</strong>, <strong>cell</strong>, <strong>home</strong>, and <strong>business</strong> are all <strong><u>optional</u></strong><strong> <u>values</u></strong>. Not all people have a middle initial, live in an apartment, or have multiple phone numbers. When asking the user for this information you should first ask if they wish to enter it:Member <strong>middleInitial</strong> prompt (member of the Name type):&gt;Do you want to enter a middle initial(s)? (y or n): &lt;Member <strong>apartmentNumber</strong> prompt (member of the Address type): &gt;Do you want to enter an apartment number? (y or n): &lt;Member <strong>cell</strong> prompt (member of the Numbers type):&gt;Do you want to enter a cell phone number? (y or n): &lt;Member <strong>home</strong> prompt (member of the Numbers type):&gt;Do you want to enter a home phone number? (y or n): &lt;Member <strong>business</strong> prompt (member of the Numbers type):&gt;Do you want to enter a business phone number? (y or n): &lt;</td>

  </tr>

 </tbody>

</table>

<u>Figure</u>: 1.2.1 – Prompts




<h2>Contact Name</h2>




<ul>

 <li>Prompt the user to enter the required member data for the Name First, ask for the first name:</li>

</ul>

&gt;Please enter the contact’s first name: &lt;

<ul>

 <li>Read and store the C string value the user enters into the appropriate Name member</li>

</ul>




<ul>

 <li>Prompt the user if a middle initial(s) value needs to be entered (<em>see <strong>figure: 1.2.1</strong> above regarding optional values for example prompt</em>)

  <ul>

   <li>Evaluate the entered value; if an ‘n’ is entered proceed with the next member entry otherwise prompt for the middle initial(s):</li>

   <li>&gt;Please enter the contact’s middle initial(s): &lt;</li>

   <li>Read and store the C string value the user enters into the appropriate Name member</li>

  </ul></li>

</ul>




<ul>

 <li>Prompt the user to enter the last name:</li>

</ul>

&gt;Please enter the contact’s last name: &lt;

<ul>

 <li>Read and store the C string value the user enters into the appropriate Name member</li>

</ul>




<h2>Contact Address</h2>




<ul>

 <li>Prompt the user to enter the required member data for the Address First, ask for the street number:</li>

</ul>

&gt;Please enter the contact’s street number: &lt;

<ul>

 <li>Read and store the number entered by the user into the appropriate Address member</li>

 <li><u>Hint</u>: Review the specifications for this structure member’s valid values</li>

</ul>




<ul>

 <li>Prompt the user to enter the street name:</li>

</ul>

&gt;Please enter the contact’s street name: &lt;

<ul>

 <li>Read and store the C string value the user enters into the appropriate Address member</li>

</ul>




<ul>

 <li>Prompt the user if an apartment number needs to be entered (<em>see <strong>figure: 1.2.1</strong> above regarding optional values for example prompt</em>)

  <ul>

   <li>Evaluate the entered value; if an ‘n’ is entered proceed with the next member entry otherwise prompt for the apartment number:</li>

   <li>&gt;Please enter the contact’s apartment number: &lt;</li>

   <li>Read and store the number entered by the user into the appropriate Address member</li>

   <li><u>Hint</u>: Review the specifications for this structure member’s valid values</li>

  </ul></li>

</ul>




<ul>

 <li>Prompt the user to enter the postal code:</li>

</ul>

&gt;Please enter the contact’s postal code: &lt;

<ul>

 <li>Read and store the C string value the user enters into the appropriate Address member</li>

</ul>




<ul>

 <li>Prompt the user to enter the city:</li>

</ul>

&gt;Please enter the contact’s city: &lt;

<ul>

 <li>Read and store the C string value the user enters into the appropriate Address member</li>

</ul>

<h2>Contact Numbers</h2>




<ul>

 <li>Prompt the user to enter the required member data for the Numbers First, prompt the user if a <strong>cell phone number</strong> needs to be entered (<em>see <strong>figure: 1.2.1</strong> above regarding optional values for example prompt</em>)

  <ul>

   <li>Evaluate the entered value; if an ‘n’ is entered proceed with the next member entry otherwise prompt for the cell phone number:</li>

   <li>&gt;Please enter the contact’s cell phone number: &lt;</li>

   <li>Read and store the number entered by the user into the appropriate Numbers member</li>

  </ul></li>

</ul>




<ul>

 <li>Prompt the user if a <strong>home phone number</strong> needs to be entered (<em>see <strong>figure: 1.2.1</strong> above regarding optional values for example prompt</em>)

  <ul>

   <li>Evaluate the entered value; if an ‘n’ is entered proceed with the next member entry otherwise prompt for the home phone number:</li>

   <li>&gt;Please enter the contact’s home phone number: &lt;</li>

   <li>Read and store the number entered by the user into the appropriate Numbers member</li>

  </ul></li>

</ul>




<ul>

 <li>Prompt the user if a <strong>business phone number</strong> needs to be entered (<em>see <strong>figure: 1.2.1</strong> above regarding optional values for example prompt</em>)

  <ul>

   <li>Evaluate the entered value; if an ‘n’ is entered don’t prompt for this value otherwise prompt for the business phone number:</li>

   <li>&gt;Please enter the contact’s business phone number: &lt;</li>

   <li>Read and store the number entered by the user into the appropriate Numbers member</li>

  </ul></li>

</ul>

Test the above logic and your 3 structures by referring to the below sample output (input’s are identified in <strong>RED</strong>).  Your output should match exactly:




<h2>Sample Output</h2>




Contact Management System

————————-

Please enter the contact’s first name: Tom

Do you want to enter a middle initial(s)? (y or n): y

Please enter the contact’s middle initial(s): L. A. Please enter the contact’s last name: Wong Song Please enter the contact’s street number: 20

Please enter the contact’s street name: Keele Street

Do you want to enter an apartment number? (y or n): y Please enter the contact’s apartment number: 40

Please enter the contact’s postal code: A8A 4J4

Please enter the contact’s city: North York

Do you want to enter a cell phone number? (y or n): Y

Please enter the contact’s cell phone number: 9051116666 Do you want to enter a home phone number? (y or n): Y

Please enter the contact’s home phone number: 7052227777

Do you want to enter a business phone number? (y or n): Y

Please enter the contact’s business phone number: 4163338888




Contact Details

—————

Name Details:

First name: Tom

Middle initial(s): L. A. Last name: Wong Song




Address Details:

Street number: 20

Street name: Keele Street

Apartment: 40

Postal code: A8A 4J4

City: North York




Phone Numbers:

Cell phone number: 9051116666

Home phone number: 7052227777

Business phone number: 4163338888

Structure test for Name, Address, and Numbers Done!

<h2>Milestone 2 Reflection</h2>

Please provide answers to the following in a text file named <strong>reflect.txt.</strong>

In <u>three</u> or more paragraphs and a <strong><u>minimum</u> of 150 words</strong>, explain what you learned while doing these first two milestones.  In addition to what you learned, <strong>y</strong><strong>our reflection should <u>also include the following</u></strong>:

<ul>

 <li>Can you think of a more efficient way to ask a user to add the required information to each data field? Justify your thoughts with an example.</li>

 <li>Discuss the differences between a C string and a primitive character array. What would happen if  you attempt to display the contents of a primitive character array (not a C string) using the printf specifier “%s”?</li>

</ul>

<strong>Reflections will be graded based on the published rubric (</strong><a href="https://github.com/Seneca-144100/IPC-Project/tree/master/Reflection%20Rubric.pdf">https://github.com/Seneca</a><a href="https://github.com/Seneca-144100/IPC-Project/tree/master/Reflection%20Rubric.pdf">144100/IPC-Project/tree/master/Reflection%20Rubric.pdf</a><a href="https://github.com/Seneca-144100/IPC-Project/tree/master/Reflection%20Rubric.pdf"><strong>)</strong></a><strong>.</strong>

<strong><u>Example</u></strong><strong>:  </strong>

<strong>An example reflection answer for <u>Workshop #2</u> is available demonstrating the minimum criteria: </strong><a href="https://github.com/Seneca-144100/IPC-Project/tree/master/Example%20Reflection-WS_2.pdf"><strong>https://github.com/Seneca-144100/IPC-Project/tree/master/Example%20Reflection-WS_2.pdf</strong></a><strong> </strong>

<h2>Milestone 2 Submission</h2>

If not on matrix already, upload your <strong>contacts.h</strong>,<strong> a1ms2.c</strong>, and <strong>reflect.txt</strong> files to your matrix account. Compile your code as follows:

<strong>&gt; gcc -Wall -o ms2 a1ms2.c &lt;ENTER&gt;</strong>

This command will compile your code and name your executable “<strong>ms2</strong>”.  Execute <strong>ms2</strong> and make sure everything works properly.

Then run the following script from your account and follow the instructions (replace profname.proflastname with your professors Seneca userid and <u>replace</u> <strong>NAA</strong> with <u>your</u> section):

<strong>~profname.proflastname/submit 144a1ms2/NAA_ms2 &lt;ENTER&gt;</strong><strong>  </strong>

<strong> </strong><u>Please Note</u>

<ul>

 <li>A successful submission does not guarantee full credit for this workshop.</li>

 <li>If the professor is not satisfied with your implementation, your professor may ask you to resubmit. Resubmissions will attract a penalty.</li>

</ul>

<h3>Milestone 3</h3>

A struct is a data type that contains data members, as you have seen in MS1 and MS2. Up to now the members of our structs have always been comprised of the primitive data types that are part of the C language (int, float, double, char, and arrays of these types).  The C language defines a data member as a member of any type, other than its own type.  So, this means that a struct can contain not only the primitive types but also any type that we ourselves create.

Open the project file for MS3 and look inside.  Modify the <strong>contacts.h</strong> header file to include your work from MS2 and declare another struct named Contact.  Contact has three (3) data members, user-defined types Name, Address and Numbers.  The Name type member should be called “name”, the Address type member should be called “address”, and the Numbers member should be called “numbers”.

<strong> </strong>

<strong>Milestone 3 Submission </strong>

Milestone 3 is to be done in the lab and shown to your instructor, there is no need to submit on matrix.

<h3>Milestone 4</h3>




The focus of this milestone is to change the data input process to use functions.

Open the project file for MS4 and look inside.  Review the <strong>contacts.h</strong> file and copy the contents from your work in MS3 where the comments indicate. Define the following function prototypes in <strong>contacts.h  </strong>

<u>NOTE</u>:

Only code the <strong>prototypes</strong> – NOT the full definitions in this file.  For additional help on defining functions and function prototypes please refer to the file <strong>functionsAndHeaderFiles.pdf</strong> in this milestone directory.  Here is the direct link on <strong>GitHub: </strong><a href="https://github.com/Seneca-144100/IPC-Project/tree/master/A1/MS4/functionsAndHeaderFiles.pdf">https://github.com/Seneca-144100/IPC-Project/tree/master/A1/MS4/functionsAndHeaderFiles.pdf</a><a href="https://github.com/Seneca-144100/IPC-Project/tree/master/A1/MS4/functionsAndHeaderFiles.pdf">.</a> Below is a list of the function prototypes with a full description of what each function should do.

<strong>void getName(struct Name *name)</strong> – Receives a pointer to a Name and performs the actions described below.

<ul>

 <li>Prompt the user to enter the required member data for the Name First, ask for the first name:</li>

</ul>

&gt;Please enter the contact’s first name: &lt;

<ul>

 <li>Read and store the C string value the user enters into the appropriate Name member</li>

 <li>Prompt the user if a middle initial(s) value needs to be entered (see figure: 1.2.1 in milestone 2 above regarding optional values for example prompt)

  <ul>

   <li>Evaluate the entered value; if an ‘n’ is entered proceed with the next member entry otherwise prompt for the middle initial(s):</li>

   <li>&gt;Please enter the contact’s middle initial(s): &lt;</li>

   <li>Read and store the C string value the user enters into the appropriate Name member</li>

  </ul></li>

</ul>

<ul>

 <li>Prompt the user to enter the last name:</li>

</ul>

&gt;Please enter the contact’s last name: &lt;

<ul>

 <li>Read and store the C string value the user enters into the appropriate Name member</li>

</ul>

<strong>void getAddress(struct Address *address)</strong> – Receives a pointer to an Address and performs the actions described below.

<ul>

 <li>Prompt the user to enter the required member data for the Address First, ask for the street number:</li>

</ul>

&gt;Please enter the contact’s street number: &lt;

<ul>

 <li>Read and store the number entered by the user into the appropriate Address member</li>

 <li><u>Hint</u>: Review the specifications for this structure member’s valid values</li>

 <li>Prompt the user to enter the street name:</li>

</ul>

&gt;Please enter the contact’s street name: &lt;

<ul>

 <li>Read and store the C string value the user enters into the appropriate Address member</li>

</ul>

<ul>

 <li>Prompt the user if an apartment number needs to be entered (see figure: 1.2.1 in milestone 2 regarding optional values for example prompt)

  <ul>

   <li>Evaluate the entered value; if an ‘n’ is entered proceed with the next member entry otherwise prompt for the apartment number:</li>

   <li>&gt;Please enter the contact’s apartment number: &lt;</li>

   <li>Read and store the number entered by the user into the appropriate Address member</li>

   <li><u>Hint</u>: Review the specifications for this structure member’s valid values</li>

  </ul></li>

</ul>

<ul>

 <li>Prompt the user to enter the postal code:</li>

</ul>

&gt;Please enter the contact’s postal code: &lt;

<ul>

 <li>Read and store the C string value the user enters into the appropriate Address member</li>

 <li>Prompt the user to enter the city:</li>

</ul>

&gt;Please enter the contact’s city: &lt;

<ul>

 <li>Read and store the C string value the user enters into the appropriate Address member</li>

</ul>

<strong>void getNumbers(struct Numbers *numbers)</strong> – Receives a pointer to a Numbers and performs the actions described below.




<ul>

 <li>Prompt the user to enter the required member data for the Numbers First, prompt the user if a cell phone number needs to be entered (see figure: 1.2.1 in milestone 2 above regarding optional values for example prompt)

  <ul>

   <li>Evaluate the entered value; if an ‘n’ is entered proceed with the next member entry otherwise prompt for the cell phone number:</li>

   <li>&gt;Please enter the contact’s cell phone number: &lt;</li>

   <li>Read and store the number entered by the user into the appropriate Numbers member</li>

  </ul></li>

</ul>

<ul>

 <li>Prompt the user if a home phone number needs to be entered (see figure: 1.2.1 in milestone 2 above regarding optional values for example prompt)

  <ul>

   <li>Evaluate the entered value; if an ‘n’ is entered proceed with the next member entry otherwise prompt for the home phone number:</li>

   <li>&gt;Please enter the contact’s home phone number: &lt;</li>

   <li>Read and store the number entered by the user into the appropriate Numbers member</li>

  </ul></li>

</ul>

<ul>

 <li>Prompt the user if a business phone number needs to be entered (see figure: 1.2.1 in milestone 2 above regarding optional values for example prompt)

  <ul>

   <li>Evaluate the entered value; if an ‘n’ is entered don’t prompt for this value otherwise prompt for the business phone number:</li>

   <li>&gt;Please enter the contact’s business phone number: &lt;</li>

   <li>Read and store the number entered by the user into the appropriate Numbers member</li>

  </ul></li>

</ul>

Open the file <strong>contacts.c</strong> and define the full function definitions (where the comments instruct).

<u>Hint</u>:  The logic for these functions are already done from MS2 found in file <strong>a1ms2.c</strong>




Open the file <strong>a1MS4.c</strong>.  Declare a structure of type Contact in the variable section as noted by the comments.  Similar to the code in MS2, test your Contact structure by calling the new functions added in this milestone.




<strong><u>IMPORTANT</u></strong>:

Declare a <strong>single</strong> standalone instance of a struct Contact.  <strong>All pointers passed to the new functions must reference the <u>members</u> of that </strong><strong>Contact variable.</strong>

<strong>It is <u>not permissible</u> to pass a copy of the address via another pointer variable – doing so will require a resubmission using the above specifications.</strong>

Refer to the below sample output (input’s are identified in <strong>RED</strong>).  Your output should match exactly:

Sample Output

Contact Management System

=========================

Please enter the contact’s first name: <strong>Wilma Dee</strong>

Do you want to enter a middle initial(s)? (y or n): <strong>y</strong> Please enter the contact’s middle initial(s): <strong>N. O.</strong>

Please enter the contact’s last name: <strong>Flint Rubble</strong>

Please enter the contact’s street number: <strong>30</strong> Please enter the contact’s street name: <strong>Bedrock St.</strong>

Do you want to enter an apartment number? (y or n): <strong>y</strong>

Please enter the contact’s apartment number: <strong>12</strong>

Please enter the contact’s postal code: <strong>Z8Z 7R7</strong>

Please enter the contact’s city: <strong>North York</strong>

Do you want to enter a cell phone number? (y or n): <strong>Y</strong>

Please enter the contact’s cell phone number: <strong>9992223333</strong>

Do you want to enter a home phone number? (y or n): <strong>Y</strong>

Please enter the contact’s home phone number: <strong>8881112222</strong>

Do you want to enter a business phone number? (y or n): <strong>Y</strong>

Please enter the contact’s business phone number: <strong>3337779999</strong>




Contact Details

===============

Name Details

————

First name: Wilma Dee

Middle initial(s): N. O.

Last name: Flint Rubble




Address Details

—————

Street number: 30 Street name: Bedrock St.

Apartment: 12

Postal code: Z8Z 7R7

City: North York




Phone Numbers

————-

Cell phone number: 9992223333

Home phone number: 8881112222

Business phone number: 3337779999




Structure test for Contact using functions done!

<h4>Milestone 4 Reflection</h4>

Please provide answers to the following in a text file named <strong>reflect.txt.</strong>

In <u>three</u> or more paragraphs and a <strong><u>minimum</u> </strong>of 150 words, <strong>explain what you learned</strong> from doing milestones three and four.  In addition to what you learned, <strong>y</strong><strong>our reflection should <u>also include the</u> <u>following</u></strong>:

<ul>

 <li>An explanation of why you think this assignment has asked you to code a struct, Contact, that holds three other structs as data members.</li>

 <li>An explanation why it would be <u>poor design</u> to pass a pointer to type Contact as an argument in the functions <strong><em>getName</em></strong>, <strong><em>getAddress</em></strong>, and <strong><em>getNumbers</em></strong>.</li>

</ul>




<strong>Reflections will be graded based on the published rubric (</strong><a href="https://github.com/Seneca-144100/IPC-Project/tree/master/Reflection%20Rubric.pdf">https://github.com/Seneca</a><a href="https://github.com/Seneca-144100/IPC-Project/tree/master/Reflection%20Rubric.pdf">144100/IPC-Project/tree/master/Reflection%20Rubric.pdf</a><a href="https://github.com/Seneca-144100/IPC-Project/tree/master/Reflection%20Rubric.pdf"><strong>)</strong></a><strong>.</strong>

<strong><u>Example</u></strong><strong>:  </strong>

<strong>An example reflection answer for <u>Workshop #2</u> is available demonstrating the minimum criteria: </strong><a href="https://github.com/Seneca-144100/IPC-Project/tree/master/Example%20Reflection-WS_2.pdf"><strong>https://github.com/Seneca-144100/IPC-Project/tree/master/Example%20Reflection-WS_2.pdf</strong></a>

<h4>Milestone 4 Submission</h4>

If not on matrix already, upload <strong>contacts.h</strong>, <strong>contacts.c</strong>, <strong>a1ms4.c</strong>, and <strong>reflect.txt</strong> files to your matrix account. Compile your code as follows:

<strong>&gt; gcc -Wall -o ms4 a1ms4.c contacts.c &lt;ENTER&gt;</strong>

This command will compile your code and name your executable “<strong>ms4</strong>”.  Execute <strong>ms4</strong> and make sure everything works properly.

Then run the following script from your account and follow the instructions (replace profname.proflastname with your professors Seneca userid and <u>replace</u> <strong>NAA</strong> with <u>your</u> section):

<strong>~profname.proflastname/submit 144a1ms4/NAA_ms4 &lt;ENTER&gt;</strong><strong>  </strong>


