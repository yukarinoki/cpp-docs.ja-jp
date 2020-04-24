---
title: 生のポインタ (C++)
description: C++ で生のポインタを使用する方法
ms.date: 04/21/2020
helpviewer_keywords:
- pointers [C++]
no-loc:
- void
- nullptr
- const
- char
- new
- delete
ms.openlocfilehash: 8ba188154d7395ce7be3878fa9dbee2fde08a130
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "82032097"
---
# <a name="raw-pointers-c"></a>生のポインタ (C++)

*ポインター*は変数の型です。 メモリ内のオブジェクトのアドレスを格納し、そのオブジェクトにアクセスするために使用されます。 *生のポインタ*は、生存期間が、スマート ポインタなどのカプセル化オブジェクトによって制御されない[ポインタです](smart-pointers-modern-cpp.md)。 生のポインタには、別の非ポインタ変数のアドレスを割り当てることも、値を割り[nullptr](nullptr.md)当てることもできます。 値が割り当てられていないポインターに、ランダム なデータが含まれています。

ポインターを*逆参照*して、ポインターが指すオブジェクトの値を取得することもできます。 *メンバーアクセス演算子*は、オブジェクトのメンバーへのアクセスを提供します。

```cpp
    int* p = nullptr; // declare pointer and initialize it
                      // so that it doesn't store a random address
    int i = 5;
    p = &i; // assign pointer to address of object
    int j = *p; // dereference p to retrieve the value at its address
```

ポインターは、型指定されたオブジェクトまたは を**void** 指すことができます。 プログラムがメモリ内の[ヒープ](https://wikipedia.org/wiki/Heap)上のオブジェクトを割り当てると、そのオブジェクトのアドレスをポインターの形式で受け取ります。 このようなポインタは *、所有ポインタ*と呼ばれます。 所有ポインター (またはそのコピー) を使用して、不要になったヒープ割り当てオブジェクトを明示的に解放する必要があります。 メモリを解放しないと*メモリ リーク*が発生し、そのメモリ位置はコンピュータ上の他のプログラムでは使用できなくなります。 を使用して**new** 割り当てられたメモリは**delete**、 (**delete\[または )** を使用して解放する必要があります。 詳細については、「[newとdelete演算子](new-and-delete-operators.md)」を参照してください。

```cpp
    MyClass* mc = new MyClass(); // allocate object on the heap
    mc->print(); // access class member
    delete mc; // delete object (please don't forget!)
```

ポインター ( として**const** 宣言されていない場合 ) は、メモリ内の別の位置を指すようにインクリメントまたはデクリメントできます。 この操作は *、ポインター演算*と呼ばれます。 C スタイルのプログラミングで、配列やその他のデータ構造の要素を反復処理するために使用されます。 別**const** のメモリ位置を指すポインタを作成することはできません。 [reference](references-cpp.md) 詳細については、「[constと揮発性ポインター](const-and-volatile-pointers.md)」を参照してください。

```cpp
    // declare a C-style string. Compiler adds terminating '\0'.
    const char* str = "Hello world";

    const int c = 1;
    const int* pconst = &c; // declare a non-const pointer to const int
    const int c2 = 2;
    pconst = &c2;  // OK pconst itself isn't const
    const int* const pconst2 = &c;
    // pconst2 = &c2; // Error! pconst2 is const.
```

64 ビットオペレーティング システムでは、ポインターのサイズは 64 ビットです。 システムのポインタサイズによって、アドレス可能なメモリの量が決まります。 ポインターのすべてのコピーは、同じメモリー位置を指します。 ポインタ (参照と共に) は、関数との間で大きなオブジェクトを渡すために、C++ で広く使用されます。 オブジェクト全体をコピーするよりも、オブジェクトのアドレスをコピーする方が効率的な場合が多いためです。 関数を定義する場合は、オブジェクトを変更**const** する関数を意図しない場合に、ポインター・パラメーターを指定します。 一般に**const**、参照はオブジェクトの値が 可能でない限り、関数にオブジェクトを渡す**nullptr** 場合に望ましい方法です。

[関数へのポインタを](#pointers_to_functions)使用すると、関数を他の関数に渡し、Cスタイルのプログラミングで「コールバック」に使用できます。 最新の C++ では、この目的のために[ラムダ式](lambda-expressions-in-cpp.md)を使用します。

## <a name="initialization-and-member-access"></a>初期化およびメンバー・アクセス

次の例は、生のポインターを宣言、初期化、および使用する方法を示しています。 明示的にする必要がある**new** ヒープに割り当てられたオブジェクトをポイントするためにを使用して初期化されます**delete**。 この例では、生のポインターに関連する危険性もいくつか示されています。 (この例は、最新の C++ ではなく、C スタイルのプログラミングです。

```cpp
#include <iostream>
#include <string>

class MyClass
{
public:
    int num;
    std::string name;
    void print() { std::cout << name << ":" << num << std::endl; }
};

// Accepts a MyClass pointer
void func_A(MyClass* mc)
{
    // Modify the object that mc points to.
    // All copies of the pointer will point to
    // the same modified object.
    mc->num = 3;
}

// Accepts a MyClass object
void func_B(MyClass mc)
{
    // mc here is a regular object, not a pointer.
    // Use the "." operator to access members.
    // This statement modifies only the local copy of mc.
    mc.num = 21;
    std::cout << "Local copy of mc:";
    mc.print(); // "Erika, 21"
}


int main()
{
    // Use the * operator to declare a pointer type
    // Use new to allocate and initialize memory
    MyClass* pmc = new MyClass{ 108, "Nick" };

    // Prints the memory address. Usually not what you want.
    std:: cout << pmc << std::endl;

    // Copy the pointed-to object by dereferencing the pointer
    // to access the contents of the memory location.
    // mc is a separate object, allocated here on the stack
    MyClass mc = *pmc;

    // Declare a pointer that points to mc using the addressof operator
    MyClass* pcopy = &mc;

    // Use the -> operator to access the object's public members
    pmc->print(); // "Nick, 108"

    // Copy the pointer. Now pmc and pmc2 point to same object!
    MyClass* pmc2 = pmc;

    // Use copied pointer to modify the original object
    pmc2->name = "Erika";
    pmc->print(); // "Erika, 108"
    pmc2->print(); // "Erika, 108"

    // Pass the pointer to a function.
    func_A(pmc);
    pmc->print(); // "Erika, 3"
    pmc2->print(); // "Erika, 3"

    // Dereference the pointer and pass a copy
    // of the pointed-to object to a function
    func_B(*pmc);
    pmc->print(); // "Erika, 3" (original not modified by function)

    delete(pmc); // don't forget to give memory back to operating system!
   // delete(pmc2); //crash! memory location was already deleted
}
```

## <a name="pointer-arithmetic-and-arrays"></a>ポインター演算と配列

ポインタと配列は密接に関連しています。 配列が値渡しで関数に渡されると、最初の要素へのポインターとして渡されます。 次の例は、ポインターと配列の次の重要なプロパティを示しています。

- 演算子`sizeof`は配列の合計サイズをバイト数で返します
- 要素の数を決定するには、合計バイトを 1 つの要素のサイズで除算します
- 配列が関数に渡されると、ポインター型に*減衰*します。
- ポインター`sizeof`に適用された演算子は、x86 の 4 バイトまたは x64 の 8 バイトのポインター サイズを返します

```cpp
#include <iostream>

void func(int arr[], int length)
{
    // returns pointer size. not useful here.
    size_t test = sizeof(arr);

    for(int i = 0; i < length; ++i)
    {
        std::cout << arr[i] << " ";
    }
}

int main()
{

    int i[5]{ 1,2,3,4,5 };
    // sizeof(i) = total bytes
    int j = sizeof(i) / sizeof(i[0]);
    func(i,j);
}
```

非constポインターに対して特定の算術演算を使用して、別のメモリー位置を指すことができます。 ポインターは、 **++**、**+=** および 演算子**-=** を使用してインクリメントおよび**--** デクリメントされます。 この手法は配列で使用でき、型指定されていないデータのバッファーで特に役立ちます。 A**void** は a **char** (1 バイト) のサイズだけインクリメントされます。 型指定されたポインターは、ポインターが指す型のサイズによってインクリメントされます。

ポインター演算を使用して、Windows 上のビットマップ内の個々のピクセルにアクセスする方法を次の例に示します。 **new** および**delete** と の使用、および逆参照演算子に注意してください。

```cpp
#include <Windows.h>
#include <fstream>

using namespace std;

int main()
{

    BITMAPINFOHEADER header;
    header.biHeight = 100; // Multiple of 4 for simplicity.
    header.biWidth = 100;
    header.biBitCount = 24;
    header.biPlanes = 1;
    header.biCompression = BI_RGB;
    header.biSize = sizeof(BITMAPINFOHEADER);

    constexpr int bufferSize = 30000;
    unsigned char* buffer = new unsigned char[bufferSize];

    BITMAPFILEHEADER bf;
    bf.bfType = 0x4D42;
    bf.bfSize = header.biSize + 14 + bufferSize;
    bf.bfReserved1 = 0;
    bf.bfReserved2 = 0;
    bf.bfOffBits = sizeof(BITMAPFILEHEADER) + sizeof(BITMAPINFOHEADER); //54

    // Create a gray square with a 2-pixel wide outline.
    unsigned char* begin = &buffer[0];
    unsigned char* end = &buffer[0] + bufferSize;
    unsigned char* p = begin;
    constexpr int pixelWidth = 3;
    constexpr int borderWidth = 2;

    while (p < end)
    {
            // Is top or bottom edge?
        if ((p < begin + header.biWidth * pixelWidth * borderWidth)
            || (p > end - header.biWidth * pixelWidth * borderWidth)
            // Is left or right edge?
            || (p - begin) % (header.biWidth * pixelWidth) < (borderWidth * pixelWidth)
            || (p - begin) % (header.biWidth * pixelWidth) > ((header.biWidth - borderWidth) * pixelWidth))
        {
            *p = 0x0; // Black
        }
        else
        {
            *p = 0xC3; // Gray
        }
        p++; // Increment one byte sizeof(unsigned char).
    }

    ofstream wf(R"(box.bmp)", ios::out | ios::binary);

    wf.write(reinterpret_cast<char*>(&bf), sizeof(bf));
    wf.write(reinterpret_cast<char*>(&header), sizeof(header));
    wf.write(reinterpret_cast<char*>(begin), bufferSize);

    delete[] buffer; // Return memory to the OS.
    wf.close();
}
```

## <a name="opno-locvoid-pointers"></a>void* ポインタ

生のメモリ**void** 位置を単純に指すポインタ。 C++ コードと C**void** 関数の間を渡す場合など、ポインターを使用する必要がある場合があります。

型指定されたポインターがvoidポインターにキャストされると、メモリー位置の内容は変更されません。 ただし、型情報が失われるため、インクリメントまたはデクリメント操作を実行することはできません。 メモリの場所は、たとえば、 から から`MyClass*``void*`にキャストしたり、`MyClass*`再び にキャストしたりできます。 このような操作は本質的にエラーが発生しやすく、エラーを避けるために細心の注意が必要です。 現代の C++ では、voidほとんどすべての状況でポインターを使用しないようにします。

```cpp

//func.c
void func(void* data, int length)
{
    char* c = (char*)(data);

    // fill in the buffer with data
    for (int i = 0; i < length; ++i)
    {
        *c = 0x41;
        ++c;
    }
}

// main.cpp
#include <iostream>

extern "C"
{
    void func(void* data, int length);
}

class MyClass
{
public:
    int num;
    std::string name;
    void print() { std::cout << name << ":" << num << std::endl; }
};

int main()
{
    MyClass* mc = new MyClass{10, "Marian"};
    void* p = static_cast<void*>(mc);
    MyClass* mc2 = static_cast<MyClass*>(p);
    std::cout << mc2->name << std::endl; // "Marian"

    // use operator new to allocate untyped memory block
    void* pvoid = operator new(1000);
    char* pchar = static_cast<char*>(pvoid);
    for(char* c = pchar; c < pchar + 1000; ++c)
    {
        *c = 0x00;
    }
    func(pvoid, 1000);
    char ch = static_cast<char*>(pvoid)[0];
    std::cout << ch << std::endl; // 'A'
    operator delete(p);
}
```

## <a name="pointers-to-functions"></a><a name="pointers_to_functions"></a>関数へのポインター

C スタイルのプログラミングでは、関数ポインタは主に関数を他の関数に渡すために使用されます。 この方法を使用すると、呼び出し元は関数の動作を変更せずにカスタマイズできます。 現代の C++ では、[ラムダ式](lambda-expressions-in-cpp.md)はタイプ セーフと他の利点を持つ同じ機能を提供します。

関数ポインター宣言は、指先関数に必要なシグネチャを指定します。

```cpp
// Declare pointer to any function that...

// ...accepts a string and returns a string
string (*g)(string a);

// has no return value and no parameters
void (*x)();

// ...returns an int and takes three parameters
// of the specified types
int (*i)(int i, string s, double d);
```

次の例は、パラメーター`combine`として受け取る関数を受け取`std::string`り、を返`std::string`す関数を示しています。 に渡される関数に`combine`応じて、先頭に文字列を追加するか、または追加します。

```cpp
#include <iostream>
#include <string>

using namespace std;

string base {"hello world"};

string append(string s)
{
    return base.append(" ").append(s);
}

string prepend(string s)
{
    return s.append(" ").append(base);
}

string combine(string s, string(*g)(string a))
{
    return (*g)(s);
}

int main()
{
    cout << combine("from MSVC", append) << "\n";
    cout << combine("Good morning and", prepend) << "\n";
}
```

## <a name="see-also"></a>関連項目

[スマート ポインタ](smart-pointers-modern-cpp.md)
[間接演算子: *](indirection-operator-star.md)<br/>
[address-of 演算子: &](address-of-operator-amp.md)</br>
[C++ へようこそ](welcome-back-to-cpp-modern-cpp.md)
