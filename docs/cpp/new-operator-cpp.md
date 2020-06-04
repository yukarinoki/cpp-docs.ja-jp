---
title: new 演算子 (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- new keyword [C++]
ms.assetid: 69fee812-1c28-4882-8fda-d1ad17860004
ms.openlocfilehash: ac89bf37b8aaaa9d77393b714a233f8a4c998139
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367871"
---
# <a name="new-operator-c"></a>new 演算子 (C++)

フリー ストアから*型名*のオブジェクトまたはオブジェクトの配列にメモリを割り当て、適切に型指定された 0 以外のポインターをオブジェクトに返します。

> [!NOTE]
> Microsoft C++ コンポーネント拡張機能は **、vtable**スロット エントリを追加する新しいキーワードのサポートを提供します。 詳細については、[新規(vtable の新しいスロット)を](../extensions/new-new-slot-in-vtable-cpp-component-extensions.md)参照してください。
>  Microsoft C Component Extensions のサポートを提供する、**new**キーワードによる vtable スロット エントリを追加します。 詳細については、[new (vtable の新しいスロット) ](../extensions/new-new-slot-in-vtable-cpp-component-extensions.md) を参照してください。


## <a name="syntax"></a>構文

```
[::] new [placement] new-type-name [new-initializer]
[::] new [placement] ( type-name ) [new-initializer]
```

## <a name="remarks"></a>解説

失敗した場合 **、new**は 0 を返すか、例外をスローします。詳細については[、新規および削除演算子](../cpp/new-and-delete-operators.md)を参照してください。 この既定の動作は、カスタム例外処理ルーチンを記述し、関数名を引数として[_set_new_handler](../c-runtime-library/reference/set-new-handler.md)ランタイム ライブラリ関数を呼び出すことで変更できます。

マネージ ヒープ上にオブジェクトを作成する方法については、「 [gcnew](../extensions/ref-new-gcnew-cpp-component-extensions.md)」を参照してください。

**new**を使用して C++ クラス オブジェクトのメモリを割り当てる場合、オブジェクトのコンストラクターは、メモリが割り当てられた後に呼び出されます。

[delete](../cpp/delete-operator-cpp.md)演算子を使用して **、new**演算子で割り当てられたメモリの割り当てを解除します。

次の例では、サイズ `dim` × 10 の文字の 2 次元配列を割り当てた後、解放します。 多次元配列を割り当てるときに、最初の次元を除くすべての次元は、正の値に評価される定数式であることが必要です。配列の一番左の次元は、正の値に評価される任意の値でかまいません。 **new**演算子を使用して配列を割り当てる場合、最初の次元はゼロで **、new**演算子は一意のポインタを返します。
次の例では、サイズ `dim` × 10 の文字の 2 次元配列を割り当てた後、解放します。 多次元配列を割り当てるときに、最初の次元を除くすべての次元は、正の値に評価される定数式であることが必要です。配列の一番左の次元は、正の値に評価される任意の値でかまいません。 使用して、配列を割り当てるときに、**new** 演算子は、最初の次元を 0 にすることができます。**new** 演算子は一意のポインターを返します。


```cpp
char (*pchar)[10] = new char[dim][10];
delete [] pchar;
```

*型名*には、**定数**、**揮発性**、クラス宣言、または列挙宣言を含めることはできません。 したがって、次の式は無効です。

```cpp
volatile char *vch = new volatile char[20];
```

**new**演算子は参照型をオブジェクトではないため割り当てません。

**new**演算子を使用して関数を割り当てることはできませんが、関数へのポインターの割り当てには使用できます。 次の例では、整数を返す関数への 7 個のポインターの配列を割り当てた後、解放します。

```cpp
int (**p) () = new (int (*[7]) ());
delete *p;
```

余分な**引数を指定**せずに new 演算子を使用し[、/GX、/EHa、](../build/reference/gx-enable-exception-handling.md)または[/EHs](../build/reference/eh-exception-handling-model.md)オプションを指定してコンパイルすると、コンストラクターが例外をスローした場合に、コンパイラは演算子**削除**を呼び出すコードを生成します。 [/EHa](../build/reference/eh-exception-handling-model.md)

次の一覧は **、new**の文法要素について説明しています。

*配置*<br/>
**new**をオーバーロードする場合に、追加の引数を渡す方法を提供します。

*タイプ名*<br/>
割り当てる型を指定します。組み込みまたはユーザー定義の型を指定できます。 型の指定が複雑な場合には、かっこで囲むことでバインディング順を強制的に適用できます。

*initializer*<br/>
初期化されたオブジェクトの値を指定します。 初期化子は配列には指定できません。 **new**演算子は、クラスに既定のコンストラクターがある場合にのみ、オブジェクトの配列を作成します。

## <a name="example"></a>例

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

## <a name="example"></a>例

**新**しい演算子の配置新しい形式を使用する場合、割り当てのサイズに加えて引数を持つフォームは、コンストラクターが例外をスローする場合、コンパイラは**delete**演算子の配置形式をサポートしません。 次に例を示します。


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

オプションの*初期化子*フィールドは **、new**演算子の文法に含まれています。 これにより、新しいオブジェクトをユーザー定義コンストラクターで初期化できます。 初期化の方法の詳細については、「[初期化子](../cpp/initializers.md)」を参照してください。 次の例は **、new**演算子で初期化式を使用する方法を示しています。

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

この例では、new`CheckingAcct`**演算子を**使用してオブジェクトが割り当てられますが、既定の初期化は指定されていません。 したがって、`Acct()` クラスの既定のコンストラクターが呼び出されます。 その後、オブジェクト `SavingsAcct` は、同じように割り当てられます。ただし、明示的に 34.98 に初期化されます。 34.98 は**double**型であるため、その型の引数を受け取るコンストラクターが呼び出され、初期化が処理されます。 最後に、`HowMuch` 非クラス型は 43.0 に初期化されます。

オブジェクトがクラス型で、そのクラスにコンストラクタがある場合 (前の例のように)、次のいずれかの条件が満たされた場合にのみ、new**演算子によって**オブジェクトを初期化できます。

- 初期化子内に指定された引数は、コンストラクターの引数と一致します。

- クラスには、既定のコンストラクター (引数を指定せずに呼び出すことができるコンストラクター) があります。

**new**演算子を使用して配列を割り当てる場合、要素ごとの明示的な初期化は行われません。既定のコンストラクター (存在する場合) のみが呼び出されます。 詳細については、「[デフォルト引数](../cpp/default-arguments.md)」を参照してください。

メモリの割り当てが失敗した場合 (**演算子 new**は値 0 を返します)、初期化は実行されません。 これによって、存在しないデータを初期化しようとすることを防止できます。

関数呼び出しの場合と同様に、初期化された式が評価される順序は定義されていません。 さらに、メモリの割り当てが実行される前に、これらの式が完全に評価されるものとして信頼しないでください。 メモリ割り当てが失敗し **、new**演算子が 0 を返した場合、初期化子の式の一部が完全に評価されないことがあります。

## <a name="lifetime-of-objects-allocated-with-new"></a>new で割り当てたオブジェクトの有効期間

**new**演算子で割り当てられたオブジェクトは、定義されているスコープが終了しても破棄されません。 **new**演算子は割り当てたオブジェクトへのポインターを返すため、プログラムは、それらのオブジェクトにアクセスするための適切なスコープを持つポインターを定義する必要があります。 次に例を示します。

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

*割り当て式* **(new**演算子を含む式) は、次の 3 つの処理を行います。

- 割り当てられるオブジェクトのストレージを探し、予約します。 この段階が完了すると、適切なサイズのストレージが割り当てられます。ただし、まだオブジェクトではありません。

- オブジェクトを初期化します。 初期化が完了すると、割り当てられたストレージをオブジェクトにするための十分な情報が得られます。

- *new-name*または型名 から派生したポインター型のオブジェクトへのポインター*を*返します。 プログラムでは、このポインターを使用して新しく割り当てられたオブジェクトにアクセスします。

**new**演算子は関数**演算子**new を呼び出します。 任意の型の配列、および**クラス** **、struct**、または**共用**体の型でないオブジェクトの場合は、ストレージを割り当てるグローバル関数 **::operator new**が呼び出されます。 クラス型オブジェクトは、クラスごとに独自の**演算子の新しい**静的メンバー関数を定義できます。

コンパイラは、型**型**のオブジェクトを割り当てる**new**演算子を検出すると **、:演算子 new( sizeof(** `type` **) を**呼び出すか、ユーザー定義**演算子**new が定義されていない場合は**呼**`type`び出し`type`を発行**します**。 したがって **、new**演算子は、オブジェクトに対して適切なメモリ量を割り当てることができます。

コンパイラは、**type** 型のオブジェクトを割り当てるために **new** 演算子を検出すると、`type` **:: new 演算子 (sizeof (** `type`**))**の呼び出しを発行します。または、ユーザー定義 **new 演算子** が定義されていない場合、 **:: new 演算子 (sizeof (** `type` **))** の呼び出しを発行します。そのため、**new** 演算子は、オブジェクトに適切なメモリ量を割り当てることができます。

> [!NOTE]
> **演算子 new**の引数は`size_t`型 です。 この型は\<、direct.h>、malloc.h \<>、memory.h \< \<>、search.h \<>、stddef.h \<>、stdio.h>、stdlib.h>、\<\<\<文字列.h>、および time.h>で定義されます。

文法のオプションでは *、配置*の指定が可能です[(new 演算子](../cpp/new-operator-cpp.md)の文法を参照)。 *配置*パラメータは **、演算子 new**のユーザ定義の実装にのみ使用できます。これにより、追加の情報をオペレータ**new**に渡すことができます。 *配置*フィールドを`T *TObject = new ( 0x0040 ) T;`持つ式は、クラス T`T *TObject = T::operator new( sizeof( T ), 0x0040 );`にメンバー演算子 new が含まれます`T *TObject = ::operator new( sizeof( T ), 0x0040 );`が、それ以外の場合は に変換されます。


*配置*フィールドの本来の意図は、ハードウェア依存のオブジェクトをユーザー指定のアドレスに割り当てることでした。

> [!NOTE]
> 前の例では *、配置*フィールドに 1 つの引数しか示していませんが、この方法で**演算子 new**に渡すことができる余分な引数の数に制限はありません。

クラス型に**対して演算子 new**が定義されている場合でも、グローバル演算子は次の例の形式で使用できます。

**new 演算子**が定義されているクラス型の場合でも、この例のフォームを使用して、グローバル演算子が使用することができます。


```cpp
T *TObject =::new TObject;
```

スコープ解決演算子 (`::`) は、グローバル**新規**オペレーターの使用を強制します。

## <a name="see-also"></a>関連項目

[単項演算子を含む式](../cpp/expressions-with-unary-operators.md)<br/>
[Keywords](../cpp/keywords-cpp.md)<br/>
[新規および削除演算子](../cpp/new-and-delete-operators.md)

