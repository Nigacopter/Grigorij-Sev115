#include <iostream>
#include <fstream>
#include <string>
using namespace std;
int summa = 10000; //mainiga kura darbosies ar naudiem 
int pin = 0000; //mainiga kura darbosies ar pin kodu

bool isNumber(const string& s)
{
	for (char const& ch : s) {
		if (std::isdigit(ch) == 0)
			return false;
	}
	return true;
}
// Funkcija kas kontroles lai nevaretu uzrakstit burtus kur jabut cipari 
int funkc1()
{
	int choice2;
	bool a = false;
	string piev;
	string noniem;
	int noniem2;
	int piev2; //Visas mainigas kas nepieciesamas lai musu 1 funkcija kas darbosies ar naudiem darbojas 
	ofstream dengi;
	dengi.open("money.txt", ios::app); // Veidojam TXT failu, kurā bus pierakstits visas naudu darbibas un vertiba (summa)
	cout << endl
		<< "1 - Iemaksat naudu\n"
		<< "2 - Iznemt naudu\n"
		<< " Enter your choice and press return: "; // Veidojas menu kas jautas lietotajam vai vins grib iemaksat vai iznemt naudu no bankomata
	cin >> choice2;
	switch (choice2)
	{
	case 1:
		cout << "Ievadiet summu kuru jus gribat ielikt:";

		do {
			cin >> piev;
			if (isNumber(piev) == false) {
				cout << "Ievadiet summu ar skaitliem:";
			}
			else {
				a = true;	piev2 = stoi(piev);
				summa = summa + piev2;
				dengi << summa << endl;
			}
		} while (a == false); // Darbojas ar iemaksajumiem, prasa cik lietotajs grib iemaksat, neatļauj ievadit burtus un vardus un saglaba visas pievienosanas vertiba(summa), kas glabajas musu TXT faila

		return summa + piev2;
		break;
	case 2:
		cout << "Ievadiet summu kuru jus gribat izniemt:";
		do {
			cin >> noniem;
			if (isNumber(noniem) == false) {
				cout << "Ievadiet summu ar skaitliem:";
			}
			else a = true; noniem2 = stoi(noniem);
			summa = summa - noniem2;
			dengi << summa << endl;
		} while (a == false); // Darbojas ar izniemsanu, prasa cik lietotajs grib izniemt, neatļauj ievadit burtus un vardus un saglaba visas pievienosanas vertiba(summa), kas glabajas musu TXT faila
		
		return summa - noniem2;
		break;
	}


}
int funkc2()
{
	bool b = false;
	string pin2 = "0000";
	cout << "Ja gribat izmainit PIN kodu, uzrakstiet jaunu divas reizes (PIN: XXXX):";
	do {
		cin >> pin2 >> pin;
		if ( pin<1000 || pin>9999 || pin != stoi(pin2) || isNumber(pin2) == false ) {
			cout << "Ievadiet PIN ar skaitliem vai formata (XXXX) vai 2 reizes vienadu PIN:";
		}
		else {
			b = true;	pin = stoi(pin2);
			cout << "Your new PIN code is:" << pin;
		}
	} while (b == false);
	return pin; // Funkcija darbojas ar pin kodu, prasa ievadid jauno pinu un atlauj ievadid burtus un vardus, saglaba vertiba (pin)
}

int main()// Pamat funkcija
{
	
	int choice;	// Veidojas menu ar taja pierakstitajam ta saucajamiem funkcijam
	do
	{


		cout << endl
			<< " 1 - Skaidras naudas iemaksa un iznemsana EUR valuta\n"
			<< " 2 - Parbaudit un izdrukat kartes konta atlikumu\n"
			<< " 3 - Mainit kartes PIN kodu bez maksas\n"
			<< " 4 - Pabeigt darbibas\n"
			<< " Enter your choice and press return: ";
		cin >> choice;

		switch (choice)
		{
		case 1:

			funkc1(); // Izsauc pirmo funkciju
			break;
		case 2:
			cout <<"Jusu konta atlikums ir:"<< summa; //  Izvada kontas atlikumu lietotajam
			break;
		case 3:
			funkc2(); // Izsauc otro funkciju
			break;
		case 4:
			
			cout << "End of Program.\n"; // beidz programmu
			exit(0);
			break;
		default:
			cout << "Not a Valid Choice. \n" << "Choose again.\n";
			break;
		}

	} while (choice != 5);
	return 0;
}
