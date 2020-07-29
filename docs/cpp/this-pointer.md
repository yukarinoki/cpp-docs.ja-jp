---
title: ':::no-loc(this)::: ポインター'
description: :::no-loc(this):::ポインターは、非静的メンバー関数内の現在のオブジェクトへのコンパイラによって生成されたポインターです。
ms.date: 01/22/2020
f1_keywords:
- :::no-loc(this):::_cpp
helpviewer_keywords:
- nonstatic member functions [C++]
- 'pointers, to :::no-loc(class)::: instance'
- ':::no-loc(this)::: pointer'
ms.assetid: 92e3256a-4ad9-4d46-8be1-d77fad90791f
no-loc:
- ':::no-loc(this):::'
- ':::no-loc(class):::'
- ':::no-loc(struct):::'
- ':::no-loc(union):::'
- ':::no-loc(sizeof):::'
- ':::no-loc(const):::'
- ':::no-loc(volatile):::'
ms.openlocfilehash: c851beaba7fe1091ffd7827714f90307303058c1
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225827"
---
# <a name="no-locthis-pointer"></a>:::no-loc(this)::: ポインター

**`:::no-loc(this):::`** ポインターは **`:::no-loc(class):::`** 、、 **`:::no-loc(struct):::`** 、または型の非静的メンバー関数内でのみアクセス可能なポインターです **`:::no-loc(union):::`** 。 これは、呼び出されるメンバー関数によって処理されるオブジェクトを指します。 静的メンバー関数にはポインターがありません **`:::no-loc(this):::`** 。

## <a name="syntax"></a>構文

```cpp
:::no-loc(this):::
:::no-loc(this):::->member-identifier
```

## <a name="remarks"></a>解説

オブジェクトの **`:::no-loc(this):::`** ポインターは、オブジェクト自体の一部ではありません。 オブジェクトのステートメントの結果には反映されません **`:::no-loc(sizeof):::`** 。 オブジェクトに対して非静的メンバー関数が呼び出されると、コンパイラは、オブジェクトのアドレスを非表示の引数として関数に渡します。 たとえば、次の関数を呼び出してみましょう。

```cpp
myDate.setMonth( 3 );
```

次のように解釈できます。

```cpp
setMonth( &myDate, 3 );
```

オブジェクトのアドレスは、メンバー関数内からポインターとして使用でき **`:::no-loc(this):::`** ます。 ほとんど **`:::no-loc(this):::`** のポインターは暗黙的に使用されます。 のメンバーを参照するときに、明示的なを使用する必要は **`:::no-loc(this):::`** :::no-loc(class)::: ありません。 次に例を示します。

```cpp
void Date::setMonth( int mn )
{
   month = mn;            // These three statements
   :::no-loc(this):::->month = mn;      // are equivalent
   (*:::no-loc(this):::).month = mn;
}
```

式 **`*:::no-loc(this):::`** は、通常、メンバー関数から現在のオブジェクトを返すために使用されます。

```cpp
return *:::no-loc(this):::;
```

**`:::no-loc(this):::`** ポインターは、自己参照を防ぐためにも使用されます。

```cpp
if (&Object != :::no-loc(this):::) {
// do not execute in cases of self-reference
```

> [!NOTE]
> ポインターは不変であるため、 **`:::no-loc(this):::`** ポインターへの割り当て **`:::no-loc(this):::`** は許可されません。 C++ の以前の実装では、への割り当てが許可されていま **`:::no-loc(this):::`** した。

場合によっては、 **`:::no-loc(this):::`** ポインターが直接使用されることが :::no-loc(struct)::: あります。たとえば、現在のオブジェクトのアドレスが必要な自己参照データを操作する場合などです。

## <a name="example"></a>例

```cpp
// :::no-loc(this):::_pointer.cpp
// compile with: /EHsc

#include <iostream>
#include <string.h>

using namespace std;

:::no-loc(class)::: Buf
{
public:
    Buf( char* szBuffer, size_t sizeOfBuffer );
    Buf& operator=( :::no-loc(const)::: Buf & );
    void Display() { cout << buffer << endl; }

private:
    char*   buffer;
    size_t  sizeOfBuffer;
};

Buf::Buf( char* szBuffer, size_t sizeOfBuffer )
{
    sizeOfBuffer++; // account for a NULL terminator

    buffer = new char[ sizeOfBuffer ];
    if (buffer)
    {
        strcpy_s( buffer, sizeOfBuffer, szBuffer );
        sizeOfBuffer = sizeOfBuffer;
    }
}

Buf& Buf::operator=( :::no-loc(const)::: Buf &otherbuf )
{
    if( &otherbuf != :::no-loc(this)::: )
    {
        if (buffer)
            delete [] buffer;

        sizeOfBuffer =  strlen( otherbuf.buffer ) + 1;
        buffer = new char[sizeOfBuffer];
        strcpy_s( buffer, sizeOfBuffer, otherbuf.buffer );
    }
    return *:::no-loc(this):::;
}

int main()
{
    Buf myBuf( "my buffer", 10 );
    Buf yourBuf( "your buffer", 12 );

    // Display 'my buffer'
    myBuf.Display();

    // assignment operator
    myBuf = yourBuf;

    // Display 'your buffer'
    myBuf.Display();
}
```

```Output
my buffer
your buffer
```

## <a name="type-of-the-no-locthis-pointer"></a>ポインターの型 :::no-loc(this):::

**`:::no-loc(this):::`** ポインターの型は、関数の宣言で、キーワードとキーワードを使用して変更でき **`:::no-loc(const):::`** **`:::no-loc(volatile):::`** ます。 これらの属性のいずれかを持つ関数を宣言するには、関数の引数リストの後にキーワードを追加します。

例を考えてみましょう。

```cpp
// type_of_:::no-loc(this):::_pointer1.cpp
:::no-loc(class)::: Point
{
    unsigned X() :::no-loc(const):::;
};
int main()
{
}
```

前のコードでは、 `X` **`:::no-loc(this):::`** ポインターがオブジェクトへのポインターとして扱われるメンバー関数を宣言して **`:::no-loc(const):::`** **`:::no-loc(const):::`** います。 Cv-*リスト*オプションの組み合わせを使用できますが、ポインター自体ではなくポインターによって指されるオブジェクトが常に変更され **`:::no-loc(this):::`** ます。 次の宣言で `X` **`:::no-loc(this):::`** は、ポインターがオブジェクトへのポインターである関数を宣言してい **`:::no-loc(const):::`** **`:::no-loc(const):::`** ます。

```cpp
// type_of_:::no-loc(this):::_pointer2.cpp
:::no-loc(class)::: Point
{
    unsigned X() :::no-loc(const):::;
};
int main()
{
}
```

メンバー関数のの型 **`:::no-loc(this):::`** は、次の構文によって記述されます。 *Cv 修飾子リスト*は、メンバー関数の宣言子から決定されます。 **`:::no-loc(const):::`** または **`:::no-loc(volatile):::`** (またはその両方) を指定できます。 * :::no-loc(class)::: -type*はの名前です :::no-loc(class)::: 。

[*cv-修飾子リスト*]* :::no-loc(class)::: -型* ** \* :::no-loc(const)::: :::no-loc(this)::: **

つまり、 **`:::no-loc(this):::`** ポインターは常に :::no-loc(const)::: ポインターです。 再割り当てできません。  **`:::no-loc(const):::`** **`:::no-loc(volatile):::`** メンバー関数の宣言で使用されるまたは修飾子は、 :::no-loc(class)::: **`:::no-loc(this):::`** その関数のスコープ内でポインターが指すインスタンスに適用されます。

次の表は、これらの修飾子の機能について詳細を示します。

### <a name="semantics-of-no-locthis-modifiers"></a>修飾子のセマンティクス :::no-loc(this):::

|修飾子|意味|
|--------------|-------------|
|**`:::no-loc(const):::`**|メンバーデータを変更できません。ではないメンバー関数を呼び出すことはできません **`:::no-loc(const):::`** 。|
|**`:::no-loc(volatile):::`**|メンバーデータは、アクセスされるたびにメモリから読み込まれます。特定の最適化を無効にします。|

**`:::no-loc(const):::`** ではないメンバー関数にオブジェクトを渡すと、エラーになり **`:::no-loc(const):::`** ます。

同様に、では **`:::no-loc(volatile):::`** ないメンバー関数にオブジェクトを渡すこともエラーになり **`:::no-loc(volatile):::`** ます。

として宣言されたメンバー関数は、 **`:::no-loc(const):::`** メンバーデータを変更できません。このような関数で **`:::no-loc(this):::`** は、ポインターはオブジェクトへのポインターです **`:::no-loc(const):::`** 。

> [!NOTE]
> Con :::no-loc(struct)::: と de を or :::no-loc(struct)::: として宣言することはできません **`:::no-loc(const):::`** **`:::no-loc(volatile):::`** 。 ただし、これらはまたはオブジェクトで呼び出すことができ **`:::no-loc(const):::`** **`:::no-loc(volatile):::`** ます。

## <a name="see-also"></a>関連項目

[キーワード](../cpp/keywords-cpp.md)
