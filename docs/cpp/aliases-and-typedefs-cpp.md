---
description: エイリアスと typedef (C++) についての詳細情報
title: エイリアスと typedef (C++)
ms.date: 11/04/2016
f1_keywords:
- typedef_cpp
ms.assetid: af1c24d2-4bfd-408a-acfc-482e264232f5
ms.openlocfilehash: 7b5924fd30fe1d22e6a82fb82e2d252409d782ef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97239858"
---
# <a name="aliases-and-typedefs-c"></a>エイリアスと typedef (C++)

*エイリアス宣言* を使用して、以前に宣言された型のシノニムとして使用する名前を宣言できます。 (このメカニズムは、 *型のエイリアス* とも呼ばれます)。 また、このメカニズムを使用して *エイリアステンプレート* を作成することもできます。これは、カスタムアロケーターに特に便利です。

## <a name="syntax"></a>構文

```
using identifier = type;
```

## <a name="remarks"></a>解説

*identifier*<br/>
エイリアスの名前。

*type*<br/>
エイリアスを作成する型識別子。

エイリアスでは新しい型は定義されず、既存の型名の意味を変更することはできません。

エイリアスの最も単純な形式は、C++ 03 のメカニズムに相当し **`typedef`** ます。

```cpp
// C++11
using counter = long;

// C++03 equivalent:
// typedef long counter;
```

いずれの形式でも "カウンター" 型の変数を作成できます。 次のような `std::ios_base::fmtflags` の型エイリアスが便利な場合があります。

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

エイリアスは関数ポインターでも使用できますが、同等の typedef よりもはるかに読みやすくなります。

```cpp
// C++11
using func = void(*)(int);

// C++03 equivalent:
// typedef void (*func)(int);

// func can be assigned to a function pointer value
void actual_function(int arg) { /* some code */ }
func fptr = &actual_function;
```

このメカニズムの制限は、 **`typedef`** テンプレートでは機能しないということです。 しかし、C++11 での型エイリアスの構文ではエイリアス テンプレートを作成できます。

```cpp
template<typename T> using ptr = T*;

// the name 'ptr<T>' is now an alias for pointer to T
ptr<int> ptr_int;
```

## <a name="example"></a>例

次の例に、エイリアス テンプレートをカスタム アロケーター (この場合は整数ベクター型) で使用する方法を示します。 の任意の型をに置き換えて、 **`int`** 便利なエイリアスを作成し、メインの機能コード内の複雑なパラメーターリストを非表示にすることができます。 コード全体でカスタム アロケーターを使用することで読みやすくして、入力ミスによるバグが発生するリスクを減らすことができます。

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

## <a name="typedefs"></a>Typedefs

宣言では **`typedef`** 、そのスコープ内で、宣言の *型宣言* の部分で指定された型のシノニムになる名前が導入されます。

typedef 宣言を使用して、既に言語で定義されている型や、宣言した型に対して、より短い、またはわかりやすい名前を作成できます。 Typedef 名を使用して、変更可能な実装の詳細をカプセル化できます。

**`class`**、、 **`struct`** **`union`** 、およびの宣言とは異なり **`enum`** 、 **`typedef`** 宣言は新しい型を導入しません。既存の型に新しい名前が導入されます。

を使用して宣言さ **`typedef`** れた名前は、他の識別子と同じ名前空間を使用します (ステートメントラベルを除く)。 したがって、クラス型の宣言以外では、以前に宣言された名前と同じ識別子を使用できません。 次の例を確認してください。

```cpp
// typedef_names1.cpp
// C2377 expected
typedef unsigned long UL;   // Declare a typedef name, UL.
int UL;                     // C2377: redefined.
```

他の識別子に関連する名前を隠す規則は、を使用して宣言された名前の可視性も制御し **`typedef`** ます。 したがって、次の例は C++ で有効です。

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

Typedef と同じ名前でローカル スコープの識別子を宣言するとき、あるいは同じスコープまたは内部スコープで構造体または共用体のメンバーを宣言するときは、型指定子を指定する必要があります。 次に例を示します。

```cpp
typedef char FlagType;
const FlagType x;
```

識別子、構造体メンバー、または共用体メンバーに対して `FlagType` 名を再利用するには、次のように型を指定する必要があります。

```cpp
const int FlagType;  // Type specifier required
```

次のような記述だけでは不十分です。

```cpp
const FlagType;      // Incomplete specification
```

`FlagType` は再宣言された識別子ではなく、型の一部であると見なされるためです。 この宣言は、次のような正しくない宣言であると見なされます。

```cpp
int;  // Illegal declaration
```

ポインター、関数、配列型を含め、あらゆる型を typedef で宣言できます。 構造体型または共用体型を定義する前に、構造体型または共用体型へのポインターの typedef 名を宣言できます。ただし、定義が宣言と同じ可視性である必要があります。

### <a name="examples"></a>例

宣言の用途の1つ **`typedef`** は、宣言をより均一でコンパクトにすることです。 次に例を示します。

```cpp
typedef char CHAR;          // Character type.
typedef CHAR * PSTR;        // Pointer to a string (char *).
PSTR strchr( PSTR source, CHAR target );
typedef unsigned long ulong;
ulong ul;     // Equivalent to "unsigned long ul;"
```

を使用して **`typedef`** 同じ宣言で基本型と派生型を指定するには、宣言子をコンマで区切ります。 次に例を示します。

```cpp
typedef char CHAR, *PSTR;
```

次の例は、値を返さず、2 つの int 引数を受け取る関数に対する型 `DRAWF` を用意します。

```cpp
typedef void DRAWF( int, int );
```

上記のステートメントの後 **`typedef`** 、宣言

```cpp
DRAWF box;
```

は次の宣言と同等です。

```cpp
void box( int, int );
```

**`typedef`** は、 **`struct`** ユーザー定義型を宣言して名前を指定するために、と組み合わせて使用されることがよくあります。

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

宣言は、同じ **`typedef`** 型を参照するために同じ名前を再宣言するために使用できます。 次に例を示します。

```cpp
// FILE1.H
typedef char CHAR;

// FILE2.H
typedef char CHAR;

// PROG.CPP
#include "file1.h"
#include "file2.h"   // OK
```

プログラム *PROG。CPP* には、2つのヘッダーファイルが含まれています。どちらにも名前の宣言が含まれてい **`typedef`** `CHAR` ます。 両方の宣言が同じ型を参照する限り、このような再宣言は許容されます。

は、 **`typedef`** 以前に別の型として宣言された名前を再定義することはできません。 したがって、FILE2 の場合は *です。H* contains

```cpp
// FILE2.H
typedef int CHAR;     // Error
```

コンパイラは、名前 `CHAR` を再宣言して異なる型を参照しようとするため、エラーが発生します。 このことは、次のような構造もに及びます。

```cpp
typedef char CHAR;
typedef CHAR CHAR;      // OK: redeclared as same type

typedef union REGS      // OK: name REGS redeclared
{                       //  by typedef name with the
    struct wordregs x;  //  same meaning.
    struct byteregs h;
} REGS;
```

### <a name="typedefs-in-c-vs-c"></a>C++ と C の typedef

**`typedef`** クラス型での指定子の使用は、宣言で名前のない構造体を宣言する ANSI C の手法によって主にサポートされてい **`typedef`** ます。 たとえば、多くの C プログラマは次のように記述します。

```cpp
// typedef_with_class_types1.cpp
// compile with: /c
typedef struct {   // Declare an unnamed structure and give it the
                   // typedef name POINT.
   unsigned x;
   unsigned y;
} POINT;
```

このような宣言の利点は、次のような宣言を使用できることです。

```cpp
POINT ptOrigin;
```

次のように記述する必要がありません。

```cpp
struct point_t ptOrigin;
```

C++ では、 **`typedef`** 名前と実際の型 (、、、およびの各キーワードで宣言) の違い **`class`** **`struct`** **`union`** **`enum`** がより明確になります。 ステートメントで無名の構造体を宣言する C の手法は **`typedef`** 引き続き機能しますが、c の場合と同様に数値表記の利点はありません。

```cpp
// typedef_with_class_types2.cpp
// compile with: /c /W1
typedef struct {
   int POINT();
   unsigned x;
   unsigned y;
} POINT;
```

前の例では、名前のない `POINT` クラス構文を使用して、という名前のクラスを宣言して **`typedef`** います。 `POINT` はクラス名として扱われますが、この方法で導入された名前には次の制限が適用されます。

- 名前 (シノニム) は **`class`** 、、 **`struct`** 、またはプレフィックスの後には記述できません **`union`** 。

- 名前は、クラス宣言内のコンストラクター名またはデストラクター名として使用できません。

つまり、この構文には、継承、構築、または破棄のための機能はありません。
