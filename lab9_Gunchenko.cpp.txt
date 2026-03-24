#include <iostream>
#include <iomanip>
using namespace std;

int main() {
    int N;
    cout << "Введіть розмір квадратної матриці N: ";
    cin >> N;

    double a[100][100];

    // Введення матриці
    cout << "Введіть елементи матриці:" << endl;
    for (int i = 0; i < N; i++) {
        for (int j = 0; j < N; j++) {
            cin >> a[i][j];
        }
    }

    // Пошук максимального елемента
    double maxVal = a[0][0];
    int imax = 0, jmax = 0;

    for (int i = 0; i < N; i++) {
        for (int j = 0; j < N; j++) {
            if (a[i][j] > maxVal) {
                maxVal = a[i][j];
                imax = i;
                jmax = j;
            }
        }
    }

    // Координати перетину двох діагоналей
    int c = N / 2;

    // Обмін елементів
    double temp = a[c][c];
    a[c][c] = a[imax][jmax];
    a[imax][jmax] = temp;

    // Вивід результату
    cout << "\nМатриця після заміни:" << endl;
    for (int i = 0; i < N; i++) {
        for (int j = 0; j < N; j++) {
            cout << setw(10) << a[i][j];
        }
        cout << endl;
    }

    return 0;
}
