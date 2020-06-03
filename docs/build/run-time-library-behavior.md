---
title: DLL と Visual C++ ランタイム ライブラリの動作
ms.date: 08/19/2019
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
ms.openlocfilehash: 2f2ffb13e6a80b144298bbf8cd76b5666a10b4dd
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81335659"
---
# <a name="dlls-and-visual-c-run-time-library-behavior"></a>DLL と Visual C++ ランタイム ライブラリの動作

Visual Studio を使用してダイナミックリンク ライブラリ (DLL) をビルドする場合、既定では、リンカーには Visual C++ ランタイム ライブラリ (VCRuntime) が含まれます。 VCRuntime には、C/C++ 実行可能ファイルを初期化および終了するために必要なコードが含まれています。 DLL にリンクされる場合、VCRuntime コードは `_DllMainCRTStartup` と呼ばれる内部 DLL エントリポイント関数を提供します。この関数は、Windows OS メッセージを DLL に渡してプロセスまたはスレッドにアタッチまたはデタッチします。 `_DllMainCRTStartup` 関数は、スタック バッファー セキュリティのセットアップ、C ランタイム ライブラリ (CRT) の初期化と終了、静的オブジェクトとグローバル オブジェクトのコンストラクターとデストラクターの呼び出しなど、重要なタスクを実行します。 `_DllMainCRTStartup` は、WinRT、MFC、ATL などの他のライブラリのフック関数も呼び出して、独自の初期化と終了を実行します。 この初期化がないと、CRT とその他のライブラリ、および静的変数は初期化されていない状態のままになります。 DLL が静的にリンクされた CRT を使用するか、動的にリンクされた CRT DLL を使用するかにかかわらず、同じ VCRuntime 内部初期化および終了ルーチンが呼び出されます。

## <a name="default-dll-entry-point-_dllmaincrtstartup"></a>既定の DLL エントリ ポイント _DllMainCRTStartup

Windows では、すべての DLL にオプションのエントリ ポイント関数 (通常、`DllMain`) が含まれます。エントリ ポイント関数は、初期化と終了の両方で呼び出されます。 これによって、追加のリソースを必要に応じて、割り当て/解放する機会が与えられます。 Windows には、エントリ ポイント関数が呼び出される 4 つの状況 (プロセスのアタッチ、プロセス デタッチ、スレッド アタッチ、スレッド デタッチ) があります。 DLL がプロセス アドレス空間に読み込まれると、その DLL を使用するアプリケーションが読み込まれたとき、またはアプリケーションが実行時に DLL を要求したときに、オペレーティング システムによって DLL データのコピーが個別に作成されます。 これは*プロセスのアタッチ*と呼ばれます。 *スレッドのアタッチ*は、DLL が読み込まれるプロセスによって新しいスレッドが作成されるときに発生します。 *スレッドのデタッチ*はスレッドが終了するときに発生し、*プロセスのデタッチ*は DLL が不要になり、アプリケーションによって解放されるときに発生します。 オペレーティング システムは、これらの各イベントの DLL エントリ ポイントを個別に呼び出し、各イベントの種類に対して *reason* 引数を渡します。 たとえば、OS は `DLL_PROCESS_ATTACH` を *reason* 引数として送信し、プロセスのアタッチを通知します。

VCRuntime ライブラリには、既定の初期化および終了操作を処理するために `_DllMainCRTStartup` というエントリポイント関数が用意されています。 プロセスのアタッチでは、`_DllMainCRTStartup` 関数は、バッファー セキュリティ チェックを設定し、CRT とその他のライブラリを初期化し、ランタイム型情報を初期化し、静的および非ローカルのデータのコンストラクターを初期化して呼び出し、スレッドローカル ストレージを初期化し、アタッチごとに内部静的カウンターをインクリメントしてから、ユーザーまたはライブラリが提供する `DllMain` を呼び出します。 プロセスのデタッチでは、関数はこれらのステップを逆順で実行します。 `DllMain` を呼び出し、内部カウンターをデクリメントし、デストラクターを呼び出し、CRT 終了関数と登録済み `atexit` 関数を呼び出し、他のすべてのライブラリが終了したことを通知します。 アタッチカウンターが 0 になると、関数は `FALSE` を返して、DLL をアンロードできることを Windows に示します。 `_DllMainCRTStartup` 関数は、スレッドのアタッチとスレッドのデタッチ中にも呼び出されます。 このような場合、VCRuntime コードは追加の初期化も終了も行わず、`DllMain` を呼び出してメッセージを渡すだけです。 `DllMain` がプロセスのアタッチから `FALSE` を返した場合、通知は失敗し、`_DllMainCRTStartup` は `DllMain` を再度呼び出して `DLL_PROCESS_DETACH` を *reason* 引数として渡してから、終了処理の残りを実行します。

Visual Studio で Dll をビルドする場合、VCRuntime によって提供される既定のエントリ ポイント `_DllMainCRTStartup` が自動的にリンクされます。 [/ENTRY (エントリ ポイント シンボル)](reference/entry-entry-point-symbol.md) リンカー オプションを使用して、DLL のエントリポイント関数を指定する必要はありません。

> [!NOTE]
> /ENTRY: リンカー オプションを使うと DLL の別のエントリ ポイント関数を指定できますが、そのエントリポイント関数では `_DllMainCRTStartup` が行う全処理を同じ順序で繰り返す必要があるため、この方法は推奨できません。 VCRuntime には、その動作を複製できるようにする関数が用意されています。 たとえば、プロセスのアタッチですぐに [__security_init_cookie](../c-runtime-library/reference/security-init-cookie.md) を呼び出して、[/GS (バッファー セキュリティ チェック)](reference/gs-buffer-security-check.md) バッファー チェック オプションをサポートすることができます。 `_CRT_INIT` 関数を呼び出して、エントリ ポイント関数と同じパラメーターを渡すことにより、DLL 初期化関数または終了関数の残りを実行できます。

<a name="initializing-a-dll"></a>

## <a name="initialize-a-dll"></a>DLL の初期化

DLL の読み込み時に実行する必要がある初期化コードが DLL に含まれている可能性があります。 独自の DLL 初期化関数と終了関数を実行するために、`_DllMainCRTStartup` は、指定できる `DllMain` と呼ばれる関数を呼び出します。 `DllMain` には、DLL エントリ ポイントに要求されるシグネチャが必要です。 既定のエントリ ポイント関数 `_DllMainCRTStartup` は、Windows によって渡される同じパラメーターを使用して `DllMain` を呼び出します。 既定では、`DllMain` 関数を指定しない場合、Visual Studio によってその関数が提供され、`_DllMainCRTStartup` に常に呼び出し対象が含まれるようにリンクが設定されます。 つまり、DLL を初期化する必要がない場合、DLL のビルド時に必要な処理は特にありません。

これは `DllMain` に使用されるシグネチャです。

```cpp
#include <windows.h>

extern "C" BOOL WINAPI DllMain (
    HINSTANCE const instance,  // handle to DLL module
    DWORD     const reason,    // reason for calling function
    LPVOID    const reserved); // reserved
```

一部のライブラリでは、`DllMain` 関数がラップされています。 たとえば、標準の MFC DLL では、`CWinApp` オブジェクトの `InitInstance` および `ExitInstance` メンバー関数を実装して、DLL で必要な初期化と終了を実行します。 詳細については、「[標準 MFC DLL の初期化](#initializing-regular-dlls)」セクションを参照してください。

> [!WARNING]
> DLL のエントリ ポイントで安全に実行できる処理には大きな制限があります。 `DllMain` での呼び出しが安全ではない特定の Windows API については、[一般的なベスト プラクティス](/windows/win32/Dlls/dynamic-link-library-best-practices)に関するページを参照してください。 最も単純な初期化以外にも必要である場合は、DLL の初期化関数でそれを実行します。 `DllMain` が実行された後、DLL 内の他の関数を呼び出す前に、アプリケーションが初期化関数を呼び出すように要求することができます。

<a name="initializing-non-mfc-dlls"></a>

### <a name="initialize-ordinary-non-mfc-dlls"></a>通常 (非 MFC) DLL の初期化

VCRuntime によって提供される `_DllMainCRTStartup` エントリ ポイントを使用する通常の (非 MFC) DLL で独自の初期化を実行するには、DLL ソース コードに `DllMain` という名前の関数が含まれている必要があります。 次のコードは、`DllMain` の定義がどのようなものかを示す基本的なスケルトンを示しています。

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
> 以前の Windows SDK ドキュメントでは、/ENTRY オプションを使用して、リンカー コマンドラインに DLL エントリポイント関数の実際の名前を指定する必要があることが示されています。 Visual Studio では、エントリポイント関数の名前が `DllMain` である場合、/ENTRY オプションを使用する必要はありません。 実際に、/ENTRY オプションを使用してエントリポイント関数に `DllMain` 以外の名前を指定した場合、エントリポイント関数によって `_DllMainCRTStartup` と同じ初期化呼び出しが行われない限り、CRT は適切に初期化されません。

<a name="initializing-regular-dlls"></a>

### <a name="initialize-regular-mfc-dlls"></a>標準 MFC DLL の初期化

標準 MFC Dll には `CWinApp` オブジェクトがあるので、MFC アプリケーションと同じ場所、つまり DLL の `CWinApp` 派生クラスの `InitInstance` および `ExitInstance` メンバー関数で初期化タスクと終了タスクを実行する必要があります。 MFC には `DLL_PROCESS_ATTACH` と `DLL_PROCESS_DETACH` の `_DllMainCRTStartup` によって呼び出される `DllMain` 関数が用意されているため、独自の `DllMain` 関数を記述することは避けてください。 MFC に用意されている `DllMain` 関数は、DLL が読み込まれるときに `InitInstance` を呼び出し、DLL がアンロードされる前に `ExitInstance` を呼び出します。

標準 MFC DLL では、その `InitInstance` 関数で [TlsAlloc](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsalloc) および [TlsGetValue](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsgetvalue) を呼び出すことで、複数のスレッドを追跡できます。 これらの関数により、DLL がスレッド固有のデータを追跡できます。

MFC に動的にリンクする標準 MFC DLL 内で MFC OLE、MFC データベース (または DAO)、または MFC ソケットのサポートを使用している場合は、それぞれデバッグ MFC 拡張 DLL の MFCO*version*D.dll、MFCD*version*D.dll、および MFCN*version*D.dll (*version* はバージョン番号) が自動的にリンクされます。 標準 MFC DLL の `CWinApp::InitInstance` で使用している DLL ごとに、次の定義済み初期化関数のいずれかを呼び出す必要があります。

|MFC サポートの種類|呼び出す初期化関数|
|-------------------------|-------------------------------------|
|MFC OLE (MFCO*version*D.dll)|`AfxOleInitModule`|
|MFC データベース (MFCD*version*D.dll)|`AfxDbInitModule`|
|MFC ソケット (MFCN*version*D.dll)|`AfxNetInitModule`|

<a name="initializing-extension-dlls"></a>

### <a name="initialize-mfc-extension-dlls"></a>MFC 拡張 DLL の初期化

MFC 拡張 DLL には `CWinApp` 派生オブジェクトがないため (標準 MFC DLL にはあります)、MFC DLL ウィザードによって生成される `DllMain` 関数に初期化コードと終了コードを追加する必要があります。

ウィザードには、MFC 拡張 DLL 用の次のコードが用意されています。 コードで、`PROJNAME` はプロジェクト名のプレースホルダーです。

```cpp
#include "pch.h" // For Visual Studio 2017 and earlier, use "stdafx.h"
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

初期化中に `CDynLinkLibrary` オブジェクトを作成すると、MFC 拡張 DLL がクライアント アプリケーションに `CRuntimeClass` オブジェクトまたはリソースをエクスポートできます。

1 つ以上の標準 MFC DLL から MFC 拡張 DLL を使用する場合は、`CDynLinkLibrary` オブジェクトを作成する初期化関数をエクスポートする必要があります。 その関数は、MFC 拡張 DLL を使用するそれぞれの標準 MFC DLL から呼び出す必要があります。 この初期化関数を呼び出す適切な場所は、標準 MFC DLL の `CWinApp` 派生オブジェクトの `InitInstance` メンバー関数内で、MFC 拡張 DLL のエクスポートされたクラスまたは関数のいずれかを使用する前です。

MFC DLL ウィザードによって生成される `DllMain` では、`AfxInitExtensionModule` を呼び出すことによって、モジュールの実行時クラス (`CRuntimeClass` 構造体) だけでなく、`CDynLinkLibrary` オブジェクトの作成時に使用するオブジェクト ファクトリ (`COleObjectFactory` オブジェクト) がキャプチャされます。 `AfxInitExtensionModule` の戻り値を確認する必要があります。`AfxInitExtensionModule` から 0 の値が返された場合は、`DllMain` 関数から 0 を返します。

MFC 拡張 DLL が実行可能ファイルに明示的にリンクされている場合 (つまり、実行可能ファイルが `AfxLoadLibrary` を呼び出して DLL にリンクする場合)、`DLL_PROCESS_DETACH` に `AfxTermExtensionModule` の呼び出しを追加する必要があります。 この関数を使用すると、各プロセスが MFC 拡張 DLL からデタッチされたときに MFC 拡張 DLL をクリーンアップできます (デタッチは、プロセスが終了したとき、または DLL が `AfxFreeLibrary` 呼び出しの結果としてアンロードされたときに発生します)。 MFC 拡張 DLL がアプリケーションに暗黙的にリンクされる場合、`AfxTermExtensionModule` の呼び出しは必要ありません。

MFC 拡張 DLL に明示的にリンクするアプリケーションは、DLL を解放するときに `AfxTermExtensionModule` を呼び出す必要があります。 また、アプリケーションで複数のスレッドが使用されている場合は、(Win32 関数 `LoadLibrary` および `FreeLibrary` ではなく) `AfxLoadLibrary` および `AfxFreeLibrary` も使用する必要があります。 `AfxLoadLibrary` と `AfxFreeLibrary` を使用すると、MFC 拡張 DLL がロードおよびアンロードされたときに実行される起動コードとシャットダウン コードが、グローバルの MFC 状態を破壊することがなくなります。

MFCx0.dll は `DllMain` が呼び出された時点で完全に初期化されるので、`DllMain` 内でメモリを割り当て、MFC 関数を呼び出すことができます (16 ビット バージョンの MFC とは異なります)。

拡張 DLL では、`DllMain` 関数内の `DLL_THREAD_ATTACH` および `DLL_THREAD_DETACH` ケースを処理することによって、マルチスレッド処理を行うことができます。 これらのケースは、スレッドが DLL に対してアタッチおよびデタッチするときに `DllMain` に渡されます。 DLL がアタッチされているときに [TlsAlloc](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsalloc) を呼び出すと、DLL にアタッチされているすべてのスレッドに対して、DLL はスレッド ローカル ストレージ (TLS) インデックスを維持できます。

ヘッダー ファイル Afxdllx.h には、MFC 拡張 DLL で使用される構造体の特別な定義 (`AFX_EXTENSION_MODULE` および `CDynLinkLibrary` の定義など) が含まれていることに注意してください。 このヘッダー ファイルは、MFC 拡張 DLL に含める必要があります。

> [!NOTE]
> 重要なのは、*pch.h* (Visual Studio 2017 以前では *stdafx.h*) で `_AFX_NO_XXX` マクロを定義したり未定義にしたりすることができないことです。 これらのマクロは、特定のターゲット プラットフォームでその機能がサポートされているかどうかを確認するためだけに存在します。 これらのマクロをチェックするようにプログラムを記述できます (たとえば、`#ifndef _AFX_NO_OLE_SUPPORT`)。ただし、プログラムでこれらのマクロを定義または未定義にすることはできません。

マルチスレッド処理を行うサンプルの初期化関数は、Windows SDK の[ダイナミックリンク ライブラリでスレッド ローカル ストレージを使用する方法](/windows/win32/Dlls/using-thread-local-storage-in-a-dynamic-link-library)に関するページに含まれています。 このサンプルには `LibMain` というエントリポイント関数が含まれていますが、MFC および C ランタイム ライブラリで動作するように、この関数の名前を `DllMain` にする必要があります。

## <a name="see-also"></a>関連項目

[Visual Studio での C/C++ Dll の作成](dlls-in-visual-cpp.md)<br/>
[DllMain エントリ ポイント](/windows/win32/Dlls/dllmain)<br/>
[ダイナミックリンク ライブラリのベスト プラクティス](/windows/win32/Dlls/dynamic-link-library-best-practices)
