
#include <iostream>
#include <string>
#include <cctype>
using namespace std;

int main()
{
    // Store the Morse code for each letter from A to Z
    string morseCode[26] = {
        ".-", "-...", "-.-.", "-..", ".", "..-.", "--.",
        "....", "..", ".---", "-.-", ".-..", "--", "-.",
        "---", ".--.", "--.-", ".-.", "...", "-", "..-",
        "...-", ".--", "-..-", "-.--", "--.."
    };

    string message;
    string fullCode = "";

    // Ask the user to enter a message
    cout << "Enter a short English message: ";
    getline(cin, message);

    cout << "\nMorse Code Translation\n";
    cout << "----------------------\n";

    // Read each character in the message
    for (int i = 0; i < message.length(); i++)
    {
        char letter = toupper(message[i]);

        // Translate letters from A to Z
        if (letter >= 'A' && letter <= 'Z')
        {
            int position = letter - 'A';

            cout << letter << ": " << morseCode[position] << endl;

            // Add three spaces between letters in the full message
            if (fullCode != "")
            {
                fullCode += "   ";
            }

            fullCode += morseCode[position];
        }
        else if (letter == ' ')
        {
            // Add extra spacing between words
            fullCode += "    ";
        }
    }

    // Display the complete Morse code message
    cout << "\nFull Morse Code Message:\n";
    cout << fullCode << endl;

    return 0;
}
