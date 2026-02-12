/******************************************************************************

Welcome to GDB Online.
  GDB online is an online compiler and debugger tool for C, C++, Python, PHP, Ruby, 
  C#, OCaml, VB, Perl, Swift, Prolog, Javascript, Pascal, COBOL, HTML, CSS, JS
  Code, Compile, Run and Debug online from anywhere in world.

*******************************************************************************/
#include <iostream>
#include <iomanip>
using namespace std;

int main() {
    
    double GBP_Bendras = 0.8729;
    double GBP_Pirkti = 0.8600;
    double GBP_Parduoti = 0.9220;

    double USD_Bendras = 1.1793;
    double USD_Pirkti = 1.1460;
    double USD_Parduoti = 1.2340;

    double INR_Bendras = 104.6918;
    double INR_Pirkti = 101.3862;
    double INR_Parduoti = 107.8546;

    int pasirinkimas, valiuta;
    double kursas = 0, kiekis = 0;
    string pavadinimas;

    cout << "=== Valiutos keitykla ===\n";
    cout << "1 - Palyginti valiutos kursa\n";
    cout << "2 - Pirkti valiuta\n";
    cout << "3 - Parduoti valiuta\n";
    cout << "Pasirinkite veiksma: ";
    cin >> pasirinkimas;

    cout << "\nPasirinkite valiuta:\n";
    cout << "1 - GBP\n";
    cout << "2 - USD\n";
    cout << "3 - INR\n";
    cout << "Jusu pasirinkimas: ";
    cin >> valiuta;

    switch (valiuta) {
        case 1:
            pavadinimas = "GBP";
            kursas = (pasirinkimas == 1 ? GBP_Bendras :
                     pasirinkimas == 2 ? GBP_Pirkti : GBP_Parduoti);
            break;

        case 2:
            pavadinimas = "USD";
            kursas = (pasirinkimas == 1 ? USD_Bendras :
                     pasirinkimas == 2 ? USD_Pirkti : USD_Parduoti);
            break;

        case 3:
            pavadinimas = "INR";
            kursas = (pasirinkimas == 1 ? INR_Bendras :
                     pasirinkimas == 2 ? INR_Pirkti : INR_Parduoti);
            break;

        default:
            cout << "Neteisingas valiutos pasirinkimas.\n";
            return 0;
    }


    if (pasirinkimas == 1) {
        cout << fixed << setprecision(2);
        cout << "\n1 EUR = " << kursas << " " << pavadinimas << endl;
        return 0;
    }

    cout << "\nIveskite kieki: ";
    cin >> kiekis;

    double rezultatas;

    if (pasirinkimas == 2) {
        rezultatas = kiekis * kursas;
        cout << fixed << setprecision(2);
        cout << "\nUz " << kiekis << " EUR gausite "
             << rezultatas << " " << pavadinimas << endl;
    }
    else if (pasirinkimas == 3) {
        rezultatas = kiekis / kursas;
        cout << fixed << setprecision(2);
        cout << "\nPardave " << kiekis << " " << pavadinimas
             << " gausite " << rezultatas << " EUR" << endl;
    }
    else {
        cout << "Neteisingas pasirinkimas.\n";
    }

    return 0;
}
