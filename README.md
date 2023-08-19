# CC-Validator
cout << "This program uses the Luhn Algorigthm ." << endl;
cout << " enter 'exit' to quit." << endl;

while (true) {
    
    cout << " enter a CC number : ";
    cin >> ccNumber;
    
    if (ccNumber == "exit")
        break;
    
    else if (!isNumberString(ccNumber)) {
        cout << "Bad input! ";
        continue;
    }
        
    int len = ccNumber.length();
    int doubleEvenSum = 0;  
    
    for (int i = len - 2; i >= 0; i = i - 2) {
        int dbl = ((ccNumber[i] - 48) * 2);
        if (dbl > 9) {
            dbl = (dbl / 10) + (dbl % 10);
        }
        doubleEvenSum += dbl;
    }
    

    
    for (int i = len - 1; i >= 0; i = i - 2) {
        doubleEvenSum += (ccNumber[i] - 48);
    }
    
    
    cout << (doubleEvenSum % 10 == 0 ? "Valid!" : "Invalid!") << endl;
    
    continue;        
}

return 0;
