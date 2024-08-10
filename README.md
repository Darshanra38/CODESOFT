#include <iostream>
#include <cstdlib>  // For srand() and rand()
#include <ctime>    // For time()

int main() {
    // Seed the random number generator with the current time
    std::srand(static_cast<unsigned int>(std::time(0)));
    
    // Generate a random number between 1 and 100
    int randomNumber = std::rand() % 100 + 1;
    int playerGuess = 0;
    int numberOfTries = 0;

    std::cout << "Welcome to the Number Guessing Game!" << std::endl;
    std::cout << "I have selected a number between 1 and 100. Try to guess it!" << std::endl;

    // Main game loop
    do {
        std::cout << "Enter your guess: ";
        std::cin >> playerGuess;
        numberOfTries++;

        if (playerGuess > randomNumber) {
            std::cout << "Too high! Try again." << std::endl;
        } else if (playerGuess < randomNumber) {
            std::cout << "Too low! Try again." << std::endl;
        } else {
            std::cout << "Congratulations! You guessed the number in " << numberOfTries << " tries." << std::endl;
        }

    } while (playerGuess != randomNumber);

    return 0;
}

