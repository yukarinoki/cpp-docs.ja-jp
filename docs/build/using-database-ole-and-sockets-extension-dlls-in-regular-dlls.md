---
title: 標準 MFC DLL でのデータベース、OLE、およびソケット MFC 拡張 DLL の使用
description: 標準 MFC DLL のデータベース、OLE、およびソケット MFC 拡張 DLL を使用する方法について説明します。
ms.date: 11/30/2020
helpviewer_keywords:
- DLLs [C++], initializing
- DLLs [C++], extension
- DLLs [C++], regular
ms.openlocfilehash: a28e80c4d554a86f45f708e661382ee4a54eca9e
ms.sourcegitcommit: 432c24dde31c400437c4320e8432b1ddb232f844
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2020
ms.locfileid: "96440276"
---
# <a name="using-database-ole-and-sockets-mfc-extension-dlls-in-regular-mfc-dlls"></a>標準 MFC DLL でのデータベース、OLE、およびソケット MFC 拡張 DLL の使用

標準 MFC DLL から MFC 拡張 DLL を使用する場合、MFC 拡張 DLL が標準 MFC DLL の `CDynLinkLibrary` オブジェクト チェーンに接続されていないと、1 つまたは複数の関連する問題が発生する可能性があります。 MFC データベース、OLE、およびソケット対応 DLL のデバッグ バージョンは MFC 拡張 DLL として実装されているため、これらの MFC 機能を使用していると、独自の MFC 拡張 DLL を明示的に使用していなくても、同様の問題が発生する可能性があります。 次のような現象が発生します。

- MFC 拡張 DLL 内に定義されているクラスの型のオブジェクトを逆シリアル化しようとすると、"警告:アーカイブから CYourClass を読み込むことができません。 クラスが定義されていません。" というメッセージがトレース デバッグ ウィンドウに表示され、このオブジェクトのシリアル化に失敗します。

- 不正なクラスを示す例外がスローされる場合があります。

- `AfxFindResourceHandle` から `NULL` または正しくないリソース ハンドルが返されるため、MFC 拡張 DLL に格納されているリソースの読み込みに失敗します。

- `DllGetClassObject`、`DllCanUnloadNow`、および `COleObjectFactory` の `UpdateRegistry`、`Revoke`、`RevokeAll`、および `RegisterAll` メンバー関数で、MFC 拡張 DLL 内に定義されているクラス ファクトリを見つけることができません。

- `AfxDoForAllClasses` が MFC 拡張 DLL 内のクラスに対して機能しません。

- 標準の MFC データベース、ソケット、または OLE リソースの読み込みに失敗します。 たとえば、標準 MFC DLL で MFC データベース クラスが正しく使用されている場合でも、`AfxLoadString(AFX_IDP_SQL_CONNECT_FAIL)` から空の文字列が返されます。

これらの問題を解決するには、MFC 拡張 DLL 内に `CDynLinkLibrary` オブジェクトを作成する初期化関数を作成してエクスポートします。 MFC 拡張 DLL を使用する標準 MFC DLL から、この初期化関数を 1 回だけ呼び出します。

## <a name="mfc-ole-mfc-database-or-dao-or-mfc-sockets-support"></a>MFC OLE、MFC データベース (または DAO)、または MFC ソケットのサポート

標準 MFC DLL 内で MFC OLE、MFC データベース (または DAO)、または MFC ソケットのサポートを使用している場合は、それぞれ MFC デバッグ MFC 拡張 DLL *`MFCOxxD.dll`* 、 *`MFCDxxD.dll`* 、および *`MFCNxxD.dll`* (*xx* はバージョン番号) が自動的にリンクされます。 使用する DLL ごとに、定義済みの初期化関数を呼び出してください。

- データベース サポートの場合は、標準 MFC DLL の `CWinApp::InitInstance` 関数に `AfxDbInitModule` の呼び出しを追加します。 この呼び出しは、基本クラスの呼び出し、または *`MFCDxxD.dll`* にアクセスする追加コードの前に行うようにしてください。 この関数はパラメーターを取らず、`void` が返されます。

- OLE サポートの場合は、標準 MFC DLL の `CWinApp::InitInstance` 関数に `AfxOleInitModule` の呼び出しを追加します。 `COleControlModule::InitInstance` 関数では `AfxOleInitModule` が既に呼び出されているため、OLE コントロールを作成して `COleControlModule` を使用する場合は、この呼び出しを `AfxOleInitModule` に追加しないでください。

- ソケット サポートの場合は、標準 MFC DLL の `CWinApp::InitInstance` に `AfxNetInitModule` の呼び出しを追加します。

MFC DLL とアプリケーションのリリース ビルドでは、データベース、ソケット、または OLE のサポートに個別の DLL が使用されません。 ただし、リリース モードでは、これらの初期化関数を安全に呼び出すことができます。

## <a name="cdynlinklibrary-objects"></a>CDynLinkLibrary オブジェクト

この記事の始めに説明した各操作中、MFC では特定の値またはオブジェクトを検索する必要があります。 たとえば、逆シリアル化中は、MFC では、現在使用可能なすべてのランタイム クラスを検索して、アーカイブ内のオブジェクトを適切なランタイム クラスに一致させる必要があります。

これらの検索の一部として、MFC では、`CDynLinkLibrary` オブジェクトのチェーンをたどって、使用中のすべての MFC 拡張 DLL がスキャンされます。 `CDynLinkLibrary` オブジェクトは、構築中にチェーンに自動的にアタッチされ、次に初期化中に各 MFC 拡張 DLL によって作成されます。 すべてのモジュール (アプリケーションまたは標準 MFC DLL) には、`CDynLinkLibrary` オブジェクトの独自のチェーンがあります。

MFC 拡張 DLL を `CDynLinkLibrary` チェーンに接続するには、MFC 拡張 DLL を使用するすべてのモジュールのコンテキストで `CDynLinkLibrary` オブジェクトを作成する必要があります。 標準 MFC DLL で MFC 拡張 DLL を使用するには、拡張 DLL によって、`CDynLinkLibrary` オブジェクトを作成するエクスポートされた初期化関数が提供される必要があります。 MFC 拡張 DLL を使用するすべての標準 MFC DLL は、エクスポートされた初期化関数を呼び出す必要があります。

MFC 拡張 DLL を MFC アプリケーションからのみ使用し、標準 MFC DLL からは使用しない場合は、MFC 拡張 DLL の `DllMain` 関数に `CDynLinkLibrary` オブジェクトを作成するだけで十分です。 これは、MFC DLL ウィザードの MFC 拡張 DLL コードによって実行されることです。 MFC 拡張 DLL を暗黙的に読み込む場合は、アプリケーションが起動する前に `DllMain` が読み込まれ、実行されます。 `CDynLinkLibrary` の作成はすべて、MFC DLL が MFC アプリケーション用に予約する既定のチェーンに接続されます。

1 つのチェーン内の 1 つの MFC 拡張 DLL から複数の `CDynLinkLibrary` オブジェクトを持つことはお勧めしません。 MFC 拡張 DLL がメモリから動的にアンロードされる可能性がある場合は特にそうです。 初期化関数を 1 つのモジュールから複数回呼び出さないでください。

## <a name="sample-code"></a>サンプル コード

このサンプル コードでは、標準 MFC DLL が MFC 拡張 DLL に暗黙的にリンクしていることを前提としています。 暗黙的にリンクするには、標準 MFC DLL をビルドするときに、MFC 拡張 DLL のインポート ライブラリ (LIB ファイル) にリンクします。

以下の行を MFC 拡張 DLL のソースに含める必要があります。

```cpp
// YourExtDLL.cpp:

// standard MFC extension DLL routines
#include "afxdllx.h"

static AFX_EXTENSION_MODULE extensionDLL;

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

必ず **InitYourExtDLL** 関数をエクスポートしてください。 次に示すように、 **`__declspec(dllexport)`** を使用するか、DLL の DEF ファイルにエクスポートすることができます。

```def
// YourExtDLL.Def:
LIBRARY      YOUREXTDLL
CODE         PRELOAD MOVEABLE DISCARDABLE
DATA         PRELOAD SINGLE
EXPORTS
    InitYourExtDLL
```

MFC 拡張 DLL を使用して、標準 MFC DLL 内に `CWinApp` 派生オブジェクトの `InitInstance` メンバーへの呼び出しを追加します。

```cpp
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

- [MFC 拡張 DLL の初期化](run-time-library-behavior.md#initializing-extension-dlls)

- [標準 MFC DLL の初期化](run-time-library-behavior.md#initializing-regular-dlls)

### <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

- [MFC 拡張 DLL](extension-dlls.md)

- [MFC と静的にリンクされるレギュラー MFC DLL](regular-dlls-statically-linked-to-mfc.md)

- [MFC と動的にリンクされるレギュラー MFC DLL](regular-dlls-dynamically-linked-to-mfc.md)

- [DLL の構成要素としての MFC](../mfc/tn011-using-mfc-as-part-of-a-dll.md)

- [MFC の DLL バージョン](../mfc/tn033-dll-version-of-mfc.md)

## <a name="see-also"></a>関連項目

[MFC 拡張 DLL](extension-dlls.md)
