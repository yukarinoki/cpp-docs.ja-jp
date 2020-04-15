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
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81335659"
---
# <a name="dlls-and-visual-c-run-time-library-behavior"></a>DLL と Visual C++ ランタイム ライブラリの動作

Visual Studio を使用してダイナミック リンク ライブラリ (DLL) をビルドする場合、既定では、リンカーには Visual C++ ランタイム ライブラリ (VCRuntime) が含まれます。 VCRuntime には、C/C++ 実行可能ファイルを初期化および終了するために必要なコードが含まれています。 VCRuntime コードは、DLL にリンクされている場合、プロセスまたはスレッドにアタッチまたは`_DllMainCRTStartup`デタッチする DLL への Windows OS メッセージを処理する内部 DLL エントリ ポイント関数を提供します。 この`_DllMainCRTStartup`関数は、スタック バッファ セキュリティのセットアップ、C ランタイム ライブラリ (CRT) の初期化と終了、静的オブジェクトとグローバル オブジェクトのコンストラクターとデストラクターの呼び出しなどの重要なタスクを実行します。 `_DllMainCRTStartup`また、WinRT、MFC、ATL などの他のライブラリのフック関数を呼び出して、独自の初期化と終了を実行します。 この初期化を行わない場合、CRT やその他のライブラリ、および静的変数は初期化されていない状態になります。 DLL が静的にリンクされた CRT を使用するか、動的にリンクされた CRT DLL を使用するかにかかわらず、同じ VCRuntime 内部初期化ルーチンと終了ルーチンが呼び出されます。

## <a name="default-dll-entry-point-_dllmaincrtstartup"></a>既定の DLL エントリ ポイント _DllMainCRTStartup

Windows では、すべての DLL に、初期化と終了の両方に対`DllMain`して呼び出されるオプションのエントリ ポイント関数 (通常は呼ばれる) を含めることができます。 これによって、追加のリソースを必要に応じて、割り当て/解放する機会が与えられます。 Windows には、エントリ ポイント関数が呼び出される 4 つの状況 (プロセスのアタッチ、プロセス デタッチ、スレッド アタッチ、スレッド デタッチ) があります。 DLL を使用するアプリケーションが読み込まれたとき、または実行時にアプリケーションが DLL を要求するときに、DLL がプロセス アドレス空間に読み込まれると、オペレーティング システムは DLL データのコピーを個別に作成します。 これを*プロセスアタッチ*と呼んでいます。 *スレッドのアタッチ*は、DLL が読み込まれるプロセスが新しいスレッドを作成するときに発生します。 *スレッドのデタッチ*はスレッドが終了したときに発生し、*プロセスデタッチ*は、DLL が不要になり、アプリケーションによって解放された場合です。 オペレーティング システムは、これらのイベントごとに DLL エントリ ポイントを個別に呼び出し、イベントの種類ごとに*reason*引数を渡します。 たとえば、OS はプロセス`DLL_PROCESS_ATTACH`アタッチをシグナル送信する*理由*引数として送信します。

VCRuntime ライブラリには、既定の初期化および終了`_DllMainCRTStartup`操作を処理するために呼び出されるエントリ ポイント関数が用意されています。 プロセス接続では、この`_DllMainCRTStartup`関数はバッファ セキュリティ チェックを設定し、CRT やその他のライブラリを初期化し、実行時型情報を初期化し、静的データと非ローカル データのコンストラクタを初期化して呼び出し、スレッド ローカル ストレージを初期化し、各接続の内部静的カウンタをインクリメント`DllMain`し、ユーザまたはライブラリが提供する . プロセスデタッチでは、関数は逆にこれらの手順を実行します。 呼び`DllMain`出し、内部カウンタのデクリメント、デストラクタの呼び出し、CRT`atexit`終了関数と登録関数の呼び出し、その他のライブラリに終了を通知します。 添付ファイル カウンターが 0 になると、DLL`FALSE`をアンロードできることを Windows に示すために関数が返されます。 この`_DllMainCRTStartup`関数は、スレッドのアタッチとスレッドのデタッチ時にも呼び出されます。 このような場合、VCRuntime コードは独自に追加の初期化や終了を行うのではなく、メッセージ`DllMain`を渡すだけの呼び出しを行います。 プロセス`DllMain`接続`FALSE`から戻り`_DllMainCRTStartup`、シグナルの失敗を、`DllMain`再度呼び出`DLL_PROCESS_DETACH`し、*理由*の引数として渡す場合は、終了プロセスの残りの部分を通過します。

Visual Studio で DLL を構築する場合`_DllMainCRTStartup`、VCRuntime によって提供される既定のエントリ ポイントが自動的にリンクされます。 [/ENTRY (](reference/entry-entry-point-symbol.md)エントリ ポイント シンボル) リンカー オプションを使用して、DLL のエントリ ポイント関数を指定する必要はありません。

> [!NOTE]
> /ENTRY: リンカー オプションを使用して DLL に別のエントリ ポイント関数を指定することは可能ですが、エントリ ポイント関数は同じ順序ですべての`_DllMainCRTStartup`エントリを複製する必要があるため、この関数はお勧めしません。 VCRuntime には、その動作を複製できる関数が用意されています。 たとえば、プロセスアタッチ時に[__security_init_cookie](../c-runtime-library/reference/security-init-cookie.md)を呼び出して[、/GS (バッファ セキュリティ チェック)](reference/gs-buffer-security-check.md)バッファ チェック オプションをサポートできます。 エントリ ポイント`_CRT_INIT`関数と同じパラメーターを渡して関数を呼び出して、残りの DLL 初期化関数または終了関数を実行できます。

<a name="initializing-a-dll"></a>

## <a name="initialize-a-dll"></a>DLL の初期化

DLL の初期化コードが、DLL の読み込み時に実行される必要がある場合があります。 独自の DLL 初期化関数と終了関数を実行するために、`_DllMainCRTStartup`提供できる関数を`DllMain`呼び出します。 DLL`DllMain`エントリ ポイントに必要なシグネチャを持っている必要があります。 既定のエントリ ポイント`_DllMainCRTStartup`関数`DllMain`は、Windows によって渡された同じパラメーターを使用して呼び出します。 既定では、関数を`DllMain`提供しない場合、Visual Studio は、常に呼び出す何かを`_DllMainCRTStartup`持つため、関数を提供し、リンクします。 つまり、DLL を初期化する必要がない場合は、DLL をビルドするときに特別な操作を行う必要はありません。

は、 で使用される`DllMain`シグネチャです。

```cpp
#include <windows.h>

extern "C" BOOL WINAPI DllMain (
    HINSTANCE const instance,  // handle to DLL module
    DWORD     const reason,    // reason for calling function
    LPVOID    const reserved); // reserved
```

一部のライブラリ`DllMain`は関数をラップします。 たとえば、通常の MFC DLL では、DLL で`InitInstance`必要`ExitInstance`な初期化と終了を`CWinApp`実行するオブジェクトとメンバー関数を実装します。 詳細については、「通常の[MFC DLL の初期化」を](#initializing-regular-dlls)参照してください。

> [!WARNING]
> DLL エントリ ポイントで安全に実行できる操作には、大きな制限があります。 呼び出しが安全でない特定の Windows API の`DllMain`[一般的なベスト プラクティス](/windows/win32/Dlls/dynamic-link-library-best-practices)を参照してください。 最も単純な初期化以外の何かが必要な場合は、DLL の初期化関数で行います。 アプリケーションは、実行後`DllMain`、および DLL 内の他の関数を呼び出す前に、初期化関数を呼び出す必要があります。

<a name="initializing-non-mfc-dlls"></a>

### <a name="initialize-ordinary-non-mfc-dlls"></a>通常の (非 MFC) DLL を初期化する

VCRuntime 提供の`_DllMainCRTStartup`エントリ ポイントを使用する通常の (非 MFC) DLL で独自の初期化を実行するには、DLL ソース`DllMain`コードに という関数が含まれている必要があります。 次のコードは、定義の外観を示す基本的`DllMain`なスケルトンを示しています。

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
> 古い Windows SDK ドキュメントでは、DLL エントリ ポイント関数の実際の名前は、リンカーのコマンド ラインで /ENTRY オプションを指定する必要があります。 Visual Studio では、エントリ ポイント関数の名前が`DllMain`の場合は、/ENTRY オプションを使用する必要はありません。 実際、/ENTRY オプションを使用して、エントリ ポイント関数に以外の名前を付`DllMain`けた場合、エントリ ポイント関数が同じ初期化呼び出しを`_DllMainCRTStartup`行わない限り、CRT は正しく初期化されません。

<a name="initializing-regular-dlls"></a>

### <a name="initialize-regular-mfc-dlls"></a>通常の MFC DLL を初期化する

通常の MFC DLL`CWinApp`にはオブジェクトがあるため、DLL`InitInstance``ExitInstance``CWinApp`の派生クラスのとメンバー関数で、MFC アプリケーションと同じ場所で初期化タスクと終了タスクを実行する必要があります。 MFC には`DllMain`for`_DllMainCRTStartup``DLL_PROCESS_ATTACH`と`DLL_PROCESS_DETACH`によって呼び出される関数が用意されているため、`DllMain`独自の関数を記述しないでください。 MFC によって提供`DllMain`される関数`InitInstance`は、DLL が読み込`ExitInstance`まれ、DLL がアンロードされる前に DLL が呼び出されたときに呼び出されます。

通常の MFC DLL は、関数で[TlsAlloc](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsalloc)と[TlsGetValue](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsgetvalue)を呼び出すことによって、複数のスレッドを`InitInstance`追跡できます。 これらの関数を使用すると、DLL はスレッド固有のデータを追跡できます。

MFC に動的にリンクする通常の MFC DLL では、MFC OLE、MFC データベース (DAO)、または MFC ソケットのサポートをそれぞれ使用している場合、デバッグ MFC 拡張機能 DLL MFCO*バージョン*D.dll、MFCD*バージョン*D.dll、および MFCN*バージョン*D.dll (*バージョン*番号) が自動的にリンクされます。 通常の MFC DLL で使用しているこれらの DLL ごとに、次の定義済みの初期化関数のいずれかを呼び出す必要`CWinApp::InitInstance`があります。

|MFC サポートの種類|呼び出す初期化関数|
|-------------------------|-------------------------------------|
|MFC OLE (MFCO*バージョン*D.dll)|`AfxOleInitModule`|
|MFC データベース (MFCD*バージョン*D.dll)|`AfxDbInitModule`|
|MFC ソケット (MFCN*バージョン*D.dll)|`AfxNetInitModule`|

<a name="initializing-extension-dlls"></a>

### <a name="initialize-mfc-extension-dlls"></a>MFC 拡張 DLL を初期化する

MFC 拡張 DLL には`CWinApp`派生オブジェクトがないため (通常の MFC DLL と同様)、MFC DLL ウィザードで生成`DllMain`される関数に初期化コードと終了コードを追加する必要があります。

ウィザードには、MFC 拡張 DLL に対する次のコードが用意されています。 コード内の`PROJNAME`プロジェクト名のプレースホルダーです。

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

初期化中に`CDynLinkLibrary`新しいオブジェクトを作成すると、MFC 拡張`CRuntimeClass`DLL はオブジェクトまたはリソースをクライアント アプリケーションにエクスポートできます。

1 つ以上の標準 MFC DLL から MFC 拡張 DLL を使用する場合は、オブジェクトを作成`CDynLinkLibrary`する初期化関数をエクスポートする必要があります。 この関数は、MFC 拡張 DLL を使用する各標準 MFC DLL から呼び出す必要があります。 この初期化関数を呼び出す適切な場所`InitInstance`は、MFC 拡張 DLL の`CWinApp`エクスポートされたクラスまたは関数を使用する前に、通常の MFC DLL の派生オブジェクトのメンバー関数にあります。

MFC `DllMain` DLL ウィザードによって生成される、オブジェクトの作成時に`AfxInitExtensionModule`使用する、モジュールのランタイム クラス (`CRuntimeClass`構造体) とそのオブジェクト ファクトリ (`COleObjectFactory`オブジェクト) をキャプチャする`CDynLinkLibrary`呼び出し。 の戻り値を確認する`AfxInitExtensionModule`必要があります。から`AfxInitExtensionModule`ゼロ値が返された場合は、関数からゼロ`DllMain`を返します。

MFC 拡張 DLL が実行可能ファイル (DLL へのリンクを呼び`AfxLoadLibrary`出す実行可能ファイルの呼び出し) に`AfxTermExtensionModule`明示的`DLL_PROCESS_DETACH`にリンクされる場合は、 に呼び出しを追加する必要があります。 この関数を使用すると、MFC 拡張 DLL を各プロセスが MFC 拡張 DLL から切り離したときに MFC 拡張 DLL をクリーンアップできます (プロセス`AfxFreeLibrary`が終了したとき、または呼び出しの結果として DLL がアンロードされたときに発生します)。 MFC 拡張 DLL がアプリケーションに暗黙的にリンクされる場合、呼`AfxTermExtensionModule`び出しは必要ありません。

MFC 拡張 DLL に明示的にリンクするアプリケーション`AfxTermExtensionModule`は、DLL を解放するときに呼び出す必要があります。 また、アプリケーションが`AfxLoadLibrary`複数`AfxFreeLibrary`のスレッドを使用する場合は、 `LoadLibrary` `FreeLibrary`および Win32 関数の代わりに 、 と を使用する必要があります。 MFC `AfxLoadLibrary` `AfxFreeLibrary`拡張 DLL の読み込みとアンロード時に実行されるスタートアップ コードとシャットダウン コードを使用して、グローバルな MFC 状態が破損しないようにします。

MFCx0.dll は呼び出された時間`DllMain`によって完全に初期化されるため、メモリを割り当てて`DllMain`MFC 関数を呼び出すことができます (16 ビット バージョンの MFC とは異なり)。

拡張 DLL は、関数内の ケース`DLL_THREAD_ATTACH`と`DLL_THREAD_DETACH`を処理することでマルチスレッド`DllMain`処理を行うことができます。 これらのケースは、スレッド`DllMain`が DLL をアタッチして DLL からデタッチするときに渡されます。 DLL がアタッチされているときに[TlsAlloc](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsalloc)を呼び出すと、DLL は、DLL にアタッチされた各スレッドのスレッド ローカル ストレージ (TLS) インデックスを維持できます。

ヘッダー ファイル Afxdllx.h には、MFC 拡張 DLL で使用される構造体の特殊な定義`AFX_EXTENSION_MODULE`が含まれています`CDynLinkLibrary`。 このヘッダー ファイルは、MFC 拡張 DLL に含める必要があります。

> [!NOTE]
> `_AFX_NO_XXX` *pch.h* (Visual Studio 2017 以前の*stdafx.h)* でマクロを定義したり、定義を解除したりすることは重要です。 これらのマクロは、特定のターゲット プラットフォームがその機能をサポートしているかどうかを確認する目的でのみ存在します。 これらのマクロ (たとえば) をチェックするプログラムを作成`#ifndef _AFX_NO_OLE_SUPPORT`できますが、プログラムでこれらのマクロを定義したり定義解除したりしないでください。

マルチスレッドを処理する初期化関数のサンプルは、Windows SDK の[ダイナミック リンク ライブラリでスレッド ローカル ストレージを使用](/windows/win32/Dlls/using-thread-local-storage-in-a-dynamic-link-library)するに含まれています。 サンプルには`LibMain`、 というエントリ ポイント関数が含まれていますが、MFC および`DllMain`C ランタイム ライブラリで動作するように、この関数に名前を付ける必要があります。

## <a name="see-also"></a>関連項目

[Visual Studio での C/C++ Dll の作成](dlls-in-visual-cpp.md)<br/>
[Dllメインエントリポイント](/windows/win32/Dlls/dllmain)<br/>
[ダイナミック リンク ライブラリのベスト プラクティス](/windows/win32/Dlls/dynamic-link-library-best-practices)
