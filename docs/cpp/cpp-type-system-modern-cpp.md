---
title: C++ type system
ms.date: 11/19/2019
ms.topic: conceptual
ms.assetid: 553c0ed6-77c4-43e9-87b1-c903eec53e80
ms.openlocfilehash: 1f12f7505438dc995aaf8a045fd903488e9ff092
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246599"
---
# <a name="c-type-system"></a>C++ type system

The concept of *type* is very important in C++. 変数、関数の引数、関数の戻り値をコンパイルするには、それぞれに型が必要です。 さらに、すべての式 (リテラル値を含む) には、評価前にコンパイラーにより暗黙的に型が指定されます。 Some examples of types include **int** to store integral values, **double** to store floating-point values (also known as *scalar* data types), or the Standard Library class [std::basic_string](../standard-library/basic-string-class.md) to store text. You can create your own type by defining a **class** or **struct**. 型は、変数 (または式の結果) に割り当てられるメモリの量、その変数に格納される値の種類、それらの値の解釈方法 (ビット パターンとして)、その型で実行可能な操作を指定します。 ここでは、C++ の型システムの主な機能の概要を示します。

## <a name="terminology"></a>用語

**Variable**: The symbolic name of a quantity of data so that the name can be used to access the data it refers to throughout the scope of the code where it is defined. In C++, *variable* is generally used to refer to instances of scalar data types, whereas instances of other types are usually called *objects*.

**Object**: For simplicity and consistency, this article uses the term *object* to refer to any instance of a class or structure, and when it is used in the general sense includes all types, even scalar variables.

**POD type** (plain old data): This informal category of data types in C++ refers to types that are scalar (see the Fundamental types section) or are *POD classes*. POD クラスには、POD でもない静的データ メンバーはなく、ユーザー定義のコンストラクター、ユーザー定義のデストラクター、ユーザー定義の代入演算子もありません。 また、POD クラスに仮想関数、基底クラス、プライベートまたは保護された非静的データ メンバーもありません。 POD 型は、外部データ交換によく使用されます。たとえば、C 言語で記述されたモジュール (POD 型しかありません) との交換などです。

## <a name="specifying-variable-and-function-types"></a>変数と関数の型の指定

C++ is a *strongly typed* language and it is also *statically-typed*; every object has a type and that type never changes (not to be confused with static data objects).
**When you declare a variable** in your code, you must either specify its type explicitly, or use the **auto** keyword to instruct the compiler to deduce the type from the initializer.
**When you declare a function** in your code, you must specify the type of each argument and its return value, or **void** if no value is returned by the function. 例外は、任意の型の引数を使用できる関数テンプレートを使用する場合です。

最初に変数を宣言すると、後で型を変更することはできません。 ただし、変数の値または関数の戻り値を異なる型の別の変数にコピーすることはできます。 Such operations are called *type conversions*, which are sometimes necessary but are also potential sources of data loss or incorrectness.

POD 型の変数を宣言するときは、初期化する (つまり、初期値を指定する) ことを強くお勧めします。 変数を初期化しないと、以前そのメモリ位置にたまたま存在していたビットで構成される "不要な" 値が含まれたままになります。 これは、特に自動的に初期化が行われる別の言語を使用していた場合は、覚えておくべき C++ の重要な側面です。 非 POD クラス型の変数を宣言した場合、コンストラクターにより初期化が実行されます。

次の例は、それぞれ記述を含む、いくつかの簡単な変数宣言を示しています。 この例は、コンパイラが型情報を使用して、特定の後続の処理を許可または拒否する方法も示しています。

```cpp
int result = 0;              // Declare and initialize an integer.
double coefficient = 10.8;   // Declare and initialize a floating
                             // point value.
auto name = "Lady G.";       // Declare a variable and let compiler
                             // deduce the type.
auto address;                // error. Compiler cannot deduce a type
                             // without an intializing value.
age = 12;                    // error. Variable declaration must
                             // specify a type or use auto!
result = "Kenny G.";         // error. Can’t assign text to an int.
string result = "zero";      // error. Can’t redefine a variable with
                             // new type.
int maxValue;                // Not recommended! maxValue contains
                             // garbage bits until it is initialized.
```

## <a name="fundamental-built-in-types"></a>基本 (組み込み) 型

一部の言語とは異なり、C++ には他のすべての型の派生元となる汎用基本型はありません。 The language includes many *fundamental types*, also known as *built-in types*. This includes numeric types such as **int**, **double**, **long**, **bool**, plus the **char** and **wchar_t** types for ASCII and UNICODE characters, respectively. Most fundamental types (except **bool**, **double**, **wchar_t** and related types) all have unsigned versions, which modify the range of values that the variable can store. For example, an **int**, which stores a 32-bit signed integer, can represent a value from -2,147,483,648 to 2,147,483,647. An **unsigned int**, which is also stored as 32-bits, can store a value from 0 to 4,294,967,295. 各ケースで格納できる値の合計数は同じです。範囲のみ異なります。

基本型は、実行可能な操作や他の基本型に変換する方法を制御する組み込みの規則を持つコンパイラにより認識されます。 For a complete list of built-in types and their size and numeric limits, see [Fundamental Types](../cpp/fundamental-types-cpp.md).

次の図は、組み込み型の相対サイズを示しています。

![Size in bytes of built&#45;in types](../cpp/media/built-intypesizes.png "Size in bytes of built&#45;in types")

次の表は、最もよく使用される基本型の一覧です。

|[種類]|サイズ|コメント|
|----------|----------|-------------|
|int|4 バイト|整数値の既定のオプション。|
|二重線|8 バイト|浮動小数点値の既定のオプション。|
|bool|1 バイト|true または false になる値を表します。|
|char|1 バイト|以前の C スタイル文字列内の ASCII 文字や、UNICODE に変換する必要がない std::string オブジェクトの ASCII 文字に使用します。|
|wchar_t|2 バイト|UNICODE 形式でエンコードできるワイド文字を表します (Windows では UTF-16。他のオペレーティング システムでは異なる場合があります)。 これは、型 `std::wstring` の文字列で使用される文字型です。|
|unsigned&nbsp;char|1 バイト|C++ には、組み込みの `byte` 型はありません。  バイト値を表すには unsigned char を使用します。|
|unsigned int|4 バイト|ビット フラグの既定のオプション。|
|long long|8 バイト|非常に大きな整数値を表します。|

## <a name="the-void-type"></a>void 型

The **void** type is a special type; you cannot declare a variable of type **void**, but you can declare a variable of type __void \*__ (pointer to **void**), which is sometimes necessary when allocating raw (un-typed) memory. However, pointers to **void** are not type-safe and generally their use is strongly discouraged in modern C++. In a function declaration, a **void** return value means that the function does not return a value; this is a common and acceptable use of **void**. While the C language required functions that have zero parameters to declare **void** in the parameter list, for example, `fou(void)`, this practice is discouraged in modern C++ and should be declared `fou()`. For more information, see [Type Conversions and Type Safety](../cpp/type-conversions-and-type-safety-modern-cpp.md).

## <a name="const-type-qualifier"></a>const 型修飾子

組み込み型またはユーザー定義型は、const キーワードで修飾することができます。 Additionally, member functions may be **const**-qualified and even **const**-overloaded. The value of a **const** type cannot be modified after it is initialized.

```cpp

const double PI = 3.1415;
PI = .75 //Error. Cannot modify const variable.
```

The **const** qualifier is used extensively in function and variable declarations and "const correctness" is an important concept in C++; essentially it means to use **const** to guarantee, at compile time, that values are not modified unintentionally. For more information, see [const](../cpp/const-cpp.md).

A **const** type is distinct from its non-const version; for example, **const int** is a distinct type from **int**. You can use the C++ **const_cast** operator on those rare occasions when you must remove *const-ness* from a variable. For more information, see [Type Conversions and Type Safety](../cpp/type-conversions-and-type-safety-modern-cpp.md).

## <a name="string-types"></a>文字列型

Strictly speaking, the C++ language has no built-in string type; **char** and **wchar_t** store single characters - you must declare an array of these types to approximate a string, adding a terminating null value (for example, ASCII `'\0'`) to the array element one past the last valid character (also called a *C-style string*). C スタイル文字列では、かなり多くのコードを記述するか、外部文字列ユーティリティ ライブラリ関数を使用する必要がありました。 But in modern C++, we have the Standard Library types `std::string` (for 8-bit **char**-type character strings) or `std::wstring` (for 16-bit **wchar_t**-type character strings). These C++ Standard Library containers can be thought of as native string types because they are part of the standard libraries that are included in any compliant C++ build environment. `#include <string>` ディレクティブを使用するだけで、これらの型をプログラムで使用できるようになります (If you are using MFC or ATL, the CString class is also available, but is not part of the C++ standard.) The use of null-terminated character arrays (the C-style strings previously mentioned) is strongly discouraged in modern C++.

## <a name="user-defined-types"></a>ユーザー定義型

When you define a **class**, **struct**, **union**, or **enum**, that construct is used in the rest of your code as if it were a fundamental type. メモリ内には既知のサイズがあり、コンパイル時のチェックを要求し、実行時にプログラムの有効期間を問い合わせるために使用する方法に関する一定の規則もあります。 基本の組み込み型とユーザー定義型の主な相違点は次のとおりです。

- コンパイラには、ユーザー定義型に関する組み込みの情報はありません。 It learns of the type when it first encounters the definition during the compilation process.

- クラス メンバーまたは非メンバー関数として適切な演算子を定義することで (オーバーロードを通じて)、型で実行可能な操作と他の方に変換する方法を指定します。 For more information, see [Function Overloading](function-overloading.md)

## <a name="pointer-types"></a>ポインター型

C 言語の初期バージョンからそうであったように、C++ では特別な宣言子 `*` (アスタリスク) を使用して、ポインター型の変数を宣言できます。 ポインター型には、実際のデータ値が格納されているメモリ位置のアドレスが格納されます。 In modern C++, these are referred to as *raw pointers*, and are accessed in your code through special operators `*` (asterisk) or `->` (dash with greater-than). This is called *dereferencing*, and which one that you use depends on whether you are dereferencing a pointer to a scalar or a pointer to a member in an object. ポインター型の使用は、長い間 C および C++ プログラム開発における最も困難で複雑な側面の 1 つでした。 This section outlines some facts and practices to help use raw pointers if you want to, but in modern C++ it’s no longer required (or recommended) to use raw pointers for object ownership at all, due to the evolution of the [smart pointer](../cpp/smart-pointers-modern-cpp.md) (discussed more at the end of this section). 現在でも、オブジェクトの観察には生のポインターが役立ち、使用してもかまいませんが、オブジェクトの所有権に使用する必要がある場合は慎重に使用し、生のポインターが所有するオブジェクトを作成および破棄する方法について十分に考慮してください。

まず知る必要がある点は、生のポインター変数を宣言すると、ポインターが逆参照されるときに参照するメモリ位置のアドレスを格納するのに必要なメモリだけが割り当てられるという点です。 Allocation of the memory for the data value itself (also called *backing store*) is not yet allocated. 言い換えると、生のポインター変数を宣言することで、実際のデータの変数ではなくメモリ アドレスの変数を作成することになります。 バッキング ストアへの有効なアドレスが含まれることを確認する前にポインター変数を逆参照すると、プログラムで定義されていない動作 (通常は重大なエラー) が発生します。 この種のエラーの例を次に示します。

```cpp
int* pNumber;       // Declare a pointer-to-int variable.
*pNumber = 10;      // error. Although this may compile, it is
                    // a serious error. We are dereferencing an
                    // uninitialized pointer variable with no
                    // allocated memory to point to.
```

この例では、実際の整数データまたはそこに割り当てられた有効なメモリ アドレスを格納するメモリを割り当てずに、ポインター型を逆参照しています。 このエラーを修正するコード例を次に示します。

```cpp
    int number = 10;          // Declare and initialize a local integer
                              // variable for data backing store.
    int* pNumber = &number;   // Declare and initialize a local integer
                              // pointer variable to a valid memory
                              // address to that backing store.
...
    *pNumber = 41;            // Dereference and store a new value in
                              // the memory pointed to by
                              // pNumber, the integer variable called
                              // "number". Note "number" was changed, not
                              // "pNumber".
```

修正後のコード例では、ローカル スタック メモリを使用して、`pNumber` がポイントするバッキング ストアを作成します。 ここでは、説明を簡単にするために基本型を使用しています。 In practice, the backing store for pointers are most often user-defined types that are dynamically-allocated in an area of memory called the *heap* (or *free store*) by using a **new** keyword expression (in C-style programming, the older `malloc()` C runtime library function was used). Once allocated, these variables are usually referred to as objects, especially if they are based on a class definition. Memory that is allocated with **new** must be deleted by a corresponding **delete** statement (or, if you used the `malloc()` function to allocate it, the C runtime function `free()`).

However, it is easy to forget to delete a dynamically-allocated object- especially in complex code, which causes a resource bug called a *memory leak*. したがって、最新の C++ では生のポインターを使用しないことを強くお勧めします。 It is almost always better to wrap a raw pointer in a [smart pointer](../cpp/smart-pointers-modern-cpp.md), which will automatically release the memory when its destructor is invoked (when the code goes out of scope for the smart pointer); by using smart pointers you virtually eliminate a whole class of bugs in your C++ programs. 次の例では、`MyClass` がパブリック メソッド `DoSomeWork();` を持つユーザー定義型であることを前提としています。

```cpp
void someFunction() {
    unique_ptr<MyClass> pMc(new MyClass);
    pMc->DoSomeWork();
}
  // No memory leak. Out-of-scope automatically calls the destructor
  // for the unique_ptr, freeing the resource.
```

For more information about smart pointers, see [Smart Pointers](../cpp/smart-pointers-modern-cpp.md).

For more information about pointer conversions, see [Type Conversions and Type Safety](../cpp/type-conversions-and-type-safety-modern-cpp.md).

For more information about pointers in general, see [Pointers](../cpp/pointers-cpp.md).

## <a name="windows-data-types"></a>Windows のデータ型

C および C++ 向けの従来の Win32 プログラミングでは、ほとんどの関数は Windows 固有の typedef マクロと #define マクロ (`windef.h` で定義) を使用して、パラメーターと戻り値の型を指定します。 These Windows data types are mostly just special names (aliases) given to C/C++ built-in types. For a complete list of these typedefs and preprocessor definitions, see [Windows Data Types](/windows/win32/WinProg/windows-data-types). HRESULT や LCID など、typedef には便利で内容がわかりやすいものがあります。 INT など、他の typedef には特別な意味がなく、C++ の基本型のエイリアスにすぎません。 他の Windows のデータ型には、C プログラミングおよび 16 ビット プロセッサの時代から残っている名前がありますが、最新のハードウェアやオペレーティング システムでは目的も意味もありません。 There are also special data types associated with the Windows Runtime Library, listed as [Windows Runtime base data types](/windows/win32/WinRT/base-data-types). 最新の C++ では、値の解釈方法について Windows の型が追加の意味を伝えるのでない限り、一般的なガイドラインとして C++ の基本型が推奨されます。

## <a name="more-information"></a>説明

C++ の型システムの詳細については、次のトピックを参照してください。

|||
|-|-|
|[値型](../cpp/value-types-modern-cpp.md)|Describes *value types* along with issues relating to their use.|
|[Type Conversions and Type Safety](../cpp/type-conversions-and-type-safety-modern-cpp.md)|よくある型変換の問題について説明し、その回避方法を示します。|

## <a name="see-also"></a>関連項目

[Welcome back to C++](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++ 言語リファレンス](../cpp/cpp-language-reference.md)<br/>
[.NET 標準ライブラリ](../standard-library/cpp-standard-library-reference.md)
