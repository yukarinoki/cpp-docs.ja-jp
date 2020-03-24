---
title: const (C++)
ms.date: 11/04/2016
f1_keywords:
- const_cpp
helpviewer_keywords:
- const keyword [C++]
ms.assetid: b21c0271-1ad0-40a0-b21c-5e812bba0318
ms.openlocfilehash: cc1f117cc5f26edf9cd85461281b925c97fa5225
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180305"
---
# <a name="const-c"></a>const (C++)

データ宣言を変更する場合、 **const**キーワードは、オブジェクトまたは変数が変更可能でないことを指定します。

## <a name="syntax"></a>構文

```
const declaration ;
member-function const ;
```

## <a name="const-values"></a>const の値

**Const**キーワードは、変数の値が定数であることを指定し、プログラマが変更できないようにコンパイラに指示します。

```cpp
// constant_values1.cpp
int main() {
   const int i = 5;
   i = 10;   // C3892
   i++;   // C2105
}
```

でC++は、 [#define](../preprocessor/hash-define-directive-c-cpp.md)プリプロセッサディレクティブの代わりに**const**キーワードを使用して定数値を定義できます。 **Const**で定義された値は、型チェックの対象となり、定数式の代わりに使用できます。 でC++は、次のように**const**変数を使用して配列のサイズを指定できます。

```cpp
// constant_values2.cpp
// compile with: /c
const int maxarray = 255;
char store_char[maxarray];  // allowed in C++; not allowed in C
```

C では、定数値は既定で外部リンケージに設定されるため、ソース ファイルでのみ指定できます。 C++ では、定数値は既定で内部リンケージに設定されるため、ヘッダー ファイルで指定できます。

**Const**キーワードは、ポインター宣言でも使用できます。

```cpp
// constant_values3.cpp
int main() {
   char *mybuf = 0, *yourbuf;
   char *const aptr = mybuf;
   *aptr = 'a';   // OK
   aptr = yourbuf;   // C3892
}
```

**Const**として宣言された変数へのポインターは、 **const**としても宣言されているポインターにのみ割り当てることができます。

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

**Const**として宣言されているオブジェクトの場合、定数メンバー関数のみを呼び出すことができます。 これによって、定数オブジェクトは変更されなくなります。

```cpp
birthday.getMonth();    // Okay
birthday.setMonth( 4 ); // Error
```

非定数オブジェクトに対して、定数または非定数のメンバー関数を呼び出すことができます。 また、 **const**キーワードを使用してメンバー関数をオーバーロードすることもできます。これにより、定数オブジェクトと非定数オブジェクトに対して異なるバージョンの関数を呼び出すことができます。

**Const**キーワードを使用してコンストラクターまたはデストラクターを宣言することはできません。

## <a name="const-member-functions"></a>const のメンバー関数

**Const**キーワードを使用してメンバー関数を宣言すると、関数が呼び出されるオブジェクトを変更しない "読み取り専用" 関数であることを指定します。 定数メンバー関数は、静的でないデータメンバーを変更したり、定数でないメンバー関数を呼び出したりすることはできません。定数メンバー関数を宣言するには、引数リストの閉じかっこの後に**const**キーワードを配置します。 宣言と定義の両方で**const**キーワードが必要です。

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

## <a name="c-and-c-const-differences"></a>C とC++ const の相違点

C ソースコードファイルで変数を**const**として宣言する場合は、次のようにします。

```cpp
const int i = 2;
```

そして、次のように、この変数を別のモジュールで使用できます。

```cpp
extern const int i;
```

ただし、で同じ動作を実現C++するには、 **const**変数を次のように宣言する必要があります。

```cpp
extern const int i = 2;
```

C ソースコードファイルで使用**extern**するために、 C++ソースコードファイルで extern 変数を宣言する場合は、次のように使用します。

```cpp
extern "C" const int x=10;
```

C++ コンパイラによる名前修飾を防止します。

## <a name="remarks"></a>解説

メンバー関数のパラメーターリストの後に続く場合、 **const**キーワードは、関数が呼び出されるオブジェクトを変更しないことを指定します。

**Const**の詳細については、次のトピックを参照してください。

- [const ポインターと volatile ポインター](../cpp/const-and-volatile-pointers.md)

- [型修飾子 (C 言語リファレンス)](../c-language/type-qualifiers.md)

- [volatile](../cpp/volatile-cpp.md)

- [#define](../preprocessor/hash-define-directive-c-cpp.md)

## <a name="see-also"></a>参照

[キーワード](../cpp/keywords-cpp.md)
