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
