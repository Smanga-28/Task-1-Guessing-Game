// Task-1-Guessing-Game
#include <iostream>
#include <cstdlib>
#include <ctime>
using namespace std;

int main() {
    srand(time(0));
    bool Response = true;
    
    while (Response)
	 {
        int RandomNumber = rand() % 100;
       
        cout << "Enter the attempt limit number: ";
        
        int limitNum;
        cin >> limitNum;
        int numberOfAttempts;
        
        for (numberOfAttempts = 1; numberOfAttempts <= limitNum; numberOfAttempts++)
		 {
            cout << "Please enter the guess number " << numberOfAttempts << ": ";
            int Number;
            cin >> Number;
            if(Number<=0 || Number>100) {
                cout << "The guess number must be between 1 - 100" << endl;
                break;
            }
            
            if (Number == RandomNumber) {
                cout << "Kudos! You guessed the correct number." << endl;
                break;
                
            } else if (Number < RandomNumber) {
                cout << "Your guessed number is too low." << endl;
            } else {
                cout << "Your guessed number is too high." << endl;
            }
        }
        
        if (numberOfAttempts > limitNum) {
            cout << "Game over, you've reached the maximum number of attempts. The correct number was: " << RandomNumber << endl;
        }
        cout << "Do you want to try again? (Yes/No): ";
        
        string playAgain;
        cin >> playAgain;
        Response = (playAgain == "Yes" || playAgain == "yes");
    }
    cout << "Goodbye, have a nice day!!!" << endl;
    return 0;
}
