#include <iostream>
#include <string>
#include <ctime>
#include <cstdlib>
#include <iomanip>
using namespace std;

string email,password;
int code,ran,D,r,f,e,l,p,c;
int fr,fe,fl,fp,ff,fd;
int em;
float funds;

int main() {
    // Example two-step authentication
   cout << "Enter your email: ";
    cin >> email;
    cout << "Enter your password: ";
    cin >> password;

  ran = rand() % 100;
  cout << ran << endl;
  
    
 do{
   cout << "Look at your email and enter the code: ";
   cin >> code;
   if(code != ran){
     cout << "try again" << endl;
     cin >> code;
   }
  }while(code != ran);
  if(code == ran){
    cout << "Welcome to the account" << endl;
  }

  cout << endl;

  //The users balance in account
  cin >> funds;

  //Error response if user's balance is less than $20 and $5
  if(funds < 20 && funds > 5){
    cout << "You need to watch your spending and add to your funds.";
  }else if(funds < 5){
    cout << "Stop spending. You need to add to your funds.";
  }

  //Donation amount
  cout << "How much do you want to donate? ";
  cin >> D;
  cout << "So far you have donated $" << D << endl 
    << "Thank you for your donation" << endl;
  
  //Prints transaction in the past month for user
  cout << endl << "Transactions in the past month     " << endl << "PV Mart      - $20" << endl << "Chick-fil-A  - $10" << endl 
    << "Bookstore    - $50" << endl << "Donation     - $" << D << endl;

  cout << endl;

  //User's enters how much they spent in the past month
  cout << "How much did you spend on food this month? ";
  cin >> f;
  cout << "How much did you spend on your lifestyle? ";
  cin >> c;
  cout << "How much was your phone bill for the month? ";
  cin >> p;
  cout << "How much was your rent for the month? ";
  cin >> r;
  cout << "Do you want to put money in your emergency fund? (1 for yes, 2 for no) ";
   cin >> em;
  //if-else statement for if user wants to put money in emergency fund
  if(em == 1){
    cout << "How much do you want to put in? ";
    cin >> e;
    ff = f/funds*100;
    fe = c/funds*100;
    fl = p/funds*100;
    fr = r/funds*100;
    fd = D/funds*100;
    cout << endl;

    /*Prints out the percentage of how much the user spent on
      each category in the past month including emergency fund*/
    cout << fixed << setprecision(2) << "You have " << ff << "% of your funds for food, " << endl 
      << fe << "% of your funds for lifestyle, " << endl << fl << "% of your funds for phone bill, " << endl
      << fr << "% of your funds for rent " << endl << fd << "% of your funds for donations, and" << endl
      << fe << "% of your funds for emergency fund."; 
    
  }else{
    ff = f/funds*100;
    fe = c/funds*100;
    fl = p/funds*100;
    fr = r/funds*100;
    fd = D/funds*100;

    cout << endl;

    //Prints out the percentage of how much the user spent on each category in the past month
  cout << fixed << setprecision(2) << "You have " << ff << "% of your funds for food, " << endl 
    << fe << "% of your funds for lifestyle, " << endl  << fl << "% of your funds for phone bill, " << endl 
    << fr << "% of your funds for rent, and " << endl << fd << "% of your funds for donations." << endl;
  }

    return 0;
}
