# Solve-equations-supplied-by-the-user
// PROBLEM // Enter calculation (ex. 5 + 6) : 10 - 6     // 10.0 - 6.0 = 4.0
#include <iostream>
#include <cstdlib>
#include <string>
#include <cmath>
#include <ctime>
#include <array>
#include <vector>
#include <sstream>
#include <algorithm> // Needed for find

using namespace std;

int main(){
    double dbNum1 = 0, dbNum2 = 0;
    string sCalc = "";
    vector<string> vecsCalc;

    cout << "Enter calculation (ex. 5 + 6): ";
    getline(cin, sCalc);

    stringstream ss2(sCalc);
    string indivStr;
    char space = ' ';

    while(getline(ss2, indivStr, space)){
        vecsCalc.push_back(indivStr);
    }

    dbNum1 = stoi(vecsCalc[0]);
    dbNum2 = stoi(vecsCalc[2]);
    string operation = vecsCalc[1];

    if (operation == "+"){
        printf("%.1f + %.1f = %.1f\n", dbNum1, dbNum2,
                (dbNum1 + dbNum2));
    } else if (operation == "-"){
        printf("%.1f - %.1f = %.1f\n", dbNum1, dbNum2,
                (dbNum1 - dbNum2));
    } else if (operation == "*"){
        printf("%.1f * %.1f = %.1f\n", dbNum1, dbNum2,
                (dbNum1 * dbNum2));
    } else if (operation == "/"){
        printf("%.1f / %.1f = %.1f\n", dbNum1, dbNum2,
                (dbNum1 / dbNum2));
    } else {
        cout << "Please enter only +, -, *, or /\n";
    }

    return 0;
}
