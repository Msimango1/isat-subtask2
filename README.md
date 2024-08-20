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

// Function to convert decimal to hexadecimal
std::string decimalToHexadecimal(int decimal) {
    std::stringstream stream;
    stream << std::hex << std::uppercase << decimal;
    return stream.str();
}


