---
title: DLL を管理するためのマクロと関数
ms.date: 03/27/2019
helpviewer_keywords:
- module macros in MFC
ms.assetid: 303f4161-cb5e-4099-81ad-acdb11aa60fb
ms.openlocfilehash: 6945dcc02423516e8d1cee5d8c828c4ed5069bef
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365700"
---
# <a name="macros-and-functions-for-managing-dlls"></a>DLL を管理するためのマクロと関数

|||
|-|-|
|[AFX_EXT_CLASS]](#afx_ext_class)|クラスをエクスポートします。|
|[AFX_MANAGE_STATE](#afx_manage_state)|DLL 内のエクスポートされた関数を保護します。|
|[AfxOleInitModule](#afxoleinitmodule)|MFC に動的にリンクされている通常の MFC DLL から OLE サポートを提供します。|
|[AfxNetInitModule](#afxnetinitmodule)|MFC に動的にリンクされている通常の MFC DLL から MFC ソケットをサポートします。|
|[AfxGetAmbientActCtx](#afxgetambientactctx)|モジュールごとの状態フラグの現在の状態を取得します。|
|[AfxGetStaticModuleState](#afxgetstaticmodulestate)|初期化前のモジュール状態を設定したり、クリーンアップ後に以前のモジュール状態を復元します。|
|[AfxInitExtensionModule](#afxinitextensionmodule)|DLL を初期化します。|
|[AfxSetAmbientActCtx](#afxsetambientactctx)|モジュールごとの状態フラグを設定します。|
|[AfxTermExtensionModule](#afxtermextensionmodule)|各プロセスが DLL からデタッチされるときに MFC 拡張 DLL をクリーンアップできます。|

## <a name="afx_ext_class"></a><a name="afx_ext_class"></a>AFX_EXT_CLASS

[MFC 拡張 DLL は](../../build/extension-dlls.md)、マクロ AFX_EXT_CLASSを使用してクラスをエクスポートします。MFC 拡張 DLL にリンクする実行可能ファイルは、マクロを使用してクラスをインポートします。

### <a name="remarks"></a>解説

AFX_EXT_CLASS マクロでは、MFC 拡張 DLL のビルドに使用したのと同じヘッダー ファイルを、DLL にリンクする実行可能ファイルと共に使用できます。

DLL のヘッダー ファイルで、次のようにクラスの宣言に AFX_EXT_CLASS キーワードを追加します。

```cpp
class AFX_EXT_CLASS CMyClass : public CDocument
{
// <body of class>
};
```

詳細については、「 AFX_EXT_CLASS を[使用してエクスポートおよびインポート](../../build/exporting-and-importing-using-afx-ext-class.md)する 」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxv_dll.h

## <a name="afx_manage_state"></a><a name="afx_manage_state"></a>AFX_MANAGE_STATE

DLL 内のエクスポートされた関数を保護するには、このマクロを呼び出します。

### <a name="syntax"></a>構文

```
AFX_MANAGE_STATE(AFX_MODULE_STATE* pModuleState )
```

### <a name="parameters"></a>パラメーター

*状態*<br/>
`AFX_MODULE_STATE`構造体へのポインター。

### <a name="remarks"></a>解説

このマクロが呼び出されると *、pModuleState*は、直接含まれるスコープの残りの部分の有効なモジュール状態です。 スコープを離れると、以前の有効なモジュールの状態が自動的に復元されます。
構造体`AFX_MODULE_STATE`には、モジュールのグローバル データ、つまり、プッシュまたはポップされたモジュール状態の部分が含まれます。

既定では、MFC はメイン アプリケーションのリソース ハンドルを使用してリソース テンプレートを読み込みます。 DLL 内のダイアログ ボックスを起動する関数など、DLL にエクスポートされた関数がある場合、このテンプレートは実際には DLL モジュールに格納されます。 正しいハンドルを使用するには、モジュールの状態を切り替える必要があります。 これを行うには、関数の先頭に次のコードを追加します。

```cpp
AFX_MANAGE_STATE(AfxGetStaticModuleState( ));
```

これにより、現在のモジュールの状態が、現在のスコープの終了まで[AfxGetStaticModuleState](#afxgetstaticmodulestate)から返された状態とスワップされます。

モジュールの状態と MFC の詳細については、「[新しいドキュメント、Windows、およびビューの作成](../creating-new-documents-windows-and-views.md)」の「MFC モジュールの状態データの管理」および「[テクニカル ノート 58](../tn058-mfc-module-state-implementation.md)」を参照してください。

> [!NOTE]
> MFC は、アセンブリのアクティブ化コンテキストを作成するときに[、AfxWinInit](application-information-and-management.md#afxwininit)を使用して`AFX_MANAGE_STATE`コンテキストを作成し、アクティブ化および非アクティブ化します。 また、MFC `AFX_MANAGE_STATE` DLL によって選択された適切なアクティベーション コンテキストで MFC コードを実行できるようにするために、MFC DLL だけでなく、静的 MFC ライブラリにも有効です。 詳細については、「 [MFC モジュールの状態でのアクティブ化コンテキストのサポート](../support-for-activation-contexts-in-the-mfc-module-state.md)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxstat_.h

## <a name="a-nameafxoleinitmodule-afxoleinitmodule"></a><a name="afxoleinitmodule"><a/>モジュール

MFC に動的にリンクされている通常の MFC DLL から OLE をサポートする場合は、MFC`CWinApp::InitInstance`の関数でこの関数を呼び出して MFC OLE DLL を初期化します。

### <a name="syntax"></a>構文

```
void AFXAPI AfxOleInitModule( );
```

### <a name="remarks"></a>解説

MFC OLE DLL は MFC 拡張 DLL です。MFC 拡張 DLL が`CDynLinkLibrary`チェーンに接続するためには、それを使用するすべてのモジュールのコンテキスト`CDynLinkLibrary`でオブジェクトを作成する必要があります。 `AfxOleInitModule`通常の`CDynLinkLibrary`MFC DLL のコンテキストでオブジェクトを作成し、通常の MFC `CDynLinkLibrary` DLL のオブジェクト チェーンに接続します。

OLE コントロールを作成していて、 を使用`COleControlModule`している場合は、`AfxOleInitModule`呼び`InitInstance`出しの`COleControlModule`メンバー`AfxOleInitModule`関数を呼び出す必要があります。

### <a name="requirements"></a>必要条件

**ヘッダー** \<: afxdll_.h>

## <a name="afxnetinitmodule"></a><a name="afxnetinitmodule"></a>アfxネットイニトモジュール

MFC ソケットサポートは、MFC に動的にリンクされている通常の MFC DLL から、MFC ソケット DLL を初期化する`CWinApp::InitInstance`通常の MFC DLL の関数でこの関数への呼び出しを追加します。

### <a name="syntax"></a>構文

```
void AFXAPI AfxNetInitModule( );
```

### <a name="remarks"></a>解説

MFC ソケット DLL は MFC 拡張 DLL です。MFC 拡張 DLL が`CDynLinkLibrary`チェーンに接続するためには、それを使用するすべてのモジュールのコンテキスト`CDynLinkLibrary`でオブジェクトを作成する必要があります。 `AfxNetInitModule`通常の`CDynLinkLibrary`MFC DLL のコンテキストでオブジェクトを作成し、通常の MFC `CDynLinkLibrary` DLL のオブジェクト チェーンに接続します。

### <a name="requirements"></a>必要条件

**ヘッダー:** \<afxdll_.h>

## <a name="afxgetambientactctx"></a><a name="afxgetambientactctx"></a>アfxゲットアンビエントアクトクトクト

この関数を使用して、MFC の WinSxS 動作に影響を与えるモジュールごとの状態フラグの現在の状態を取得します。

### <a name="syntax"></a>構文

```
BOOL AFXAPI AfxGetAmbientActCtx();
```

### <a name="return-value"></a>戻り値

モジュール状態フラグの現在の値。

### <a name="remarks"></a>解説

フラグが設定されている (既定) と、スレッドが MFC モジュールに入ると[(AFX_MANAGE_STATE](#afx_manage_state)を参照)、モジュールのコンテキストがアクティブになります。

フラグが設定されていない場合、モジュールのコンテキストは、エントリ時にアクティブ化されません。

モジュールのコンテキストは、通常はモジュール リソースに埋め込まれたマニフェストから決定されます。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxcomctl32.h

## <a name="afxgetstaticmodulestate"></a><a name="afxgetstaticmodulestate"></a>状態を取得します。

初期化前にモジュールの状態を設定したり、クリーンアップ後に以前のモジュール状態を復元したりするために、この関数を呼び出します。

### <a name="syntax"></a>構文

```
AFX_MODULE_STATE* AFXAPI AfxGetStaticModuleState( );
```

### <a name="return-value"></a>戻り値

`AFX_MODULE_STATE`構造体へのポインター。

### <a name="remarks"></a>解説

構造体`AFX_MODULE_STATE`には、モジュールのグローバル データ、つまり、プッシュまたはポップされたモジュール状態の部分が含まれます。

既定では、MFC はメイン アプリケーションのリソース ハンドルを使用してリソース テンプレートを読み込みます。 DLL 内のダイアログ ボックスを起動する関数など、DLL にエクスポートされた関数がある場合、このテンプレートは実際には DLL モジュールに格納されます。 正しいハンドルを使用するには、モジュールの状態を切り替える必要があります。 これを行うには、関数の先頭に次のコードを追加します。

```cpp
AFX_MANAGE_STATE(AfxGetStaticModuleState( ));
```

これにより、現在のモジュールの状態が現在のスコープの`AfxGetStaticModuleState`終了まで返された状態とスワップされます。

モジュールの状態と MFC の詳細については、「[新しいドキュメント、Windows、およびビューの作成](../creating-new-documents-windows-and-views.md)」の「MFC モジュールの状態データの管理」および「[テクニカル ノート 58](../tn058-mfc-module-state-implementation.md)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxstat_.h

## <a name="afxinitextensionmodule"></a>AfxInitExtensionModule

MFC 拡張 DLL でこの関数を呼`DllMain`び出して、DLL を初期化します。

### <a name="syntax"></a>構文

```
BOOL AFXAPI AfxInitExtensionModule( AFX_EXTENSION_MODULE& state,  HMODULE hModule );
```

### <a name="parameters"></a>パラメーター

*状態*<br/>
初期化後に MFC 拡張 DLL モジュールの状態を格納する[AFX_EXTENSION_MODULE構造体](afx-extension-module-structure.md)構造体への参照。 状態には、前`DllMain`に実行される通常の静的オブジェクトの構築の一部として MFC 拡張 DLL によって初期化されたランタイム クラス オブジェクトのコピーが含まれます。

*hモジュール*<br/>
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

`AfxInitExtensionModule`DLL の HMODULE のコピーを作成し、後でオブジェクトが作成されるときに使用するために`CRuntimeClass`、DLL のランタイム クラス (構造体`COleObjectFactory`) とそのオブジェクト ファクトリ`CDynLinkLibrary`(オブジェクト) をキャプチャします。
MFC 拡張 DLL は、次の`DllMain`2 つの操作を実行する必要があります。

- を呼び出し[、](#afxinitextensionmodule)戻り値を確認します。

- DLL`CDynLinkLibrary`が[CRuntimeClass 構造体](cruntimeclass-structure.md)オブジェクトをエクスポートする場合、または独自のカスタム リソースを持つ場合は、オブジェクトを作成します。

各プロセスが`AfxTermExtensionModule`MFC 拡張 DLL からデタッチされるときに MFC 拡張 DLL をクリーンアップするために`AfxFreeLibrary`呼び出すことができます (これは、プロセスが終了したとき、または呼び出しの結果として DLL がアンロードされたときに発生します)。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdll_.h

## <a name="afxsetambientactctx"></a><a name="afxsetambientactctx"></a>アfxセットアンビエントアククトクト

この関数を使用して、MFC の WinSxS 動作に影響するモジュールごとの状態フラグを設定します。

### <a name="syntax"></a>構文

```
void AFXAPI AfxSetAmbientActCtx(BOOL bSet);
```

### <a name="parameters"></a>パラメーター

*bセット*<br/>
モジュール状態フラグの新しい値。

### <a name="remarks"></a>解説

フラグが設定されている (既定) と、スレッドが MFC モジュールに入ると[(AFX_MANAGE_STATE](#afx_manage_state)を参照)、モジュールのコンテキストがアクティブになります。
フラグが設定されていない場合、モジュールのコンテキストは、エントリ時にアクティブ化されません。
モジュールのコンテキストは、通常はモジュール リソースに埋め込まれたマニフェストから決定されます。

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

## <a name="afxtermextensionmodule"></a><a name="afxtermextensionmodule"></a>エクステンションモジュール

各プロセスが DLL からデタッチ (プロセスが終了したとき、または呼び出しの結果として DLL がアンロードされたときに発生する) 場合に MFC 拡張 DLL`AfxFreeLibrary`をクリーンアップするには、この関数を呼び出します。

### <a name="syntax"></a>構文

```
void AFXAPI AfxTermExtensionModule(  AFX_EXTENSION_MODULE& state,  BOOL bAll  = FALSE );
```

### <a name="parameters"></a>パラメーター

*状態*<br/>
MFC 拡張 DLL モジュールの状態を格納する[AFX_EXTENSION_MODULE](afx-extension-module-structure.md)構造体への参照。

*ボール*<br/>
TRUE の場合は、MFC 拡張 DLL モジュールをすべてクリーンアップします。 それ以外の場合は、現在の DLL モジュールのみをクリーンアップします。

### <a name="remarks"></a>解説

`AfxTermExtensionModule`モジュールに接続されているローカル ストレージを削除し、メッセージ マップ キャッシュからエントリを削除します。 次に例を示します。

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

アプリケーションで MFC 拡張 DLL を動的に読み込んで解放する`AfxTermExtensionModule`場合は、 を呼び出してください。 ほとんどの MFC 拡張 DLL は動的に読み込まれていないため (通常はインポート ライブラリを介`AfxTermExtensionModule`してリンクされます)、呼び出しは通常必要ありません。

MFC 拡張 DLL は、その中で[AfxInitExtensionModule](#afxinitextensionmodule)を呼び出す必要があります`DllMain`。 DLL が[CRuntimeClass](cruntimeclass-structure.md)オブジェクトをエクスポートする場合、または独自のカスタム リソースを持つ場合`CDynLinkLibrary`は、`DllMain`でオブジェクトを作成する必要もあります。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdll_.h

## <a name="see-also"></a>関連項目

[マクロとグローバル](mfc-macros-and-globals.md)<br/>
[AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox)<br/>
[MFC モジュールの状態データの管理](../managing-the-state-data-of-mfc-modules.md)<br/>
