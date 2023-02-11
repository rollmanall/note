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
