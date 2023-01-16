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
