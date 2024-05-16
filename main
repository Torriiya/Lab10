#include <iostream>
#include <fstream>
#include <limits>

using namespace std;

int main() {
    // Считывание размера массива и элементов из одного файла
    int N;
    ifstream file("data.txt");
    if (!file.is_open()) {
        cerr << "Ошибка: Не удалось открыть файл data.txt" << endl;
        return 1;
    }
    file >> N;

    // Выделение памяти для массивов
    int* arr = new int[N];
    int* updatedArr = new int[N];

    // Считывание элементов массива
    for (int i = 0; i < N; i++) {
        file >> arr[i];
    }

    // Копирование массива в обновленный массив
    for (int i = 0; i < N; i++) {
        updatedArr[i] = arr[i];
    }

    // Поиск минимального и максимального элементов
    int minElement = arr[0], maxElement = arr[0];
    int minIndex = 0, maxIndex = 0;
    for (int i = 1; i < N; i++) {
        if (arr[i] < minElement) {
            minElement = arr[i];
            minIndex = i;
        }
        if (arr[i] > maxElement) {
            maxElement = arr[i];
            maxIndex = i;
        }
    }

    // Обнуление элементов между минимальным и максимальным (не включая их)
    for (int i = minIndex + 1; i < maxIndex; i++) {
        updatedArr[i] = 0;
    }

    // Запись обоих массивов в файл
    file.close();
    file.open("data.txt", ios::trunc); // Очистка файла перед записью
    if (!file.is_open()) {
        cerr << "Ошибка: Не удалось открыть файл data.txt" << endl;
        return 1;
    }

    // Запись исходного массива
    file << "Исходный массив:" << endl;
    for (int i = 0; i < N; i++) {
        file << arr[i] << " ";
    }
    file << endl;

    // Запись обновленного массива
    file << "Обновленный массив:" << endl;
    for (int i = 0; i < N; i++) {
        file << updatedArr[i] << " ";
    }
    file.close();

    // Освобождение памяти
    delete[] arr;
    delete[] updatedArr;

    return 0;
}
