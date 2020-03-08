---
title: Dll と Visual C++ランタイムライブラリの動作
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
ms.openlocfilehash: 572a0ba70c1ba2d46d2d9fd6d8ac543a77bbbc01
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2020
ms.locfileid: "78856775"
---
# <a name="dlls-and-visual-c-run-time-library-behavior"></a>Dll と Visual C++ランタイムライブラリの動作

Visual Studio を使用してダイナミックリンクライブラリ (DLL) をビルドする場合、既定では、リンカーにはC++ visual ランタイムライブラリ (vcruntime) が含まれます。 VCRuntime には、C/C++実行可能ファイルを初期化して終了するために必要なコードが含まれています。 DLL にリンクされている場合、VCRuntime コードは `_DllMainCRTStartup` と呼ばれる内部 DLL エントリポイント関数を提供します。この関数は、Windows OS メッセージを DLL に処理して、プロセスまたはスレッドにアタッチまたはデタッチします。 `_DllMainCRTStartup` 関数は、スタックバッファーセキュリティのセットアップ、C ランタイムライブラリ (CRT) の初期化と終了、静的オブジェクトとグローバルオブジェクトのコンストラクターとデストラクターの呼び出しなど、重要なタスクを実行します。 また `_DllMainCRTStartup` は、WinRT、MFC、ATL などの他のライブラリのフック関数を呼び出して、独自の初期化と終了を実行します。 この初期化がないと、CRT とその他のライブラリ、および静的変数は初期化されていない状態のままになります。 同じ VCRuntime 内部初期化および終了ルーチンは、DLL が静的にリンクされた CRT を使用するか、動的にリンクされた CRT DLL を使用するかにかかわらず呼び出されます。

## <a name="default-dll-entry-point-_dllmaincrtstartup"></a>既定の DLL エントリポイント _DllMainCRTStartup

Windows では、すべての Dll にオプションのエントリポイント関数 (通常は `DllMain`と呼ばれます) を含めることができます。これは初期化と終了の両方で呼び出されます。 これによって、追加のリソースを必要に応じて、割り当て/解放する機会が与えられます。 Windows には、エントリ ポイント関数が呼び出される 4 つの状況 (プロセスのアタッチ、プロセス デタッチ、スレッド アタッチ、スレッド デタッチ) があります。 DLL がプロセスアドレス空間に読み込まれると、その DLL を使用するアプリケーションが読み込まれたとき、またはアプリケーションが実行時に DLL を要求したときに、オペレーティングシステムによって DLL データのコピーが個別に作成されます。 これを*プロセスアタッチ*と呼びます。 *スレッドのアタッチ*は、DLL が読み込まれるプロセスによって新しいスレッドが作成されるときに発生します。 スレッドの*デタッチ*は、スレッドが終了したときに発生し、*プロセスデタッチ*は、DLL が不要になり、アプリケーションによって解放されたときに発生します。 オペレーティングシステムは、これらの各イベントに対して DLL エントリポイントを個別に呼び出し、各イベントの種類に*reason*引数を渡します。 たとえば、OS は `DLL_PROCESS_ATTACH` を送信するために、 *reason*引数としてを送信します。

VCRuntime ライブラリには、既定の初期化および終了操作を処理するために `_DllMainCRTStartup` というエントリポイント関数が用意されています。 プロセスのアタッチでは、`_DllMainCRTStartup` 関数は、バッファーセキュリティチェックを設定し、CRT とその他のライブラリを初期化し、ランタイム型情報を初期化し、静的およびローカルでないデータのコンストラクターを初期化して呼び出し、スレッドローカルストレージを初期化し、アタッチごとに内部静的カウンターをインクリメントしてから、ユーザーまたはライブラリが提供する `DllMain`を呼び出します。 プロセスのデタッチでは、関数はこれらの手順を逆に実行します。 このメソッドは、`DllMain`を呼び出し、内部カウンターをデクリメントし、デストラクターを呼び出し、CRT 終了関数と登録されている `atexit` 関数を呼び出し、他のすべてのライブラリが終了したことを通知します。 Attachment カウンターが0になると、関数は `FALSE` を返して、DLL をアンロードできることを Windows に示します。 `_DllMainCRTStartup` 関数は、スレッドのアタッチとスレッドのデタッチ中にも呼び出されます。 このような場合、VCRuntime コードは追加の初期化も終了もせず、`DllMain` を呼び出してメッセージを渡すだけです。 `DllMain` がプロセスのアタッチから `FALSE` 返された場合、シグナルが失敗した場合は `_DllMainCRTStartup`、`DllMain` を再度呼び出して、 *reason*引数として `DLL_PROCESS_DETACH` を渡した後、残りの終了処理を実行します。

Visual Studio で Dll をビルドする場合、VCRuntime によって提供される既定のエントリポイント `_DllMainCRTStartup` が自動的にリンクされます。 [/Entry (エントリポイントシンボル)](reference/entry-entry-point-symbol.md)リンカーオプションを使用して、DLL のエントリポイント関数を指定する必要はありません。

> [!NOTE]
> /ENTRY: リンカーオプションを使用して DLL 用に別のエントリポイント関数を指定することもできますが、これは推奨されません。これは、エントリポイント関数が、`_DllMainCRTStartup` が実行するすべてのものを同じ順序で複製する必要があるためです。 VCRuntime には、動作を複製できるようにする関数が用意されています。 たとえば、プロセスのアタッチ時にすぐに[__security_init_cookie](../c-runtime-library/reference/security-init-cookie.md)を呼び出して、 [/gs (バッファーセキュリティチェック)](reference/gs-buffer-security-check.md)バッファーチェックオプションをサポートすることができます。 `_CRT_INIT` 関数を呼び出して、エントリポイント関数と同じパラメーターを渡すことにより、残りの DLL 初期化関数または終了関数を実行できます。

<a name="initializing-a-dll"></a>

## <a name="initialize-a-dll"></a>DLL の初期化

Dll の読み込み時に実行する必要がある初期化コードが DLL に含まれている可能性があります。 独自の DLL 初期化関数と終了関数を実行するために、`_DllMainCRTStartup` は、指定できる `DllMain` と呼ばれる関数を呼び出します。 `DllMain` には、DLL エントリポイントに必要な署名が必要です。 既定のエントリポイント関数 `_DllMainCRTStartup`、Windows によって渡される同じパラメーターを使用して `DllMain` を呼び出します。 既定では、`DllMain` 関数を指定しない場合、Visual Studio によってその関数が提供され、`_DllMainCRTStartup` には常にを呼び出すようにリンクが設定されます。 つまり、dll を初期化する必要がない場合は、DLL をビルドするときに特別な操作は必要ありません。

これは `DllMain`に使用される署名です。

```cpp
#include <windows.h>

extern "C" BOOL WINAPI DllMain (
    HINSTANCE const instance,  // handle to DLL module
    DWORD     const reason,    // reason for calling function
    LPVOID    const reserved); // reserved
```

一部のライブラリでは、`DllMain` 関数がラップされています。 たとえば、通常の MFC DLL では、`CWinApp` オブジェクトの `InitInstance` と `ExitInstance` メンバー関数を実装して、DLL で必要な初期化と終了を実行します。 詳細については、「[通常の MFC dll の初期化](#initializing-regular-dlls)」セクションを参照してください。

> [!WARNING]
> DLL のエントリポイントで安全に実行できることには大きな制限があります。 `DllMain`での呼び出しが安全ではない特定の Windows Api の[一般的なベストプラクティス](/windows/win32/Dlls/dynamic-link-library-best-practices)を参照してください。 必要なものが最も単純な初期化である場合は、DLL の初期化関数でそれを実行します。 `DllMain` が実行された後、DLL 内の他の関数を呼び出す前に、アプリケーションが初期化関数を呼び出すように要求することができます。

<a name="initializing-non-mfc-dlls"></a>

### <a name="initialize-ordinary-non-mfc-dlls"></a>通常の (非 MFC) Dll を初期化する

VCRuntime によって提供される `_DllMainCRTStartup` エントリポイントを使用する通常の (非 MFC) Dll で独自の初期化を実行するには、DLL ソースコードに `DllMain`という名前の関数が含まれている必要があります。 次のコードは、`DllMain` の定義がどのようなものかを示す基本的なスケルトンを示しています。

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
> 以前の Windows SDK のドキュメントでは、/ENTRY オプションを使用して、リンカーコマンドラインに DLL エントリポイント関数の実際の名前を指定する必要があることが示されています。 Visual Studio では、エントリポイント関数の名前が `DllMain`場合に/ENTRY オプションを使用する必要はありません。 実際に、/ENTRY オプションを使用して、エントリポイント関数に `DllMain`以外の名前を指定した場合、エントリポイント関数によって `_DllMainCRTStartup` 同じ初期化呼び出しが行われない限り、CRT は適切に初期化されません。

<a name="initializing-regular-dlls"></a>

### <a name="initialize-regular-mfc-dlls"></a>レギュラー MFC Dll の初期化

通常の MFC Dll には `CWinApp` オブジェクトがあるので、MFC アプリケーションと同じ場所で初期化タスクと終了タスクを実行する必要があります。これには、DLL の `CWinApp`派生クラスの `InitInstance` および `ExitInstance` メンバー関数を指定します。 MFC には `DLL_PROCESS_ATTACH` と `DLL_PROCESS_DETACH`の `_DllMainCRTStartup` によって呼び出される `DllMain` 関数が用意されているため、独自の `DllMain` 関数を記述することは避けてください。 MFC に用意されている `DllMain` 関数は、DLL が読み込まれるときに `InitInstance` を呼び出し、DLL がアンロードされる前に `ExitInstance` を呼び出します。

通常の MFC DLL では、`InitInstance` 関数で[TlsAlloc](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsalloc)と[TlsGetValue](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsgetvalue)を呼び出すことによって、複数のスレッドを追跡できます。 これらの関数は、DLL がスレッド固有のデータを追跡できるようにします。

Mfc に動的にリンクされるレギュラー MFC DLL では、mfc OLE、MFC Database (または DAO)、または MFC ソケットのサポートをそれぞれ使用している場合は、debug MFC extension Dll MFCO*バージョン*d. .DLL、mfco*バージョン*d. .DLL、および mfco*バージョン*d. ( *version*はバージョン番号) は自動的にリンクされます。 通常の MFC DLL の `CWinApp::InitInstance`で使用している Dll ごとに、次の定義済みの初期化関数のいずれかを呼び出す必要があります。

|MFC のサポートの種類|呼び出す初期化関数|
|-------------------------|-------------------------------------|
|MFC OLE (MFCO*バージョン*d. .dll)|`AfxOleInitModule`|
|MFC データベース (MFCD*バージョン*d. .dll)|`AfxDbInitModule`|
|MFC ソケット (MFCN*バージョン*d. .dll)|`AfxNetInitModule`|

<a name="initializing-extension-dlls"></a>

### <a name="initialize-mfc-extension-dlls"></a>MFC 拡張 Dll の初期化

MFC 拡張 Dll には `CWinApp`派生オブジェクト (通常の MFC Dll) がないため、MFC DLL ウィザードによって生成される `DllMain` 関数に初期化コードと終了コードを追加する必要があります。

ウィザードには、MFC 拡張 Dll 用の次のコードが用意されています。 コードでは、`PROJNAME` はプロジェクト名のプレースホルダーです。

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

初期化中に新しい `CDynLinkLibrary` オブジェクトを作成すると、MFC 拡張 DLL は、`CRuntimeClass` オブジェクトまたはリソースをクライアントアプリケーションにエクスポートできます。

1つ以上の通常の MFC Dll から MFC 拡張 DLL を使用する場合は、`CDynLinkLibrary` オブジェクトを作成する初期化関数をエクスポートする必要があります。 この関数は、MFC 拡張 DLL を使用する通常の MFC Dll から呼び出す必要があります。 この初期化関数を呼び出す適切な場所は、MFC 拡張 DLL のエクスポートされたクラスまたは関数のいずれかを使用する前に、通常の MFC DLL の `CWinApp`派生オブジェクトの `InitInstance` メンバー関数に含まれています。

MFC DLL ウィザードによって生成される `DllMain` では、`AfxInitExtensionModule` を呼び出すことによって、モジュールの実行時クラス (`CRuntimeClass` 構造体) だけでなく、`CDynLinkLibrary` オブジェクトの作成時に使用するオブジェクトファクトリ (`COleObjectFactory` オブジェクト) がキャプチャされます。 `AfxInitExtensionModule`の戻り値を確認する必要があります。`AfxInitExtensionModule`から0の値が返された場合は、`DllMain` 関数から0を返します。

MFC 拡張 DLL が実行可能ファイルに明示的にリンクされている場合 (つまり、実行可能ファイルが DLL にリンクするために `AfxLoadLibrary` を呼び出す場合)、`DLL_PROCESS_DETACH`に `AfxTermExtensionModule` の呼び出しを追加する必要があります。 この関数を使用すると、各プロセスが MFC 拡張 DLL からデタッチされたときに mfc 拡張 DLL をクリーンアップできます (プロセスが終了したとき、または DLL が `AfxFreeLibrary` 呼び出しの結果としてアンロードされたときに発生します)。 MFC 拡張 DLL がアプリケーションに暗黙的にリンクされる場合、`AfxTermExtensionModule` の呼び出しは必要ありません。

MFC 拡張 Dll に明示的にリンクするアプリケーションは、DLL を解放するときに `AfxTermExtensionModule` を呼び出す必要があります。 また、アプリケーションで複数のスレッドが使用されている場合は、(Win32 関数 `LoadLibrary` および `FreeLibrary`ではなく) `AfxLoadLibrary` および `AfxFreeLibrary` も使用する必要があります。 `AfxLoadLibrary` と `AfxFreeLibrary` を使用すると、MFC 拡張 DLL が読み込まれてアンロードされたときに実行される起動コードとシャットダウンコードが、MFC のグローバル状態を破壊することがなくなります。

Mfcx0.dll は `DllMain` が呼び出された時間によって完全に初期化されるので、メモリを割り当て、`DllMain` 内で MFC 関数を呼び出すことができます (16 ビットバージョンの MFC とは異なります)。

拡張 Dll では、`DllMain` 関数内の `DLL_THREAD_ATTACH` と `DLL_THREAD_DETACH` ケースを処理することによって、マルチスレッド処理を行うことができます。 これらのケースは、スレッドが DLL からアタッチおよびデタッチするときに `DllMain` に渡されます。 Dll がアタッチされているときに[TlsAlloc](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsalloc)を呼び出すと、DLL は dll にアタッチされているすべてのスレッドに対してスレッドローカルストレージ (TLS) インデックスを維持できます。

ヘッダーファイル Afxdllx には、MFC 拡張 Dll で使用される構造体 (`AFX_EXTENSION_MODULE` および `CDynLinkLibrary`の定義など) の特別な定義が含まれていることに注意してください。 このヘッダーファイルは、MFC 拡張 DLL に含める必要があります。

> [!NOTE]
>  *Pch* (Visual Studio 2017 以前の*stdafx.h* ) では、`_AFX_NO_XXX` マクロを定義したり、未定義にしたりすることはできません。 これらのマクロは、特定のターゲットプラットフォームでその機能がサポートされているかどうかを確認するためだけに存在します。 これらのマクロをチェックするようにプログラムを記述できます (たとえば、`#ifndef _AFX_NO_OLE_SUPPORT`)。ただし、プログラムでこれらのマクロを定義または未定義にすることはできません。

マルチスレッド処理を行うサンプル初期化関数は、Windows SDK の[ダイナミックリンクライブラリにあるスレッドローカルストレージを使用](/windows/win32/Dlls/using-thread-local-storage-in-a-dynamic-link-library)する場合に含まれます。 このサンプルには `LibMain`というエントリポイント関数が含まれていますが、MFC および C ランタイムライブラリで動作するように、この関数に名前を `DllMain` する必要があります。

## <a name="see-also"></a>参照

[Visual Studio での C/C++ Dll の作成](dlls-in-visual-cpp.md)<br/>
[DllMain エントリポイント](/windows/win32/Dlls/dllmain)<br/>
[ダイナミックリンクライブラリのベストプラクティス](/windows/win32/Dlls/dynamic-link-library-best-practices)
