#include <iostream>
#ifdef _WIN32
#include <conio.h>
#elif __linux
#include <termios.h>
#endif

using namespace std;

#ifdef _WIN32
namespace Windows {
	bool run = true;

	void Case1(string Num, char qt, string text) {
		system("cls");
		std::cout << "Для закінчення введення даних натисніть клавішу esc\n";
		while (run) {
			if (_kbhit()) {
				qt = _getch();
				for (int i = 0; i < Num.length(); i++) {
					if (qt == Num[i]) {
						qt = ' ';
					}
					else if (qt == 13) {
						qt = '\n';
					}
					else if (qt == 27) {
						run = false;
						qt = ' ';
						break;
					}
				}
				text += qt;
				std::cout << qt;
			}
		}
		std::cout << endl << "Ви ввели текст:\n";
		std::cout << text << endl;
		run = true;
	}
	void Case2(string Symb, char qt, string text) {
		system("cls");
		std::cout << "Для закінчення введення даних натисніть клавішу esc\n";
		while (run) {
			if (_kbhit()) {
				qt = _getch();
				for (int i = 0; i < Symb.length(); i++) {
					if (qt == Symb[i]) {
						qt = ' ';
					}
					else if (qt == 13) {
						qt = '\n';
					}
					else if (qt == 27) {
						run = false;
						qt = ' ';
						break;
					}
				}
				text += qt;
				std::cout << qt;
			}
		}
		std::cout << endl << "Ви ввели текст:\n";
		std::cout << text << endl;
		run = true;
	}
	void Case3(string Eng, char qt, string text) {
		system("cls");
		std::cout << "Для закінчення введення даних натисніть клавішу esc\n";
		while (run) {
			if (_kbhit()) {
				qt = _getch();
				for (int i = 0; i < Eng.length(); i++) {
					if (qt == Eng[i]) {
						qt = ' ';
					}
					else if (qt == 13) {
						qt = '\n';
					}
					else if (qt == 27) {
						run = false;
						qt = ' ';
						break;
					}
				}
				text += qt;
				std::cout << qt;
			}
		}
		std::cout << endl << "Ви ввели текст:\n";
		std::cout << text << endl;
		run = true;
	}
	void Case4(string Ukr, char qt, string text) {
		system("cls");
		std::cout << "Для закінчення введення даних натисніть клавішу esc\n";
		while (run) {
			if (_kbhit()) {
				qt = _getch();
				for (int i = 0; i < Ukr.length(); i++) {
					if (qt == Ukr[i]) {
						qt = ' ';
					}
					else if (qt == 13) {
						qt = '\n';
					}
					else if (qt == 27) {
						run = false;
						qt = ' ';
						break;
					}
				}
				text += qt;
				std::cout << qt;
			}
		}
		std::cout << endl << "Ви ввели текст:\n";
		std::cout << text << endl;
		run = true;
	}
}
#elif __linux
namespace Linux {
	struct termios Old, New;

	void Case1(string Num, char qt, string text) {
		system("clear");
		cout << "Для закінчення введення даних натисніть клавішу esc\n";
		tcgetattr(0, &Old);
		New = Old;
		New.c_lflag &= ~(ICANON | ECHO);
		tcsetattr(0, TCSANOW, &New);
		qt = getchar();
		while ((qt = getchar()) != 27) {
			for (int i = 0; i < Num.length(); i++) {
				if (qt == Num[i]) {
					qt = ' ';
				}
			}
			text += qt;
			cout << qt;
		}
		tcsetattr(0, TCSANOW, &Old);
		cout << endl << "Ви ввели текст:\n";
		cout << text << endl;
	}
	void Case2(string Symb, char qt, string text) {
		system("clear");
		cout << "Для закінчення введення даних натисніть клавішу esc\n";
		tcgetattr(0, &Old);
		New = Old;
		New.c_lflag &= ~(ICANON | ECHO);
		tcsetattr(0, TCSANOW, &New);
		qt = getchar();
		while ((qt = getchar()) != 27) {
			for (int i = 0; i < Symb.length(); i++) {
				if (qt == Symb[i]) {
					qt = ' ';
				}
			}
			text += qt;
			cout << qt;
		}
		tcsetattr(0, TCSANOW, &Old);
		cout << endl << "Ви ввели текст:\n";
		cout << text << endl;
	}
	void Case3(string Eng, char qt, string text) {
		system("clear");
		cout << "Для закінчення введення даних натисніть клавішу esc\n";
		tcgetattr(0, &Old);
		New = Old;
		New.c_lflag &= ~(ICANON | ECHO);
		tcsetattr(0, TCSANOW, &New);
		qt = getchar();
		while ((qt = getchar()) != 27) {
			for (int i = 0; i < Eng.length(); i++) {
				if (qt == Eng[i]) {
					qt = ' ';
				}
			}
			text += qt;
			cout << qt;
		}
		tcsetattr(0, TCSANOW, &Old);
		cout << endl << "Ви ввели текст:\n";
		cout << text << endl;
	}
	void Case4(string Ukr, char qt, string text) {
		system("clear");
		cout << "Для закінчення введення даних натисніть клавішу esc\n";
		tcgetattr(0, &Old);
		New = Old;
		New.c_lflag &= ~(ICANON | ECHO);
		tcsetattr(0, TCSANOW, &New);
		qt = getchar();
		while ((qt = getchar()) != 27) {
			for (int i = 0; i < Ukr.length(); i++) {
				if (qt == Ukr[i]) {
					qt = ' ';
				}
			}
			text += qt;
			cout << qt;
		}
		tcsetattr(0, TCSANOW, &Old);
		cout << endl << "Ви ввели текст:\n";
		cout << text << endl;
	}
}
#endif

namespace both {
	string Ukr = "йцукенгшщзхждлорпавфячсмитьбюЙЦУКЕНГШЩЗХЖДЛОРПАВФЯЧСМИТЬБЮґҐІіЄєЇї";
	string Eng = "qwertyuioplkjhgfdsazxcvbnmQWERTYUIOPLKJHGFDSAZXCVBNM";
	string Num = "0123456789";
	string Symb = "`~!@#$%^&*()_+}{|\":<>?/.,\\';][=-№";
	string text;
	int choice = 0;
	char qt = ' ';
	bool menu_run = true;

	void PrintMenu(int& choice) {
		std::cout << "Press 1 to replace numbers with spaces.\n";
		std::cout << "Press 2 to replace punctuation with spaces.\n";
		std::cout << "Press 3 to replace English letters with spaces.\n";
		std::cout << "Press 4 to replace Ukrainian letters with spaces.\n";
		std::cout << "Press 5 to see the list of changes\n\n";

		std::cout << "Your choice: "; cin >> choice;
	}

	void Case5() {
#ifdef _WIN32
		system("cls");
#elif __linux
		system("clear");
#endif
		std::cout << "Version 2.341\n";
		std::cout << "1. Improved part of code for Windows.\n";
		std::cout << "2. Improved part of code for Linuxю.\n";
		std::cout << "3. The <stdlib.h> library has been removed.\n";
		std::cout << "4. The <clocale> library has been removed.\n";
		std::cout << "5. The <windows.h> library has been removed for Windows.\n";
		std::cout << "6. Fixed issues that caused text not to be displayed.\n\n";
	}
}

int main() {
#ifdef __linux
	while (both::menu_run) {
		both::PrintMenu(both::choice);
		switch (both::choice) {
		case 1:
			Linux::Case1(both::Num, both::qt, both::text);
			break;
		case 2:
			Linux::Case2(both::Symb, both::qt, both::text);
			break;
		case 3:
			Linux::Case3(both::Eng, both::qt, both::text);
			break;
		case 4:
			Linux::Case4(both::Ukr, both::qt, both::text);
			break;
		case 5:
			both::Case5();
			break;
		default:
			both::menu_run = false;
			break;
		}
	}
#elif _WIN32
	system("chcp 1251>nul");
	while (both::menu_run) {
		both::PrintMenu(both::choice);
		switch (both::choice) {
		case 1:
			Windows::Case1(both::Num, both::qt, both::text);
			break;
		case 2:
			Windows::Case2(both::Symb, both::qt, both::text);
			break;
		case 3:
			Windows::Case3(both::Eng, both::qt, both::text);
			break;
		case 4:
			Windows::Case4(both::Ukr, both::qt, both::text);
			break;
		case 5:
			both::Case5();
			break;
		default:
			both::menu_run = false;
			break;
		}
	}
#endif
}

/*
Розгляньте програму. Здійсніть рефакторинг кода:
1) щоб не було повторень оголошення і визначення змінних в тексті програми
2) фрагменти кода, які повторюються, оформіть функціями
*/
