# -#include <iostream>
using namespace std;

// تابع برای جمع دو ماتریس
void addMatrices(int matrix1[][3], int matrix2[][3], int result[][3], int rows, int cols) {
    for(int i = 0; i < rows; i++) {
        for(int j = 0; j < cols; j++) {
            result[i][j] = matrix1[i][j] + matrix2[i][j];
        }
    }
}

// تابع برای تفریق دو ماتریس
void subtractMatrices(int matrix1[][3], int matrix2[][3], int result[][3], int rows, int cols) {
    for(int i = 0; i < rows; i++) {
        for(int j = 0; j < cols; j++) {
            result[i][j] = matrix1[i][j] - matrix2[i][j];
        }
    }
}

// تابع برای چاپ ماتریس
void printMatrix(int matrix[][3], int rows, int cols) {
    for(int i = 0; i < rows; i++) {
        for(int j = 0; j < cols; j++) {
            cout << matrix[i][j] << " ";
        }
        cout << endl;
    }
}

int main() {
    const int rows = 3;
    const int cols = 3;

    int matrix1[rows][cols] = {{1, 2, 3}, {4, 5, 6}, {7, 8, 9}};
    int matrix2[rows][cols] = {{9, 8, 7}, {6, 5, 4}, {3, 2, 1}};
    int resultAdd[rows][cols];
    int resultSubtract[rows][cols];

    cout << "Matrix 1:" << endl;
    printMatrix(matrix1, rows, cols);

    cout << "Matrix 2:" << endl;
    printMatrix(matrix2, rows, cols);

    // جمع ماتریس‌ها
    addMatrices(matrix1, matrix2, resultAdd, rows, cols);
    cout << "\nSum of the matrices:" << endl;
    printMatrix(resultAdd, rows, cols);

    // تفریق ماتریس‌ها
    subtractMatrices(matrix1, matrix2, resultSubtract, rows, cols);
    cout << "\nDifference of the matrices:" << endl;
    printMatrix(resultSubtract, rows, cols);

    return 0;
}

#include <iostream>
using namespace std;

// تابع برای ضرب یک عدد در ماتریس
void multiplyMatrixByScalar(int matrix[][3], int scalar, int result[][3], int rows, int cols) {
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            result[i][j] = matrix[i][j] * scalar;
        }
    }
}

// تابع برای چاپ ماتریس
void printMatrix(int matrix[][3], int rows, int cols) {
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            cout << matrix[i][j] << " ";
        }
        cout << endl;
    }
}

int main() {
    const int rows = 3;
    const int cols = 3;

    // تعریف ماتریس
    int matrix[rows][cols] = {{1, 2, 3}, {4, 5, 6}, {7, 8, 9}};
    int result[rows][cols];
    int scalar;

    // وارد کردن عدد
    cout << "Enter a scalar number to multiply with the matrix: ";
    cin >> scalar;

    cout << "\nOriginal Matrix:" << endl;
    printMatrix(matrix, rows, cols);

    // ضرب عدد در ماتریس
    multiplyMatrixByScalar(matrix, scalar, result, rows, cols);

    cout << "\nMatrix after multiplying by " << scalar << ":" << endl;
    printMatrix(result, rows, cols);

    return 0;
}

#include <iostream>
using namespace std;

// تابع برای دریافت ماتریس از کاربر
void inputMatrix(int matrix[][10], int rows, int cols) {
    cout << "Enter the elements of the matrix:" << endl;
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            cout << "Element [" << i + 1 << "][" << j + 1 << "]: ";
            cin >> matrix[i][j];
        }
    }
}

// تابع برای چاپ ماتریس
void printMatrix(int matrix[][10], int rows, int cols) {
    cout << "The matrix is:" << endl;
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            cout << matrix[i][j] << " ";
        }
        cout << endl;
    }
}

int main() {
    int rows, cols;
    
    // دریافت ابعاد ماتریس از کاربر
    cout << "Enter the number of rows: ";
    cin >> rows;
    cout << "Enter the number of columns: ";
    cin >> cols;

    // تعریف ماتریس
    int matrix[10][10];  // فرض می‌کنیم حداکثر ابعاد 10x10 باشد

    // دریافت ماتریس از کاربر
    inputMatrix(matrix, rows, cols);

    // چاپ ماتریس
    printMatrix(matrix, rows, cols);

    return 0;
}

#include <iostream>
using namespace std;

// تابع برای چاپ ماتریس
void printMatrix(int matrix[][10], int rows, int cols) {
    cout << "The matrix is:" << endl;
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            cout << matrix[i][j] << " ";
        }
        cout << endl;
    }
}

int main() {
    int rows, cols;
    
    // دریافت ابعاد ماتریس از کاربر
    cout << "Enter the number of rows: ";
    cin >> rows;
    cout << "Enter the number of columns: ";
    cin >> cols;

    // تعریف ماتریس
    int matrix[10][10];  // فرض می‌کنیم حداکثر ابعاد 10x10 باشد

    // دریافت مقادیر ماتریس از کاربر
    cout << "Enter the elements of the matrix:" << endl;
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            cout << "Element [" << i + 1 << "][" << j + 1 << "]: ";
            cin >> matrix[i][j];
        }
    }

    // چاپ ماتریس
    printMatrix(matrix, rows, cols);

    return 0;
}

#include <iostream>
using namespace std;

// تابع برای ضرب دو ماتریس
void multiplyMatrices(int matrix1[][10], int matrix2[][10], int result[][10], int rows1, int cols1, int rows2, int cols2) {
    // بررسی امکان ضرب ماتریس‌ها
    if (cols1 != rows2) {
        cout << "Matrix multiplication is not possible. The number of columns of the first matrix must equal the number of rows of the second matrix." << endl;
        return;
    }
    
    // ضرب ماتریس‌ها
    for (int i = 0; i < rows1; i++) {
        for (int j = 0; j < cols2; j++) {
            result[i][j] = 0;
            for (int k = 0; k < cols1; k++) {
                result[i][j] += matrix1[i][k] * matrix2[k][j];
            }
        }
    }
}

// تابع برای چاپ ماتریس
void printMatrix(int matrix[][10], int rows, int cols) {
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            cout << matrix[i][j] << " ";
        }
        cout << endl;
    }
}

int main() {
    int rows1, cols1, rows2, cols2;

    // دریافت ابعاد ماتریس اول
    cout << "Enter the number of rows and columns for the first matrix: ";
    cin >> rows1 >> cols1;

    // دریافت ابعاد ماتریس دوم
    cout << "Enter the number of rows and columns for the second matrix: ";
    cin >> rows2 >> cols2;

    // تعریف ماتریس‌ها
    int matrix1[10][10], matrix2[10][10], result[10][10];

    // دریافت مقادیر ماتریس اول از کاربر
    cout << "Enter the elements of the first matrix:" << endl;
    for (int i = 0; i < rows1; i++) {
        for (int j = 0; j < cols1; j++) {
            cout << "Element [" << i + 1 << "][" << j + 1 << "]: ";
            cin >> matrix1[i][j];
        }
    }

    // دریافت مقادیر ماتریس دوم از کاربر
    cout << "Enter the elements of the second matrix:" << endl;
    for (int i = 0; i < rows2; i++) {
        for (int j = 0; j < cols2; j++) {
            cout << "Element [" << i + 1 << "][" << j + 1 << "]: ";
            cin >> matrix2[i][j];
        }
    }

    // ضرب ماتریس‌ها
    multiplyMatrices(matrix1, matrix2, result, rows1, cols1, rows2, cols2);

    // چاپ نتیجه
    cout << "Result of matrix multiplication:" << endl;
    printMatrix(result, rows1, cols2);

    return 0;
}

#include <iostream>
using namespace std;

// تابع برای جستجو یک آرایه در ماتریس
bool searchArrayInMatrix(int matrix[][10], int rows, int cols, int array[], int arraySize) {
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            // بررسی اگر اولین عنصر آرایه با عنصر فعلی ماتریس برابر باشد
            if (matrix[i][j] == array[0]) {
                bool found = true;
                // جستجو برای بقیه عناصر آرایه در همان ردیف یا ستون
                for (int k = 1; k < arraySize; k++) {
                    // بررسی در صورت برخورد با محدوده ماتریس
                    if (i + k < rows && matrix[i + k][j] == array[k]) {
                        continue;
                    } else {
                        found = false;
                        break;
                    }
                }
                if (found) {
                    return true; // اگر آرایه پیدا شد، تابع true برمی‌گرداند
                }
            }
        }
    }
    return false; // اگر آرایه پیدا نشد
}

// تابع برای چاپ ماتریس
void printMatrix(int matrix[][10], int rows, int cols) {
    cout << "Matrix is:" << endl;
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            cout << matrix[i][j] << " ";
        }
        cout << endl;
    }
}

int main() {
    int rows, cols, arraySize;

    // دریافت ابعاد ماتریس
    cout << "Enter the number of rows and columns for the matrix: ";
    cin >> rows >> cols;

    // تعریف ماتریس
    int matrix[10][10];

    // دریافت مقادیر ماتریس از کاربر
    cout << "Enter the elements of the matrix:" << endl;
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            cout << "Element [" << i + 1 << "][" << j + 1 << "]: ";
            cin >> matrix[i][j];
        }
    }

    // دریافت آرایه برای جستجو
    cout << "Enter the size of the array to search: ";
    cin >> arraySize;
    int array[arraySize];

    cout << "Enter the elements of the array:" << endl;
    for (int i = 0; i < arraySize; i++) {
        cout << "Element " << i + 1 << ": ";
        cin >> array[i];
    }

    // چاپ ماتریس
    printMatrix(matrix, rows, cols);

    // جستجو برای آرایه در ماتریس
    if (searchArrayInMatrix(matrix, rows, cols, array, arraySize)) {
        cout << "The array is found in the matrix." << endl;
    } else {
        cout << "The array is not found in the matrix." << endl;
    }

    return 0;
}
