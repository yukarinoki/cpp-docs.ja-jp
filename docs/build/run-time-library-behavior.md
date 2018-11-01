---
title: Dll と Visual C ランタイム ライブラリの動作
ms.date: 11/04/2016
f1_keywords:
- _DllMainCRTStartup
- CRT_INIT
helpviewer_keywords:
- DLLs [C++], entry point function
- process detach [C++]
- process attach [C++]
- DLLs [C++], run-time library behavior
- DllMain function
- _CRT_INIT macro
- _DllMainCRTStartup method
- run-time [C++], DLL startup sequence
- DLLs [C++], startup sequence
ms.assetid: e06f24ab-6ca5-44ef-9857-aed0c6f049f2
ms.openlocfilehash: 8293e2e05193b34802aba0af722dd06155fdcd81
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50429056"
---
# <a name="dlls-and-visual-c-run-time-library-behavior"></a>Dll と Visual C ランタイム ライブラリの動作

既定では、Visual C を使用してダイナミック リンク ライブラリ (DLL) をビルドすると、リンカーには、Visual C ランタイム ライブラリ (VCRuntime) が含まれています。 VCRuntime には、初期化および C と C++ 実行可能ファイルを終了するに必要なコードが含まれています。 VCRuntime コードが呼び出される内部の DLL エントリ ポイント関数を提供する DLL にリンクされている、`_DllMainCRTStartup`アタッチまたはデタッチ プロセスまたはスレッドを DLL への Windows OS メッセージを処理します。 `_DllMainCRTStartup`関数がスタック バッファーのセキュリティを設定する、C ランタイム ライブラリ (CRT) の初期化と終了などの必須のタスクを実行し、静的とグローバル オブジェクトのコンス トラクターとデストラクターを呼び出します。 `_DllMainCRTStartup` 呼び出しは、独自の初期化と終了を実行するには、WinRT、MFC、および ATL などの他のライブラリの関数をフックします。 この初期化、CRT とその他のライブラリだけでなく、静的変数、なしのままになりますが初期化されていない状態です。 静的にリンクされた CRT または CRT DLL を動的にリンクされた DLL を使用しているかどうか、同じ VCRuntime の内部初期化および終了ルーチンが呼び出されます。

## <a name="default-dll-entry-point-dllmaincrtstartup"></a>既定の DLL エントリ ポイント _DllMainCRTStartup

すべての Dll、Windows で通常は、省略可能なエントリ ポイント関数を含めることができます`DllMain`は初期化と終了の両方に対して呼び出されます。 これによって、追加のリソースを必要に応じて、割り当て/解放する機会が与えられます。 Windows には、エントリ ポイント関数が呼び出される 4 つの状況 (プロセスのアタッチ、プロセス デタッチ、スレッド アタッチ、スレッド デタッチ) があります。 使用するアプリケーションが読み込まれるときに、またはアプリケーションが実行時に DLL を要求したときに、プロセスのアドレス空間に DLL が読み込まれると、オペレーティング システムは、DLL のデータの個別のコピーを作成します。 これは呼び出されます*プロセスのアタッチ*します。 *スレッドのアタッチ*で DLL を読み込むプロセスは、新しいスレッドを作成するときに発生します。 *スレッドのデタッチ*スレッドが終了するときに発生し、*プロセスのデタッチ*は、DLL は必要なくなりましたが、アプリケーションがリリースされる場合。 各イベントは、渡すのオペレーティング システムが DLL エントリ ポイントを個別に呼び出して、*理由*イベントの種類ごとの引数。 たとえば、OS が送信`DLL_PROCESS_ATTACH`として、*理由*プロセスの通知への引数のアタッチします。

VCRuntime ライブラリには、呼び出されるエントリ ポイント関数が用意されています`_DllMainCRTStartup`既定の初期化と終了操作を処理します。 プロセスにアタッチ、`_DllMainCRTStartup`関数バッファー セキュリティ チェックを設定、CRT とその他のライブラリを初期化します、実行時の型情報を初期化しますを初期化し、静的および非ローカルのデータのコンス トラクターを呼び出す、スレッド ローカル ストレージを初期化します、、各接続の内部の静的なカウンターをインクリメントし、ユーザーまたはライブラリの指定を呼び出して`DllMain`します。 プロセスのデタッチ、関数は逆の順序でこれらの手順を実行します。 呼び出す`DllMain`デクリメント内部のカウンターにデストラクターを呼び出して、CRT の呼び出しの終了関数、および登録されている`atexit`関数、およびその他のライブラリの終了を通知します。 添付ファイルのカウンターがゼロに時を返します`FALSE`を Windows に DLL がアンロードできることを示します。 `_DllMainCRTStartup`スレッドで呼び出されますもアタッチし、スレッドをデタッチします。 このような場合は、VCRuntime コードが追加の初期化や終了、単独ではありませんし、呼び出すだけです`DllMain`に沿ってメッセージを渡す。 場合`DllMain`返します`FALSE`プロセスからアタッチ、障害の通知`_DllMainCRTStartup`呼び出し`DllMain`もう一度渡します`DLL_PROCESS_DETACH`として、*理由*引数は、その後の残りが、終了プロセス。

既定のエントリ ポイントの Visual C の Dll を作成するときに`_DllMainCRTStartup`によって提供される VCRuntime が自動的にリンクされています。 使用して DLL のエントリ ポイント関数を指定する必要はありません、 [/ENTRY (エントリ ポイント シンボル)](../build/reference/entry-entry-point-symbol.md)リンカー オプション。

> [!NOTE]
> Dll の場合、/ENTRY を使用して別のエントリ ポイント関数を指定することは可能です: リンカー オプション、お勧めしませんが、エントリ ポイント関数がすべてのものを複製する必要がありますのでを`_DllMainCRTStartup`は、同じ順序で。 VCRuntime は、その動作を複製するための機能を提供します。 たとえば、呼び出すことができます[_ _security_init_cookie](../c-runtime-library/reference/security-init-cookie.md)すぐにプロセスをサポートするアタッチ、 [/GS (バッファー セキュリティ チェック)](../build/reference/gs-buffer-security-check.md)オプションをオンにするバッファー。 呼び出すことができます、`_CRT_INIT`関数、エントリ ポイント関数の DLL の初期化や終了処理関数の残りの部分を実行すると、同じパラメーターを渡します。

<a name="initializing-a-dll"></a>

## <a name="initialize-a-dll"></a>DLL の初期化

DLL、DLL の読み込み時に実行する必要があります初期化コードがあります。 独自 DLL の初期化と終了関数を実行するための順序で`_DllMainCRTStartup`という名前の関数を呼び出す`DllMain`を行うことができます。 `DllMain` DLL エントリ ポイントに必要な署名が必要です。 既定のエントリ ポイント関数`_DllMainCRTStartup`呼び出し`DllMain`Windows に渡し、同じパラメーターを使用します。 指定しない場合、既定で、`DllMain`関数の場合、Visual C に付属およびリンクでように`_DllMainCRTStartup`を呼び出すものは常に持ちます。 これは、DLL を初期化する必要がない場合は、DLL のビルド時に影響を行う必要がある特別なものを意味します。

これは、使用される署名`DllMain`:

```cpp
#include <windows.h>

extern "C" BOOL WINAPI DllMain (
    HINSTANCE const instance,  // handle to DLL module
    DWORD     const reason,    // reason for calling function
    LPVOID    const reserved); // reserved
```

いくつかのライブラリをラップ、`DllMain`する関数。 たとえば、レギュラー MFC DLL では、実装、`CWinApp`オブジェクトの`InitInstance`と`ExitInstance`の初期化と終了が必要な DLL を実行するメンバー関数。 詳細については、次を参照してください。、[レギュラー MFC Dll の初期化](#initializing-regular-dlls)セクション。

> [!WARNING]
> 安全に行える、DLL エントリ ポイントには、重要な制限があります。 参照してください[一般的なベスト プラクティス](/windows/desktop/Dlls/dynamic-link-library-best-practices)で呼び出しても安全ではない特定の Windows Api の`DllMain`します。 必要がある場合、最も簡単な初期化はで初期化関数、DLL の。 後の初期化関数を呼び出すアプリケーションを要求できます`DllMain`が実行し、前に、関数を呼び出す他の DLL にします。

<a name="initializing-non-mfc-dlls"></a>

### <a name="initialize-ordinary-non-mfc-dlls"></a>(MFC ではない) 通常の Dll を初期化します。

VCRuntime 指定を使用する (MFC ではない) 通常の Dll で、独自の初期化を実行する`_DllMainCRTStartup`、エントリ ポイント DLL ソース コードが呼び出される関数を含める必要があります`DllMain`します。 次のコードの表示の定義を示す基本的なスケルトン`DllMain`ようになります。

```cpp
#include <windows.h>

extern "C" BOOL WINAPI DllMain (
    HINSTANCE const instance,  // handle to DLL module
    DWORD     const reason,    // reason for calling function
    LPVOID    const reserved)  // reserved
{
    // Perform actions based on the reason for calling.
    switch (reason)
    {
    case DLL_PROCESS_ATTACH:
        // Initialize once for each new process.
        // Return FALSE to fail DLL load.
        break;

    case DLL_THREAD_ATTACH:
        // Do thread-specific initialization.
        break;

    case DLL_THREAD_DETACH:
        // Do thread-specific cleanup.
        break;

    case DLL_PROCESS_DETACH:
        // Perform any necessary cleanup.
        break;
    }
    return TRUE;  // Successful DLL_PROCESS_ATTACH.
}
```

> [!NOTE]
> 以前の Windows SDK ドキュメントでは、リンカーの/ENTRY オプションを使用してコマンドラインで DLL のエントリ ポイント関数の実際の名前を指定する必要がありますされることを述べています。 Visual c には、エントリ ポイント関数の名前がある場合は、/ENTRY オプションを使用する必要はありません`DllMain`します。 実際には、名前と/ENTRY オプションを使用する場合、エントリ ポイント関数もの以外の`DllMain`、CRT は適切に初期化されません、エントリ ポイント関数が、同じ初期化呼び出しを行わない限り、`_DllMainCRTStartup`なります。

<a name="initializing-regular-dlls"></a>

### <a name="initialize-regular-mfc-dlls"></a>レギュラー MFC Dll を初期化します。

レギュラー MFC Dll があるため、`CWinApp`オブジェクト、MFC アプリケーションと同じ場所での初期化と終了タスクを実行する必要があります: で、`InitInstance`と`ExitInstance`の DLL のメンバー関数`CWinApp`の派生クラス。 MFC に用意されているため、`DllMain`関数によって呼び出される`_DllMainCRTStartup`の`DLL_PROCESS_ATTACH`と`DLL_PROCESS_DETACH`、独自に記述する必要がありますいない`DllMain`関数。 MFC の`DllMain`関数呼び出し`InitInstance`ときに、DLL が読み込まれ、呼び出し`ExitInstance`DLL が読み込まれる前にします。

レギュラー MFC DLL を監視できる複数のスレッドを呼び出して[TlsAlloc](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-tlsalloc)と[TlsGetValue](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-tlsgetvalue)でその`InitInstance`関数。 これらの関数は、スレッド固有のデータを追跡するために、DLL を許可します。

動的にリンクする MFC、または使用する、MFC OLE、MFC データベース (DAO)、または MFC ソケットをサポート、それぞれ、デバッグ MFC 拡張 Dll MFCO、レギュラー MFC DLL で*バージョン*D.dll、MFCD*バージョン*D.dll、および MFCN*バージョン*D.dll (場所*バージョン*バージョン番号です) で自動的にリンクされます。 各レギュラー MFC DLL に使用してこれらの Dll の次の定義済みの初期化関数の 1 つを呼び出す必要があります`CWinApp::InitInstance`します。

|MFC のサポートの種類|初期化関数を呼び出す|
|-------------------------|-------------------------------------|
|MFC OLE (MFCO*バージョン*D.dll)|`AfxOleInitModule`|
|MFC データベース (MFCD*バージョン*D.dll)|`AfxDbInitModule`|
|MFC ソケット (MFCN*バージョン*D.dll)|`AfxNetInitModule`|

<a name="initializing-extension-dlls"></a>

### <a name="initialize-mfc-extension-dlls"></a>MFC 拡張 Dll を初期化します。

MFC 拡張 Dll があるないため、`CWinApp`の派生オブジェクト (レギュラー MFC Dll の操作)、初期化と終了のコードを追加する必要があります、 `DllMain` MFC DLL ウィザードによって生成される関数。

ウィザードでは、MFC 拡張 Dll の次のコードを提供します。 コードでは、`PROJNAME`プロジェクトの名前のプレース ホルダーです。

```cpp
#include "stdafx.h"
#include <afxdllx.h>

#ifdef _DEBUG
#define new DEBUG_NEW
#undef THIS_FILE
static char THIS_FILE[] = __FILE__;
#endif
static AFX_EXTENSION_MODULE PROJNAMEDLL = { NULL, NULL };

extern "C" int APIENTRY
DllMain(HINSTANCE hInstance, DWORD dwReason, LPVOID lpReserved)
{
   if (dwReason == DLL_PROCESS_ATTACH)
   {
      TRACE0("PROJNAME.DLL Initializing!\n");

      // MFC extension DLL one-time initialization
      AfxInitExtensionModule(PROJNAMEDLL,
                                 hInstance);

      // Insert this DLL into the resource chain
      new CDynLinkLibrary(Dll3DLL);
   }
   else if (dwReason == DLL_PROCESS_DETACH)
   {
      TRACE0("PROJNAME.DLL Terminating!\n");
   }
   return 1;   // ok
}
```

新しいを作成する`CDynLinkLibrary`オブジェクトの初期化中には、MFC 拡張 DLL のエクスポートを`CRuntimeClass`オブジェクトまたはクライアント アプリケーションにリソース。

MFC 拡張 DLL から 1 つまたは複数のレギュラー MFC Dll を使用する場合は、作成の初期化関数をエクスポートする必要があります、`CDynLinkLibrary`オブジェクト。 MFC 拡張 DLL を使用する標準の MFC Dll のそれぞれから、その関数を呼び出す必要があります。 初期化関数の呼び出しを適切な場所は、`InitInstance`メンバー関数は、レギュラー MFC DLL の`CWinApp`-MFC 拡張 DLL のエクスポートされたクラスまたは関数のいずれかを使用する前に派生オブジェクト。

`DllMain`を MFC DLL ウィザードで生成されたへの呼び出し`AfxInitExtensionModule`モジュールの実行時のクラスをキャプチャする (`CRuntimeClass`構造) とそのオブジェクトのファクトリ (`COleObjectFactory`オブジェクト) のときに使用、`CDynLinkLibrary`オブジェクトが作成されます。 戻り値を確認する必要があります`AfxInitExtensionModule`から 0 が返された場合`AfxInitExtensionModule`から 0 を返します、`DllMain`関数。

実行可能ファイルに MFC 拡張 DLL は明示的にリンクされている場合 (つまり実行可能ファイルの呼び出し`AfxLoadLibrary`DLL にリンクする) への呼び出しを追加する必要があります`AfxTermExtensionModule`で`DLL_PROCESS_DETACH`します。 この機能により、各プロセスは、MFC 拡張 DLL からデタッチされるときに、MFC 拡張 DLL をクリーンアップする MFC (動作は、プロセスが終了したとき、またはの結果として DLL をアンロード、`AfxFreeLibrary`呼び出します)。 MFC 拡張 DLL は、アプリケーションへの呼び出しに暗黙的にリンクする場合`AfxTermExtensionModule`必要はありません。

MFC 拡張 Dll へのリンクが明示的に呼び出す必要のあるアプリケーション`AfxTermExtensionModule`DLL を解放します。 使用する必要があります`AfxLoadLibrary`と`AfxFreeLibrary`(Win32 関数ではなく`LoadLibrary`と`FreeLibrary`)、アプリケーションが複数のスレッドを使用している場合。 使用して`AfxLoadLibrary`と`AfxFreeLibrary`スタートアップとシャット ダウン コード MFC 拡張 DLL が読み込まれ、アンロードが MFC のグローバル状態を破損しないときに実行されることを確認します。

時間によって、MFCx0.dll が完全に初期化されるため、`DllMain`が呼び出されると、メモリを割り当てるし、内の MFC 関数を呼び出す`DllMain`(MFC の 16 ビット バージョン) とは異なりします。

処理できる拡張 Dll の処理でマルチ スレッド、`DLL_THREAD_ATTACH`と`DLL_THREAD_DETACH`でケース、`DllMain`関数。 このような場合に渡される`DllMain`スレッドがアタッチし、DLL からデタッチします。 呼び出す[TlsAlloc](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-tlsalloc)によりスレッド ローカル ストレージ (TLS) は、DLL にアタッチされているすべてのスレッドのインデックスを維持するために、DLL、DLL がアタッチされます。

Afxdllx.h ヘッダー ファイルには、構造体の定義などの MFC 拡張 Dll で使用される特殊な定義が含まれています`AFX_EXTENSION_MODULE`と`CDynLinkLibrary`します。 MFC 拡張 DLL では、このヘッダー ファイルを含める必要があります。

> [!NOTE]
>  する定義も未定義のいずれかの重要な`_AFX_NO_XXX`Stdafx.h でマクロ。 これらのマクロは、特定のターゲット プラットフォームでは、かどうか、その機能がサポートしているかどうかをチェックするためにのみ存在します。 これらのマクロをチェックするようプログラムを記述することができます (たとえば、 `#ifndef _AFX_NO_OLE_SUPPORT`)、プログラムの定義またはこれらのマクロの定義を解除する必要があることはありませんが。

マルチ スレッドのハンドルが含まれているサンプルの初期化関数[を使用してスレッド ローカル ストレージにダイナミック リンク ライブラリ](/windows/desktop/Dlls/using-thread-local-storage-in-a-dynamic-link-library)Windows SDK に含まれています。 サンプルが呼び出されるエントリ ポイント関数が含まれているメモ`LibMain`、この関数の名前が`DllMain`MFC および C ランタイム ライブラリで動作するようにします。

## <a name="see-also"></a>関連項目

[Visual C++ の DLL](../build/dlls-in-visual-cpp.md)<br/>
[DllMain のエントリ ポイント](/windows/desktop/Dlls/dllmain)<br/>
[ダイナミック リンク ライブラリのベスト プラクティス](/windows/desktop/Dlls/dynamic-link-library-best-practices)