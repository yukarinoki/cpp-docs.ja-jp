---
title: スレッド間の例外転送 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 61847500e9e4fbcfc0912e51afe599ed31601ec2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="transporting-exceptions-between-threads"></a>スレッド間の例外転送
Visual C がサポート*例外の転送*を別の 1 つのスレッドからです。 例外の転送により、1 つのスレッドで例外をキャッチし、その例外が別のスレッドにスローされたように見せることができます。 たとえば、この機能を使用して、プライマリ スレッドでそのセカンダリ スレッドによってスローされたすべての例外を処理するマルチスレッド アプリケーションを作成できます。 例外の転送は、主に並列プログラミング ライブラリまたはシステムを作成する開発者にとって便利です。 Visual C では、例外の転送を実装する、 [exception_ptr](../standard-library/exception-typedefs.md#exception_ptr)型および[current_exception](../standard-library/exception-functions.md#current_exception)、 [rethrow_exception](../standard-library/exception-functions.md#rethrow_exception)、および[make_exception_ptr](../standard-library/exception-functions.md#make_exception_ptr)関数。  
  
## <a name="syntax"></a>構文  
  
```  
namespace std   
{  
   typedef unspecified exception_ptr;   
   exception_ptr current_exception();  
   void rethrow_exception(exception_ptr p);  
   template<class E>   
       exception_ptr make_exception_ptr(E e) noexcept;  
}  
```  
  
#### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`unspecified`|`exception_ptr` 型を実装するために使用される未指定の内部クラス。|  
|`p`|例外を参照する `exception_ptr` オブジェクト。|  
|`E`|例外を表すクラス。|  
|`e`|パラメーター `E` クラスのインスタンス。|  
  
## <a name="return-value"></a>戻り値  
 `current_exception` 関数は、現在進行中の例外を参照する `exception_ptr` オブジェクトを返します。 処理中の例外がない場合、関数は、例外に関連付けられていない `exception_ptr` オブジェクトを返します。  
  
 `make_exception_ptr` 関数は、`exception_ptr` パラメーターで指定された例外を参照する `e` オブジェクトを返します。  
  
## <a name="remarks"></a>コメント  
  
## <a name="scenario"></a>シナリオ  
 可変作業量を処理するようにスケーリングするアプリケーションを作成する場合を想定します。 この目的を達成するために、初期プライマリ スレッドがジョブの実行に必要な数のセカンダリ スレッドを作成するマルチスレッド アプリケーションを設計します。 セカンダリ スレッドは、リソースの管理、負荷の分散、スループットの向上などの点でプライマリ スレッドを補助します。 作業の分散によって、マルチスレッド アプリケーションは、シングル スレッド アプリケーションよりもパフォーマンスが向上します。  
  
 ただし、セカンダリ スレッドが例外をスローした場合、プライマリ スレッドがその例外を処理するようにします。 これは、セカンダリ スレッドの数に関係なく、アプリケーションが例外を一貫した統一された方法で処理するようにしたいためです。  
  
## <a name="solution"></a>ソリューション  
 上記のシナリオを処理するために、C++ 標準はスレッド間での例外の転送をサポートしています。 セカンダリ スレッドは、例外をスローする場合、その例外は次のようになります。、*現在の例外*です。 現実の世界にたとえて、現在の例外と呼ばれます*インフライト*です。 現在の例外は、スローされた時点から、それをキャッチする例外ハンドラーによって返されるまでが処理中です。  
  
 セカンダリ スレッドは、`catch` ブロックで現在の例外をキャッチし、`current_exception` オブジェクトに例外を保存するために `exception_ptr` 関数を呼び出します。 `exception_ptr` オブジェクトはセカンダリ スレッドとプライマリ スレッドで使用できる必要があります。 たとえば、`exception_ptr` オブジェクトは、アクセスがミューテックスによって制御されるグローバル変数にすることができます。 用語*例外を転送*1 つのスレッドで例外は、別のスレッドがアクセスできる形式に変換できることを意味します。  
  
 次に、プライマリ スレッドが `rethrow_exception` 関数を呼び出します。これは、`exception_ptr` オブジェクトから例外を抽出してスローします。 例外がスローされると、プライマリ スレッドで現在の例外になります。 つまり、例外はプライマリ スレッドで発生したように見えます。  
  
 最後に、プライマリ スレッドは `catch` ブロックの現在の例外をキャッチし、その例外を処理するか、高レベルの例外ハンドラーにスローできます。 また、プライマリ スレッドは例外を無視し、プロセスが終了することを許可できます。  
  
 ほとんどのアプリケーションは、スレッド間で例外を転送する必要はありません。 ただし、システムでセカンダリ スレッド、プロセッサ、またはコア間に作業を分割できるため、並列計算のシステムにこの機能を使うと便利です。 並列コンピューティング環境では、単一の専用スレッドがセカンダリ スレッドからのすべての例外を処理し、すべてのアプリケーションに一貫した例外処理モデルを提供できます。  
  
 C++ 標準委員会の提案の詳細については、「Language Support for Transporting Exceptions between Threads (スレッド間の例外を転送するための言語のサポート)」というタイトルのドキュメント番号 N2179 をインターネットで検索してください。  
  
## <a name="exception-handling-models-and-compiler-options"></a>例外処理モデルとコンパイラ オプション  
 アプリケーションの例外処理モデルは、例外をキャッチして転送できるかどうかを判断します。 Visual C++ は、C++ 例外、構造化例外処理 (SEH) 例外、共通言語ランタイム (CLR) 例外を処理できる 3 種類のモデルをサポートします。 使用して、 [/EH](../build/reference/eh-exception-handling-model.md)と[/clr](../build/reference/clr-common-language-runtime-compilation.md)コンパイラ オプションをアプリケーションの例外処理モデルを指定します。  
  
 例外を転送できるのは、コンパイラ オプションとプログラミング ステートメントの次の組み合わせだけです。 他の組み合わせでは、例外をキャッチできないか、例外をキャッチできても転送できません。  
  
-   **/EHa**コンパイラ オプションおよび`catch`ステートメントは、SEH と C++ の例外を転送できます。  
  
-   **/EHa**、 **/EHs**、および **/EHsc**コンパイラ オプションおよび`catch`ステートメントは、C++ 例外を転送できます。  
  
-   **/CLR**または **/CLR: 純粋な**コンパイラ オプションおよび`catch`ステートメントは、C++ 例外を転送できます。 **/CLR**コンパイラ オプションではの仕様、 **/EHa**オプション。 コンパイラがマネージ例外の転送をサポートしないことに注意してください。 これは、マネージ例外から派生するため、 [System.Exception クラス](../standard-library/exception-class.md)は既に、共通言語ランタイムの機能を使用してスレッド間で移動できるオブジェクト。  
  
    > [!IMPORTANT]
    >  指定することをお勧め、 **/EHsc**コンパイラ オプションとのみの C++ 例外をキャッチします。 公開する自分でセキュリティの脅威を使用する場合、 **/EHa**または **/CLR**コンパイラ オプションおよび**キャッチ**省略記号を含むステートメント*例外宣言*(`catch(...)`)。 `catch` ステートメントを使用して、いくつかの特定の例外をキャプチャしようとする場合があるかもしれません。 しかし、`catch(...)` ステートメントは、致命的な例外を含むすべての C++ 例外と SEH 例外をキャプチャします。 予期しない例外を無視するか、誤って操作すると、悪意あるコードが、プログラムのセキュリティを侵す機会が生じます。  
  
## <a name="usage"></a>使用法  
 次のセクションを使用して例外を転送する方法について説明、`exception_ptr`型、および`current_exception`、 `rethrow_exception`、および`make_exception_ptr`関数。  
  
### <a name="exceptionptr-type"></a>exception_ptr 型  
 現在の例外またはユーザーが指定した例外のインスタンスを参照するには、`exception_ptr` オブジェクトを使用します。 Microsoft の実装では、例外は [EXCEPTION_RECORD](http://msdn.microsoft.com/library/windows/desktop/aa363082) 構造体によって表されます。 各 `exception_ptr` オブジェクトには、例外を表す `EXCEPTION_RECORD` 構造体のコピーを指す例外参照フィールドが含まれています。  
  
 `exception_ptr` 変数を宣言する場合、変数は例外に関連付けられません。 つまり、例外参照フィールドが NULL です。 このような `exception_ptr` オブジェクトは、*null exception_ptr* と呼ばれます。  
  
 例外を `current_exception` オブジェクトに割り当てるには、`make_exception_ptr` または `exception_ptr` 関数を使用します。 `exception_ptr` 変数に例外を割り当てた場合、変数の例外参照フィールドは例外のコピーを指します。 例外をコピーするためのメモリが不足している場合、例外参照フィールドは、[std::bad_alloc](../standard-library/bad-alloc-class.md) 例外のコピーを指し示します。 場合、`current_exception`または`make_exception_ptr`関数は何らかの理由、関数の呼び出しは、例外をコピーすることはできません、[終了](../c-runtime-library/reference/terminate-crt.md)を現在のプロセスを終了する関数。  
  
 名前とは異なり、`exception_ptr` オブジェクト自体はポインターではありません。 ポインターのセマンティクスに従わず、ポインターのメンバー アクセス (`->`) 演算子または間接 (*) 演算子で使用することはできません。 `exception_ptr` オブジェクトには、パブリック データ メンバーまたはメンバー関数がありません。  
  
 **比較:**  
  
 等値演算子 (`==`) と不等値演算子 (`!=`) を使用して、2 種類の `exception_ptr` オブジェクトを比較できます。 演算子は、例外を表す `EXCEPTION_RECORD` 構造体のバイナリ値 (ビット パターン) は比較しません。 代わりに、演算子は `exception_ptr` オブジェクトの例外参照フィールドのアドレスを比較します。 その結果、null `exception_ptr` と NULL 値を比較すると、等しいと評価されます。  
  
### <a name="currentexception-function"></a>current_exception 関数  
 `current_exception` ブロックで `catch` 関数を呼び出します。 例外が処理中で `catch` ブロックで例外をキャッチできる場合、`current_exception` 関数は、例外を参照する `exception_ptr` オブジェクトを返します。 それ以外の場合、関数は null `exception_ptr` オブジェクトを返します。  
  
 **詳細:**  
  
 `current_exception` 関数は、`catch` ステートメントが[例外宣言](../cpp/try-throw-and-catch-statements-cpp.md)ステートメントを指定しているかどうかに関係なく、処理中の例外をキャプチャします。  
  
 現在の例外のデストラクターは、例外を再スローしない場合、`catch` ブロックの最後に呼び出されます。 ただし、デストラクターで `current_exception` 関数を呼び出しても、その関数は現在の例外を参照する `exception_ptr` オブジェクトを返します。  
  
 `current_exception` 関数を連続して呼び出すと、現在の例外のさまざまなコピーを参照する `exception_ptr` オブジェクトが返されます。 その結果、オブジェクトは、異なるコピーを参照しているため、コピーが同じバイナリ値を持っている場合でも、比較においては等しくないと評価されます。  
  
 **SEH 例外:**  
  
 使用する場合、 **/EHa**コンパイラ オプションは、SEH 例外をキャッチするには、C++ では`catch`ブロックします。 `current_exception` 関数は、SEH 例外を参照する `exception_ptr` オブジェクトを返します。 および`rethrow_exception`thetransported を呼び出す場合、関数が、SEH 例外をスロー`exception_ptr`オブジェクトを引数として。  
  
 `current_exception` 関数は、SEH `exception_ptr` 終了ハンドラー、`__finally` 例外ハンドラー、または `__except` のフィルター式内で呼び出されると、null `__except` を返します。  
  
 転送された例外は、入れ子になった例外をサポートしません。 入れ子になった例外は、例外の処理中に別の例外がスローされると発生します。 入れ子になった例外をキャッチする場合、`EXCEPTION_RECORD.ExceptionRecord` データ メンバーは、関連の例外を記述する `EXCEPTION_RECORD` 構造体のチェーンを指し示します。 `current_exception` 関数は、`exception_ptr` データ メンバーがゼロ設定された `ExceptionRecord` オブジェクトを返すため、入れ子になった例外をサポートしていません。  
  
 SEH 例外をキャッチする場合、`EXCEPTION_RECORD.ExceptionInformation` データ メンバー配列のポインターで参照されるメモリを管理する必要があります。 対応する `exception_ptr` オブジェクトの有効期間中はメモリが有効であること、および `exception_ptr` オブジェクトが削除されるときにメモリが解放されることを保証する必要があります。  
  
 転送例外の機能と共に構造化例外 (SE) 変換関数を使用できます。 SEH 例外が C++ 例外に変換される場合、`current_exception` 関数は、元の SEH 例外ではなく変換された例外を参照する `exception_ptr` を返します。 `rethrow_exception` 関数は、その後、元の例外ではなく変換された例外をスローします。 SE 変換関数の詳細については、次を参照してください。 [_set_se_translator](../c-runtime-library/reference/set-se-translator.md)です。  
  
### <a name="rethrowexception-function"></a>rethrow_exception 関数  
 キャッチした例外を `exception_ptr` オブジェクトに保存すると、プライマリ スレッドはオブジェクトを処理できます。 プライマリ スレッドで、引数として `rethrow_exception` オブジェクトを指定して `exception_ptr` 関数を呼び出します。 `rethrow_exception` 関数は `exception_ptr` オブジェクトから例外を抽出し、プライマリ スレッドのコンテキストで例外をスローします。 場合、`p`のパラメーター、`rethrow_exception`関数は、null `exception_ptr`、関数のスロー [std::bad_exception](../standard-library/bad-exception-class.md)です。  
  
 抽出された例外はプライマリ スレッドで現在の例外になり、他の例外と同様に扱うことができます。 例外をキャッチした場合は、その例外をすぐに処理するか、`throw` ステートメントを使用してさらに高いレベルの例外ハンドラーに送信できます。 それ以外の場合は、何も実行されず、既定のシステム例外ハンドラーによってプロセスが終了されます。  
  
### <a name="makeexceptionptr-function"></a>make_exception_ptr 関数  
 `make_exception_ptr` 関数は、クラスのインスタンスを引数として受け取り、そのインスタンスを参照する `exception_ptr` を返します。 通常は、[例外クラス](../standard-library/exception-class.md) オブジェクトを `make_exception_ptr` 関数への引数として指定しますが、任意のクラスのオブジェクトを引数に使用できます。  
  
 `make_exception_ptr` 関数を呼び出すことは、C++ 例外をスローして、`catch` ブロック内でキャッチすることと同じであり、`current_exception` 関数を呼び出すことは、例外を参照する `exception_ptr` オブジェクトを返すことと同じです。 `make_exception_ptr` 関数の Microsoft 実装は、例外のスローとキャッチよりも効果的です。  
  
 通常、アプリケーションは `make_exception_ptr` 関数を必要とせず、使用は推奨されていません。  
  
## <a name="example"></a>例  
 次の例は、標準 C++ 例外とカスタム C++ 例外をあるスレッドから別のスレッドに転送します。  
  
```  
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
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<exception>  
  
## <a name="see-also"></a>関連項目  
 [例外処理](../cpp/exception-handling-in-visual-cpp.md)     
 [/EH (例外処理モデル)](../build/reference/eh-exception-handling-model.md)   
 [/clr (共通言語ランタイムのコンパイル)](../build/reference/clr-common-language-runtime-compilation.md)