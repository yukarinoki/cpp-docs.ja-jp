---
description: '詳細情報: new 演算子 (C++)'
title: new 演算子 (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- new keyword [C++]
ms.assetid: 69fee812-1c28-4882-8fda-d1ad17860004
ms.openlocfilehash: 5bfc6fdc59348defc87d26dae1056ae80dab3ec5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97268627"
---
# <a name="new-operator-c"></a>new 演算子 (C++)

フリーストアから *型名* のオブジェクトまたはオブジェクトの配列にメモリを割り当て、オブジェクトへの適切に型指定された0以外のポインターを返します。

> [!NOTE]
> Microsoft C++ コンポーネント拡張では、 **`new`** vtable スロットエントリを追加するためのキーワードがサポートされています。 詳細については、「 [new (vtable の新しいスロット)](../extensions/new-new-slot-in-vtable-cpp-component-extensions.md) 」を参照してください。

## <a name="syntax"></a>構文

```
[::] new [placement] new-type-name [new-initializer]
[::] new [placement] ( type-name ) [new-initializer]
```

## <a name="remarks"></a>解説

失敗した場合は、0を返すか、例外をスローします。詳細については、 **`new`** 「 [new および delete 演算子](../cpp/new-and-delete-operators.md) 」を参照してください。 この既定の動作を変更するには、カスタム例外処理ルーチンを記述し、引数として関数名を指定して [_set_new_handler](../c-runtime-library/reference/set-new-handler.md) ランタイムライブラリ関数を呼び出します。

マネージヒープにオブジェクトを作成する方法の詳細については、「 [gcnew](../extensions/ref-new-gcnew-cpp-component-extensions.md)」を参照してください。

**`new`** を使用して C++ クラスオブジェクトにメモリを割り当てると、メモリが割り当てられた後にオブジェクトのコンストラクターが呼び出されます。

演算子で割り当てられたメモリの割り当てを解除するには、 [delete](../cpp/delete-operator-cpp.md) 演算子を使用し **`new`** ます。

次の例では、サイズ `dim` × 10 の文字の 2 次元配列を割り当てた後、解放します。 多次元配列を割り当てるときに、最初の次元を除くすべての次元は、正の値に評価される定数式であることが必要です。配列の一番左の次元は、正の値に評価される任意の値でかまいません。 演算子を使用して配列を割り当てる場合 **`new`** 、最初の次元はゼロになり **`new`** ます。つまり、演算子は一意のポインターを返します。

```cpp
char (*pchar)[10] = new char[dim][10];
delete [] pchar;
```

*型名* には **`const`** 、、 **`volatile`** 、クラス宣言、または列挙宣言を含めることはできません。 したがって、次の式は無効です。

```cpp
volatile char *vch = new volatile char[20];
```

演算子は、 **`new`** オブジェクトではないため、参照型を割り当てません。

演算子は、 **`new`** 関数の割り当てには使用できませんが、関数へのポインターの割り当てに使用できます。 次の例では、整数を返す関数への 7 個のポインターの配列を割り当てた後、解放します。

```cpp
int (**p) () = new (int (*[7]) ());
delete *p;
```

**`new`** 引数を追加せずに演算子を使用し、 [/Gx](../build/reference/gx-enable-exception-handling.md)、 [/Eha](../build/reference/eh-exception-handling-model.md)、または [/ehs](../build/reference/eh-exception-handling-model.md)オプションを指定してコンパイルすると、コンパイラは、 **`delete`** コンストラクターが例外をスローした場合に operator を呼び出すためのコードを生成します。

次の一覧では、の文法要素について説明し **`new`** ます。

*場所*<br/>
をオーバーロードする場合に、追加の引数を渡す方法を提供 **`new`** します。

*型名*<br/>
割り当てる型を指定します。組み込みまたはユーザー定義の型を指定できます。 型の指定が複雑な場合には、かっこで囲むことでバインディング順を強制的に適用できます。

*initializer*<br/>
初期化されたオブジェクトの値を指定します。 初期化子は配列には指定できません。 演算子は、 **`new`** クラスに既定のコンストラクターがある場合にのみ、オブジェクトの配列を作成します。

## <a name="example-allocate-and-free-a-character-array"></a>例: 文字配列の割り当てと解放

次のコード例では、文字配列と `CName` クラスのオブジェクトを割り当てた後、解放します。

```cpp
// expre_new_Operator.cpp
// compile with: /EHsc
#include <string.h>

class CName {
public:
   enum {
      sizeOfBuffer = 256
   };

   char m_szFirst[sizeOfBuffer];
   char m_szLast[sizeOfBuffer];

public:
   void SetName(char* pszFirst, char* pszLast) {
     strcpy_s(m_szFirst, sizeOfBuffer, pszFirst);
     strcpy_s(m_szLast, sizeOfBuffer, pszLast);
   }

};

int main() {
   // Allocate memory for the array
   char* pCharArray = new char[CName::sizeOfBuffer];
   strcpy_s(pCharArray, CName::sizeOfBuffer, "Array of characters");

   // Deallocate memory for the array
   delete [] pCharArray;
   pCharArray = NULL;

   // Allocate memory for the object
   CName* pName = new CName;
   pName->SetName("Firstname", "Lastname");

   // Deallocate memory for the object
   delete pName;
   pName = NULL;
}
```

## <a name="example-new-operator"></a>例: `new` 演算子

割り当てのサイズに加えて引数を指定した形式の新しい演算子の配置を使用する場合 **`new`** 、 **`delete`** コンストラクターが例外をスローした場合、コンパイラは演算子の配置形式をサポートしません。 次に例を示します。

```cpp
// expre_new_Operator2.cpp
// C2660 expected
class A {
public:
   A(int) { throw "Fail!"; }
};
void F(void) {
   try {
      // heap memory pointed to by pa1 will be deallocated
      // by calling ::operator delete(void*).
      A* pa1 = new A(10);
   } catch (...) {
   }
   try {
      // This will call ::operator new(size_t, char*, int).
      // When A::A(int) does a throw, we should call
      // ::operator delete(void*, char*, int) to deallocate
      // the memory pointed to by pa2.  Since
      // ::operator delete(void*, char*, int) has not been implemented,
      // memory will be leaked when the deallocation cannot occur.

      A* pa2 = new(__FILE__, __LINE__) A(20);
   } catch (...) {
   }
}

int main() {
   A a;
}
```

## <a name="initializing-object-allocated-with-new"></a>new で割り当てたオブジェクトの初期化

オプションの *初期化子* フィールドは、演算子の文法に含まれてい **`new`** ます。 これにより、新しいオブジェクトをユーザー定義コンストラクターで初期化できます。 初期化の方法の詳細については、「 [初期化子](../cpp/initializers.md)」を参照してください。 次の例は、演算子で初期化式を使用する方法を示してい **`new`** ます。

```cpp
// expre_Initializing_Objects_Allocated_with_new.cpp
class Acct
{
public:
    // Define default constructor and a constructor that accepts
    //  an initial balance.
    Acct() { balance = 0.0; }
    Acct( double init_balance ) { balance = init_balance; }
private:
    double balance;
};

int main()
{
    Acct *CheckingAcct = new Acct;
    Acct *SavingsAcct = new Acct ( 34.98 );
    double *HowMuch = new double ( 43.0 );
    // ...
}
```

この例では、オブジェクト `CheckingAcct` は演算子を使用して割り当てられてい **`new`** ますが、既定の初期化は指定されていません。 したがって、`Acct()` クラスの既定のコンストラクターが呼び出されます。 その後、オブジェクト `SavingsAcct` は、同じように割り当てられます。ただし、明示的に 34.98 に初期化されます。 34.98 は型であるため **`double`** 、その型の引数を受け取るコンストラクターは、初期化を処理するために呼び出されます。 最後に、`HowMuch` 非クラス型は 43.0 に初期化されます。

オブジェクトがクラス型であり、そのクラスにコンストラクターがある場合 (前の例のように)、 **`new`** 次の条件のいずれかが満たされている場合にのみ、オブジェクトを演算子によって初期化できます。

- 初期化子内に指定された引数は、コンストラクターの引数と一致します。

- クラスには、既定のコンストラクター (引数を指定せずに呼び出すことができるコンストラクター) があります。

演算子を使用して配列を割り当てるときは、明示的に要素ごとに初期化を行うことはできません。 **`new`** 既定のコンストラクター (存在する場合) のみが呼び出されます。 詳細については、「 [既定の引数](../cpp/default-arguments.md) 」を参照してください。

メモリ割り当てが失敗した場合 (**operator new** は値0を返します)、初期化は実行されません。 これによって、存在しないデータを初期化しようとすることを防止できます。

関数呼び出しの場合と同様に、初期化された式が評価される順序は定義されていません。 さらに、メモリの割り当てが実行される前に、これらの式が完全に評価されるものとして信頼しないでください。 メモリ割り当てが失敗し、 **`new`** 演算子がゼロを返した場合、初期化子の一部の式が完全に評価されないことがあります。

## <a name="lifetime-of-objects-allocated-with-new"></a>new で割り当てたオブジェクトの有効期間

演算子で割り当てられたオブジェクトは **`new`** 、定義されているスコープが終了したときに破棄されません。 演算子は、 **`new`** 割り当てられたオブジェクトへのポインターを返すので、プログラムは、これらのオブジェクトにアクセスするための適切なスコープのポインターを定義する必要があります。 次に例を示します。

```cpp
// expre_Lifetime_of_Objects_Allocated_with_new.cpp
// C2541 expected
int main()
{
    // Use new operator to allocate an array of 20 characters.
    char *AnArray = new char[20];

    for( int i = 0; i < 20; ++i )
    {
        // On the first iteration of the loop, allocate
        //  another array of 20 characters.
        if( i == 0 )
        {
            char *AnotherArray = new char[20];
        }
    }

    delete [] AnotherArray; // Error: pointer out of scope.
    delete [] AnArray;      // OK: pointer still in scope.
}
```

この例では、ポインター `AnotherArray` がスコープ外になると、オブジェクトを削除できなくなります。

## <a name="how-new-works"></a>new の機能

*割り当て式*(演算子を含む式) で **`new`** は、次の3つの処理が行われます。

- 割り当てられるオブジェクトのストレージを探し、予約します。 この段階が完了すると、適切なサイズのストレージが割り当てられます。ただし、まだオブジェクトではありません。

- オブジェクトを初期化します。 初期化が完了すると、割り当てられたストレージをオブジェクトにするための十分な情報が得られます。

- *新しい型名* または *型名* から派生したポインター型のオブジェクトへのポインターを返します。 プログラムでは、このポインターを使用して新しく割り当てられたオブジェクトにアクセスします。

**`new`** 演算子は、function **演算子 new** を呼び出します。 任意の型の配列、型、型、または型ではないオブジェクトの場合、 **`class`** **`struct`** **`union`** グローバル関数 **:: operator new** が呼び出されてストレージが割り当てられます。 クラス型のオブジェクトは、クラスごとに独自の **operator new** static メンバー関数を定義できます。

コンパイラは、型 type **`new`** のオブジェクトを割り当てる演算子を検出すると、 `type` **:: operator new (sizeof (** )) の呼び出しを発行します。 `type` または、ユーザー定義の **operator new** が定義されていない場合は **:: operator new (sizeof (** `type` **))** を呼び出します。 このため、 **`new`** 演算子はオブジェクトに対して適切な量のメモリを割り当てることができます。

> [!NOTE]
> **Operator new** の引数は型 `size_t` です。 この型は、、、、、、、、、およびで定義されてい \<direct.h> \<malloc.h> \<memory.h> \<search.h> \<stddef.h> \<stdio.h> \<stdlib.h> \<string.h> \<time.h> ます。

文法のオプションでは、 *配置* を指定できます (「 [New 演算子](../cpp/new-operator-cpp.md)の文法」を参照してください)。 *Placement* パラメーターは、 **operator new** のユーザー定義の実装に対してのみ使用できます。これにより、追加の情報を **operator new** に渡すことができます。 などの *配置* フィールドを持つ式 `T *TObject = new ( 0x0040 ) T;` は、 `T *TObject = T::operator new( sizeof( T ), 0x0040 );` クラス T にメンバー演算子 new がある場合はに変換され、それ以外の場合はに変換され `T *TObject = ::operator new( sizeof( T ), 0x0040 );` ます。

*配置* フィールドの本来の目的は、ハードウェアに依存するオブジェクトをユーザーが指定したアドレスに割り当てることができるようにすることでした。

> [!NOTE]
> 前の例では *配置* フィールドに1つの引数のみを示していますが、この方法では **演算子** に渡すことができる余分な引数の数に制限はありません。

クラス型に対して **operator new** が定義されている場合でも、次の例の形式を使用してグローバル演算子を使用できます。

```cpp
T *TObject =::new TObject;
```

スコープ解決演算子 () は、 `::` グローバル演算子の使用を強制し **`new`** ます。

## <a name="see-also"></a>関連項目

[単項演算子を含む式](../cpp/expressions-with-unary-operators.md)<br/>
[キーワード](../cpp/keywords-cpp.md)<br/>
[new および delete 演算子](../cpp/new-and-delete-operators.md)
