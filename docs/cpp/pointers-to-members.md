---
title: メンバーへのポインター
ms.date: 11/04/2016
helpviewer_keywords:
- declarations, pointers
- class members [C++], pointers to
- pointers, to members
- members [C++], pointers to
- pointers, declarations
ms.assetid: f42ddb79-9721-4e39-95b1-c56b55591f68
ms.openlocfilehash: 75bd29310d64b0309ac48be053aa43cc0084aa2d
ms.sourcegitcommit: 1a8fac06478da8bee1f6d70e25afbad94144af1a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/30/2020
ms.locfileid: "84226093"
---
# <a name="pointers-to-members"></a>メンバーへのポインター

メンバーへのポインターの宣言は、ポインター宣言の特殊なケースです。  これらは、次のシーケンスを使用して宣言されています。

> *ストレージクラス指定子の*<sub>選択</sub>: *cv-修飾子*<sub>opt</sub> *型指定子* *ms-修飾子*<sub>opt</sub> *修飾名* **`::*`** *cv-修飾子*<sub>opt</sub> *識別子* *pm-初期化子*<sub>opt</sub>**`;`**

1. 宣言指定子: 

   - ストレージ クラスの指定子 (省略可能)。

   - 省略可能な**const**および**volatile**指定子。

   - 型指定子: 型の名前。 これは、クラスではなく、ポイントするメンバーの型です。

1. 宣言子: 

   - オプションの Microsoft 固有の修飾子。 詳細については、「 [Microsoft 固有の修飾子](../cpp/microsoft-specific-modifiers.md)」を参照してください。

   - 指されるメンバーが含まれるクラスの修飾名。

   - __`::`__ 演算子。

   - __`*`__ 演算子。

   - 省略可能な**const**および**volatile**指定子。

   - メンバーへのポインターを指定する識別子。

1. 省略可能な pointer-to-member 初期化子:

   - **`=`** 演算子。

   - **`&`** 演算子。

   - クラスの修飾名。

   - __`::`__ 演算子。

   - 適切な型のクラスの非静的メンバーの名前。

当然ながら、1 つの宣言で複数の宣言子 (および関連する初期化子) を使用できます。 メンバーへのポインターは、クラスの静的メンバー、参照型のメンバー、またはを指していない可能性があり **`void`** ます。

クラスのメンバーへのポインターは、通常のポインターとは異なります。メンバーの型とメンバーが属するクラスの両方の型情報が含まれています。 通常のポインターは、メモリ内の 1 つのオブジェクトだけを識別します (1 つのオブジェクトのアドレスだけを持ちます)。 クラスのメンバーへのポインターは、クラスのインスタンスのメンバーを識別します。 次の例では、`Window` クラス、およびメンバー データへのポインターをいくつか宣言します。

```cpp
// pointers_to_members1.cpp
class Window
{
public:
   Window();                               // Default constructor.
   Window( int x1, int y1,                 // Constructor specifying
   int x2, int y2 );                       // Window size.
   bool SetCaption( const char *szTitle ); // Set window caption.
   const char *GetCaption();               // Get window caption.
   char *szWinCaption;                     // Window caption.
};

// Declare a pointer to the data member szWinCaption.
char * Window::* pwCaption = &Window::szWinCaption;
int main()
{
}
```

前の例で `pwCaption` は、は型のクラスのメンバーへのポインターです `Window` `char*` 。 `pwCaption` の型は `char * Window::*` です。 次のコードでは、メンバー関数 `SetCaption` および `GetCaption` へのポインターを宣言します。

```cpp
const char * (Window::* pfnwGC)() = &Window::GetCaption;
bool (Window::* pfnwSC)( const char * ) = &Window::SetCaption;
```

ポインター `pfnwGC` および `pfnwSC` はそれぞれ、`GetCaption` クラスの `SetCaption` および `Window` を指します。 次のコードは、メンバー `pwCaption` へのポインターを使用してウィンドウ キャプションに情報を直接コピーします。

```cpp
Window  wMainWindow;
Window *pwChildWindow = new Window;
char   *szUntitled    = "Untitled -  ";
int     cUntitledLen  = strlen( szUntitled );

strcpy_s( wMainWindow.*pwCaption, cUntitledLen, szUntitled );
(wMainWindow.*pwCaption)[cUntitledLen - 1] = '1';     // same as
// wMainWindow.SzWinCaption [cUntitledLen - 1] = '1';
strcpy_s( pwChildWindow->*pwCaption, cUntitledLen, szUntitled );
(pwChildWindow->*pwCaption)[cUntitledLen - 1] = '2'; // same as
// pwChildWindow->szWinCaption[cUntitledLen - 1] = '2';
```

演算子 **`.*`** と **`->*`** 演算子 (メンバーへのポインター演算子) の違いは、演算子が **`.*`** オブジェクト参照またはオブジェクト参照を指定してメンバーを選択し、 **`->*`** 演算子がポインターを通じてメンバーを選択することです。 これらの演算子の詳細については、「 [Pointer-to-member 演算子を使用した式](../cpp/pointer-to-member-operators-dot-star-and-star.md)」を参照してください。

メンバーへのポインター演算子の結果は、メンバーの型になります。 このケースでは `char *` です。

次のコードでは、メンバーへのポインターを使用して、メンバー関数 `GetCaption` および `SetCaption` を呼び出します。

```cpp
// Allocate a buffer.
enum {
    sizeOfBuffer = 100
};
char szCaptionBase[sizeOfBuffer];

// Copy the main window caption into the buffer
//  and append " [View 1]".
strcpy_s( szCaptionBase, sizeOfBuffer, (wMainWindow.*pfnwGC)() );
strcat_s( szCaptionBase, sizeOfBuffer, " [View 1]" );
// Set the child window's caption.
(pwChildWindow->*pfnwSC)( szCaptionBase );
```

## <a name="restrictions-on-pointers-to-members"></a>メンバーへのポインターに関する制約

静的メンバーのアドレスがメンバーへのポインターではありません。 これは、静的メンバーの1つのインスタンスへの通常のポインターです。 静的メンバーのインスタンスは、特定のクラスのすべてのオブジェクトに対して1つだけ存在します。 つまり、通常の address of ( **&** ) 演算子と逆参照 () 演算子を使用でき <strong>\*</strong> ます。

## <a name="pointers-to-members-and-virtual-functions"></a>メンバーと仮想関数へのポインター

メンバーへのポインター関数を使用した仮想関数の呼び出しは、関数が直接呼び出されたかのように機能します。 正しい関数が v テーブルで検索され、呼び出されます。

この場合も、仮想関数が正しく機能するうえで重要なことは、基底クラスへのポインターを介して仮想関数を呼び出すことです。 (仮想関数の詳細については、「[仮想関数](../cpp/virtual-functions.md)」を参照してください)。

次のコードは、メンバー関数へのポインターを介して仮想関数を呼び出す方法を示しています。

```cpp
// virtual_functions.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

class Base
{
public:
    virtual void Print();
};
void (Base::* bfnPrint)() = &Base::Print;
void Base::Print()
{
    cout << "Print function for class Base" << endl;
}

class Derived : public Base
{
public:
    void Print();  // Print is still a virtual function.
};

void Derived::Print()
{
    cout << "Print function for class Derived" << endl;
}

int main()
{
    Base   *bPtr;
    Base    bObject;
    Derived dObject;
    bPtr = &bObject;    // Set pointer to address of bObject.
    (bPtr->*bfnPrint)();
    bPtr = &dObject;    // Set pointer to address of dObject.
    (bPtr->*bfnPrint)();
}

// Output:
// Print function for class Base
// Print function for class Derived
```
