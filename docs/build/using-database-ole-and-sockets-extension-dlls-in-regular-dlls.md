---
title: 標準の MFC Dll でのデータベース、OLE、およびソケットの MFC 拡張 Dll の使用 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DLLs [C++], initializing
- DLLs [C++], extension
- DLLs [C++], regular
ms.assetid: 9f1d14a7-9e2a-4760-b3b6-db014fcdb7ff
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f902f3b512b5684cf185829fdf4346b8851ff8ba
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="using-database-ole-and-sockets-mfc-extension-dlls-in-regular-mfc-dlls"></a>標準の MFC Dll でのデータベース、OLE、およびソケットの MFC 拡張 Dll の使用
MFC 拡張 DLL がないワイヤード (有線) にする場合は、MFC 拡張 DLL を正規の MFC DLL からを使用する場合、 **CDynLinkLibrary**オブジェクトのチェーンの正規の MFC DLL の一連の関連する問題の 1 つ以上に実行する可能性があります。 MFC データベース、OLE、およびソケットのデバッグ バージョンをサポートしているため、Dll が MFC 拡張 Dll として実装されてを明示的に使用していない、独自の MFC 拡張 Dll のいずれかのいなくても、機能をこれらの MFC を使用している場合と同様の問題が発生する可能性があります。 いくつかの現象は次のとおりです。  
  
-   クラスの型のオブジェクトを逆シリアル化しようとしています。 定義されている場合、MFC 拡張 DLL を、メッセージ"警告: アーカイブから CYourClass を読み込むことができません。 クラス定義されていません。" シリアル化が失敗のトレースのデバッグ ウィンドウとオブジェクトに表示されます。  
  
-   無効なクラスを示す例外がスローされます。  
  
-   MFC 拡張 DLL に格納されているリソースを読み込みが失敗`AfxFindResourceHandle`返します**NULL**または正しくないリソース ハンドル。  
  
-   `DllGetClassObject`、 `DllCanUnloadNow`、および`UpdateRegistry`、 `Revoke`、 `RevokeAll`、および`RegisterAll`のメンバー関数は`COleObjectFactory`MFC 拡張 DLL で定義されているクラス ファクトリの検索に失敗します。  
  
-   `AfxDoForAllClasses` MFC 拡張 DLL 内のすべてのクラスに対しては機能しません。  
  
-   標準の MFC データベース、ソケットの場合、または OLE リソースを読み込めませんでした。 たとえば、 **AfxLoadString**(**AFX_IDP_SQL_CONNECT_FAIL**) 標準の MFC DLL が MFC データベース クラスを使用して正しく場合でも、空の文字列を返します。  
  
 これらの問題を解決作成し、MFC 拡張 DLL を作成する初期化関数をエクスポートするには、 **CDynLinkLibrary**オブジェクト。 MFC 拡張 DLL を使用する各正規の MFC DLL から 1 回だけ初期化関数の呼び出しです。  
  
## <a name="mfc-ole-mfc-database-or-dao-or-mfc-sockets-support"></a>MFC OLE、MFC データベース (または DAO)、または MFC ソケットのサポート  
 MFC ソケットがそれぞれ標準 MFC DLL のサポート、MFC OLE、MFC データベース (または DAO) を使用している、または、MFC デバッグ MFC 拡張 Dll MFCOxxD.dll、MFCDxxD.dll、および MFCNxxD.dll (xx はバージョン番号) は自動的にリンクします。 これらの Dll は、使用するごとに定義済みの初期化関数を呼び出す必要があります。  
  
 データベース サポートの呼び出しを追加して`AfxDbInitModule`正規 MFC dll の`CWinApp::InitInstance`関数。 この呼び出しは、基底クラスを呼び出す前に発生または MFCDxxD.dll をアクセスするコードを追加確認してください。 この関数は、パラメーターを受け取らないし、void を返します。  
  
 OLE サポートへの呼び出しを追加`AfxOleInitModule`正規 MFC dll の`CWinApp::InitInstance`します。 なお、 **COleControlModule InitInstance**関数呼び出し`AfxOleInitModule`既に、したがって OLE コントロールを構築してを使用している場合`COleControlModule`への呼び出しを追加しないでください`AfxOleInitModule`。  
  
 ソケットのサポートの呼び出しを追加して`AfxNetInitModule`正規 MFC dll の`CWinApp::InitInstance`します。  
  
 MFC Dll のリリース ビルドをことと、アプリケーションでは、ソケットの場合、データベースの個別の Dll を使用しないでくださいまたは OLE サポートを注意してください。 ただしをリリース モードでこれらの初期化関数を呼び出しても安全です。  
  
## <a name="cdynlinklibrary-objects"></a>CDynLinkLibrary オブジェクト  
 各このトピックの冒頭に示した操作中に、MFC は、目的の値またはオブジェクトを検索する必要があります。 たとえば、逆シリアル化中に MFC が、適切なランタイム クラスでアーカイブ内のオブジェクトと一致する現在使用可能なすべてのランタイム クラスを検索する必要があります。  
  
 MFC がのチェーンに、使用中のすべての MFC 拡張 Dll でのスキャンに、これらの検索の一部として**CDynLinkLibrary**オブジェクト。 **CDynLinkLibrary**オブジェクト、構築時に、チェーンに自動的にアタッチし、初期化中にさらに各 MFC 拡張 DLL によって作成されます。 さらに、(アプリケーションまたはレギュラー MFC DLL) のすべてのモジュールには、独自のチェーン**CDynLinkLibrary**オブジェクト。  
  
 MFC 拡張 DLL にワイヤード (有線) を取得するため、 **CDynLinkLibrary**チェーンを作成する必要があります、 **CDynLinkLibrary** MFC 拡張 DLL を使用するすべてのモジュールのコンテキスト内のオブジェクト。 そのため、MFC 拡張 DLL は標準の MFC Dll から使用することが場合が備わっていることを作成するエクスポートされた初期化関数、 **CDynLinkLibrary**オブジェクト。 MFC の拡張機能を使用する各レギュラー DLL は MFC DLL にエクスポートされた初期化関数を呼び出す必要があります。  
  
 MFC 拡張 DLL はのみ使用する予定 MFC アプリケーション (.exe) と標準の MFC DLL からしない場合は、それを作成するための十分な**CDynLinkLibrary** MFC 拡張 DLL 内のオブジェクト`DllMain`です。 これは、MFC DLL ウィザード MFC 拡張 DLL のコードの動作です。 MFC 拡張 DLL を暗黙的に、読み込み時に`DllMain`を読み込んで、アプリケーションが開始する前に実行します。 どの**CDynLinkLibrary**の作成は、ワイヤード (有線) 既定チェーンに、MFC DLL が MFC アプリケーションの予約をします。  
  
 複数を設定することは適切であることに注意してください**CDynLinkLibrary** MFC 拡張 DLL がメモリから動的に読み込まれます場合は特に、1 つのチェーン内の 1 つの MFC 拡張 DLL からのオブジェクトします。 初期化関数も複数回から呼び出さないで 1 つのモジュール。  
  
## <a name="sample-code"></a>サンプル コード  
 このサンプル コードでは、標準の MFC DLL が MFC 拡張 DLL にリンクが暗黙的に想定しています。 これは、標準の MFC DLL を作成するときに MFC 拡張 DLL のインポート ライブラリ (.lib) にリンクすることによって行います。  
  
 次の行は、MFC 拡張 DLL のソースにする必要があります。  
  
```  
// YourExtDLL.cpp:  
  
// standard MFC extension DLL routines  
#include "afxdllx.h"  
  
static AFX_EXTENSION_MODULE NEAR extensionDLL = { NULL, NULL };  
  
extern "C" int APIENTRY  
DllMain(HINSTANCE hInstance, DWORD dwReason, LPVOID lpReserved)  
{  
    if (dwReason == DLL_PROCESS_ATTACH)  
    {  
        // MFC extension DLL one-time initialization  
        if (!AfxInitExtensionModule(extensionDLL, hInstance))  
           return 0;  
    }  
    return 1;   // ok  
}  
  
// Exported DLL initialization is run in context of  
// application or regular MFC DLL  
extern "C" void WINAPI InitYourExtDLL()  
{  
    // create a new CDynLinkLibrary for this app  
    new CDynLinkLibrary(extensionDLL);  
  
    // add other initialization here  
}  
```  
  
 インポートできるように、 **InitYourExtDLL**関数。 こうことが使用して**方式**または次のように、DLL の .def ファイル内。  
  
```  
// YourExtDLL.Def:  
LIBRARY      YOUREXTDLL  
CODE         PRELOAD MOVEABLE DISCARDABLE  
DATA         PRELOAD SINGLE  
EXPORTS  
    InitYourExtDLL  
```  
  
 呼び出しを追加、`InitInstance`のメンバー、`CWinApp`の MFC 拡張 DLL を使用して各正規の MFC DLL 内のオブジェクトを派生します。  
  
```  
// YourRegularDLL.cpp:  
  
class CYourRegularDLL : public CWinApp  
{  
public:  
    virtual BOOL InitInstance(); // Initialization  
    virtual int ExitInstance();  // Termination  
  
    // nothing special for the constructor  
    CYourRegularDLL(LPCTSTR pszAppName) : CWinApp(pszAppName) { }  
};  
  
BOOL CYourRegularDLL::InitInstance()  
{  
    // any DLL initialization goes here  
    TRACE0("YOUR regular MFC DLL initializing\n");  
  
    // wire any MFC extension DLLs into CDynLinkLibrary chain  
    InitYourExtDLL();  
  
    return TRUE;  
}  
```  
  
### <a name="what-do-you-want-to-do"></a>実行する操作  
  
-   [MFC 拡張 DLL を初期化します。](../build/run-time-library-behavior.md#initializing-extension-dlls)  
  
-   [正規の MFC Dll を初期化します。](../build/run-time-library-behavior.md#initializing-regular-dlls)  
  
### <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください  
  
-   [MFC 拡張 DLL](../build/extension-dlls.md)  
  
-   [MFC と静的にリンクされるレギュラー MFC DLL](../build/regular-dlls-statically-linked-to-mfc.md)  
  
-   [MFC と動的にリンクされるレギュラー MFC DLL](../build/regular-dlls-dynamically-linked-to-mfc.md)  
  
-   [DLL の一部としての MFC を使用します。](../mfc/tn011-using-mfc-as-part-of-a-dll.md)  
  
-   [MFC の DLL バージョン](../mfc/tn033-dll-version-of-mfc.md)  
  
## <a name="see-also"></a>関連項目  
 [MFC 拡張 DLL](../build/extension-dlls.md)