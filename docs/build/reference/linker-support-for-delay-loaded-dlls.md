---
description: 詳細については、「リンカーによる遅延読み込み Dll のサポート」を参照してください。
title: リンカーによる DLL の遅延読み込み
ms.date: 01/19/2021
helpviewer_keywords:
- delayed loading of DLLs, linker support
ms.openlocfilehash: 02991d6ac409ef301e326eea63ece8c5c7775010
ms.sourcegitcommit: c20734f18d3d49bb38b1628c68b53b54b3eeeb03
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2021
ms.locfileid: "99522418"
---
# <a name="linker-support-for-delay-loaded-dlls"></a>リンカーによる DLL の遅延読み込み

MSVC リンカーは、Dll の遅延読み込みをサポートしています。 この機能により、Windows SDK の関数を使用したり、DLL の遅延読み込みを実装したりする必要がなく [`LoadLibrary`](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryw) [`GetProcAddress`](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress) なります。

遅延読み込みを行わない場合、実行時に DLL を読み込む唯一の方法は、およびを使用することです。 `LoadLibrary` `GetProcAddress` オペレーティングシステムは、それを使用する実行可能ファイルまたは dll が読み込まれたときに dll を読み込みます。

遅延読み込みを使用すると、DLL を暗黙的にリンクするときに、プログラムがその DLL 内の関数を呼び出すまで DLL の読み込みを遅らせるオプションが提供されます。

アプリケーションでは、ヘルパー関数と共に[ `/DELAYLOAD` (遅延読み込みインポート)](delayload-delay-load-import.md)リンカーオプションを使用して DLL の読み込みを遅延させることができます。 (既定のヘルパー関数の実装は、Microsoft によって提供されます)。ヘルパー関数は、およびを呼び出すことによって、実行時に必要に応じて DLL を読み込み `LoadLibrary` `GetProcAddress` ます。

次の場合は、DLL の遅延読み込みを検討してください。

- プログラムが DLL 内の関数を呼び出さない可能性があります。

- DLL 内の関数は、プログラムの実行中に遅延するまで呼び出されないことがあります。

DLL の遅延読み込みは、EXE プロジェクトまたは DLL プロジェクトのビルド時に指定できます。 1つ以上の Dll 自体の読み込みを遅らせている DLL プロジェクトは、で遅延読み込みされたエントリポイントを呼び出すことは `DllMain` できません。

## <a name="specify-dlls-to-delay-load"></a><a name="specify-dlls-to-delay-load"></a> 遅延読み込みする Dll の指定

リンカーオプションを使用して、読み込みを遅延させる Dll を指定でき [`/delayload:`*`dllname`*](delayload-delay-load-import.md) ます。 独自のバージョンのヘルパー関数を使用する予定がない場合 *`delayimp.lib`* は、(デスクトップアプリケーションの場合) または (UWP アプリの場合) にプログラムをリンクする必要もあり *`dloadhelper.lib`* ます。

DLL の遅延読み込みの簡単な例を次に示します。

```cpp
// cl t.cpp user32.lib delayimp.lib  /link /DELAYLOAD:user32.dll
#include <windows.h>
// uncomment these lines to remove .libs from command line
// #pragma comment(lib, "delayimp")
// #pragma comment(lib, "user32")

int main() {
   // user32.dll will load at this point
   MessageBox(NULL, "Hello", "Hello", MB_OK);
}
```

DEBUG バージョンのプロジェクトをビルドします。 デバッガーを使用してコードをステップ実行すると、の *`user32.dll`* 呼び出しを行ったときにのみが読み込まれることがわかり `MessageBox` ます。

## <a name="explicitly-unload-a-delay-loaded-dll"></a><a name="explicitly-unload-a-delay-loaded-dll"></a> 遅延読み込みされた DLL の明示的なアンロード

[`/delay:unload`](delay-delay-load-import-settings.md)リンカーオプションを使用すると、遅延読み込みされた DLL をコードで明示的にアンロードできます。 既定では、遅延読み込みされたインポートは、インポートアドレステーブル (IAT) に残ります。 ただし、リンカーコマンドラインでを使用する場合、 **`/delay:unload`** ヘルパー関数は、呼び出しによる DLL の明示的なアンロードをサポート `__FUnloadDelayLoadedDLL2` し、IAT を元の形式にリセットします。 現在、無効なポインターが上書きされます。 IAT は、 [`ImgDelayDescr`](understanding-the-helper-function.md#calling-conventions-parameters-and-return-type) 元の iat のコピー (存在する場合) のアドレスを含む構造体のフィールドです。

### <a name="example-of-unloading-a-delay-loaded-dll"></a>遅延読み込みされた DLL のアンロードの例

次の例では、関数を含む DLL を明示的にアンロードする方法を示し *`MyDll.dll`* `fnMyDll` ます。

```C
// link with /link /DELAYLOAD:MyDLL.dll /DELAY:UNLOAD
#include <windows.h>
#include <delayimp.h>
#include "MyDll.h"
#include <stdio.h>

#pragma comment(lib, "delayimp")
#pragma comment(lib, "MyDll")
int main()
{
    BOOL TestReturn;
    // MyDLL.DLL will load at this point
    fnMyDll();

    //MyDLL.dll will unload at this point
    TestReturn = __FUnloadDelayLoadedDLL2("MyDll.dll");

    if (TestReturn)
        printf_s("\nDLL was unloaded");
    else
        printf_s("\nDLL was not unloaded");
}
```

遅延読み込みされた DLL のアンロードに関する重要な注意事項:

- 関数の実装は、ファイルの `__FUnloadDelayLoadedDLL2` *`delayhlp.cpp`* MSVC *`include`* ディレクトリにあります。 詳細については、「 [遅延読み込みヘルパー関数に](understanding-the-helper-function.md)ついて」を参照してください。

- *`name`* 関数のパラメーターは、 `__FUnloadDelayLoadedDLL2` インポートライブラリに含まれるものと完全に一致する必要があります (ケースを含む)。 (その文字列は、イメージのインポートテーブルにもあります)。インポートライブラリの内容は、を使用して表示でき [`DUMPBIN /DEPENDENTS`](dependents.md) ます。 大文字と小文字を区別せずに文字列を一致させる場合は、を更新して、大文字と小文字を区別しない `__FUnloadDelayLoadedDLL2` CRT 文字列関数または WINDOWS API 呼び出しのいずれかを使用できます。

## <a name="bind-delay-loaded-imports"></a><a name="bind-delay-loaded-imports"></a> 遅延読み込みされたインポートのバインド

既定のリンカー動作では、遅延読み込みされた DLL に対して、バインド可能なインポートアドレステーブル (IAT) が作成されます。 DLL がバインドされている場合、ヘルパー関数は、参照される各インポートでを呼び出すのではなく、バインドされた情報を使用しようとし `GetProcAddress` ます。 タイムスタンプまたは優先アドレスが、読み込まれている DLL 内のアドレスと一致しない場合、ヘルパー関数はバインドされたインポートアドレステーブルが古くなっているものと見なします。 この処理は、IAT が存在しない場合と同様に行われます。

DLL の遅延読み込みされたインポートをバインドしない場合は、 [`/delay:nobind`](delay-delay-load-import-settings.md) リンカーのコマンドラインでを指定します。 リンカーは、バインドされたインポートアドレステーブルを生成しません。これにより、イメージファイルの領域が節約されます。

## <a name="load-all-imports-for-a-delay-loaded-dll"></a><a name="load-all-imports-for-a-delay-loaded-dll"></a> 遅延読み込みされた DLL のすべてのインポートを読み込みます

で定義されている関数は、 `__HrLoadAllImportsForDll` *`delayhlp.cpp`* リンカーオプションで指定された DLL からすべてのインポートを読み込むようにリンカーに指示 [`/delayload`](delayload-delay-load-import.md) します。

すべてのインポートを一度に読み込むと、エラー処理を1か所に一元化できます。 インポートに対する実際のすべての呼び出しについて、構造化例外処理を回避できます。 また、プロセスによってアプリケーションが失敗する状況を回避します。たとえば、ヘルパーコードがインポートの読み込みに失敗した場合、他のユーザーの読み込みが成功した場合などです。

を呼び出す `__HrLoadAllImportsForDll` と、フックとエラー処理の動作は変更されません。 詳細については、「 [エラー処理と通知](error-handling-and-notification.md)」を参照してください。

`__HrLoadAllImportsForDll` DLL 自体に格納されている名前と大文字と小文字を区別する比較を行います。

という関数でを使用して `__HrLoadAllImportsForDll` `TryDelayLoadAllImports` 、名前付き DLL の読み込みを試みる例を次に示します。 関数を使用して、 `CheckDelayException` 例外の動作を決定します。

```C
int CheckDelayException(int exception_value)
{
    if (exception_value == VcppException(ERROR_SEVERITY_ERROR, ERROR_MOD_NOT_FOUND) ||
        exception_value == VcppException(ERROR_SEVERITY_ERROR, ERROR_PROC_NOT_FOUND))
    {
        // This example just executes the handler.
        return EXCEPTION_EXECUTE_HANDLER;
    }
    // Don't attempt to handle other errors
    return EXCEPTION_CONTINUE_SEARCH;
}

bool TryDelayLoadAllImports(LPCSTR szDll)
{
    __try
    {
        HRESULT hr = __HrLoadAllImportsForDll(szDll);
        if (FAILED(hr))
        {
            // printf_s("Failed to delay load functions from %s\n", szDll);
            return false;
        }
    }
    __except (CheckDelayException(GetExceptionCode()))
    {
        // printf_s("Delay load exception for %s\n", szDll);
        return false;
    }
    // printf_s("Delay load completed for %s\n", szDll);
    return true;
}
```

の結果を使用して、 `TryDelayLoadAllImports` インポート関数を呼び出すかどうかを制御できます。

## <a name="error-handling-and-notification"></a>エラー処理と通知

プログラムが遅延読み込みされた Dll を使用する場合は、エラーを確実に処理する必要があります。 プログラムの実行中にエラーが発生すると、ハンドルされない例外が発生します。 DLL 遅延読み込みエラー処理と通知の詳細については、「 [エラー処理と通知](error-handling-and-notification.md)」を参照してください。

## <a name="dump-delay-loaded-imports"></a><a name="dump-delay-loaded-imports"></a> 遅延読み込みされたインポートのダンプ

遅延読み込みされたインポートは、を使用してダンプでき [`DUMPBIN /IMPORTS`](imports-dumpbin.md) ます。 これらのインポートは、標準のインポートとは少し異なる情報で表示されます。 これらは、リストの独自のセクションに分離 `/imports` され、遅延読み込みのインポートとして明示的にラベル付けされます。 イメージにアンロード情報が含まれている場合は、そのことに注意してください。 バインド情報が存在する場合は、インポートのバインドされたアドレスと共に、ターゲット DLL の時刻と日付のスタンプが示されます。

## <a name="constraints-on-delay-load-dlls"></a><a name="constraints-on-delay-load-dlls"></a> 遅延読み込みの Dll に関する制約

DLL インポートの遅延読み込みには、いくつかの制約があります。

- データのインポートはサポートされていません。 回避策として、 `LoadLibrary` (または [`GetModuleHandle`](/windows/win32/api/libloaderapi/nf-libloaderapi-getmodulehandlew) 遅延読み込みヘルパーが DLL を読み込んだことを確認した後にを使用して) およびを使用して、データのインポートを明示的に処理し `GetProcAddress` ます。

- 遅延読み込みは *`Kernel32.dll`* サポートされていません。 遅延読み込みヘルパールーチンを機能させるには、この DLL を読み込む必要があります。

- 転送されたエントリポイントの[バインド](#bind-delay-loaded-imports)はサポートされていません。

- 起動時に読み込まれるのではなく、DLL が遅延読み込みされた場合、プロセスの動作が異なることがあります。 これは、遅延読み込み DLL のエントリポイントで発生するプロセスごとの初期化がある場合に表示されます。 その他のケースには、を使用して宣言された静的 TLS (スレッドローカルストレージ) があり [`__declspec(thread)`](../../cpp/thread.md) ます。これは、を介して DLL が読み込まれるときに処理されません `LoadLibrary` 。 動的 TLS は、、、、およびを使用して、 [`TlsAlloc`](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsalloc) [`TlsFree`](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsfree) [`TlsGetValue`](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsgetvalue) [`TlsSetValue`](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlssetvalue) 静的な dll または遅延読み込みされた dll で引き続き使用できます。

- 各関数の最初の呼び出しの後に、インポートされた関数への静的グローバル関数ポインターを再初期化します。 これが必要なのは、関数ポインターの最初の使用は、読み込まれた関数ではなくサンクを指しているためです。

- 現時点では、通常のインポートメカニズムを使用しているときに、DLL から特定のプロシージャのみの読み込みを遅延する方法はありません。

- カスタム呼び出し規則 (x86 アーキテクチャでの条件コードの使用など) はサポートされていません。 また、浮動小数点レジスタはどのプラットフォームにも保存されません。 カスタムヘルパールーチンまたはフックルーチンが浮動小数点型を使用する場合に注意してください。ルーチンは、浮動小数点パラメーターでレジスタ呼び出し規約を使用するコンピューターに、完全な浮動小数点の状態を保存および復元する必要があります。 特に、help 関数の数値データプロセッサ (NDP) スタックで浮動小数点パラメーターを受け取る CRT 関数を呼び出す場合は、CRT DLL の遅延読み込みに注意してください。

## <a name="understand-the-delay-load-helper-function"></a>遅延読み込みヘルパー関数について

リンカーでサポートされる遅延読み込みのヘルパー関数は、実行時に実際に DLL を読み込むものです。 ヘルパー関数を変更して、その動作をカスタマイズできます。 で指定されたヘルパー関数を使用する代わりに *`delayimp.lib`* 、独自の関数を記述し、プログラムにリンクします。 1つのヘルパー関数は、遅延読み込みされたすべての Dll に対して機能します。 詳細については、「 [遅延読み込みヘルパー関数に](understanding-the-helper-function.md) ついて」および「 [独自のヘルパー関数の開発](understanding-the-helper-function.md#develop-your-own-helper-function)」を参照してください。

## <a name="see-also"></a>関連項目

[Visual Studio での C/C++ Dll の作成](../dlls-in-visual-cpp.md)<br/>
[MSVC リンカーのリファレンス](linking.md)
