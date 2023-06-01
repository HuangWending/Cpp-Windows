# Cpp-Windows
C++创建窗口
#include <windows.h>：包含Windows API的头文件，提供了与操作系统交互的功能。
LRESULT CALLBACK WindowProc(HWND hwnd, UINT uMsg, WPARAM wParam, LPARAM lParam)：窗口过程的回调函数，用于处理窗口消息。
int WINAPI WinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPSTR lpCmdLine, int nCmdShow)：程序的入口点。
WNDCLASS wc = {};：定义一个WNDCLASS结构体对象wc，用于注册窗口类。
wc.lpfnWndProc = WindowProc;：指定窗口过程的回调函数。
wc.hInstance = hInstance;：指定窗口实例的句柄。
wc.lpszClassName = "MyWindowClass";：指定窗口类的名称。
RegisterClass(&wc);：注册窗口类。
HWND hwnd = CreateWindowEx(...);：创建窗口实例。
ShowWindow(hwnd, nCmdShow);：显示窗口。
MSG msg = {};：定义一个MSG结构体对象msg，用于接收窗口消息。
while (GetMessage(&msg, NULL, 0, 0)) { ... }：消息循环，处理窗口消息。
TranslateMessage(&msg);：将虚拟键消息转换为字符消息。
DispatchMessage(&msg);：将消息分派给窗口过程进行处理。
switch (uMsg) { ... }：窗口过程中的消息处理。
case WM_DESTROY: ...：当窗口被销毁时的处理。
PostQuitMessage(0);：发送退出消息，终止消息循环。
return DefWindowProc(hwnd, uMsg, wParam, lParam);：默认的窗口消息处理。
创建一个标题为"HuangWending's Window"、大小为400x300像素的窗口，并进入消息循环，处理窗口消息。当你关闭窗口时，程序将退出。
