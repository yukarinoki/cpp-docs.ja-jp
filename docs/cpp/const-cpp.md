---
title: const (C++)
ms.date: 11/04/2016
f1_keywords:
- const_cpp
helpviewer_keywords:
- const keyword [C++]
ms.assetid: b21c0271-1ad0-40a0-b21c-5e812bba0318
ms.openlocfilehash: db79e228f1fabc4b2da0a7778126a1b576a67768
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229039"
---
# <a name="const-c"></a>const (C++)

データ宣言を変更する場合、 **`const`** キーワードは、オブジェクトまたは変数が変更可能でないことを指定します。

## <a name="syntax"></a>構文

```
const declaration ;
member-function const ;
```

## <a name="const-values"></a>const の値

キーワードは、 **`const`** 変数の値が定数であることを指定し、プログラマがそれを変更できないようにコンパイラに指示します。

```cpp
// constant_values1.cpp
int main() {
   const int i = 5;
   i = 10;   // C3892
   i++;   // C2105
}
```

C++ では、 **`const`** [#define](../preprocessor/hash-define-directive-c-cpp.md)プリプロセッサディレクティブの代わりにキーワードを使用して定数値を定義できます。 で定義された値 **`const`** は、型チェックの対象となり、定数式の代わりに使用できます。 C++ では、次のように変数を使用して配列のサイズを指定でき **`const`** ます。

```cpp
// constant_values2.cpp
// compile with: /c
const int maxarray = 255;
char store_char[maxarray];  // allowed in C++; not allowed in C
```

C では、定数値は既定で外部リンケージに設定されるため、ソース ファイルでのみ指定できます。 C++ では、定数値は既定で内部リンケージに設定されるため、ヘッダー ファイルで指定できます。

キーワードは、 **`const`** ポインター宣言でも使用できます。

```cpp
// constant_values3.cpp
int main() {
   char *mybuf = 0, *yourbuf;
   char *const aptr = mybuf;
   *aptr = 'a';   // OK
   aptr = yourbuf;   // C3892
}
```

として宣言された変数へのポインターは、 **`const`** としても宣言されているポインターにのみ割り当てることができ **`const`** ます。

```cpp
// constant_values4.cpp
#include <stdio.h>
int main() {
   const char *mybuf = "test";
   char *yourbuf = "test2";
   printf_s("%s\n", mybuf);

   const char *bptr = mybuf;   // Pointer to constant data
   printf_s("%s\n", bptr);

   // *bptr = 'a';   // Error
}
```

定数データへのポインターを関数パラメーターとして使用して、ポインターを通じて渡されるパラメーターが関数によって変更されないようにすることができます。

として宣言されているオブジェクトの場合 **`const`** 、定数メンバー関数のみを呼び出すことができます。 これによって、定数オブジェクトは変更されなくなります。

```cpp
birthday.getMonth();    // Okay
birthday.setMonth( 4 ); // Error
```

非定数オブジェクトに対して、定数または非定数のメンバー関数を呼び出すことができます。 キーワードを使用してメンバー関数をオーバーロードすることもできます **`const`** 。これにより、定数および非定数オブジェクトに対して異なるバージョンの関数を呼び出すことができます。

キーワードを使用してコンストラクターまたはデストラクターを宣言することはできません **`const`** 。

## <a name="const-member-functions"></a>const のメンバー関数

キーワードを使用してメンバー関数を宣言すると **`const`** 、その関数が呼び出されるオブジェクトを変更しない "読み取り専用" 関数であることを指定します。 定数メンバー関数は、静的でないデータメンバーを変更したり、定数でないメンバー関数を呼び出したりすることはできません。定数メンバー関数を宣言するには、 **`const`** 引数リストの閉じかっこの後にキーワードを配置します。 **`const`** 宣言と定義の両方でキーワードが必要です。

```cpp
// constant_member_function.cpp
class Date
{
public:
   Date( int mn, int dy, int yr );
   int getMonth() const;     // A read-only function
   void setMonth( int mn );   // A write function; can't be const
private:
   int month;
};

int Date::getMonth() const
{
   return month;        // Doesn't modify anything
}
void Date::setMonth( int mn )
{
   month = mn;          // Modifies data member
}
int main()
{
   Date MyDate( 7, 4, 1998 );
   const Date BirthDate( 1, 18, 1953 );
   MyDate.setMonth( 4 );    // Okay
   BirthDate.getMonth();    // Okay
   BirthDate.setMonth( 4 ); // C2662 Error
}
```

## <a name="c-and-c-const-differences"></a>C と C++ の const の相違点

C ソースコードファイルで変数をとして宣言する場合は **`const`** 、次のようにします。

```cpp
const int i = 2;
```

そして、次のように、この変数を別のモジュールで使用できます。

```cpp
extern const int i;
```

ただし、C++ でも同じ動作を得るには、変数を次のように宣言する必要があり **`const`** ます。

```cpp
extern const int i = 2;
```

**`extern`** C ソースコードファイルで使用するために C++ ソースコードファイルで変数を宣言する場合は、次のようにします。

```cpp
extern "C" const int x=10;
```

C++ コンパイラによる名前修飾を防止します。

## <a name="remarks"></a>解説

メンバー関数のパラメーターリストの後に続く場合、キーワードは、 **`const`** 関数が呼び出されるオブジェクトを変更しないことを指定します。

の詳細につい **`const`** ては、次のトピックを参照してください。

- [const ポインターと volatile ポインター](../cpp/const-and-volatile-pointers.md)

- [型修飾子 (C 言語リファレンス)](../c-language/type-qualifiers.md)

- [volatile](../cpp/volatile-cpp.md)

- [#define](../preprocessor/hash-define-directive-c-cpp.md)

## <a name="see-also"></a>関連項目

[キーワード](../cpp/keywords-cpp.md)
