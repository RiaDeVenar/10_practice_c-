# 10_practice_c-
Обмін і пошук
#include <iostream>
using namespace std;

void swapByPointer(int *a, int *b) 
{
    int temp = *a;
    *a = *b;
    *b = temp;
}

int sumByPointer(const int *p, int size) 
{
    int sum = 0;
    for (int i = 0; i < size; i++) 
    {
        sum += *(p + i); 
    }
    return sum;
}

int* findMax(int *p, int size) 
{
    int *maxPtr = p;
    for (int i = 1; i < size; i++) 
    {
        if (*(p + i) > *maxPtr) 
        {
            maxPtr = p + i;
        }
    }
    return maxPtr;
}

int main() 
{
    int n;
    if (!(cin >> n)) return 1;

    int arr[100];
    for (int i = 0; i < n; i++) 
    {
        cin >> arr[i];
    }

    int sum = sumByPointer(arr, n);
    cout << "suma " << sum << "\n";

    int *maxPtr = findMax(arr, n);
    
    int maxIndex = maxPtr - arr; 
    
    cout << "max " << *maxPtr << " index " << maxIndex << "\n";

    swapByPointer(arr, maxPtr);

    cout << "pislia obminu ";
        for (int i = 0; i < n; i++) 
        {
            cout << arr[i];
        
            if (i < n - 1) 
            {
                cout << " ";
            }
        }
    cout << "\n";

    return 0;
}
