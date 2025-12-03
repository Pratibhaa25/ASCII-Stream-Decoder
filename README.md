# ASCII-Stream-Decoder
A lightweight C++ tool that converts a stream of ASCII values into readable text. Supports space-separated input, validates each value, and safely skips invalid entries.
#include <iostream>
#include <sstream>
using namespace std;

int main() {
    cout << "Enter ASCII values (0-255) separated by spaces:\n";

    string input;
    getline(cin, input);

    stringstream ss(input);
    int value;
    string result = "";

    while (ss >> value) {
        if (value < 0 || value > 255) {
            cout << "[Skipped invalid: " << value << "] ";
            continue;
        }
        result += char(value);
    }

    cout << "Decoded Text: " << result << endl;
    return 0;
}
