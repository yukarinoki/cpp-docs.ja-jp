---
title: Dll および Visual C ランタイム ライブラリの動作 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- _DllMainCRTStartup
- CRT_INIT
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: feee3d888fbf43bfd8675ccc83a04fd4e1f0b528
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32392063"
---
# <a name="dlls-and-visual-c-run-time-library-behavior"></a>Dll および Visual C ランタイム ライブラリの動作  
  
既定では、Visual C を使用してダイナミック リンク ライブラリ (DLL) をビルドするときに、リンカーには、Visual C ランタイム ライブラリ (VCRuntime) が含まれています。 VCRuntime には、初期化および終了した C と C++ 実行可能ファイルに必要なコードが含まれています。 VCRuntime コードが呼び出される内部の DLL エントリ ポイント関数を提供する DLL にリンクされている、`_DllMainCRTStartup`アタッチまたはデタッチ プロセスまたはスレッドに DLL への Windows OS メッセージを処理します。 `_DllMainCRTStartup`関数がスタック バッファーのセキュリティ設定、C ランタイム ライブラリ (CRT) の初期化と終了などの必須のタスクを実行し、静的およびグローバル オブジェクトに対してコンス トラクターとデストラクターを呼び出します。 `_DllMainCRTStartup` また呼び出しは、独自の初期化と終了を実行するには、WinRT、MFC や ATL などその他のライブラリの関数をフックします。 この初期化、CRT およびその他のライブラリと同様に、静的変数、なしと状態のままに、初期化されていません。 静的にリンクされた CRT または CRT DLL を動的にリンクされた DLL を使用しているかどうか、同じ VCRuntime の内部初期化および終了ルーチンが呼び出されます。  
  
## <a name="default-dll-entry-point-dllmaincrtstartup"></a>既定の DLL エントリ ポイント _DllMainCRTStartup  
  
Windows では、すべての Dll が通常と呼ばれる、省略可能なエントリ ポイント関数を含めることができます`DllMain`、つまりの初期化と終了の両方に対して呼び出されます。 これによって、追加のリソースを必要に応じて、割り当て/解放する機会が与えられます。 Windows には、エントリ ポイント関数が呼び出される 4 つの状況 (プロセスのアタッチ、プロセス デタッチ、スレッド アタッチ、スレッド デタッチ) があります。 それを使用するアプリケーションが読み込まれるときに、またはアプリケーションが実行時に DLL を要求したときに、プロセスのアドレス空間に DLL が読み込まれると、オペレーティング システムは DLL のデータの個別のコピーを作成します。 これと呼ばれる*プロセスのアタッチ*です。 *スレッドのアタッチ*プロセスで、DLL が読み込まれる新しいスレッドを作成するときに発生します。 *スレッドのデタッチ*スレッドが終了するときに発生し、*プロセスのデタッチ*は、DLL は必要なくなりましたとアプリケーションによってリリースされたときにします。 これらの各イベントを渡すのオペレーティング システムが DLL エントリ ポイントを個別に呼び出して、*理由*各イベントの種類の引数。 たとえば、OS が送信`DLL_PROCESS_ATTACH`として、*理由*プロセスの通知への引数をアタッチします。  
  
VCRuntime ライブラリには、呼び出されるエントリ ポイント関数が用意されています`_DllMainCRTStartup`既定の初期化と終了操作を処理します。 プロセスにアタッチ、`_DllMainCRTStartup`関数バッファー セキュリティ チェックを設定 CRT とその他のライブラリを初期化します、実行時の型情報を初期化を初期化し、静的および非ローカルのデータのコンス トラクターを呼び出しますスレッド ローカル ストレージを初期化します、各接続の静的内部カウンターをインクリメントし、ユーザーがまたはライブラリの指定を呼び出します`DllMain`です。 プロセスのデタッチ、関数が逆の順序で次の手順を通過します。 呼び出す`DllMain`デクリメント、内部カウンターにデストラクターを呼び出して、CRT の呼び出しの終了が機能し、登録されている`atexit`関数、および終了の他のすべてのライブラリに通知します。 関数を返します、添付ファイルのカウンターがゼロになる、 `FALSE` Windows に DLL が読み込まれたできることを示すためにします。 `_DllMainCRTStartup`関数はスレッドの中に呼び出されますもアタッチし、スレッドをデタッチします。 このような場合、VCRuntime コードではない追加の初期化または、それ自体に終了と呼び出すだけ`DllMain`に沿ってメッセージに渡します。 場合`DllMain`返します`FALSE`プロセスからアタッチ時、失敗の通知`_DllMainCRTStartup`呼び出し`DllMain`もう一度渡します`DLL_PROCESS_DETACH`として、*理由*引数、しを通過の残りの部分、終了プロセスです。  
  
Visual c で既定のエントリ ポイント Dll を作成するときに`_DllMainCRTStartup`によって提供される VCRuntime は自動的にリンクします。 使用して DLL のエントリ ポイント関数を指定する必要はありません、 [/ENTRY (エントリ ポイント シンボル)](../build/reference/entry-entry-point-symbol.md)リンカー オプション。  
  
> [!NOTE]
> Dll の場合、/ENTRY を使用して別のエントリ ポイント関数を指定することができますが: リンカー オプション、お勧めしませんが、エントリ ポイント関数が、すべてのものが重複しているためを`_DllMainCRTStartup`は、同じ順序で。 VCRuntime では、その動作を複製することができる関数を提供します。 たとえばを呼び出すことができます[_ _security_init_cookie](../c-runtime-library/reference/security-init-cookie.md)すぐにプロセスをサポートする添付、 [/GS (バッファー セキュリティ チェック)](../build/reference/gs-buffer-security-check.md)バッファー オプションをオンにします。 呼び出すことができます、`_CRT_INIT`関数、エントリ ポイント関数の DLL の初期化や終了処理関数の残りの部分を実行すると、同じパラメーターを渡すことです。  
  
<a name="initializing-a-dll"></a>  
  
## <a name="initialize-a-dll"></a>DLL の初期化  
  
DLL は、DLL の読み込み時に実行する必要がありますの初期化コードがあります。 独自 DLL の初期化と終了関数を実行するための順序で`_DllMainCRTStartup`という名前の関数を呼び出す`DllMain`提供できます。 `DllMain` DLL エントリ ポイントに必要なシグネチャを持つ必要があります。 既定のエントリ ポイント関数`_DllMainCRTStartup`呼び出し`DllMain`Windows によって渡されたのと同じパラメーターを使用しています。 既定では、指定しない場合、`DllMain`関数の場合、Visual C はいずれかを提供しでのリンクを示しますように`_DllMainCRTStartup`を呼び出すことが常にします。 つまり、DLL を初期化する必要がない場合があることを DLL のビルド時に行うには特にありません。  
  
これを使用する署名`DllMain`:  
  
```cpp  
#include <windows.h>  
  
extern "C" BOOL WINAPI DllMain (
    HINSTANCE const instance,  // handle to DLL module 
    DWORD     const reason,    // reason for calling function
    LPVOID    const reserved); // reserved
```  
  
一部のライブラリのラップ、`DllMain`する関数。 たとえば、正規の MFC DLL では、実装、`CWinApp`オブジェクトの`InitInstance`と`ExitInstance`初期化および DLL で必要な終了処理を実行するメンバー関数。 詳細については、次を参照してください。、 [MFC Dll の初期化 regular](#initializing-regular-dlls)セクションです。  
  
> [!WARNING]
> 安全に実行できる DLL エントリ ポイントでには、重要な制限があります。 参照してください[一般的なベスト プラクティス](https://msdn.microsoft.com/library/windows/desktop/dn633971#general_best_practices)で呼び出しても安全ではない特定の Windows Api の`DllMain`します。 派必要がある場合、最も簡単な初期化ことが初期化関数で、DLL の。 この関数を呼び出して初期化後にアプリケーションを要求できます`DllMain`が実行し、前に、関数を呼び出す他の DLL にします。  
  
<a name="initializing-non-mfc-dlls"></a>  
  
### <a name="initialize-ordinary-non-mfc-dlls"></a>通常 (MFC ではない) Dll を初期化します。  
  
VCRuntime 指定を使用する (MFC ではない) 通常の Dll で独自の初期化を実行する`_DllMainCRTStartup`エントリ ポイント DLL ソース コードが呼び出される関数を含める必要があります`DllMain`です。 次のコードの定義を示す基本的なスケルトン`DllMain`のようになります。  
  
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
> 以前の Windows SDK ドキュメントの質問、リンカーの/ENTRY オプションを使用してコマンドラインで DLL エントリ ポイント関数の実際の名前を指定する必要があります。 Visual C には、エントリ ポイント関数の名前がある場合は、/ENTRY オプションを使用する必要はありません`DllMain`です。 実際には、名前と/ENTRY オプションを使用する場合、エントリ ポイント以外の関数のもの`DllMain`、CRT は適切に初期化されません、エントリ ポイント関数が、同じ初期化呼び出しを行わない限り、`_DllMainCRTStartup`なります。  
  
<a name="initializing-regular-dlls"></a>  
  
### <a name="initialize-regular-mfc-dlls"></a>正規の MFC Dll を初期化します。  
  
標準の MFC Dll があるため、`CWinApp`オブジェクト、MFC アプリケーションと同じ場所に、初期化と終了のタスクを実行する必要があります: で、`InitInstance`と`ExitInstance`の DLL のメンバー関数は`CWinApp`-派生クラス。 MFC に用意されているため、`DllMain`関数によって呼び出される`_DllMainCRTStartup`の`DLL_PROCESS_ATTACH`と`DLL_PROCESS_DETACH`、独自に記述する必要がありますいない`DllMain`関数。 MFC 標準`DllMain`関数呼び出し`InitInstance`、DLL が読み込まれ、呼び出し`ExitInstance`DLL が読み込まれる前にします。  
  
正規の MFC DLL を監視できる複数のスレッドを呼び出して[TlsAlloc](http://msdn.microsoft.com/library/windows/desktop/ms686801)と[TlsGetValue](http://msdn.microsoft.com/library/windows/desktop/ms686812)でその`InitInstance`関数。 これらの関数は、スレッド固有のデータを追跡するために DLL を許可します。  
  
動的にリンクする MFC、またはを使用する、MFC OLE、MFC データベース (DAO)、または MFC ソケットをサポート、それぞれ、デバッグ MFC 拡張 Dll MFCO 正規 MFC DLL の*バージョン*D.dll、MFCD*バージョン*D.dll、および MFCN*バージョン*D.dll (ここで*バージョン*バージョン番号です) 自動的にリンクします。 呼び出す必要があります、次の定義済みの初期化関数のいずれかの標準 MFC DLL に使用しているこれらの Dll の各`CWinApp::InitInstance`です。  
  
|MFC サポートの種類|初期化関数を呼び出す|  
|-------------------------|-------------------------------------|  
|MFC OLE (MFCO*バージョン*D.dll)|`AfxOleInitModule`|  
|MFC データベース (MFCD*バージョン*D.dll)|`AfxDbInitModule`|  
|MFC ソケット (MFCN*バージョン*D.dll)|`AfxNetInitModule`|  
  
<a name="initializing-extension-dlls"></a>  
  
### <a name="initialize-mfc-extension-dlls"></a>MFC 拡張 Dll を初期化します。  
  
MFC 拡張 Dll があるないため、 `CWinApp`-派生オブジェクト (標準の MFC Dll の操作)、初期化と終了コードを追加する必要があります、 `DllMain` MFC DLL ウィザードを生成する関数。  
  
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
  
新たに作成する`CDynLinkLibrary`により、MFC 拡張をエクスポートする DLL は初期化中にオブジェクトを`CRuntimeClass`オブジェクトまたはクライアント アプリケーションにリソース。  
  
MFC 拡張 DLL を 1 つまたは複数の標準 MFC Dll からを使用する場合を作成する初期化関数をエクスポートする必要があります、`CDynLinkLibrary`オブジェクト。 MFC 拡張 DLL を使用する標準の MFC Dll のそれぞれからは、その関数を呼び出す必要があります。 初期化関数の呼び出しに適した場所は、`InitInstance`メンバー関数は、正規の MFC DLL の`CWinApp`-MFC 拡張 DLL のエクスポートされたクラスまたは関数のいずれかを使用する前にオブジェクトを派生します。  
  
`DllMain`を MFC DLL ウィザードで生成されたへの呼び出し`AfxInitExtensionModule`モジュールの実行時のクラスをキャプチャ (`CRuntimeClass`構造体) のオブジェクト ファクトリだけでなく (`COleObjectFactory`オブジェクト) のときに使用、`CDynLinkLibrary`オブジェクトを作成します。 戻り値を確認する必要があります`AfxInitExtensionModule`からゼロの値が返された場合です。 `AfxInitExtensionModule`、から 0 を返します、`DllMain`関数。  
  
MFC 拡張 DLL は、実行可能ファイルに明示的にリンクする場合 (つまり、実行可能ファイルが`AfxLoadLibrary`DLL へのリンクを) への呼び出しを追加する必要があります`AfxTermExtensionModule`で`DLL_PROCESS_DETACH`です。 この機能により、各プロセスは、MFC 拡張 DLL からデタッチするときに、MFC 拡張 DLL をクリーンアップする MFC (動作は、プロセスが終了するとき、またはの結果として、DLL がアンロードされたとき、`AfxFreeLibrary`呼び出します)。 MFC 拡張 DLL は、アプリケーションへの呼び出しに暗黙的にリンクされる場合`AfxTermExtensionModule`必要はありません。  
  
MFC 拡張 Dll へのリンクが明示的に呼び出す必要のあるアプリケーション`AfxTermExtensionModule`DLL を解放します。 使用する必要があります`AfxLoadLibrary`と`AfxFreeLibrary`(Win32 関数ではなく`LoadLibrary`と`FreeLibrary`) アプリケーションは、複数のスレッドを使用している場合。 使用して`AfxLoadLibrary`と`AfxFreeLibrary`スタートアップおよびシャット ダウン コード MFC 拡張 DLL の読み込みし、アンロードに MFC のグローバル状態が破損していないときに実行されることを確認します。  
  
時間によって、MFCx0.dll が完全に初期化されるため`DllMain`が呼び出されると、メモリを割り当てるして内の MFC 関数を呼び出す`DllMain`(MFC の 16 ビット バージョン) とは異なりです。  
  
拡張 Dll が注意を処理するマルチ スレッド、`DLL_THREAD_ATTACH`と`DLL_THREAD_DETACH`でケース、`DllMain`関数。 このような場合に渡される`DllMain`スレッドがアタッチし、DLL からデタッチします。 呼び出す[TlsAlloc](http://msdn.microsoft.com/library/windows/desktop/ms686801) DLL をアタッチするときと、スレッド ローカル ストレージ (TLS) は、DLL にアタッチされているすべてのスレッドのインデックスを維持するために、DLL ができます。  
  
Afxdllx.h ヘッダー ファイルには、構造体の定義などの MFC 拡張 Dll で使用されるに特別な定義が含まれています`AFX_EXTENSION_MODULE`と`CDynLinkLibrary`です。 MFC 拡張 DLL では、このヘッダー ファイルを含める必要があります。  
  
> [!NOTE]
>  ある定義も未定義のいずれかの重要である、 `_AFX_NO_XXX` Stdafx.h でマクロです。 これらのマクロは、特定のターゲット プラットフォームでは、か、その機能がサポートしているかどうかをチェックするためにのみ存在します。 これらのマクロをチェックするようプログラムを記述することができます (たとえば、 `#ifndef _AFX_NO_OLE_SUPPORT`)、プログラムが定義する必要がありますしない、またはこれらのマクロを未定義はします。  
  
マルチ スレッドのハンドルが含まれているサンプル初期化関数[を使用してスレッド ローカル ストレージ、ダイナミック リンク ライブラリで](http://msdn.microsoft.com/library/windows/desktop/ms686997)Windows SDK に含まれています。 サンプルが呼び出されるエントリ ポイント関数が含まれているメモ`LibMain`、この関数の名前が、 `DllMain` MFC および C ランタイム ライブラリで利用できるようにします。  
  
## <a name="see-also"></a>関連項目  
  
[Visual C++ の DLL](../build/dlls-in-visual-cpp.md)  
[DllMain のエントリ ポイント](https://msdn.microsoft.com/library/windows/desktop/ms682583.aspx)  
[ダイナミック リンク ライブラリのベスト プラクティス](https://msdn.microsoft.com/library/windows/desktop/dn633971.aspx)  