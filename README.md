// Project1.cpp : This file contains the 'main' function. Program execution begins and ends there.
//

//************************************ PROGRAM IDENTIFICATION ***************************************
//*                                                                                                                                                           *
//* PROGRAM FILE NAME: Project1.cpp ASSIGNMENT #: 1                                                            *
//*                                                                                                                                                           *
//* PROGRAM AUTHOR: Andres Gutierrez                                                                                         *
//*																																							  *
//* COURSE #: CSC 24400 11 SEMESTER: Fall 2018 INSTRUCTOR: Dr. Miller                             *
//*                                                                                                                                                           *
//* DUE DATE: September 17, 2018                                                                                                     *
//*************************************************************************************************** 


//*********************************** PROGRAM DESCRIPTION *******************************************
//*                                                                                                                                                            *
//* PROCESS: This program is designed to read a list of data consisting of persons name and       *
//* ages. It is then to echo print the name of the person as many times as the age of the person       *
//* scores.																						                                                        *
//*																																		                        *
//* CLASSES DEFINED                                                                                                                          *
//*                                                                                                                                                             *
//* USER DEFINED FUNCTIONS         
//*                                printMessage - Prints the name and age of the person depending on the age *
//*              
//*                                       
//* INPUT FILES:
//* OUTPUT FILES:
//***************************************************************************************************

#include "pch.h"
#include <iostream>
#include <string>
#include <iomanip> 
using namespace std;

void Header(ostream &Outfile)
{
	// Receives – the output file stream
	// Task - Prints the output preamble
	// Returns - Nothing
	Outfile << endl;
	Outfile << setw(35) << " --------------------------------- " << endl;
	Outfile << setw(35) << "|     START OF PROGRAM OUTPUT     |" << endl;
	Outfile << setw(35) << " --------------------------------- " << endl;
	return;
}



void Footer(ostream &Outfile)
{
	// Receives – the output file stream
	// Task - Prints the output salutation
	// Returns - Nothing
	Outfile << endl;
	Outfile << setw(35) << " --------------------------------- " << endl;
	Outfile << setw(35) << "|      END OF PROGRAM OUTPUT      |" << endl;
	Outfile << setw(35) << " --------------------------------- " << endl;
	Outfile << endl;
	return;
}


void printMessage(int age, string name)
{
	// Receives - the age and name of the person
	// Task - Prints the name and age of the person
	// Returns - Nothing
	if (age <= 0) // starts an if statement. Executes only if age is less or equal than zero
	{
		cout << "\nHello infant " << name; // print the string 
	}
	else if (age >= 1) // Executes only if age is more or equal to one. 
	{
		for (int i = 0; i < age; i++) // Executes a for loop until I is less than age 
		{
			cout << "\nHello " << name;  // print the string 
		}
	}
	cout << "\n"; // prints a new line
	cout << "Output Complete!"; // prints the sentence
	cout << "\n";
	Footer(cout); // calls the footer
}

int main(void)
{
	Header(cout); // calls the header 
	string name; // creates a variable of type string 
	cout << "Please enter you name: \n"; // ask the user for their name 
	getline(cin, name); // reads and store the name into the variable 
	cout << "\n"; // prints a new line 
	int age; // creates a new variable of type int 
	cout << "Please enter you age (in years): \n"; // ask the user for their age 
	cin >> age; // read and store the age on the variable 
	cout << "\n"; // prints a new line 
	cout << "Generating output ... \n"; // prints the sentence 
	printMessage(age, name); // call for the printMessage function while sends the information storaged on the variables called age and name
	return 0;
}
