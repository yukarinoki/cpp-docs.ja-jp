---
title: スレッド間の例外転送
ms.date: 05/07/2019
helpviewer_keywords:
- std::current_exception
- transporting exceptions between threads
- std::copy_exception
- exception_ptr
- std::exception_ptr
- std::rethrow_exception
- current_exception
- transport exceptions between threads
- copy_exception
- rethrow_exception
- move exceptions between threads
ms.assetid: 5c95d57b-acf5-491f-8122-57c5df0edd98
ms.openlocfilehash: 25b09c508b932a4d1470f6b23f03aa52e62c68cc
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246310"
---
# <a name="transporting-exceptions-between-threads"></a>スレッド間の例外転送

The Microsoft C++ compiler (MSVC) supports *transporting an exception* from one thread to another. 例外の転送により、1 つのスレッドで例外をキャッチし、その例外が別のスレッドにスローされたように見せることができます。 たとえば、この機能を使用して、プライマリ スレッドでそのセカンダリ スレッドによってスローされたすべての例外を処理するマルチスレッド アプリケーションを作成できます。 例外の転送は、主に並列プログラミング ライブラリまたはシステムを作成する開発者にとって便利です。 To implement transporting exceptions, MSVC provides the [exception_ptr](../standard-library/exception-typedefs.md#exception_ptr) type and the [current_exception](../standard-library/exception-functions.md#current_exception), [rethrow_exception](../standard-library/exception-functions.md#rethrow_exception), and [make_exception_ptr](../standard-library/exception-functions.md#make_exception_ptr) functions.

## <a name="syntax"></a>構文

```cpp
namespace std
{
   typedef unspecified exception_ptr;
   exception_ptr current_exception();
   void rethrow_exception(exception_ptr p);
   template<class E>
       exception_ptr make_exception_ptr(E e) noexcept;
}
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*unspecified*|`exception_ptr` 型を実装するために使用される未指定の内部クラス。|
|*P*|例外を参照する `exception_ptr` オブジェクト。|
|*E*|例外を表すクラス。|
|*e*|パラメーター `E` クラスのインスタンス。|

## <a name="return-value"></a>戻り値

`current_exception` 関数は、現在進行中の例外を参照する `exception_ptr` オブジェクトを返します。 処理中の例外がない場合、関数は、例外に関連付けられていない `exception_ptr` オブジェクトを返します。

The `make_exception_ptr` function returns an `exception_ptr` object that references the exception specified by the *e* parameter.

## <a name="remarks"></a>Remarks

### <a name="scenario"></a>通信の種類

可変作業量を処理するようにスケーリングするアプリケーションを作成する場合を想定します。 この目的を達成するために、初期プライマリ スレッドがジョブの実行に必要な数のセカンダリ スレッドを作成するマルチスレッド アプリケーションを設計します。 セカンダリ スレッドは、リソースの管理、負荷の分散、スループットの向上などの点でプライマリ スレッドを補助します。 作業の分散によって、マルチスレッド アプリケーションは、シングル スレッド アプリケーションよりもパフォーマンスが向上します。

ただし、セカンダリ スレッドが例外をスローした場合、プライマリ スレッドがその例外を処理するようにします。 これは、セカンダリ スレッドの数に関係なく、アプリケーションが例外を一貫した統一された方法で処理するようにしたいためです。

### <a name="solution"></a>解決策:

上記のシナリオを処理するために、C++ 標準はスレッド間での例外の転送をサポートしています。 If a secondary thread throws an exception, that exception becomes the *current exception*. By analogy to the real world, the current exception is said to be *in flight*. 現在の例外は、スローされた時点から、それをキャッチする例外ハンドラーによって返されるまでが処理中です。

The secondary thread can catch the current exception in a **catch** block, and then call the `current_exception` function to store the exception in an `exception_ptr` object. `exception_ptr` オブジェクトはセカンダリ スレッドとプライマリ スレッドで使用できる必要があります。 たとえば、`exception_ptr` オブジェクトは、アクセスがミューテックスによって制御されるグローバル変数にすることができます。 The term *transport an exception* means an exception in one thread can be converted to a form that can be accessed by another thread.

次に、プライマリ スレッドが `rethrow_exception` 関数を呼び出します。これは、`exception_ptr` オブジェクトから例外を抽出してスローします。 例外がスローされると、プライマリ スレッドで現在の例外になります。 つまり、例外はプライマリ スレッドで発生したように見えます。

Finally, the primary thread can catch the current exception in a **catch** block and then process it or throw it to a higher level exception handler. また、プライマリ スレッドは例外を無視し、プロセスが終了することを許可できます。

ほとんどのアプリケーションは、スレッド間で例外を転送する必要はありません。 ただし、システムでセカンダリ スレッド、プロセッサ、またはコア間に作業を分割できるため、並列計算のシステムにこの機能を使うと便利です。 並列コンピューティング環境では、単一の専用スレッドがセカンダリ スレッドからのすべての例外を処理し、すべてのアプリケーションに一貫した例外処理モデルを提供できます。

C++ 標準委員会の提案の詳細については、「Language Support for Transporting Exceptions between Threads (スレッド間の例外を転送するための言語のサポート)」というタイトルのドキュメント番号 N2179 をインターネットで検索してください。

### <a name="exception-handling-models-and-compiler-options"></a>Exception-handling models and compiler options

アプリケーションの例外処理モデルは、例外をキャッチして転送できるかどうかを判断します。 Visual C++ は、C++ 例外、構造化例外処理 (SEH) 例外、共通言語ランタイム (CLR) 例外を処理できる 3 種類のモデルをサポートします。 Use the [/EH](../build/reference/eh-exception-handling-model.md) and [/clr](../build/reference/clr-common-language-runtime-compilation.md) compiler options to specify your application's exception-handling model.

例外を転送できるのは、コンパイラ オプションとプログラミング ステートメントの次の組み合わせだけです。 他の組み合わせでは、例外をキャッチできないか、例外をキャッチできても転送できません。

- The **/EHa** compiler option and the **catch** statement can transport SEH and C++ exceptions.

- The **/EHa**, **/EHs**, and **/EHsc** compiler options and the **catch** statement can transport C++ exceptions.

- The **/CLR** compiler option and the **catch** statement can transport C++ exceptions. The **/CLR** compiler option implies specification of the **/EHa** option. コンパイラがマネージド例外の転送をサポートしないことに注意してください。 This is because managed exceptions, which are derived from the [System.Exception class](../standard-library/exception-class.md), are already objects that you can move between threads by using the facilities of the common languange runtime.

   > [!IMPORTANT]
   > We recommend that you specify the **/EHsc** compiler option and catch only C++ exceptions. You expose yourself to a security threat if you use the **/EHa** or **/CLR** compiler option and a **catch** statement with an ellipsis *exception-declaration* (`catch(...)`). You probably intend to use the **catch** statement to capture a few specific exceptions. しかし、`catch(...)` ステートメントは、致命的な例外を含むすべての C++ 例外と SEH 例外をキャプチャします。 予期しない例外を無視するか、誤って操作すると、悪意あるコードが、プログラムのセキュリティを侵す機会が生じます。

## <a name="usage"></a>使用方法

The following sections describe how to transport exceptions by using the `exception_ptr` type, and the `current_exception`, `rethrow_exception`, and `make_exception_ptr` functions.

## <a name="exception_ptr-type"></a>exception_ptr type

現在の例外またはユーザーが指定した例外のインスタンスを参照するには、`exception_ptr` オブジェクトを使用します。 Microsoft の実装では、例外は [EXCEPTION_RECORD](/windows/win32/api/winnt/ns-winnt-exception_record) 構造体によって表されます。 各 `exception_ptr` オブジェクトには、例外を表す `EXCEPTION_RECORD` 構造体のコピーを指す例外参照フィールドが含まれています。

`exception_ptr` 変数を宣言する場合、変数は例外に関連付けられません。 つまり、例外参照フィールドが NULL です。 このような `exception_ptr` オブジェクトは、*null exception_ptr* と呼ばれます。

例外を `current_exception` オブジェクトに割り当てるには、`make_exception_ptr` または `exception_ptr` 関数を使用します。 `exception_ptr` 変数に例外を割り当てた場合、変数の例外参照フィールドは例外のコピーを指します。 例外をコピーするためのメモリが不足している場合、例外参照フィールドは、[std::bad_alloc](../standard-library/bad-alloc-class.md) 例外のコピーを指し示します。 If the `current_exception` or `make_exception_ptr` function cannot copy the exception for any other reason, the function calls the [terminate](../c-runtime-library/reference/terminate-crt.md) function to exit the current process.

名前とは異なり、`exception_ptr` オブジェクト自体はポインターではありません。 It does not obey pointer semantics and cannot be used with the pointer member access (`->`) or indirection (`*`) operators. `exception_ptr` オブジェクトには、パブリック データ メンバーまたはメンバー関数がありません。

### <a name="comparisons"></a>比較

等値演算子 (`==`) と不等値演算子 (`!=`) を使用して、2 種類の `exception_ptr` オブジェクトを比較できます。 演算子は、例外を表す `EXCEPTION_RECORD` 構造体のバイナリ値 (ビット パターン) は比較しません。 代わりに、演算子は `exception_ptr` オブジェクトの例外参照フィールドのアドレスを比較します。 その結果、null `exception_ptr` と NULL 値を比較すると、等しいと評価されます。

## <a name="current_exception-function"></a>current_exception function

Call the `current_exception` function in a **catch** block. If an exception is in flight and the **catch** block can catch the exception, the `current_exception` function returns an `exception_ptr` object that references the exception. それ以外の場合、関数は null `exception_ptr` オブジェクトを返します。

### <a name="details"></a>説明

The `current_exception` function captures the exception that is in flight regardless of whether the **catch** statement specifies an [exception-declaration](../cpp/try-throw-and-catch-statements-cpp.md) statement.

The destructor for the current exception is called at the end of the **catch** block if you do not rethrow the exception. ただし、デストラクターで `current_exception` 関数を呼び出しても、その関数は現在の例外を参照する `exception_ptr` オブジェクトを返します。

`current_exception` 関数を連続して呼び出すと、現在の例外のさまざまなコピーを参照する `exception_ptr` オブジェクトが返されます。 その結果、オブジェクトは、異なるコピーを参照しているため、コピーが同じバイナリ値を持っている場合でも、比較においては等しくないと評価されます。

### <a name="seh-exceptions"></a>SEH exceptions

If you use the **/EHa** compiler option, you can catch an SEH exception in a C++ **catch** block. `current_exception` 関数は、SEH 例外を参照する `exception_ptr` オブジェクトを返します。 And the `rethrow_exception` function throws the SEH exception if you call it with thetransported `exception_ptr` object as its argument.

The `current_exception` function returns a null `exception_ptr` if you call it in an SEH **__finally** termination handler, an **__except** exception handler, or the **__except** filter expression.

転送された例外は、入れ子になった例外をサポートしません。 入れ子になった例外は、例外の処理中に別の例外がスローされると発生します。 入れ子になった例外をキャッチする場合、`EXCEPTION_RECORD.ExceptionRecord` データ メンバーは、関連の例外を記述する `EXCEPTION_RECORD` 構造体のチェーンを指し示します。 `current_exception` 関数は、`exception_ptr` データ メンバーがゼロ設定された `ExceptionRecord` オブジェクトを返すため、入れ子になった例外をサポートしていません。

SEH 例外をキャッチする場合、`EXCEPTION_RECORD.ExceptionInformation` データ メンバー配列のポインターで参照されるメモリを管理する必要があります。 対応する `exception_ptr` オブジェクトの有効期間中はメモリが有効であること、および `exception_ptr` オブジェクトが削除されるときにメモリが解放されることを保証する必要があります。

転送例外の機能と共に構造化例外 (SE) 変換関数を使用できます。 SEH 例外が C++ 例外に変換される場合、`current_exception` 関数は、元の SEH 例外ではなく変換された例外を参照する `exception_ptr` を返します。 `rethrow_exception` 関数は、その後、元の例外ではなく変換された例外をスローします。 For more information about SE translator functions, see [_set_se_translator](../c-runtime-library/reference/set-se-translator.md).

## <a name="rethrow_exception-function"></a>rethrow_exception function

キャッチした例外を `exception_ptr` オブジェクトに保存すると、プライマリ スレッドはオブジェクトを処理できます。 プライマリ スレッドで、引数として `rethrow_exception` オブジェクトを指定して `exception_ptr` 関数を呼び出します。 `rethrow_exception` 関数は `exception_ptr` オブジェクトから例外を抽出し、プライマリ スレッドのコンテキストで例外をスローします。 If the *p* parameter of the `rethrow_exception` function is a null `exception_ptr`, the function throws [std::bad_exception](../standard-library/bad-exception-class.md).

抽出された例外はプライマリ スレッドで現在の例外になり、他の例外と同様に扱うことができます。 If you catch the exception, you can handle it immediately or use a **throw** statement to send it to a higher level exception handler. それ以外の場合は、何も実行されず、既定のシステム例外ハンドラーによってプロセスが終了されます。

## <a name="make_exception_ptr-function"></a>make_exception_ptr 関数

`make_exception_ptr` 関数は、クラスのインスタンスを引数として受け取り、そのインスタンスを参照する `exception_ptr` を返します。 通常は、[例外クラス](../standard-library/exception-class.md) オブジェクトを `make_exception_ptr` 関数への引数として指定しますが、任意のクラスのオブジェクトを引数に使用できます。

Calling the `make_exception_ptr` function is equivalent to throwing a C++ exception, catching it in a **catch** block, and then calling the `current_exception` function to return an `exception_ptr` object that references the exception. `make_exception_ptr` 関数の Microsoft 実装は、例外のスローとキャッチよりも効果的です。

通常、アプリケーションは `make_exception_ptr` 関数を必要とせず、使用は推奨されていません。

## <a name="example"></a>例

次の例は、標準 C++ 例外とカスタム C++ 例外をあるスレッドから別のスレッドに転送します。

```cpp
// transport_exception.cpp
// compile with: /EHsc /MD
#include <windows.h>
#include <stdio.h>
#include <exception>
#include <stdexcept>

using namespace std;

// Define thread-specific information.
#define THREADCOUNT 2
exception_ptr aException[THREADCOUNT];
int           aArg[THREADCOUNT];

DWORD WINAPI ThrowExceptions( LPVOID );

// Specify a user-defined, custom exception.
// As a best practice, derive your exception
// directly or indirectly from std::exception.
class myException : public std::exception {
};
int main()
{
    HANDLE aThread[THREADCOUNT];
    DWORD ThreadID;

    // Create secondary threads.
    for( int i=0; i < THREADCOUNT; i++ )
    {
        aArg[i] = i;
        aThread[i] = CreateThread(
            NULL,       // Default security attributes.
            0,          // Default stack size.
            (LPTHREAD_START_ROUTINE) ThrowExceptions,
            (LPVOID) &aArg[i], // Thread function argument.
            0,          // Default creation flags.
            &ThreadID); // Receives thread identifier.
        if( aThread[i] == NULL )
        {
            printf("CreateThread error: %d\n", GetLastError());
            return -1;
        }
    }

    // Wait for all threads to terminate.
    WaitForMultipleObjects(THREADCOUNT, aThread, TRUE, INFINITE);
    // Close thread handles.
    for( int i=0; i < THREADCOUNT; i++ ) {
        CloseHandle(aThread[i]);
    }

    // Rethrow and catch the transported exceptions.
    for ( int i = 0; i < THREADCOUNT; i++ ) {
        try {
            if (aException[i] == NULL) {
                printf("exception_ptr %d: No exception was transported.\n", i);
            }
            else {
                rethrow_exception( aException[i] );
            }
        }
        catch( const invalid_argument & ) {
            printf("exception_ptr %d: Caught an invalid_argument exception.\n", i);
        }
        catch( const myException & ) {
            printf("exception_ptr %d: Caught a  myException exception.\n", i);
        }
    }
}
// Each thread throws an exception depending on its thread
// function argument, and then ends.
DWORD WINAPI ThrowExceptions( LPVOID lpParam )
{
    int x = *((int*)lpParam);
    if (x == 0) {
        try {
            // Standard C++ exception.
            // This example explicitly throws invalid_argument exception.
            // In practice, your application performs an operation that
            // implicitly throws an exception.
            throw invalid_argument("A C++ exception.");
        }
        catch ( const invalid_argument & ) {
            aException[x] = current_exception();
        }
    }
    else {
        // User-defined exception.
        aException[x] = make_exception_ptr( myException() );
    }
    return TRUE;
}
```

```Output
exception_ptr 0: Caught an invalid_argument exception.
exception_ptr 1: Caught a  myException exception.
```

## <a name="requirements"></a>［要件］

**ヘッダー:** \<exception>

## <a name="see-also"></a>関連項目

[例外処理](../cpp/exception-handling-in-visual-cpp.md)<br/>
[/EH (例外処理モデル)](../build/reference/eh-exception-handling-model.md)<br/>
[/clr (共通言語ランタイムのコンパイル)](../build/reference/clr-common-language-runtime-compilation.md)
