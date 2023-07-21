#if defined WIN32
	#include "WindowsLogic.h"
#elif defined MAC
    #include "MacLogic.h"
#elif defined LINUX
    #include "LinuxLogic.h"
#endif

class Message
{
public:
    Message(int a) {
	yourObj = YorClass(a);
    }
	YourClass yourObj;
};
#include <iostream>
#include <thread>  //线程类型在此头文件中定义
#include <string>
using namespace std;

int main() {
    //定义线程函数（匿名函数），此函数接收两个参数
    auto func = [](int tId, int num) {
        for (size_t i = 0; i < num; i++)
        {
            string str = "thread id:" + 
                to_string(tId) + "  print:" + to_string(i) + "\n";
            cout << str;
        }
    };
    //开一个线程执行线程函数，给线程函数传入两个参数：0,6
    thread t(func, 0, 6);
    //开另一个线程执行线程函数，参数为1,6
    thread t2(func, 1, 6);
    //join方法可以等待线程结束，
    //如果线程不结束就开启另一个线程，那么两个线程是并行执行的
    //此处两个线程就是并行执行的
    t.join();
    t2.join();
    auto c = getchar();
    for (size_t j = 0; j < num; j++)
        {
            string str = "thread id:" + 
                to_string(tId) + "  print:" + to_string(j) + "\n";
            cout << str;
        }
}

模块：iostream、thread、string
auto func = [](double a, double b) {
        for (size_t i = 0; i < j; i++)
        {
            string str = "id:" + 
                to_string(a) + "  print:" + to_string(i) + "\n";
            cout << str;
        }
    };
    
    排序：
#include <iostream>
using namespace std;

// 交换两个元素
void swap(int* a, int* b) {
    int tmp = *a;
    *a = *b;
    *b = tmp;
}

int partition(int arr[], int low, int high) {
    int pivot = arr[high]; // 选取最后一个元素作为基准
    int i = low - 1; // i 指向最后一个小于等于基准的元素

    for (int j = low; j < high; j++) {
        if (arr[j] <= pivot) {
            i++;
            swap(&arr[i], &arr[j]);
        }
    }
    swap(&arr[i+1], &arr[high]);
    return i + 1;
}

// 快速排序函数
void quickSort(int arr[], int low, int high) {
    if (low < high) {
        int pi = partition(arr, low, high);

        quickSort(arr, low, pi - 1);
        quickSort(arr, pi + 1, high);
    }
}

int main() {
    int arr[] = {10, 7, 8, 9, 1, 5};
    int n = sizeof(arr) / sizeof(arr[0]);

    quickSort(arr, 0, n-1);

    cout << "排序后的数组：" << endl;
    for (int i = 0; i < n; i++) {
        cout << arr[i] << " ";
    }
    cout << endl;

    return 0;
}
冒泡排序：
#include <iostream>
using namespace std;

void bubbleSort(int arr[], int n) {
    for (int i = 0; i < n - 1; ++i) {
        for (int j = 0; j < n - i - 1; ++j) {
            if (arr[j] > arr[j + 1]) {
                swap(arr[j], arr[j + 1]);
            }
        }
    }
}

int main() {
    int arr[] = { 64, 25, 12, 22, 11 };
    int n = sizeof(arr) / sizeof(arr[0]);
    bubbleSort(arr, n);
    cout << "Sorted array: ";
    for (int i = 0; i < n; ++i) {
        cout << arr[i] << " ";
    }
    return 0;
}
c++
#include <iostream>
using namespace std;

void bubbleSort(int arr[], int n) {
    for (int i = 0; i < n-1; i++) {
        for (int j = 0; j < n-i-1; j++) {
            if (arr[j] > arr[j+1]) {
                // 交换元素
                int temp = arr[j];
                arr[j] = arr[j+1];
                arr[j+1] = temp;
            }
        }
    }
}

int main() {
    int arr[] = {64, 34, 25, 12, 22, 11, 90};
    int n = sizeof(arr) / sizeof(arr[0]);
    
    cout << "原始数组：";
    for (int i = 0; i < n; i++) {
        cout << arr[i] << " ";
    }
    
    bubbleSort(arr, n);
    
    cout << "\n排序后的数组：";
    for (int i = 0; i < n; i++) {
        cout << arr[i] << " ";
    }
    
    return 0;
}

