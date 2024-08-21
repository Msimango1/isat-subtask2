# isat-subtask2
#include <iostream>
#include <string>
#include <sstream>
#include <iomanip>

// Converts a decimal number to its binary representation
std::string decimalToBinaryString(int decimalNumber) {
    if (decimalNumber == 0) return "0";
    std::string binaryString;
    while (decimalNumber > 0) {
        binaryString = (decimalNumber % 2 ? "1" : "0") + binaryString;
        decimalNumber /= 2;
    }
    return binaryString;
}

// Converts a binary string to its decimal equivalent
int binaryStringToDecimal(const std::string& binaryString) {
    int decimalNumber = 0;
    for (char bit : binaryString) {
        decimalNumber = (decimalNumber << 1) | (bit - '0');
    }
    return decimalNumber;
}

// Converts a decimal number to its hexadecimal representation
std::string decimalToHexString(int decimalNumber) {
    std::stringstream hexStream;
    hexStream << std::hex << std::uppercase << decimalNumber;
    return hexStream.str();
}

// Converts a hexadecimal string to its decimal equivalent
int hexStringToDecimal(const std::string& hexString) {
    int decimalNumber;
    std::stringstream hexStream(hexString);
    hexStream >> std::hex >> decimalNumber;
    return decimalNumber;
}

int main() {
    int menuChoice;
    do {
        std::cout << "Select an option:\n";
        std::cout << "1. Decimal to Binary\n";
        std::cout << "2. Binary to Decimal\n";
        std::cout << "3. Decimal to Hexadecimal\n";
        std::cout << "4. Hexadecimal to Decimal\n";
        std::cout << "5. Exit\n";
        std::cout << "Enter your choice (1-5): ";
        std::cin >> menuChoice;

        switch (menuChoice) {
            case 1: {
                int decimalNumber;
                std::cout << "Enter a decimal number: ";
                std::cin >> decimalNumber;
                std::cout << "Binary representation: " << decimalToBinaryString(decimalNumber) << std::endl;
                break;
            }
            case 2: {
                std::string binaryString;
                std::cout << "Enter a binary number: ";
                std::cin >> binaryString;
                std::cout << "Decimal representation: " << binaryStringToDecimal(binaryString) << std::endl;
                break;
            }
            case 3: {
                int decimalNumber;
                std::cout << "Enter a decimal number: ";
                std::cin >> decimalNumber;
                std::cout << "Hexadecimal representation: " << decimalToHexString(decimalNumber) << std::endl;
                break;
            }
            case 4: {
                std::string hexString;
                std::cout << "Enter a hexadecimal number: ";
                std::cin >> hexString;
                std::cout << "Decimal representation: " << hexStringToDecimal(hexString) << std::endl;
                break;
            }
            case 5:
                std::cout << "Exiting...\n";
                break;
            default:
                std::cout << "Invalid choice. Please enter a number between 1 and 5.\n";
                break;
        }
    } while (menuChoice != 5);

    return 0;
}
 
 


