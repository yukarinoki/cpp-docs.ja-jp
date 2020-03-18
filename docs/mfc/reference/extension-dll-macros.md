---
title: Dll を管理するためのマクロと関数
ms.date: 03/27/2019
helpviewer_keywords:
- module macros in MFC
ms.assetid: 303f4161-cb5e-4099-81ad-acdb11aa60fb
ms.openlocfilehash: b27f8763b60dc7ce3ee074cad1365e7e1de3a7e6
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2020
ms.locfileid: "79426697"
---
# <a name="macros-and-functions-for-managing-dlls"></a>Dll を管理するためのマクロと関数

|||
|-|-|
|[AFX_EXT_CLASS](#afx_ext_class)]|クラスをエクスポートします。|
|[AFX_MANAGE_STATE](#afx_manage_state)|DLL 内のエクスポート関数を保護します。|
|[AfxOleInitModule](#afxoleinitmodule)|MFC に動的にリンクされている通常の MFC DLL から OLE サポートを提供します。|
|[AfxNetInitModule](#afxnetinitmodule)|Mfc に動的にリンクされるレギュラー MFC DLL からの MFC ソケットサポートを提供します。|
|[AfxGetAmbientActCtx](#afxgetambientactctx)|モジュールごとの状態フラグの現在の状態を取得します。|
|[AfxGetStaticModuleState](#afxgetstaticmodulestate)|初期化の前にモジュールの状態を設定するか、クリーンアップ後に前のモジュールの状態を復元します。|
|[AfxInitExtensionModule](#afxinitextensionmodule)|DLL を初期化します。|
|[AfxSetAmbientActCtx](#afxsetambientactctx)|モジュールごとの状態フラグを設定します。これは、MFC の WinSxS 動作に影響します。|
|[AfxTermExtensionModule](#afxtermextensionmodule)|各プロセスが DLL からデタッチされたときに mfc 拡張 DLL をクリーンアップできるようにします。|

## <a name="afx_ext_class"></a>AFX_EXT_CLASS

[MFC 拡張 dll](../../build/extension-dlls.md)では、マクロ AFX_EXT_CLASS を使用してクラスをエクスポートします。MFC 拡張 DLL にリンクする実行可能ファイルは、マクロを使用してクラスをインポートします。

### <a name="remarks"></a>解説

AFX_EXT_CLASS マクロでは、MFC 拡張 DLL のビルドに使用されるものと同じヘッダーファイルを、DLL にリンクする実行可能ファイルと共に使用できます。

DLL のヘッダーファイルで、次のように、クラスの宣言に AFX_EXT_CLASS キーワードを追加します。

```cpp
class AFX_EXT_CLASS CMyClass : public CDocument
{
// <body of class>
};
```

詳細については、「 [AFX_EXT_CLASS を使用したエクスポートとインポート](../../build/exporting-and-importing-using-afx-ext-class.md)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxv_dll

## <a name="afx_manage_state"></a>AFX_MANAGE_STATE

DLL 内のエクスポートされた関数を保護するには、このマクロを呼び出します。

### <a name="syntax"></a>構文

```
AFX_MANAGE_STATE(AFX_MODULE_STATE* pModuleState )
```

### <a name="parameters"></a>パラメーター

*pModuleState*<br/>
`AFX_MODULE_STATE` 構造体へのポインター。

### <a name="remarks"></a>解説

このマクロが呼び出されると、 *pModuleState*は、すぐ外側のスコープの残りの部分に対する有効なモジュール状態になります。 スコープを離れると、以前の有効なモジュールの状態が自動的に復元されます。
`AFX_MODULE_STATE` 構造体には、モジュールのグローバルデータ、つまり、プッシュまたはポップされたモジュールの状態の部分が含まれます。

既定では、MFC はメインアプリケーションのリソースハンドルを使用して、リソーステンプレートを読み込みます。 Dll 内のダイアログボックスを起動する関数など、DLL にエクスポートされた関数がある場合、このテンプレートは実際には DLL モジュールに格納されます。 適切なハンドルが使用されるようにするには、モジュールの状態を切り替える必要があります。 これを行うには、関数の先頭に次のコードを追加します。

```cpp
AFX_MANAGE_STATE(AfxGetStaticModuleState( ));
```

これにより、現在のモジュールの状態が、現在のスコープの末尾まで[AfxGetStaticModuleState](#afxgetstaticmodulestate)から返された状態と交換されます。

モジュールの状態と MFC の詳細については、「[新しいドキュメント、ウィンドウ、およびビューの作成](../creating-new-documents-windows-and-views.md)」および「[テクニカルノート 58](../tn058-mfc-module-state-implementation.md)」の「Mfc モジュールの状態データの管理」を参照してください。

> [!NOTE]
>  MFC がアセンブリのアクティベーションコンテキストを作成するときに、 [AfxWinInit](application-information-and-management.md#afxwininit)を使用してコンテキストを作成し、それをアクティブ化および非アクティブ化するように `AFX_MANAGE_STATE` します。 また、mfc コードがユーザー DLL によって選択された適切なアクティベーションコンテキストで実行できるようにするために、静的な MFC ライブラリおよび MFC Dll に対して `AFX_MANAGE_STATE` が有効になっていることにも注意してください。 詳細については、「 [MFC モジュール状態でのアクティベーションコンテキストのサポート](../support-for-activation-contexts-in-the-mfc-module-state.md)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxstat_

## <a name="a-nameafxoleinitmodulea-afxoleinitmodule"></a><a name="afxoleinitmodule"><a/> AfxOleInitModule

MFC に動的にリンクされている通常の MFC DLL から OLE をサポートするには、mfc OLE DLL を初期化するために、通常の MFC DLL の `CWinApp::InitInstance` 関数でこの関数を呼び出します。

### <a name="syntax"></a>構文

```
void AFXAPI AfxOleInitModule( );
```

### <a name="remarks"></a>解説

MFC OLE DLL は、MFC 拡張 DLL です。MFC 拡張 DLL を `CDynLinkLibrary` チェーンに接続するには、それを使用するすべてのモジュールのコンテキストで `CDynLinkLibrary` オブジェクトを作成する必要があります。 `AfxOleInitModule` は、標準の mfc dll のコンテキストで `CDynLinkLibrary` オブジェクトを作成し、通常の MFC DLL の `CDynLinkLibrary` オブジェクトチェーンに接続できるようにします。

OLE コントロールを構築していて `COleControlModule`を使用している場合は、`COleControlModule` の `InitInstance` メンバー関数が `AfxOleInitModule`を呼び出すため、`AfxOleInitModule` を呼び出さないでください。

### <a name="requirements"></a>必要条件

**ヘッダー**: \<afxdll_ >

## <a name="afxnetinitmodule"></a>AfxNetInitModule

Mfc に動的にリンクされるレギュラー MFC DLL からの MFC ソケットのサポートについては、MFC ソケット DLL を初期化するために、通常の MFC DLL の `CWinApp::InitInstance` 関数でこの関数の呼び出しを追加します。

### <a name="syntax"></a>構文

```
void AFXAPI AfxNetInitModule( );
```

### <a name="remarks"></a>解説

MFC ソケット DLL は、MFC 拡張 DLL です。MFC 拡張 DLL を `CDynLinkLibrary` チェーンに接続するには、それを使用するすべてのモジュールのコンテキストで `CDynLinkLibrary` オブジェクトを作成する必要があります。 `AfxNetInitModule` は、標準の mfc dll のコンテキストで `CDynLinkLibrary` オブジェクトを作成し、通常の MFC DLL の `CDynLinkLibrary` オブジェクトチェーンに接続できるようにします。

### <a name="requirements"></a>必要条件

**ヘッダー:** \<afxdll_ >

## <a name="afxgetambientactctx"></a>AfxGetAmbientActCtx

この関数を使用して、モジュールごとの状態フラグの現在の状態を取得します。これは、MFC の WinSxS 動作に影響します。

### <a name="syntax"></a>構文

```
BOOL AFXAPI AfxGetAmbientActCtx();
```

### <a name="return-value"></a>戻り値

モジュール状態フラグの現在の値。

### <a name="remarks"></a>解説

フラグが設定されている場合 (既定)、スレッドが MFC モジュールに入っている (「 [AFX_MANAGE_STATE](#afx_manage_state)」を参照) と、モジュールのコンテキストがアクティブ化されます。

フラグが設定されていない場合、モジュールのコンテキストはエントリでアクティブ化されません。

モジュールのコンテキストは、通常、モジュールリソースに埋め込まれているマニフェストから決定されます。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxcomctl32.h

## <a name="afxgetstaticmodulestate"></a>AfxGetStaticModuleState

初期化の前にモジュールの状態を設定するか、クリーンアップ後に前のモジュールの状態を復元するために、この関数を呼び出します。

### <a name="syntax"></a>構文

```
AFX_MODULE_STATE* AFXAPI AfxGetStaticModuleState( );
```

### <a name="return-value"></a>戻り値

`AFX_MODULE_STATE` 構造体へのポインター。

### <a name="remarks"></a>解説

`AFX_MODULE_STATE` 構造体には、モジュールのグローバルデータ、つまり、プッシュまたはポップされたモジュールの状態の部分が含まれます。

既定では、MFC はメインアプリケーションのリソースハンドルを使用して、リソーステンプレートを読み込みます。 Dll 内のダイアログボックスを起動する関数など、DLL にエクスポートされた関数がある場合、このテンプレートは実際には DLL モジュールに格納されます。 適切なハンドルが使用されるようにするには、モジュールの状態を切り替える必要があります。 これを行うには、関数の先頭に次のコードを追加します。

```cpp
AFX_MANAGE_STATE(AfxGetStaticModuleState( ));
```

これにより、現在のモジュールの状態が、現在のスコープの末尾まで `AfxGetStaticModuleState` から返された状態と交換されます。

モジュールの状態と MFC の詳細については、「[新しいドキュメント、ウィンドウ、およびビューの作成](../creating-new-documents-windows-and-views.md)」および「[テクニカルノート 58](../tn058-mfc-module-state-implementation.md)」の「Mfc モジュールの状態データの管理」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxstat_

## <a name="afxinitextensionmodule"></a>AfxInitExtensionModule

DLL を初期化するには、MFC 拡張 DLL の `DllMain` でこの関数を呼び出します。

### <a name="syntax"></a>構文

```
BOOL AFXAPI AfxInitExtensionModule( AFX_EXTENSION_MODULE& state,  HMODULE hModule );
```

### <a name="parameters"></a>パラメーター

*状態*<br/>
初期化後の MFC 拡張 DLL モジュールの状態を格納する[AFX_EXTENSION_MODULE 構造](afx-extension-module-structure.md)体への参照。 状態には、`DllMain` が入力される前に実行される通常の静的オブジェクト構築の一部として、MFC 拡張 DLL によって初期化されたランタイムクラスオブジェクトのコピーが含まれます。

*hModule*<br/>
MFC 拡張 DLL モジュールのハンドル。

### <a name="return-value"></a>戻り値

MFC 拡張 DLL が正常に初期化された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

次に例を示します。

```cpp
static AFX_EXTENSION_MODULE NVC_MFC_DLLDLL = { NULL, NULL };
extern "C" int APIENTRY
DllMain(HINSTANCE hInstance, DWORD dwReason, LPVOID lpReserved)
{
    // Remove this if you use lpReserved
    UNREFERENCED_PARAMETER(lpReserved);

    if (dwReason == DLL_PROCESS_ATTACH)
    {
        TRACE0("NVC_MFC_DLL.DLL Initializing!\n");

        // MFC extension DLL one-time initialization
        if (!AfxInitExtensionModule(NVC_MFC_DLLDLL, hInstance))
            return 0;
...
```

`AfxInitExtensionModule` は、DLL の HMODULE のコピーを作成し、DLL のランタイムクラス (`CRuntimeClass` 構造) とそのオブジェクトファクトリ (`COleObjectFactory` オブジェクト) をキャプチャして、後で `CDynLinkLibrary` オブジェクトを作成するときに使用します。
MFC 拡張 Dll では、`DllMain` 関数で次の2つの処理を行う必要があります。

- [AfxInitExtensionModule](#afxinitextensionmodule)を呼び出し、戻り値を確認します。

- DLL が[CRuntimeClass Structure](cruntimeclass-structure.md)オブジェクトをエクスポートする場合、または独自のカスタムリソースがある場合は、`CDynLinkLibrary` オブジェクトを作成します。

各プロセスが MFC 拡張 DLL からデタッチされたとき (プロセスが終了したとき、または DLL が `AfxFreeLibrary` 呼び出しの結果としてアンロードされたとき) に、`AfxTermExtensionModule` を呼び出して MFC 拡張 DLL をクリーンアップできます。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdll_

## <a name="afxsetambientactctx"></a>AfxSetAmbientActCtx

モジュールごとの状態フラグを設定するには、この関数を使用します。これは、MFC の WinSxS 動作に影響します。

### <a name="syntax"></a>構文

```
void AFXAPI AfxSetAmbientActCtx(BOOL bSet);
```

### <a name="parameters"></a>パラメーター

*bSet*<br/>
モジュール状態フラグの新しい値。

### <a name="remarks"></a>解説

フラグが設定されている場合 (既定)、スレッドが MFC モジュールに入っている (「 [AFX_MANAGE_STATE](#afx_manage_state)」を参照) と、モジュールのコンテキストがアクティブ化されます。
フラグが設定されていない場合、モジュールのコンテキストはエントリでアクティブ化されません。
モジュールのコンテキストは、通常、モジュールリソースに埋め込まれているマニフェストから決定されます。

### <a name="example"></a>例

```cpp
BOOL CMFCListViewApp::InitInstance()
{
   AfxSetAmbientActCtx(FALSE);
   // Remainder of function definition omitted.
}
```

### <a name="requirements"></a>必要条件

**ヘッダー:** afxcomctl32.h

## <a name="afxtermextensionmodule"></a>AfxTermExtensionModule

この関数を呼び出して、各プロセスが DLL からデタッチされたときに mfc 拡張 DLL をクリーンアップできるようにします。これは、プロセスが終了したとき、または DLL が `AfxFreeLibrary` 呼び出しの結果としてアンロードされたときに発生します。

### <a name="syntax"></a>構文

```
void AFXAPI AfxTermExtensionModule(  AFX_EXTENSION_MODULE& state,  BOOL bAll  = FALSE );
```

### <a name="parameters"></a>パラメーター

*状態*<br/>
MFC 拡張 DLL モジュールの状態を格納している[AFX_EXTENSION_MODULE](afx-extension-module-structure.md)構造体への参照。

*遊び*<br/>
TRUE の場合は、すべての MFC 拡張 DLL モジュールをクリーンアップします。 それ以外の場合は、現在の DLL モジュールだけをクリーンアップします。

### <a name="remarks"></a>解説

モジュールにアタッチされているすべてのローカルストレージを削除し、メッセージマップキャッシュからエントリを削除 `AfxTermExtensionModule` ます。 次に例を示します。

```cpp
static AFX_EXTENSION_MODULE NVC_MFC_DLLDLL = { NULL, NULL };
extern "C" int APIENTRY
DllMain(HINSTANCE hInstance, DWORD dwReason, LPVOID lpReserved)
{
    // Remove this if you use lpReserved
    UNREFERENCED_PARAMETER(lpReserved);

    if (dwReason == DLL_PROCESS_ATTACH)
    {
        TRACE0("NVC_MFC_DLL.DLL Initializing!\n");

        // MFC extension DLL one-time initialization
        if (!AfxInitExtensionModule(NVC_MFC_DLLDLL, hInstance))
            return 0;

        new CMyDynLinkLibrary(NVC_MFC_DLLDLL);

    }
    else if (dwReason == DLL_PROCESS_DETACH)
    {
        TRACE0("NVC_MFC_DLL.DLL Terminating!\n");

        // Terminate the library before destructors are called
        AfxTermExtensionModule(NVC_MFC_DLLDLL);
    }
    return 1;   // ok
}
```

アプリケーションで MFC 拡張 Dll を動的に読み込んで解放する場合は、必ず `AfxTermExtensionModule`を呼び出してください。 ほとんどの MFC 拡張 Dll は動的に読み込まれない (通常はインポートライブラリを使用してリンクされている) ため、`AfxTermExtensionModule` の呼び出しは通常必要ありません。

MFC 拡張 Dll では、`DllMain`で[AfxInitExtensionModule](#afxinitextensionmodule)を呼び出す必要があります。 DLL が[CRuntimeClass](cruntimeclass-structure.md)オブジェクトをエクスポートする場合、または独自のカスタムリソースがある場合は、`DllMain`で `CDynLinkLibrary` オブジェクトを作成する必要もあります。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdll_

## <a name="see-also"></a>参照

[マクロとグローバル](mfc-macros-and-globals.md)<br/>
[AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox)<br/>
[MFC モジュールの状態データの管理](../managing-the-state-data-of-mfc-modules.md)<br/>
