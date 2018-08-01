---
title: エイリアスと typedef (C++) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- typedef_cpp
dev_langs:
- C++
ms.assetid: af1c24d2-4bfd-408a-acfc-482e264232f5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5fe9e5c1099f6c30483cdb20c48daf9c35fbed8e
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2018
ms.locfileid: "39404978"
---
# <a name="aliases-and-typedefs-c"></a>エイリアスと typedef (C++)
使用することができます、*エイリアス宣言*以前に宣言された型のシノニムとして使用する名前を宣言します。 (このメカニズムは、別名非公式、*型の別名*)。 このメカニズムを使用して作成する、*エイリアス テンプレート*、カスタム アロケーターに特に便利ですがあることができます。  
  
## <a name="syntax"></a>構文  
  
```  
using identifier = type;  
```  
  
## <a name="remarks"></a>Remarks  
 *identifier*  
 エイリアスの名前。  
  
 *type*  
 エイリアスを作成する型識別子。  
  
 エイリアスでは新しい型は定義されず、既存の型名の意味を変更することはできません。  
  
 エイリアスの最も単純な形式は、 **typedef** c++ 03 のメカニズム。  
  
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
  
 また、エイリアスは、関数ポインターの場合は、操作しますが、同等の typedef よりもずっと読みは。  
  
```cpp  
// C++11  
using func = void(*)(int);  
  
// C++03 equivalent:  
// typedef void (*func)(int);  
  
// func can be assigned to a function pointer value  
void actual_function(int arg) { /* some code */ }  
func fptr = &actual_function;  
  
```  
  
 制限事項、 **typedef**メカニズムは、テンプレートを使用しないことです。 しかし、C++11 での型エイリアスの構文ではエイリアス テンプレートを作成できます。  
  
```cpp  
template<typename T> using ptr = T*;   
  
// the name 'ptr<T>' is now an alias for pointer to T  
ptr<int> ptr_int;  
  
```  
  
## <a name="example"></a>例  
 次の例に、エイリアス テンプレートをカスタム アロケーター (この場合は整数ベクター型) で使用する方法を示します。 任意の型を置き換えることができる**int**主要な機能コードのリストを複合型のパラメーターを非表示にする便利なエイリアスを作成します。 コード全体でカスタム アロケーターを使用することで読みやすくして、入力ミスによるバグが発生するリスクを減らすことができます。  
  
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
 A **typedef**宣言に名前をそのスコープの中で指定した型のシノニムになりますが導入されています、*型宣言*宣言の一部です。  
  
 typedef 宣言を使用して、既に言語で定義されている型や、宣言した型に対して、より短い、またはわかりやすい名前を作成できます。 Typedef 名を使用して、変更可能な実装の詳細をカプセル化できます。  
  
 異なり、**クラス**、**構造体**、**共用体**、および**enum**宣言、 **typedef**宣言は新しい型を導入していません-既存の型の新しい名前を導入します。  
  
 使用して宣言された名前**typedef** (ステートメント ラベル) を除くその他の識別子と同じ名前空間を占有します。 したがって、クラス型の宣言以外では、以前に宣言された名前と同じ識別子を使用できません。 次に例を示します。  
  
```cpp 
// typedef_names1.cpp  
// C2377 expected  
typedef unsigned long UL;   // Declare a typedef name, UL.  
int UL;                     // C2377: redefined.  
```  
  
 その他の識別子に関連する名前隠蔽規則も使用して宣言された名前の可視性を管理**typedef**します。 したがって、次の例は C++ で有効です。  
  
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
  
 Typedef と同じ名前でローカル スコープの識別子を宣言するとき、あるいは同じスコープまたは内部スコープで構造体または共用体のメンバーを宣言するときは、型指定子を指定する必要があります。 例えば:  
  
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
  
### <a name="examples"></a>使用例  
 用途の 1 つ**typedef**宣言より同型でコンパクトな宣言を作成します。 例えば:  
  
```cpp  
typedef char CHAR;          // Character type.  
typedef CHAR * PSTR;        // Pointer to a string (char *).  
PSTR strchr( PSTR source, CHAR target );  
typedef unsigned long ulong;  
ulong ul;     // Equivalent to "unsigned long ul;"  
```  
  
 使用する**typedef**同じ宣言内には、基本と派生型を指定するにはコンマで宣言子を分離することができます。 例えば:  
  
```cpp 
typedef char CHAR, *PSTR;  
```  
  
 次の例は、値を返さず、2 つの int 引数を受け取る関数に対する型 `DRAWF` を用意します。  
  
```cpp 
typedef void DRAWF( int, int );  
```  
  
 上記の後に**typedef**ステートメントでは、宣言  
  
```cpp 
DRAWF box;   
```  
  
 は次の宣言と同等です。  
  
```cpp 
void box( int, int );  
```  
  
 **typedef**多くの場合、組み合わせる**構造体**を宣言し、ユーザー定義型の名前します。  
  
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
 **Typedef**宣言を同じ型を参照する同じ名前を再宣言して使用できます。 例えば:  
  
```cpp  
// FILE1.H  
typedef char CHAR;  
  
// FILE2.H  
typedef char CHAR;  
  
// PROG.CPP  
#include "file1.h"  
#include "file2.h"   // OK  
``` 
  
 プログラム*PROG します。CPP*両方が含まれている 2 つのヘッダー ファイルが含まれます**typedef**名の宣言`CHAR`します。 両方の宣言が同じ型を参照する限り、このような再宣言は許容されます。  
  
 A **typedef**は以前に異なる型として宣言する名前を再定義できません。 そのため場合、 *FILE2 します。H*が含まれています  
  
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
  
### <a name="typedefs-in-c-vs-c"></a>typedef:  C++ と C  
 使用、 **typedef**で名前のない構造体を宣言する ANSI C プラクティスのため大きく指定子がクラス型がサポートされている**typedef**宣言します。 たとえば、多くの C プログラマは次のように記述します。  
  
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
  
 C++ では、間の差**typedef**名と実際の型 (で宣言された、**クラス**、**構造体**、**共用体**、および**enum**キーワード) がより明確です。 C の実習で無名の構造体を宣言するを**typedef**ステートメントが機能、その利点はなく表記 C. では、  
  
```cpp  
// typedef_with_class_types2.cpp  
// compile with: /c /W1  
typedef struct {  
   int POINT();  
   unsigned x;  
   unsigned y;  
} POINT;  
```  
  
 前の例は、という名前のクラスを宣言します。`POINT`名前のないクラスを使用して**typedef**構文。 `POINT` はクラス名として扱われますが、この方法で導入された名前には次の制限が適用されます。  
  
-   名前 (シノニム) が後に表示されることはできません、**クラス**、**構造体**、または**共用体**プレフィックス。  
  
-   名前は、クラス宣言内のコンストラクター名またはデストラクター名として使用できません。  
  
 つまり、この構文には、継承、構築、または破棄のための機能はありません。  