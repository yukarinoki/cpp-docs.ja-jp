---
title: 生のポインター (C++)
description: C++ で生のポインターを使用する方法
ms.date: 04/21/2020
helpviewer_keywords:
- pointers [C++]
no-loc:
- ':::no-loc(void):::'
- ':::no-loc(nullptr):::'
- ':::no-loc(const):::'
- ':::no-loc(char):::'
- ':::no-loc(new):::'
- ':::no-loc(delete):::'
ms.openlocfilehash: 53679559888191fe7f2aad7cb5a70d607974ae96
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233653"
---
# <a name="raw-pointers-c"></a>生のポインター (C++)

*ポインター*は変数の型です。 オブジェクトのアドレスをメモリに格納し、そのオブジェクトにアクセスするために使用されます。 *生のポインター*は、[スマートポインター](smart-pointers-modern-cpp.md)など、カプセル化されたオブジェクトによって有効期間が制御されないポインターです。 生のポインターには、別の非ポインター変数のアドレスを割り当てることも、値を割り当てることもでき [:::no-loc(nullptr):::](:::no-loc(nullptr):::.md) ます。 値が割り当てられていないポインターには、ランダムなデータが含まれています。

ポインターを*逆*参照して、そのポインターが指すオブジェクトの値を取得することもできます。 *メンバーアクセス演算子*は、オブジェクトのメンバーへのアクセスを提供します。

```cpp
    int* p = :::no-loc(nullptr):::; // declare pointer and initialize it
                      // so that it doesn't store a random address
    int i = 5;
    p = &i; // assign pointer to address of object
    int j = *p; // dereference p to retrieve the value at its address
```

ポインターは、型指定されたオブジェクトまたはを指すことができ **`:::no-loc(void):::`** ます。 プログラムによってメモリ内の[ヒープ](https://wikipedia.org/wiki/Heap)にオブジェクトが割り当てられると、オブジェクトのアドレスがポインターの形式で受信されます。 このようなポインターは、所有している*ポインター*と呼ばれます。 不要になったときに、ヒープに割り当てられたオブジェクトを明示的に解放するには、所有しているポインター (またはそのコピー) を使用する必要があります。 メモリの解放に失敗すると、*メモリリーク*が発生し、そのメモリの場所をコンピューター上の他のプログラムで使用できなくなります。 を使用して割り当てられたメモリは、 **`:::no-loc(new):::`** **`:::no-loc(delete):::`** (または) ** :::no-loc(delete)::: \[ **を使用して解放する必要があります。 詳細については、「」 [ :::no-loc(new)::: および「 :::no-loc(delete)::: 演算子](:::no-loc(new):::-and-:::no-loc(delete):::-operators.md)」を参照してください。

```cpp
    MyClass* mc = :::no-loc(new)::: MyClass(); // allocate object on the heap
    mc->print(); // access class member
    :::no-loc(delete)::: mc; // :::no-loc(delete)::: object (please don't forget!)
```

ポインター (として宣言されていない場合) は、 **`:::no-loc(const):::`** メモリ内の別の場所を指すようにインクリメントまたはデクリメントできます。 この操作は、*ポインター演算*と呼ばれます。 これは、C スタイルのプログラミングで、配列またはその他のデータ構造体の要素を反復処理するために使用されます。 ポインターを別のメモリ位置を指すようにすることは **`:::no-loc(const):::`** できません。その意味は[参照](references-cpp.md)に似ています。 詳細については、「」 [ :::no-loc(const)::: および「volatile ポインター](:::no-loc(const):::-and-volatile-pointers.md)」を参照してください。

```cpp
    // declare a C-style string. Compiler adds terminating '\0'.
    :::no-loc(const)::: :::no-loc(char):::* str = "Hello world";

    :::no-loc(const)::: int c = 1;
    :::no-loc(const)::: int* p:::no-loc(const)::: = &c; // declare a non-:::no-loc(const)::: pointer to :::no-loc(const)::: int
    :::no-loc(const)::: int c2 = 2;
    p:::no-loc(const)::: = &c2;  // OK p:::no-loc(const)::: itself isn't :::no-loc(const):::
    :::no-loc(const)::: int* :::no-loc(const)::: p:::no-loc(const):::2 = &c;
    // p:::no-loc(const):::2 = &c2; // Error! p:::no-loc(const):::2 is :::no-loc(const):::.
```

64ビットオペレーティングシステムでは、ポインターのサイズは64ビットです。 システムのポインターサイズによって、使用可能なメモリの量が決まります。 ポインターのすべてのコピーが同じメモリ位置を指しています。 ポインター (および参照) は、より大きなオブジェクトを関数との間でやり取りするために C++ で幅広く使用されます。 これは、多くの場合、オブジェクト全体をコピーするよりも、オブジェクトのアドレスをコピーする方が効率的であるためです。 関数を定義する場合は、 **`:::no-loc(const):::`** 関数がオブジェクトを変更することを意図しない限り、ポインターパラメーターをとして指定します。 一般に、オブジェクト **`:::no-loc(const):::`** の値がである可能性がある場合を除き、オブジェクトを関数に渡すには、参照を使用することをお勧めし **`:::no-loc(nullptr):::`** ます。

[関数へのポインター](#pointers_to_functions)を使用すると、関数を他の関数に渡すことができ、C スタイルのプログラミングでは "コールバック" に使用されます。 最新の C++ では、この目的で[ラムダ式](lambda-expressions-in-cpp.md)を使用します。

## <a name="initialization-and-member-access"></a>初期化とメンバーアクセス

次の例は、生のポインターを宣言、初期化、および使用する方法を示しています。 これは、を使用して初期化され、 **`:::no-loc(new):::`** ヒープに割り当てられたオブジェクトをポイントします。これは明示的に指定する必要があり **`:::no-loc(delete):::`** ます。 この例では、生のポインターに関連するいくつかの危険も示しています。 (この例は C スタイルのプログラミングであり、最新の C++ ではないことに注意してください)。

```cpp
#include <iostream>
#include <string>

class MyClass
{
public:
    int num;
    std::string name;
    :::no-loc(void)::: print() { std::cout << name << ":" << num << std::endl; }
};

// Accepts a MyClass pointer
:::no-loc(void)::: func_A(MyClass* mc)
{
    // Modify the object that mc points to.
    // All copies of the pointer will point to
    // the same modified object.
    mc->num = 3;
}

// Accepts a MyClass object
:::no-loc(void)::: func_B(MyClass mc)
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
    // Use :::no-loc(new)::: to allocate and initialize memory
    MyClass* pmc = :::no-loc(new)::: MyClass{ 108, "Nick" };

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

    :::no-loc(delete):::(pmc); // don't forget to give memory back to operating system!
   // :::no-loc(delete):::(pmc2); //crash! memory location was already :::no-loc(delete):::d
}
```

## <a name="pointer-arithmetic-and-arrays"></a>ポインターの算術演算と配列

ポインターと配列は密接に関連しています。 配列が値渡しで関数に渡されると、最初の要素へのポインターとして渡されます。 次の例は、ポインターと配列の次の重要なプロパティを示しています。

- 演算子は、 **`sizeof`** 配列の合計サイズ (バイト単位) を返します。
- 要素の数を決定するには、合計バイトを1つの要素のサイズで除算します。
- 配列が関数に渡されると、 *decays*はポインター型になります。
- **`sizeof`** ポインターに適用した場合の演算子は、ポインターのサイズ、x86 の場合は4バイト、x64 の場合は8バイトを返します。

```cpp
#include <iostream>

:::no-loc(void)::: func(int arr[], int length)
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

特定の算術演算を非ポインターで使用して :::no-loc(const)::: 、別のメモリ位置を指すようにすることができます。 ポインターは、、、およびの各演算子を使用してインクリメントおよびデクリメントされ **++** **+=** **-=** **--** ます。 この手法は配列で使用でき、型指定されていないデータのバッファーで特に便利です。 は **:::no-loc(void):::\*** 、のサイズ (1 バイト) によって増加し **`:::no-loc(char):::`** ます。 型指定されたポインターは、ポインターが指す型のサイズによって増加します。

次の例は、ポインター演算を使用して、Windows 上のビットマップ内の個々のピクセルにアクセスする方法を示しています。 とを使用し、 **`:::no-loc(new):::`** 逆参照演算子を使用することに注意して **`:::no-loc(delete):::`** ください。

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

    :::no-loc(const):::expr int bufferSize = 30000;
    unsigned :::no-loc(char):::* buffer = :::no-loc(new)::: unsigned :::no-loc(char):::[bufferSize];

    BITMAPFILEHEADER bf;
    bf.bfType = 0x4D42;
    bf.bfSize = header.biSize + 14 + bufferSize;
    bf.bfReserved1 = 0;
    bf.bfReserved2 = 0;
    bf.bfOffBits = sizeof(BITMAPFILEHEADER) + sizeof(BITMAPINFOHEADER); //54

    // Create a gray square with a 2-pixel wide outline.
    unsigned :::no-loc(char):::* begin = &buffer[0];
    unsigned :::no-loc(char):::* end = &buffer[0] + bufferSize;
    unsigned :::no-loc(char):::* p = begin;
    :::no-loc(const):::expr int pixelWidth = 3;
    :::no-loc(const):::expr int borderWidth = 2;

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
        p++; // Increment one byte sizeof(unsigned :::no-loc(char):::).
    }

    ofstream wf(R"(box.bmp)", ios::out | ios::binary);

    wf.write(reinterpret_cast<:::no-loc(char):::*>(&bf), sizeof(bf));
    wf.write(reinterpret_cast<:::no-loc(char):::*>(&header), sizeof(header));
    wf.write(reinterpret_cast<:::no-loc(char):::*>(begin), bufferSize);

    :::no-loc(delete):::[] buffer; // Return memory to the OS.
    wf.close();
}
```

## <a name="no-locvoid-pointers"></a>:::no-loc(void):::* ポインター

を指すポインターは、 **`:::no-loc(void):::`** 単に生のメモリ位置を指します。 場合によっては **:::no-loc(void):::\*** 、C++ コードと C 関数の間を渡すときなどに、ポインターを使用する必要があります。

型指定されたポインターがポインターにキャストされると、 :::no-loc(void)::: メモリ位置の内容は変更されません。 ただし、インクリメントまたはデクリメント操作を実行できないように、型情報は失われます。 などのメモリ位置をキャストすることができ `MyClass*` **`:::no-loc(void):::*`** `MyClass*` ます。 このような操作は本質的にエラーが発生しやすく、エラーに細心の注意を払う必要があり :::no-loc(void)::: ます。 最新の C++ では、 :::no-loc(void)::: ほとんどすべての状況でポインターの使用が推奨されていません。

```cpp

//func.c
:::no-loc(void)::: func(:::no-loc(void):::* data, int length)
{
    :::no-loc(char):::* c = (:::no-loc(char):::*)(data);

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
    :::no-loc(void)::: func(:::no-loc(void):::* data, int length);
}

class MyClass
{
public:
    int num;
    std::string name;
    :::no-loc(void)::: print() { std::cout << name << ":" << num << std::endl; }
};

int main()
{
    MyClass* mc = :::no-loc(new)::: MyClass{10, "Marian"};
    :::no-loc(void):::* p = static_cast<:::no-loc(void):::*>(mc);
    MyClass* mc2 = static_cast<MyClass*>(p);
    std::cout << mc2->name << std::endl; // "Marian"

    // use operator :::no-loc(new)::: to allocate untyped memory block
    :::no-loc(void):::* p:::no-loc(void)::: = operator :::no-loc(new):::(1000);
    :::no-loc(char):::* p:::no-loc(char)::: = static_cast<:::no-loc(char):::*>(p:::no-loc(void):::);
    for(:::no-loc(char):::* c = p:::no-loc(char):::; c < p:::no-loc(char)::: + 1000; ++c)
    {
        *c = 0x00;
    }
    func(p:::no-loc(void):::, 1000);
    :::no-loc(char)::: ch = static_cast<:::no-loc(char):::*>(p:::no-loc(void):::)[0];
    std::cout << ch << std::endl; // 'A'
    operator :::no-loc(delete):::(p);
}
```

## <a name="pointers-to-functions"></a><a name="pointers_to_functions"></a>関数へのポインター

C スタイルのプログラミングでは、関数ポインターは主に他の関数に関数を渡すために使用されます。 この手法を使用すると、呼び出し元は関数の動作を変更せずにカスタマイズできます。 最新の C++ では、[ラムダ式](lambda-expressions-in-cpp.md)によって同じ機能が提供され、型の安全性が向上し、その他の利点もあります。

関数ポインター宣言は、ポイント先の関数が持つ必要があるシグネチャを指定します。

```cpp
// Declare pointer to any function that...

// ...accepts a string and returns a string
string (*g)(string a);

// has no return value and no parameters
:::no-loc(void)::: (*x)();

// ...returns an int and takes three parameters
// of the specified types
int (*i)(int i, string s, double d);
```

次の例は、を受け取ってを返す関数を `combine` パラメーターとして受け取る関数を示して `std::string` `std::string` います。 に渡される関数に応じて `combine` 、文字列の先頭または末尾に値が付加されます。

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

[スマートポインター](smart-pointers-modern-cpp.md) 
[間接演算子: *](indirection-operator-star.md)<br/>
[address-of 演算子: &](address-of-operator-amp.md)</br>
[C++ へようこそ](welcome-back-to-cpp-modern-cpp.md)
