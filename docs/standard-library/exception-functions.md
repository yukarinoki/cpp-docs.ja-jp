---
description: '詳細情報: &lt; 例外 &gt; 関数'
title: '&lt;exception&gt; 関数'
ms.date: 11/04/2016
f1_keywords:
- exception/std::current_exception
- exception/std::get_terminate
- exception/std::get_unexpected
- exception/std::make_exception_ptr
- exception/std::rethrow_exception
- exception/std::set_terminate
- exception/std::set_unexpected
- exception/std::terminate
- exception/std::uncaught_exception
- exception/std::unexpected
ms.assetid: c09ac569-5e35-4fe8-872d-ca5810274dd7
helpviewer_keywords:
- std::current_exception [C++]
- std::get_terminate [C++]
- std::get_unexpected [C++]
- std::make_exception_ptr [C++]
- std::rethrow_exception [C++]
- std::set_terminate [C++]
- std::set_unexpected [C++]
- std::terminate [C++]
- std::uncaught_exception [C++]
- std::unexpected [C++]
ms.openlocfilehash: f885b75462c2c7e20552d33e63048e7a55a51d67
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97232565"
---
# <a name="ltexceptiongt-functions"></a>&lt;exception&gt; 関数

## <a name="current_exception"></a><a name="current_exception"></a> current_exception

現在の例外へのスマート ポインターを取得します。

```cpp
exception_ptr current_exception();
```

### <a name="return-value"></a>戻り値

現在の例外を指す [exception_ptr](../standard-library/exception-typedefs.md#exception_ptr) オブジェクト。

### <a name="remarks"></a>解説

catch ブロックで `current_exception` 関数を呼び出します。 例外が処理中で、catch ブロックで例外をキャッチできる場合、`current_exception` 関数は、例外を参照する `exception_ptr` オブジェクトを返します。 それ以外の場合、関数は null `exception_ptr` オブジェクトを返します。

関数は、 `current_exception` **`catch`** ステートメントが [例外宣言](../cpp/try-throw-and-catch-statements-cpp.md) ステートメントを指定しているかどうかに関係なく、処理中の例外をキャプチャします。

現在の例外のデストラクターは、例外を再スローしない場合、ブロックの最後に呼び出され **`catch`** ます。 ただし、デストラクターで `current_exception` 関数を呼び出しても、その関数は現在の例外を参照する `exception_ptr` オブジェクトを返します。

`current_exception` 関数を連続して呼び出すと、現在の例外のさまざまなコピーを参照する `exception_ptr` オブジェクトが返されます。 その結果、オブジェクトは、異なるコピーを参照しているため、コピーが同じバイナリ値を持っている場合でも、比較においては等しくないと評価されます。

## <a name="make_exception_ptr"></a><a name="make_exception_ptr"></a> make_exception_ptr

例外のコピーを保持する [exception_ptr](../standard-library/exception-typedefs.md#exception_ptr) オブジェクトを作成します。

```cpp
template <class E>
    exception_ptr make_exception_ptr(E Except);
```

### <a name="parameters"></a>パラメーター

*ば*\
コピーする例外を持つクラス。 通常は、[例外クラス](../standard-library/exception-class.md) オブジェクトを `make_exception_ptr` 関数への引数として指定しますが、任意のクラスのオブジェクトを引数に使用できます。

### <a name="return-value"></a>戻り値

*以外* のの現在の例外のコピーを指す [exception_ptr](../standard-library/exception-typedefs.md#exception_ptr)オブジェクト。

### <a name="remarks"></a>解説

`make_exception_ptr` 関数を呼び出すことは、C++ 例外をスローし、その例外を catch ブロック内でキャッチしてから、[current_exception](../standard-library/exception-functions.md#current_exception) 関数を呼び出し、例外を参照する `exception_ptr` オブジェクトを返すことと同じです。 `make_exception_ptr` 関数の Microsoft 実装は、例外のスローとキャッチよりも効果的です。

通常、アプリケーションは `make_exception_ptr` 関数を必要とせず、使用は推奨されていません。

## <a name="rethrow_exception"></a><a name="rethrow_exception"></a> rethrow_exception

パラメーターとして渡された例外をスローします。

```cpp
void rethrow_exception(exception_ptr P);
```

### <a name="parameters"></a>パラメーター

*Irtran-p*\
再スローするためにキャッチされる例外。 *P* が null [exception_ptr](../standard-library/exception-typedefs.md#exception_ptr)の場合、関数は [std:: bad_exception](../standard-library/bad-exception-class.md)をスローします。

### <a name="remarks"></a>解説

キャッチした例外を `exception_ptr` オブジェクトに保存すると、プライマリ スレッドはオブジェクトを処理できます。 プライマリ スレッドで、引数として `rethrow_exception` オブジェクトを指定して `exception_ptr` 関数を呼び出します。 `rethrow_exception` 関数は `exception_ptr` オブジェクトから例外を抽出し、プライマリ スレッドのコンテキストで例外をスローします。

## <a name="get_terminate"></a><a name="get_terminate"></a> get_terminate

現在の `terminate_handler` 関数を取得します。

```cpp
terminate_handler get_terminate();
```

## <a name="set_terminate"></a><a name="set_terminate"></a> set_terminate

プログラムの終了時に呼び出される新しい `terminate_handler` を設定します。

```cpp
terminate_handler set_terminate(terminate_handler fnew) throw();
```

### <a name="parameters"></a>パラメーター

*fnew*\
終了時に呼び出される関数。

### <a name="return-value"></a>戻り値

終了時に呼び出されていた、以前の関数のアドレス。

### <a name="remarks"></a>解説

関数は、新しい [terminate_handler](../standard-library/exception-typedefs.md#terminate_handler) を関数 * *fnew* として確立します。 したがって、 *fnew* を null ポインターにすることはできません。 この関数は、以前の終了ハンドラーのアドレスを返します。

### <a name="example"></a>例

```cpp
// exception_set_terminate.cpp
// compile with: /EHsc
#include <exception>
#include <iostream>

using namespace std;

void termfunction()
{
    cout << "My terminate function called." << endl;
    abort();
}

int main()
{
    terminate_handler oldHandler = set_terminate(termfunction);

    // Throwing an unhandled exception would also terminate the program
    // or we could explicitly call terminate();

    //throw bad_alloc();
    terminate();
}
```

## <a name="get_unexpected"></a><a name="get_unexpected"></a> get_unexpected

現在の `unexpected_handler` 関数を取得します。

```cpp
unexpected_handler get_unexpected();
```

## <a name="rethrow_if_nested"></a><a name="rethrow_if_nested"></a> rethrow_if_nested

```cpp
template <class E>
    void rethrow_if_nested(const E& e);
```

### <a name="remarks"></a>解説

ポリモーフィックなクラス型でない場合、またはにアクセスできない場合やあいまいな場合は、何の影響もあり `nested_exception` ません。 それ以外の場合、は動的なキャストを実行します。

## <a name="set_unexpected"></a><a name="set_unexpected"></a> set_unexpected

予期しない例外が発生したときに新しい `unexpected_handler` が存在するように設定します。

```cpp
unexpected_handler set_unexpected(unexpected_handler fnew) throw();
```

### <a name="parameters"></a>パラメーター

*fnew*\
予期しない例外が発生したときに呼び出される関数。

### <a name="return-value"></a>戻り値

以前の `unexpected_handler` のアドレス。

### <a name="remarks"></a>解説

*fnew* を null ポインターにすることはできません。

C++ 標準では、関数が throw のリストにない例外をスローした場合に、`unexpected` を呼び出す必要があります。 現在の実装では、これをサポートしていません。 次の例では、`unexpected` を直接呼び出し、その後で `unexpected_handler` を呼び出します。

### <a name="example"></a>例

```cpp
// exception_set_unexpected.cpp
// compile with: /EHsc
#include <exception>
#include <iostream>

using namespace std;

void uefunction()
{
    cout << "My unhandled exception function called." << endl;
    terminate(); // this is what unexpected() calls by default
}

int main()
{
    unexpected_handler oldHandler = set_unexpected(uefunction);

    unexpected(); // library function to force calling the
                  // current unexpected handler
}
```

## <a name="terminate"></a><a name="terminate"></a> 解約

終了ハンドラーを呼び出します。

```cpp
void terminate();
```

### <a name="remarks"></a>解説

関数は、型の関数である terminate ハンドラーを呼び出し **`void`** ます。 `terminate`がプログラムによって直接呼び出された場合、終了ハンドラーは[set_terminate](../standard-library/exception-functions.md#set_terminate)を呼び出すことによって最後に設定されたものになります。 `terminate`Throw 式の評価中に、他のいくつかの理由によってが呼び出された場合、終了ハンドラーは、throw 式を評価した直後に有効なものになります。

終了ハンドラーは、呼び出し元に戻らない場合があります。 プログラムの起動時、終了ハンドラーはを呼び出す関数です `abort` 。

### <a name="example"></a>例

`terminate` の使用例については、「[set_unexpected](../standard-library/exception-functions.md#set_unexpected)」を参照してください。

## <a name="throw_with_nested"></a><a name="throw_with_nested"></a> throw_with_nested

```cpp
template <class T> [[noreturn]]
    void throw_with_nested(T&& t);
```

### <a name="remarks"></a>解説

入れ子になった例外を使用して例外をスローします。

## <a name="uncaught_exception"></a><a name="uncaught_exception"></a> uncaught_exception

**`true`** スローされた例外が現在処理されている場合にのみ、を返します。

```cpp
bool uncaught_exception();
```

### <a name="return-value"></a>戻り値

**`true`** スロー式の評価が完了してから、一致するハンドラーで例外宣言の初期化が完了するか、または throw 式の結果として [予期しない](../standard-library/exception-functions.md#unexpected)呼び出しを行った後に、を返します。 特に、 `uncaught_exception` は、 **`true`** 例外のアンワインド中に呼び出されるデストラクターから呼び出されると、を返します。 デバイス上で、`uncaught_exception` は Windows CE 5.00 以降のバージョン (Windows Mobile 2005 プラットフォームを含む) でのみサポートされます。

### <a name="example"></a>例

```cpp
// exception_uncaught_exception.cpp
// compile with: /EHsc
#include <exception>
#include <iostream>
#include <string>

class Test
{
public:
   Test( std::string msg ) : m_msg( msg )
   {
      std::cout << "In Test::Test(\"" << m_msg << "\")" << std::endl;
   }
   ~Test( )
   {
      std::cout << "In Test::~Test(\"" << m_msg << "\")" << std::endl
         << "        std::uncaught_exception( ) = "
         << std::uncaught_exception( )
         << std::endl;
   }
private:
    std::string m_msg;
};

// uncaught_exception will be true in the destructor
// for the object created inside the try block because
// the destructor is being called as part of the unwind.

int main( void )
   {
      Test t1( "outside try block" );
      try
      {
         Test t2( "inside try block" );
         throw 1;
      }
      catch (...) {
   }
}
```

```Output
In Test::Test("outside try block")
In Test::Test("inside try block")
In Test::~Test("inside try block")
        std::uncaught_exception( ) = 1
In Test::~Test("outside try block")
        std::uncaught_exception( ) = 0
```

## <a name="unexpected"></a><a name="unexpected"></a> 不適切

予期しないハンドラーを呼び出します。

```cpp
void unexpected();
```

### <a name="remarks"></a>解説

C++ 標準では、関数が throw のリストにない例外をスローした場合に、`unexpected` を呼び出す必要があります。 現在の実装では、これをサポートしていません。 次の例では、予期しないハンドラーを呼び出す `unexpected` を直接呼び出します。

関数は、予期しないハンドラー (型の関数) を呼び出し **`void`** ます。 `unexpected` がプログラムによって直接呼び出される場合、予期しないハンドラーは、[set_unexpected](../standard-library/exception-functions.md#set_unexpected) の呼び出しによって最も新しく設定されたものとなります。

予期しないハンドラーは、呼び出し元に戻らない場合があります。 次の処理を行って実行を終了する場合があります。

- 例外指定内にリストされた型のオブジェクトをスローする。予期しないハンドラーがプログラムから直接呼び出される場合は任意の型のオブジェクトをスローする。

- [bad_exception](../standard-library/bad-exception-class.md) 型のオブジェクトをスローする。

- [Terminate](../standard-library/exception-functions.md#terminate)、またはを呼び出して `abort` `exit` います。

プログラムの起動時に、予期しないハンドラーは、[terminate](../standard-library/exception-functions.md#terminate) を呼び出す関数となります。

### <a name="example"></a>例

`unexpected` の使用例については、「[set_unexpected](../standard-library/exception-functions.md#set_unexpected)」を参照してください。
