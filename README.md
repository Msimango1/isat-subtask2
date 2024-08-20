# isat-subtask2
#include <iostream>
#include <string>
#include <sstream>
#include <iomanip>

// Function to convert decimal to binary
std::string decimalToBinary(int decimal) {
    if (decimal == 0) return "0";
    std::string binary;
    while (decimal > 0) {
        binary = (decimal % 2 ? "1" : "0") + binary;
        decimal /= 2;
    }
    return binary;
}

// Function to convert binary to decimal
int binaryToDecimal(const std::string& binary) {
    int decimal = 0;
    for (char bit : binary) {
        decimal = (decimal << 1) | (bit - '0');
    }
    return decimal;
}

// Function to convert decimal to hexadecimal
std::string decimalToHexadecimal(int decimal) {
    std::stringstream stream;
    stream << std::hex << std::uppercase << decimal;
    return stream.str();
}

// Function to convert hexadecimal to decimal
int hexadecimalToDecimal(const std::string& hex) {
    int decimal;
    std::stringstream stream(hex);
    stream >> std::hex >> decimal;
    return decimal;
}

int main() {
    int choice;
    do {
        std::cout << "Select an option:\n";
        std::cout << "1. Decimal to Binary\n";
        std::cout << "2. Binary to Decimal\n";
        std::cout << "3. Decimal to Hexadecimal\n";
        std::cout << "4. Hexadecimal to Decimal\n";
        std::cout << "5. Exit\n";
        std::cout << "Enter your choice (1-5): ";
        std::cin >> choice;

        switch (choice) {
            case 1: {
                int decimal;
                std::cout << "Enter a decimal number: ";
                std::cin >> decimal;
                std::cout << "Binary representation: " << decimalToBinary(decimal) << std::endl;
                break;
            }
            case 2: {
                std::string binary;
                std::cout << "Enter a binary number: ";
                std::cin >> binary;
                std::cout << "Decimal representation: " << binaryToDecimal(binary) << std::endl;
                break;
            }
            case 3: {
                int decimal;
                std::cout << "Enter a decimal number: ";
                std::cin >> decimal;
                std::cout << "Hexadecimal representation: " << decimalToHexadecimal(decimal) << std::endl;
                break;
            }
            case 4: {
                std::string hex;
                std::cout << "Enter a hexadecimal number: ";
                std::cin >> hex;
                std::cout << "Decimal representation: " << hexadecimalToDecimal(hex) << std::endl;
                break;
            }
            case 5:
                std::cout << "Exiting...\n";
                break;
            default:
                std::cout << "Invalid choice. Please select a number between 1 and 5.\n";
                break;
        }
    } while (choice != 5);

    return 0;
}
