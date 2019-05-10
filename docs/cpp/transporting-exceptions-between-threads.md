---
title: スレッド間の例外を転送
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
ms.openlocfilehash: e59883c75fde9938a213fb4e888e6b05a79cf4f7
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221926"
---
# <a name="transporting-exceptions-between-threads"></a>スレッド間の例外を転送

MicrosoftC++コンパイラ (MSVC) がサポート*例外の転送*別に 1 つのスレッドから。 例外の転送により、1 つのスレッドで例外をキャッチし、その例外が別のスレッドにスローされたように見せることができます。 たとえば、この機能を使用して、プライマリ スレッドでそのセカンダリ スレッドによってスローされたすべての例外を処理するマルチスレッド アプリケーションを作成できます。 例外の転送は、主に並列プログラミング ライブラリまたはシステムを作成する開発者にとって便利です。 MSVC は、例外の転送を実装するために、 [exception_ptr](../standard-library/exception-typedefs.md#exception_ptr)型と[current_exception](../standard-library/exception-functions.md#current_exception)、 [rethrow_exception](../standard-library/exception-functions.md#rethrow_exception)、および[make_exception_ptr](../standard-library/exception-functions.md#make_exception_ptr)関数。

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
|*p*|例外を参照する `exception_ptr` オブジェクト。|
|*E*|例外を表すクラス。|
|*e*|パラメーター `E` クラスのインスタンス。|

## <a name="return-value"></a>戻り値

`current_exception` 関数は、現在進行中の例外を参照する `exception_ptr` オブジェクトを返します。 処理中の例外がない場合、関数は、例外に関連付けられていない `exception_ptr` オブジェクトを返します。

`make_exception_ptr`関数が返される、`exception_ptr`で指定された例外を参照するオブジェクト、 *e*パラメーター。

## <a name="remarks"></a>Remarks

### <a name="scenario"></a>シナリオ

可変作業量を処理するようにスケーリングするアプリケーションを作成する場合を想定します。 この目的を達成するために、初期プライマリ スレッドがジョブの実行に必要な数のセカンダリ スレッドを作成するマルチスレッド アプリケーションを設計します。 セカンダリ スレッドは、リソースの管理、負荷の分散、スループットの向上などの点でプライマリ スレッドを補助します。 作業の分散によって、マルチスレッド アプリケーションは、シングル スレッド アプリケーションよりもパフォーマンスが向上します。

ただし、セカンダリ スレッドが例外をスローした場合、プライマリ スレッドがその例外を処理するようにします。 これは、セカンダリ スレッドの数に関係なく、アプリケーションが例外を一貫した統一された方法で処理するようにしたいためです。

### <a name="solution"></a>ソリューション

上記のシナリオを処理するために、C++ 標準はスレッド間での例外の転送をサポートしています。 セカンダリ スレッドは、例外をスローする場合、その例外になります、*現在の例外*します。 現実の世界にたとえて、現在の例外があると言います*飛行*します。 現在の例外は、スローされた時点から、それをキャッチする例外ハンドラーによって返されるまでが処理中です。

セカンダリ スレッドで現在の例外をキャッチできる、**キャッチ**ブロックを呼び出して、`current_exception`関数で例外を格納する、`exception_ptr`オブジェクト。 `exception_ptr` オブジェクトはセカンダリ スレッドとプライマリ スレッドで使用できる必要があります。 たとえば、`exception_ptr` オブジェクトは、アクセスがミューテックスによって制御されるグローバル変数にすることができます。 用語*例外を転送*1 つのスレッドで例外は、別のスレッドによってアクセスできる形式に変換できることを意味します。

次に、プライマリ スレッドが `rethrow_exception` 関数を呼び出します。これは、`exception_ptr` オブジェクトから例外を抽出してスローします。 例外がスローされると、プライマリ スレッドで現在の例外になります。 つまり、例外はプライマリ スレッドで発生したように見えます。

最後に、プライマリ スレッドがで現在の例外をキャッチできる、**キャッチ**ブロックしし、それを処理またはより高いレベルの例外ハンドラーに例外をスローします。 また、プライマリ スレッドは例外を無視し、プロセスが終了することを許可できます。

ほとんどのアプリケーションは、スレッド間で例外を転送する必要はありません。 ただし、システムでセカンダリ スレッド、プロセッサ、またはコア間に作業を分割できるため、並列計算のシステムにこの機能を使うと便利です。 並列コンピューティング環境では、単一の専用スレッドがセカンダリ スレッドからのすべての例外を処理し、すべてのアプリケーションに一貫した例外処理モデルを提供できます。

C++ 標準委員会の提案の詳細については、「Language Support for Transporting Exceptions between Threads (スレッド間の例外を転送するための言語のサポート)」というタイトルのドキュメント番号 N2179 をインターネットで検索してください。

### <a name="exception-handling-models-and-compiler-options"></a>例外処理モデルとコンパイラ オプション

アプリケーションの例外処理モデルは、例外をキャッチして転送できるかどうかを判断します。 Visual C++ は、C++ 例外、構造化例外処理 (SEH) 例外、共通言語ランタイム (CLR) 例外を処理できる 3 種類のモデルをサポートします。 使用して、 [/EH](../build/reference/eh-exception-handling-model.md)と[/clr](../build/reference/clr-common-language-runtime-compilation.md)コンパイラ オプションをアプリケーションの例外処理モデルを指定します。

例外を転送できるのは、コンパイラ オプションとプログラミング ステートメントの次の組み合わせだけです。 他の組み合わせでは、例外をキャッチできないか、例外をキャッチできても転送できません。

- **/EHa**コンパイラ オプションおよび**キャッチ**ステートメントは、SEH と C++ の例外を転送できます。

- **/EHa**、 **/EHs**、および **/EHsc**コンパイラ オプションおよび**キャッチ**ステートメントは、C++ 例外を転送できます。

- **/CLR**コンパイラ オプションおよび**キャッチ**ステートメントは、C++ 例外を転送できます。 **/CLR**コンパイラ オプションの仕様の意味、 **/EHa**オプション。 コンパイラがマネージド例外の転送をサポートしないことに注意してください。 これは、マネージ例外から派生したため、 [System.Exception クラス](../standard-library/exception-class.md)は既に、共通言語ランタイムの機能を使用して、スレッド間を移動するオブジェクト。

   > [!IMPORTANT]
   > 指定することをお勧め、 **/EHsc**コンパイラ オプションとのみの C++ 例外をキャッチします。 自分をさらすことに、セキュリティの脅威を使用する場合、 **/EHa**または **/CLR**コンパイラ オプションおよび**キャッチ**省略記号を含むステートメント*例外宣言*(`catch(...)`)。 使用する可能性があります、**キャッチ**ステートメントをいくつかの特定の例外をキャプチャします。 しかし、`catch(...)` ステートメントは、致命的な例外を含むすべての C++ 例外と SEH 例外をキャプチャします。 予期しない例外を無視するか、誤って操作すると、悪意あるコードが、プログラムのセキュリティを侵す機会が生じます。

## <a name="usage"></a>使用法

次のセクションを使用して例外を転送する方法について説明、`exception_ptr`型、および`current_exception`、 `rethrow_exception`、および`make_exception_ptr`関数。

## <a name="exceptionptr-type"></a>exception_ptr 型

現在の例外またはユーザーが指定した例外のインスタンスを参照するには、`exception_ptr` オブジェクトを使用します。 Microsoft の実装では、例外は [EXCEPTION_RECORD](/windows/desktop/api/winnt/ns-winnt-_exception_record) 構造体によって表されます。 各 `exception_ptr` オブジェクトには、例外を表す `EXCEPTION_RECORD` 構造体のコピーを指す例外参照フィールドが含まれています。

`exception_ptr` 変数を宣言する場合、変数は例外に関連付けられません。 つまり、例外参照フィールドが NULL です。 このような `exception_ptr` オブジェクトは、*null exception_ptr* と呼ばれます。

例外を `current_exception` オブジェクトに割り当てるには、`make_exception_ptr` または `exception_ptr` 関数を使用します。 `exception_ptr` 変数に例外を割り当てた場合、変数の例外参照フィールドは例外のコピーを指します。 例外をコピーするためのメモリが不足している場合、例外参照フィールドは、[std::bad_alloc](../standard-library/bad-alloc-class.md) 例外のコピーを指し示します。 場合、`current_exception`または`make_exception_ptr`関数はその他の理由、関数呼び出しの例外をコピーすることはできません、[終了](../c-runtime-library/reference/terminate-crt.md)を現在のプロセスを終了する関数。

名前とは異なり、`exception_ptr` オブジェクト自体はポインターではありません。 ポインターのセマンティクスに従わず、ポインターのメンバー アクセスでは使用できません (`->`) または間接参照 (`*`) 演算子。 `exception_ptr` オブジェクトには、パブリック データ メンバーまたはメンバー関数がありません。

### <a name="comparisons"></a>比較

等値演算子 (`==`) と不等値演算子 (`!=`) を使用して、2 種類の `exception_ptr` オブジェクトを比較できます。 演算子は、例外を表す `EXCEPTION_RECORD` 構造体のバイナリ値 (ビット パターン) は比較しません。 代わりに、演算子は `exception_ptr` オブジェクトの例外参照フィールドのアドレスを比較します。 その結果、null `exception_ptr` と NULL 値を比較すると、等しいと評価されます。

## <a name="currentexception-function"></a>current_exception 関数

呼び出す、`current_exception`で機能、**キャッチ**ブロックします。 例外が処理中の場合、**キャッチ**ブロックが例外をキャッチ、`current_exception`関数が返される、`exception_ptr`例外を参照するオブジェクト。 それ以外の場合、関数は null `exception_ptr` オブジェクトを返します。

### <a name="details"></a>説明

`current_exception`関数かどうかに関係なく処理中である例外では、**キャッチ**ステートメントを指定します、[例外宣言](../cpp/try-throw-and-catch-statements-cpp.md)ステートメント。

末尾に現在の例外のデストラクターが呼び出されます、**キャッチ**例外が再スローしない場合にブロックします。 ただし、デストラクターで `current_exception` 関数を呼び出しても、その関数は現在の例外を参照する `exception_ptr` オブジェクトを返します。

`current_exception` 関数を連続して呼び出すと、現在の例外のさまざまなコピーを参照する `exception_ptr` オブジェクトが返されます。 その結果、オブジェクトは、異なるコピーを参照しているため、コピーが同じバイナリ値を持っている場合でも、比較においては等しくないと評価されます。

### <a name="seh-exceptions"></a>SEH 例外

使用する場合、 **/EHa**コンパイラ オプションは、SEH 例外をキャッチするには、C++ で**キャッチ**ブロックします。 `current_exception` 関数は、SEH 例外を参照する `exception_ptr` オブジェクトを返します。 および`rethrow_exception`thetransported で呼び出すことがある場合、関数は、SEH 例外をスローします。`exception_ptr`オブジェクトを引数として。

`current_exception`関数は null を返します`exception_ptr`、SEH でそれを呼び出す場合 **_ _finally**終了ハンドラーを **_ _except**例外ハンドラー、または **__except**フィルター式。

転送された例外は、入れ子になった例外をサポートしません。 入れ子になった例外は、例外の処理中に別の例外がスローされると発生します。 入れ子になった例外をキャッチする場合、`EXCEPTION_RECORD.ExceptionRecord` データ メンバーは、関連の例外を記述する `EXCEPTION_RECORD` 構造体のチェーンを指し示します。 `current_exception` 関数は、`exception_ptr` データ メンバーがゼロ設定された `ExceptionRecord` オブジェクトを返すため、入れ子になった例外をサポートしていません。

SEH 例外をキャッチする場合、`EXCEPTION_RECORD.ExceptionInformation` データ メンバー配列のポインターで参照されるメモリを管理する必要があります。 対応する `exception_ptr` オブジェクトの有効期間中はメモリが有効であること、および `exception_ptr` オブジェクトが削除されるときにメモリが解放されることを保証する必要があります。

転送例外の機能と共に構造化例外 (SE) 変換関数を使用できます。 SEH 例外が C++ 例外に変換される場合、`current_exception` 関数は、元の SEH 例外ではなく変換された例外を参照する `exception_ptr` を返します。 `rethrow_exception` 関数は、その後、元の例外ではなく変換された例外をスローします。 SE 変換関数の詳細については、次を参照してください。 [_set_se_translator](../c-runtime-library/reference/set-se-translator.md)します。

## <a name="rethrowexception-function"></a>rethrow_exception 関数

キャッチした例外を `exception_ptr` オブジェクトに保存すると、プライマリ スレッドはオブジェクトを処理できます。 プライマリ スレッドで、引数として `rethrow_exception` オブジェクトを指定して `exception_ptr` 関数を呼び出します。 `rethrow_exception` 関数は `exception_ptr` オブジェクトから例外を抽出し、プライマリ スレッドのコンテキストで例外をスローします。 場合、 *p*のパラメーター、`rethrow_exception`関数は、null `exception_ptr`、関数はスロー [std::bad_exception](../standard-library/bad-exception-class.md)します。

抽出された例外はプライマリ スレッドで現在の例外になり、他の例外と同様に扱うことができます。 例外をキャッチする場合は、すぐに処理またはを使用して、**スロー**より高いレベルの例外ハンドラーに送信するステートメント。 それ以外の場合は、何も実行されず、既定のシステム例外ハンドラーによってプロセスが終了されます。

## <a name="makeexceptionptr-function"></a>make_exception_ptr 関数

`make_exception_ptr` 関数は、クラスのインスタンスを引数として受け取り、そのインスタンスを参照する `exception_ptr` を返します。 通常は、[例外クラス](../standard-library/exception-class.md) オブジェクトを `make_exception_ptr` 関数への引数として指定しますが、任意のクラスのオブジェクトを引数に使用できます。

呼び出す、`make_exception_ptr`関数は内でキャッチ、C++ 例外をスローすることに相当、**キャッチ**ブロックしを呼び出す、`current_exception`を返す関数、`exception_ptr`例外を参照するオブジェクト。 `make_exception_ptr` 関数の Microsoft 実装は、例外のスローとキャッチよりも効果的です。

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

## <a name="requirements"></a>必要条件

**ヘッダー:** \<exception>

## <a name="see-also"></a>関連項目

[例外処理](../cpp/exception-handling-in-visual-cpp.md)<br/>
[/EH (例外処理モデル)](../build/reference/eh-exception-handling-model.md)<br/>
[/clr (共通言語ランタイムのコンパイル)](../build/reference/clr-common-language-runtime-compilation.md)