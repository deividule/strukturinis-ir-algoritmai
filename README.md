#include <iostream>
#include <fstream>
#include <vector>
#include <iomanip>
#include <windows.h>

    using namespace std;
    struct menuItemType {
    string menuItem;
    double menuPrice;
};
    void getData(vector<menuItemType>& menuList) {
    ifstream file("menu.txt");
    if (!file) {
    cout << "Nepavyko atidaryti menu.txt failo!\n";
    return;
    }
    string line;
    while (getline(file, line)) {
    size_t pos = line.find(';');
    if (pos != string::npos) {
    string name = line.substr(0, pos);
    double price = stod(line.substr(pos + 1));
    menuList.push_back({name, price});
        }
    }
    file.close();
}
void showMenu(const vector<menuItemType>& menuList) {
    cout << "Meniu:\n";
    for (int i = 0; i < menuList.size(); i++) {
    cout << i + 1 << ". " << menuList[i].menuItem
    << " - " << fixed << setprecision(2)
    << menuList[i].menuPrice << " EUR\n";
    }
}
    void printCheck(const vector<menuItemType>& menuList) {
    ofstream outFile("receipt.txt");
    double total = 0;
    int choice, quantity;
    cout << "\nPasirinkite patiekalus (0 - baigti):\n";
    while (true) {
    cout << "Numeris: ";
    cin >> choice;
    if (choice == 0) break;
    if (choice < 1 || choice > menuList.size()) {
    cout << "Blogas pasirinkimas!\n";
    continue;
    }
    cout << "Kiekis: ";
    cin >> quantity;
    double sum = menuList[choice - 1].menuPrice * quantity;
    total += sum;
    cout << quantity << " " << menuList[choice - 1].menuItem
    << " - " << fixed << setprecision(2) << sum << " EUR\n";
    outFile << quantity << " " << menuList[choice - 1].menuItem
    << " - " << fixed << setprecision(2) << sum << " EUR\n";
    }
    double tax = total * 0.21;
    double finalSum = total + tax;
    cout << "\nPVM (21%): " << tax << " EUR\n";
    cout << "Galutine suma: " << finalSum << " EUR\n";
    outFile << "\nPVM (21%): " << tax << " EUR\n";
    outFile << "Galutine suma: " << finalSum << " EUR\n";
    outFile.close();
}

int main() {
    SetConsoleOutputCP(65001);
    SetConsoleCP(65001);
    vector<menuItemType> menuList;
    getData(menuList);
    cout << "Sveiki atvyke i restorana!\n\n";
    showMenu(menuList);
    printCheck(menuList);

    return 0;
}
