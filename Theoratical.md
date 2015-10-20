#       Assignment 1
##Questions from 1 - 4, 6, 8 - 10.
###Question 1:
A **_Class_** Is a block of code that defines a set of elements and functions performing an event with specified properties which can be inherited by objects defined with that Class.
###Question 2:
A Class defines **abstraction** by naming  a set of elements and functions by only one name which is the class name and events performed by that class can be called by that name as for the **encapsulation** because it organize and categorize the events into named functions can be hidden by declaring them as **_private_** or unhidden by declaring them as **_public_** and the public functions can be called outside of that class.
###Question 3:
An **_Object_** is the class child which inherits all its properties and elements and functions so its an **instance** of that class.
###Question 4:
Class **_Functions_** perform a certain event but **_Data members_** are spaces in memory.
###Question 6:
A class **_Constructor_** is a special member function of a class that is executed whenever we create new objects of that class.
A **_Destructor_** is a special member function of a class that is executed whenever an object of it's class goes out of scope or whenever the delete expression is applied to a pointer to the object of that class.
###Question 8:
**_Default Constructor_** doesn’t have any parameters  and they exist to initialize the data members of a class.
###Question 9:
```C++
string GetCompanyName(void)
{
	return Company;
}
int GetShares(void)
{
	return share_val;
}
int GetTotalValue(void)
{
	return total_val;
}
```
###Question 10:
**_this_** is a pointer and **_*this_** is a dereferenced pointer.
If you had a function that returned this it would be a pointer to the current object while a function that returned *this would be a clone of the current object allocated on the stack unless you have specified the return type of the method to return a reference.
#Coding Problems
##Question 5,7 & 1,2,6
###Question 5,7,2:
```C++
#include <iostream>
#include <string>
using namespace std;
class Profile {
public:
Profile(string name,int balance,string acc_no)
	{
ClientName = name;
AccountNumber = acc_no;
Balance = balance;
	};
string GetClientName(void)
{
	return ClientName;
}
string GetAccountNumber(void)
{
	return AccountNumber;
}
int GetBalance(void)
{
	return Balance;
}
void Deposit(int amount)
{
 Balance += amount;
}
void Withdraw(int amount)
{
 Balance -= amount;
}

private:
string ClientName;
string AccountNumber;
int Balance;
};

void main()
{
Profile x("ziad",1000,"19874");
x.Deposit(100);
x.Withdraw(10);
cout<<x.GetBalance()<< "\n";
};
```
##Question 2:
```C++
#include <string>
#include <iostream>
#include <cstring>
using namespace std;
class Person
{
public:
	Person()
	{
		FirstName = "Your First Name";
		char lname[LIMIT] = "Your Last Name";
strcpy(LastName, lname);
	}
	Person(string fname,char lname[25] = "Your Last Name")
	{
		FirstName = fname;
		strcpy(LastName, lname);
	}
	
	void Show(void)
	{
cout<< FirstName << " , " << LastName << "\n";
	}
	void FormalShow(void)
	{
cout<< LastName << " , " << FirstName << "\n";
	}
private:
	static const int LIMIT = 25;
string FirstName;
char LastName[LIMIT];
};
void main()
{
Person x;
Person z("ziad");
Person y("ziad","Sousa");
x.Show();
x.FormalShow();
y.Show();
y.FormalShow();
z.Show();
z.FormalShow();
};
```
###Question 6:
```C++
#include <iostream>
using namespace std;
class Move
{
private:
	double x;
	double y;
	double dx;
	double dy;
public:
	Move(double a = 0,double b = 0)
	{
		x = a;
		y = b;
		dx = a;
		dy = b;
	}
	void addx(double v)
	{
x += v;
	}
	void addy(double v)
	{
y += v;
	}
	void Showmove(void) const
	{
		cout<<"X value : " << x << " Y value : " << y << " \n";
	}
	void Add( Move &m)
	{
m.addx(x);
m.addy(y);
	}
	void Reset(void)
	{
x = dx;
y = dy;
	}
};
void main()
{
Move x(10,10);
Move y(10,10);
x.Add(y);
y.Showmove();
y.Reset();
y.Showmove();
};
```

