---
title: エイリアス と typedef (C++)
ms.date: 11/04/2016
f1_keywords:
- typedef_cpp
ms.assetid: af1c24d2-4bfd-408a-acfc-482e264232f5
ms.openlocfilehash: 155f1868123514dfec89ab448ef22f2da225c4d3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62155291"
---
# <a name="aliases-and-typedefs-c"></a>エイリアス と typedef (C++)

*エイリアス宣言* を用いて以前に宣言された型の同意語としての名前を宣言することができます。 (このメカニズムは非公式には *型エイリアス* と呼ばれたりします)。このメカニズムを使用して *エイリアステンプレート* を作成する事が出来て、これはカスタムアロケーターの場合には特に有用です。

## <a name="syntax"></a>構文

```
using identifier = type;
```

## <a name="remarks"></a>Remarks

*identifier*<br/>
エイリアスの名前。

*type*<br/>
エイリアスを作成する対象の型識別子。

エイリアスでは新しい型は定義されず、既存の型名の意味を変更することはできません。

エイリアスの最も単純な形式は、C++03 の **typedef** 機能と同等です。

```cpp
// C++11
using counter = long;

// C++03 equivalent:
// typedef long counter;
```

いずれの形式でも "counter" 型の変数を作成できます。 次のような `std::ios_base::fmtflags` の型エイリアスが便利な場合があります。

```cpp
// C++11
using fmtfl = std::ios_base::fmtflags;

// C++03 equivalent:
// typedef std::ios_base::fmtflags fmtfl;

fmtfl fl_orig = std::cout.flags();
fmtfl fl_hex = (fl_orig & ~std::cout.basefield) | std::cout.showbase | std::cout.hex;
// ...
std::cout.flags(fl_hex);
```

エイリアスはまた関数ポインターを取り扱う事も出来ますが、同等品の typedef よりも可読性がずっと良いものになります。

```cpp
// C++11
using func = void(*)(int);

// C++03 equivalent:
// typedef void (*func)(int);

// func can be assigned to a function pointer value
void actual_function(int arg) { /* some code */ }
func fptr = &actual_function;
```

**typedef** 機能の制限としてテンプレートを扱えない事があります。しかし、C++11 の型エイリアスの構文ではエイリアステンプレートを作成する事ができます。

```cpp
template<typename T> using ptr = T*;

// the name 'ptr<T>' is now an alias for pointer to T
ptr<int> ptr_int;
```

## <a name="example"></a>例

次の例では、カスタムアロケーター (この場合は整数ベクター型) にエイリアステンプレートを使用する方法を示します。 **int** を任意の型に置き換えることができる便利なエイリアスを作成して、main関数のコードから複雑なパラメーターリストを隠蔽する事が出来ます。カスタムアロケーターをあなたのコード全体にわたって使う事で可読性を向上させる事が出来、そして入力ミスによる不具合を引き起こす危険性を減らすことができます。

```cpp
#include <stdlib.h>
#include <new>

template <typename T> struct MyAlloc {
    typedef T value_type;

    MyAlloc() { }
    template <typename U> MyAlloc(const MyAlloc<U>&) { }

    bool operator==(const MyAlloc&) const { return true; }
    bool operator!=(const MyAlloc&) const { return false; }

    T * allocate(const size_t n) const {
        if (n == 0) {
            return nullptr;
        }

        if (n > static_cast<size_t>(-1) / sizeof(T)) {
            throw std::bad_array_new_length();
        }

        void * const pv = malloc(n * sizeof(T));

        if (!pv) {
            throw std::bad_alloc();
        }

        return static_cast<T *>(pv);
    }

    void deallocate(T * const p, size_t) const {
        free(p);
    }
};

#include <vector>
using MyIntVector = std::vector<int, MyAlloc<int>>;

#include <iostream>

int main ()
{
    MyIntVector foov = { 1701, 1764, 1664 };

    for (auto a: foov) std::cout << a << " ";
    std::cout << "\n";

    return 0;
}
```

```Output
1701 1764 1664
```

## <a name="typedefs"></a>typedef

**typedef** 宣言はそのスコープの中に *型宣言* 部によって指定された型の同義語になる名前を導入します。

typedef 宣言を使用する事で、既に言語で定義されている型やあなたが宣言した型に対して、より短いまたはわかりやすい名前を作成できます。typedef 名は変更されるかもしれない実装の詳細のカプセル化を可能にします。

**クラス**、**構造体**、**共用体**、および**列挙対** の宣言と異なり、**typedef** 宣言は新しい型の導入はしません - 既存の型に対する新しい名前を導入します。

**typedef** を使用して宣言された名前はその他の識別子（ステートメントラベルを除く）と同じ名前空間を占有します。したがって、クラス型宣言の中を除いて、以前に宣言された名前と同じ識別子を使用できません。下記の例を見て下さい:

```cpp
// typedef_names1.cpp
// C2377 expected
typedef unsigned long UL;   // Declare a typedef name, UL.
int UL;                     // C2377: redefined.
```

その他の識別子に関連している名前の隠蔽規則は **typedef** を使用して宣言された名前の可視性も管理します。したがって、次の例はC++では適格です。

```cpp
// typedef_names2.cpp
typedef unsigned long UL;   // Declare a typedef name, UL
int main()
{
   unsigned int UL;   // Redeclaration hides typedef name
}

// typedef UL back in scope
```

```cpp
// typedef_specifier1.cpp
typedef char FlagType;

int main()
{
}

void myproc( int )
{
    int FlagType;
}
```

typedef と同じ名前でローカルスコープの識別子を宣言するとき、あるいは同じスコープまたは内部スコープで構造体または共用体のメンバーを宣言するときは、型指定子を指定する必要があります。 例えば:

```cpp
typedef char FlagType;
const FlagType x;
```

名前 `FlagType` を識別子、構造体メンバー、または共用体メンバーに対して再利用するには、その型を指定する必要があります。

```cpp
const int FlagType;  // Type specifier required
```

下記の記述だけでは不十分です。

```cpp
const FlagType;      // Incomplete specification
```

なぜなら `FlagType` は再宣言された識別子ではなく、型の一部であると見なされるためです。この宣言は、次のような正しくない宣言と見なされました。

```cpp
int;  // Illegal declaration
```

ポインター、関数、配列型を含め、あらゆる型を typedef で宣言できます。構造体型または共用体型を定義する前に、構造体型または共用体型へのポインターの typedef 名を宣言できます。ただし、定義が宣言と同じ可視性を持つ必要があります。

### <a name="examples"></a>使用例

**typedef** 宣言の用途の1つは、宣言をより統一されたコンパクトなものにする事です。 例えば:

```cpp
typedef char CHAR;          // Character type.
typedef CHAR * PSTR;        // Pointer to a string (char *).
PSTR strchr( PSTR source, CHAR target );
typedef unsigned long ulong;
ulong ul;     // Equivalent to "unsigned long ul;"
```

**typedef** を使用して同じ宣言内に基本と派生型を指定するには、カンマを使って宣言を分けることができます。 例:

```cpp
typedef char CHAR, *PSTR;
```

次のコード例は、返り値無しで2つのint引数を受け取る関数に対する型 `DRAWF` を提供します。

```cpp
typedef void DRAWF( int, int );
```

上記の **typedef** 文の後の、この宣言

```cpp
DRAWF box;
```

は次の宣言と同等です。

```cpp
void box( int, int );
```

**typedef** はしばしばユーザー定義型の名前を宣言する為に **struct** と組み合わせられます。

```cpp
// typedef_specifier2.cpp
#include <stdio.h>

typedef struct mystructtag
{
    int   i;
    double f;
} mystruct;

int main()
{
    mystruct ms;
    ms.i = 10;
    ms.f = 0.99;
    printf_s("%d   %f\n", ms.i, ms.f);
}
```

```Output
10   0.990000
```

### <a name="re-declaration-of-typedefs"></a>typedef の再宣言

**typedef** 宣言は同じ型を参照する同じ名前を再宣言する事に使う事も出来ます。 例えば:

```cpp
// FILE1.H
typedef char CHAR;

// FILE2.H
typedef char CHAR;

// PROG.CPP
#include "file1.h"
#include "file2.h"   // OK
```

プログラム *PROG.cpp* は 名前 `CHAR` に対する **typedef** 宣言が両方に含まれている2つのヘッダーファイルを include します。両方の宣言が同じ型を参照する限り、このような再宣言は許容されます。

**typedef** は以前と異なる型として名前を再定義する事はできません。そのため、もし *FILE2.H* が以下の記述を含んでいたら

```cpp
// FILE2.H
typedef int CHAR;     // Error
```

名前 `CHAR` を以前と異なる型を参照して再宣言しようしたためコンパイラはエラーを発行します。 このことは、次のような構成の場合にも及びます。

```cpp
typedef char CHAR;
typedef CHAR CHAR;      // OK: redeclared as same type

typedef union REGS      // OK: name REGS redeclared
{                       //  by typedef name with the
    struct wordregs x;  //  same meaning.
    struct byteregs h;
} REGS;
```

### <a name="typedefs-in-c-vs-c"></a>typedef:  C++ 対 C

クラス型と併せた **typedef** 指定子の使用は大きく維持されていますが、それは **typedef** 宣言で無名構造体を宣言するANSI Cの作法の為です。たとえば、多くのCプログラマは次のような記述を使います。

```cpp
// typedef_with_class_types1.cpp
// compile with: /c
typedef struct {   // Declare an unnamed structure and give it the
                   // typedef name POINT.
   unsigned x;
   unsigned y;
} POINT;
```

このような宣言の利点は、次のような宣言を可能にする事にあります。

```cpp
POINT ptOrigin;
```

次のように記述する必要はありません。

```cpp
struct point_t ptOrigin;
```

C++では、**typedef** 名と実際の型（**class**、**struct**、**union**、そして **enum** キーワードを使って宣言された）との差はより明確です。**typedef**文を使って無名構造体を宣言するCの作法は変わらず機能しますが、Cであったような表記上の利点はもたらしません。

```cpp
// typedef_with_class_types2.cpp
// compile with: /c /W1
typedef struct {
   int POINT();
   unsigned x;
   unsigned y;
} POINT;
```

前の例は、名前無しクラスの **typedef** 構文を使用して`POINT` という名前のクラスを宣言しています。`POINT` はクラス名として扱われますが、この方法で導入された名前には次の制限が適用されます。

- 名前（同義名）が **class**、**struct**、また **union** 前置詞の後に登場することはできません。

- 名前は、クラス宣言内のコンストラクター名またはデストラクター名として使用できません。

つまり、この構文には、継承、コンストラクタ、またはデストラクタのための機能はありません。
