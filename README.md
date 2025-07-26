#include <iostream>
#include <fstream>
#include <string>
#include <sstream>

using namespace std;

// Function to write data to a file
void writeToFile(const string& filename) {
    ofstream outFile(filename);  // Open file for writing
    if (outFile.is_open()) {
        string data;
        cout << "Enter text to write to the file (type 'end' to stop):\n";
        // Read data until 'end' is entered
        while (true) {
            getline(cin, data);
            if (data == "end") {
                break;  // Stop if 'end' is typed
            }
            outFile << data << endl;  // Write data to file
        }
        cout << "Data written to the file successfully.\n";
        outFile.close();  // Close the file
    } else {
        cout << "Error opening file for writing!\n";
    }
}

// Function to append data to a file
void appendToFile(const string& filename) {
    ofstream outFile(filename, ios::app);  // Open file for appending
    if (outFile.is_open()) {
        string data;
        cout << "Enter text to append to the file (type 'end' to stop):\n";
        // Read data until 'end' is entered
        while (true) {
            getline(cin, data);
            if (data == "end") {
                break;  // Stop if 'end' is typed
            }
            outFile << data << endl;  // Append data to file
        }
        cout << "Data appended to the file successfully.\n";
        outFile.close();  // Close the file
    } else {
        cout << "Error opening file for appending!\n";
    }
}

// Function to read data from a file
void readFromFile(const string& filename) {
    ifstream inFile(filename);  // Open file for reading
    if (inFile.is_open()) {
        string line;
        cout << "File contents:\n";
        while (getline(inFile, line)) {
            cout << line << endl;  // Display each line from the file
        }
        inFile.close();  // Close the file
    } else {
        cout << "Error opening file for reading!\n";
    }
}

int main() {
    int choice;
    string filename;

    cout << "File Management Tool\n";
    cout << "---------------------\n";
    cout << "Enter the filename: ";
    cin >> filename;
    cin.ignore();  // To ignore the newline character after entering the filename

    do {
        // Main menu
        cout << "\nChoose an option:\n";
        cout << "1. Write to File\n";
        cout << "2. Append to File\n";
        cout << "3. Read from File\n";
        cout << "4. Exit\n";
        cout << "Enter your choice (1, 2, 3, or 4): ";
        cin >> choice;
        cin.ignore();  // To ignore the newline character after entering the choice

        switch (choice) {
            case 1:
                writeToFile(filename);  // Write to file
                break;
            case 2:
                appendToFile(filename);  // Append to file
                break;
            case 3:
                readFromFile(filename);  // Read from file
                break;
            case 4:
                cout << "Exiting the program.\n";
                break;
            default:
                cout << "Invalid choice! Please enter a valid option.\n";
                break;
        }
    } while (choice != 4);  // Exit when user chooses option 4

    return 0;
}
