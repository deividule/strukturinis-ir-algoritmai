/******************************************************************************

Welcome to GDB Online.
  GDB online is an online compiler and debugger tool for C, C++, Python, PHP, Ruby, 
  C#, OCaml, VB, Perl, Swift, Prolog, Javascript, Pascal, COBOL, HTML, CSS, JS
  Code, Compile, Run and Debug online from anywhere in world.

*******************************************************************************/
#include <iostream>

#include <string>

using namespace std;

int main() {

    string vardas = "Jonas";
    string pavarde = "Jonaitis";
    int amzius = 20;
    string grupe = "IF-23";
    int kursas = 2;
    string studijuPrograma = "Informatika";

    cout << "STUDENTAS" << endl;
    cout << "Vardas: " << vardas << endl;
    cout << "Pavarde: " << pavarde << endl;
    cout << "Amzius: " << amzius << endl;
    cout << "Grupe: " << grupe << endl;
    cout << "Kursas: " << kursas << endl;
    cout << "Studiju programa: " << studijuPrograma << endl;
    cout << endl;

    string pavadinimas = "Kauno Zalgiris";
    int ikurimoMetai = 1944;
    string savininkas = "Paulius Motiejunas";
    string arena = "Zalgirio arena";
    int vietuSkaicius = 15415;

    cout << "SPORTO KLUBAS" << endl;
    cout << "Pavadinimas: " << pavadinimas << endl;
    cout << "Ikurimo metai: " << ikurimoMetai << endl;
    cout << "Savininkas: " << savininkas << endl;
    cout << "Arena: " << arena << endl;
    cout << "Vietu skaicius: " << vietuSkaicius << endl;
    cout << endl;

    string marke = "OPEL";
    string modelis = "ZAFIRA";
    int pagaminimoMetai = 2010;
    double litrazas = 2.0;
    string spalva = "sidabrine";

    cout << "Automobilis " << marke << " " << modelis
         << " yra pagamintas " << pagaminimoMetai
         << " metais. Jo motoras " << litrazas
         << " l litrazo. Automobilis yra "
         << spalva << " spalvos." << endl;
    cout << endl;

    int a = 13;
    int b = 5;
    double c = 17.5;

    cout << a + b - c << endl;
    cout << 15 / 2 + c << endl;
    cout << a / static_cast<double>(b) + 2 * c << endl;
    cout << 14 % 3 + 6.3 + b / a << endl;
    cout << static_cast<int>(c) % 5 + a - b << endl;
    cout << 13.5 / 2 + 4.0 * 3.5 + 18 << endl;
    cout << endl;

    double x1, x2, x3, x4, x5;
    cin >> x1 >> x2 >> x3 >> x4 >> x5;

    double vidurkis = (x1 + x2 + x3 + x4 + x5) / 5;
    cout << "Vidurkis: " << vidurkis << endl;
    cout << endl;

    int skaicius;
    cin >> skaicius;

    int desimtys = skaicius / 10;
    int vienetai = skaicius % 10;

    cout << "Skaitmenu suma: " << desimtys + vienetai << endl;

    return 0;
}
