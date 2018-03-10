# Library-Management
#include<iostream>
#include<string.h>
#include<conio.h>
using namespace std;
class Library_Management
{
public:
    string passwd="";
    char ch;
    int selection;
    void admin()
    {
        cout<<"Admin"<<endl<<"Password: ";
         ch = _getch();
        while(ch != 13)
            {
            passwd.push_back(ch);
            cout << '*';
            ch = _getch();
            }
        if(passwd=="vanami")
        {
            execute();
        }
        else
        {
            cout<<"Enter correct password"<<endl;
            admin();
        }
    }
    void guest()
    {
        cout<<"List of all the books are:"<<endl;
    }
    void execute()
    {
        cout<<endl<<"What do you want to do?"<<endl;
        cout<<"1. Check availability  "<<endl<<"2. Issue a book"<<endl<<"3. Add a Book"<<endl;
        cin>>selection;
        switch(selection)
        {
        case 1:
            availablity();
            break;

        case 2:
            issue();
            break;

        case 3:
            add_book();
            break;

        default:
            cout<<"Enter valid input."<<endl;
            execute();
            break;

        }
    }
    void availablity()
    {
        cout<<"Lists of Books available are";
    }
    void issue()
    {
        cout<<"Issue page";
    }
    void add_book()
    {
        cout<<"Enter Book Details";
    }
};
int main()
{
    Library_Management lm;
    int user_entry;
    cout<<"1. Admin"<<endl<<"2. Guest"<<endl;
    cin>>user_entry;
    if(user_entry==1)
    {
        lm.admin();
    }
    else
    {
        lm.guest();
    }
    return 0;
}
