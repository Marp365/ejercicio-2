Crea un programa que llene un arreglo con 100 números enteros aleatorios entre 1 y 500. Luego, utiliza estructuras de control para identificar y mostrar cuántos de esos números son primos.

#include <iostream>
#include <cstdlib>
#include <ctime>
using namespace std;

bool esPrimo(int n) {
    if (n <= 1) return false;
    for (int i = 2; i * i <= n; i++) {
        if (n % i == 0) return false;
    }
    return true;
}

int main() {
    int numeros[100];
    int contadorPrimos = 0;

    srand(time(0));

    for (int i = 0; i < 100; i++) {
        numeros[i] = rand() % 500 + 1;
        if (esPrimo(numeros[i])) {
            contadorPrimos++;
        }
    }

    cout << "Cantidad de números primos: " << contadorPrimos << endl;

    return 0;
}
