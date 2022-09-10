
#include <iostream>

/**------------------------------------------

    Program 1: Layered Pine Tree
    Prompt for the number of tree layers and display
    ASCII layered pine tree

    Course: CS 141, Fall 2022.
    System: MacOS and G++
    Author: Dr. Sara Riazi
 ---------------------------------------------**/

#include <iostream>   // for cin and cout
#include <iomanip>    // for setw. The number in setw(...) is the total of blank spaces including the printed item.

using namespace std; // so that we don't need to preface every cin and cout with std::

int main()
{
    // Display the menu and get the user choice
    int menu_option = 0;
    cout << "Program 1: The Pine Tree            \n"
         << "Choose from the following options:  \n"
         << "   1. Display the HELLO graphic  \n"
         << "   2. Display The Pine Tree        \n"
         << "   3. Exit the program          \n"
         << "Your choice -> ";
    cin >> menu_option;
    
    if (menu_option == 3) { // Handle menu option of 3 to exit
        exit(0); // The call to exit the code successfully (0 means the runs didn't encounter any problem).  
    }

    else if (menu_option == 1) { // Handle menu option of 1 to display custom ASCII graphics
        // Display ASCII graphics for "HELLO".  
	// The main purpose of this part is to give you hints about usnig setw and setfill and their behaviors.
	
	//the character for the frame of our display.
	char frame = '-';
	cout << "Enter your frame character: ";
        cin >> frame;	
	cout << endl;
	// The goal of next three lines is to print a line with 77 dashes differently. 
	cout << setfill(frame); //change the default character for filling the fields defined using setw. You can change it fill to different character to see the difference.
        cout << setw(78) << "\n"; // \n counts in 78 so you will get 77 dashes plus one \n  
        cout << setw(78) << endl; ///after setfill you need to pass a string or character to push setfil to fill the field, otherwise you will see an empty line for this instruction. See the differnce in output from this line and the above line. 
        cout << setw(77) << frame << endl; //I use 77 with setfill and one extra at the end to get the same result
        
	cout << setw(8) << " " << "   **    **    ********    **         **         ********    " << setw(9) << "\n";
        cout << setw(8) << " " << "   **    **    ********    **         **         ********    " << setw(9) << "\n";
        cout << setw(8) << " " << "   **    **    **          **         **         **    **    " << setw(9) << "\n";
        cout << setw(8) << " " << "   ********    ********    **         **         **    **    " << setw(9) << "\n";
        cout << setw(8) << " " << "   ********    ********    **         **         **    **    " << setw(9) << "\n";
        cout << setw(8) << " " << "   **    **    **          **         **         **    **    " << setw(9) << "\n";
        cout << setw(8) << " " << "   **    **    ********    ********   ********   ********    " << setw(9) << "\n";
        cout << setw(8) << " " << "   **    **    ********    ********   ********   ********    " << setw(9) << "\n";
        cout << setw(77) << frame << endl; //the extra character is - so in total we will have 77 dashes.
        cout << setw(78) << "\n"; //again, the extra character is \n so you have set the width to 78	
	
	//you can do it this way using a for-loop too 
	 for (int i = 0; i < 77; i++) {
            cout << frame;
        }
        cout << endl;



    } else if (menu_option == 2) {
        // Prompt for and get the number of layers for the tree.
        int number_of_tree_layers = 0;
	cout << "Number of tree layers -> ";
        cin >> number_of_tree_layers;
        
	cout << endl; //do not remove this line. It is essential for the autograder! 

	

	int square = 5 + (number_of_tree_layers - 1) * 2;                /* this varible signifies  maximum number of character that will be printed in last row,
                                                                 it will help   calculating total number of spaces required before each row */

// PRINTING PALM TREE

for (int i = 1; i <= number_of_tree_layers; i++)                // this for loop will help printing each layer one by one , each layer has 3 rows

{
    int start_space = square / 2 - (i - 1) + 1;            // for each layer , this variable calculate the total number of space required in first row of layer
    int start_star = 2 * i - 1;                            //   for each layer , this variable calculate the total number of star to be printed in first row of layer

    for (int j = 1; j <= 3; j++)                   // this for loop will print 3 rows of each layer one by one and also change the row
    {
        // spacing - this for loop is to print total number of initial spaces required before printing stars in each vertical layer
        for (int k = 1; k <= start_space - j; k++)
        {
            cout << " ";
        }

        // this for loop will print total number of required '*' character for that vertical layer
        for (int k = 1; k <= start_star + 2 * (j - 1); k++)
        {
            cout << "*";
        }

        cout << endl;                      // changing row  after printing each row of layer
    }
}
// PRINTING ROOT

int root_length = 2 * number_of_tree_layers;                  /* root_lenth will signify how long will the root be depending on number_of_tree_layer
                                                             it can be easily obeserved that root length is double of the number of layers of palm tree(looking at pattern )*/

for (int i = 0; i < root_length; i++)                   /* this for loop will help to print the root in verical direction,
                                                            it will  change the line as soon as 1 layer of root is printed*/

{
    // spacing  - this for loop is to print total number of initial spaces required before printing root in each vertical layer
    for (int k = 1; k <= number_of_tree_layers; k++)
        cout << " ";

    // this for loop will print total number of required '|' character for that vertical layer
    for (int k = 0; k < 3; k++)
        cout << "|";

    cout << endl;                  // changing row  after printing each row of root
}
    } //end if( menu_option == 2)


    cout << endl; //DO NOT CHANGE THIS LINE
    
    return 0;
}
STUDENT
Gabriela Pinela-Padilla
AUTOGRADER SCORE
0.0 / 75.0
QUESTION 2
Program Style Grading
- / 25.0 pts
