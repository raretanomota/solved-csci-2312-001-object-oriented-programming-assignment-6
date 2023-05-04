Download Link: https://assignmentchef.com/product/solved-csci-2312-001-object-oriented-programming-assignment-6
<br>
For this assignment, you will use pointers with dynamic memory, templates, binary files and exception handling to build a multi-purpose, generic, Single Linked List. Anytime you are using dynamic memory, you should have a Copy Constructor, overloaded Assignment Operator, and a Destructor. Though this will be similar in functionality to the C++ Standard Template Library (STL) forward_list, you will create your own using pointers (instead of forward_list, list or vector).




Create a Student struct with a name[20] and a student id.




Overload the &lt;&lt; for a Student.




Create a Node with templated data (so that you can have Nodes of any legitimate data type). Nodes also have pointers to other Nodes (that must be templated). Structs are acceptable means of describing Nodes.




Create a templated List class (templated with the same type of data that is used in your Node). This class should maintain a head pointer to templated Nodes. This is the start of your linked list. This class should have the following member functions:

<strong> </strong>

<strong>Appropriate Constructors</strong>

<strong> </strong>

<strong>Copy Constructor</strong>

<ul>

 <li>Used to give the values of an already declared list to another list</li>

 <li>Deep Copy</li>

 <li>Set the calling object’s headPtr to nullptr</li>

 <li>Copy every node from what is in the parameter to the object created with the Copy Constructor. Consider using your push_back function.</li>

</ul>




<strong>Overloaded Assignment Operator</strong>

<ul>

 <li>Used to assign the values of one already declared list to another already declared list</li>

 <li>Deep Copy</li>

 <li>Delete anything that might be pointed to by headPtr (Considering using your pop_back function)</li>

 <li>Copy every node from what is in the parameter to the called object created by the assignment (again consider using your push_back function)</li>

 <li>Return the value of what is pointed to (return *this). Remember the “this” pointer refers to the object that called the member function</li>

</ul>




<strong>clear</strong>

<ul>

 <li>Delete ALL of the nodes in the linked list</li>

 <li>If you are not concurrently enrolled in Data Structures, you can send your instructor an email asking for the code to the clear function</li>

</ul>

<strong> </strong>

<strong>Destructor</strong>

<ul>

 <li>Get your clear working first…then AND only then should you call clear in your Destructor</li>

</ul>




<strong>push_front</strong> and <strong>push_back</strong>: Pushes data entered as input parameter (Nodes are not input parameter, but nodes will be created and added in the two push functions) into the front or back of the list. Remember that this is an array of characters, so you will #include &lt;cstring&gt;, then use functions like strcpy to set values of character arrays.




<strong>pop_front</strong> and <strong>pop_back</strong>:

<ul>

 <li>Removes data from the front or back of the list</li>

 <li>Should throw an exception if trying to pop an empty list.</li>

</ul>

<strong>printList</strong>: Function should be called printList and implemented with a loop and the &lt;&lt; operator for the data. (&lt;&lt; does not work well when templated, so you can’t overload that operator for the list)




<u>In main:</u>

<ul>

 <li>Create a pointer to a list and assign it to a new pointer</li>

 <li>Demonstrate all functions with multiple ints and use cout statements and the printList to describe each the functions.</li>

 <li>Create a pointer to a second list and construct it with the first list</li>

 <li>Print out the second list to show that your copy constructor worked.</li>

 <li>Create a pointer to a third list, then use = to assign it to the first list</li>

 <li>Print out the third list to show that your assignment operator worked.</li>

 <li>Demonstrate exception handling of pop_front.</li>

 <li>Delete both pointers</li>

</ul>




<ul>

 <li>Declare a list of type Students</li>

 <li>Read in Students from provided binary file students.dat.</li>

 <li>Use push_front to create a linked list of students. Note: if you don’t get 3 records read in from students.dat, you could try writing some binary students before reading them in…then comment that out once you get the students.dat to read in properly.</li>

</ul>




Remember your ROCkET Analysis. You really need to draw out this functionality on paper. When dealing with pointers, it is also critical that you code just a little at a time, then evaluate that functionality. Refer to HW2, where you used the debugger. If you get a run time error, you might be trying to access a null pointer, or perhaps you are not setting deleted links to null pointer.




<strong>Template reminders</strong>: Templates must be defined in the same compilation unit, or you will get a linking error. You should name your definition of a templated class with a .h file. Name your implementation with a .hpp. Then in main, you need to #include both the .h and .hpp files. Because you did a #include of the .hpp file, you do NOT add this to your makefile (if you are using a Linux system)…just the .cpp files. Likewise, if compiling using Visual Studios or XCode, you must remove that code from the project, or add it to the header files(remove not delete!). If you do not you will get a linking error. Since we are templating the Node type, both struct and Class definitions for the Node and list and implementations should have template &lt;typename DATA&gt; at the top of each member function or definition. Then to declare an object you would call like a vector with Node&lt;DATA&gt; or List&lt;DATA&gt;




<strong>Submission</strong>: Like the other homeworks, you must turn in a single zipped file called LastnameHW6 with your .h, .hpp, .cpp files, a readme.txt, and a makefile…all tested on the csegrid.ucdenver.pvt. Remember, if you include a file, you do NOT compile it.