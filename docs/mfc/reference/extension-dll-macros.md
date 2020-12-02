---
title: Dll を管理するためのマクロと関数
description: Dll を管理するための MFC マクロと関数のリファレンスガイドです。
ms.date: 11/30/2020
helpviewer_keywords:
- module macros in MFC
ms.openlocfilehash: b70c4506d49f656e1570f2500cfaa39c28053291
ms.sourcegitcommit: 432c24dde31c400437c4320e8432b1ddb232f844
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2020
ms.locfileid: "96440326"
---
# <a name="macros-and-functions-for-managing-dlls"></a>Dll を管理するためのマクロと関数

| 名前 | 説明 |
|--|--|
| [`AFX_EXT_CLASS`](#afx_ext_class)] | クラスをエクスポートします。 |
| [`AFX_MANAGE_STATE`](#afx_manage_state) | DLL 内のエクスポート関数を保護します。 |
| [`AfxOleInitModule`](#afxoleinitmodule) | MFC に動的にリンクされている通常の MFC DLL から OLE サポートを提供します。 |
| [`AfxNetInitModule`](#afxnetinitmodule) | Mfc に動的にリンクされるレギュラー MFC DLL からの MFC ソケットサポートを提供します。 |
| [`AfxGetAmbientActCtx`](#afxgetambientactctx) | モジュールごとの状態フラグの現在の状態を取得します。 |
| [`AfxGetStaticModuleState`](#afxgetstaticmodulestate) | 初期化の前にモジュールの状態を設定し、クリーンアップ後に以前のモジュールの状態を復元します。 |
| [`AfxInitExtensionModule`](#afxinitextensionmodule) | DLL を初期化します。 |
| [`AfxSetAmbientActCtx`](#afxsetambientactctx) | モジュールごとの状態フラグを設定します。これは、MFC の WinSxS 動作に影響します。 |
| [`AfxTermExtensionModule`](#afxtermextensionmodule) | 各プロセスが DLL からデタッチされたときに mfc 拡張 DLL をクリーンアップできるようにします。 |

## <a name="afx_ext_class"></a><a name="afx_ext_class"></a> `AFX_EXT_CLASS`

[Mfc 拡張 dll](../../build/extension-dlls.md) では、マクロを使用して `AFX_EXT_CLASS` クラスをエクスポートします。 mfc 拡張 dll にリンクする実行可能ファイルは、マクロを使用してクラスをインポートします。

### <a name="remarks"></a>注釈

マクロでは `AFX_EXT_CLASS` 、MFC 拡張 dll をビルドするために使用するのと同じヘッダーファイルを、dll にリンクする実行可能ファイルと共に使用できます。

DLL のヘッダーファイルで、次のように、 `AFX_EXT_CLASS` クラスの宣言にキーワードを追加します。

```cpp
class AFX_EXT_CLASS CMyClass : public CDocument
{
// <body of class>
};
```

詳細については、「[を使用 `AFX_EXT_CLASS` したエクスポートとインポート](../../build/exporting-and-importing-using-afx-ext-class.md)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:**\<afxv_dll.h>

## <a name="afx_manage_state"></a><a name="afx_manage_state"></a> `AFX_MANAGE_STATE`

DLL 内のエクスポートされた関数を保護するには、このマクロを呼び出します。

### <a name="syntax"></a>構文

```cpp
AFX_MANAGE_STATE(AFX_MODULE_STATE* pModuleState )
```

### <a name="parameters"></a>パラメーター

*`pModuleState`*<br/>
構造体へのポインター `AFX_MODULE_STATE` 。

### <a name="remarks"></a>注釈

このマクロが呼び出されると、 *`pModuleState`* は、すぐ外側のスコープの残りの部分に対する有効なモジュール状態になります。 スコープを離れると、以前の有効なモジュールの状態が自動的に復元されます。

構造体には、 `AFX_MODULE_STATE` モジュールのグローバルデータ (つまり、プッシュまたはポップされるモジュールの状態の部分) が格納されます。

既定では、MFC はメインアプリケーションのリソースハンドルを使用して、リソーステンプレートを読み込みます。 Dll 内のダイアログボックスを起動する関数など、DLL にエクスポートされた関数がある場合、リソーステンプレートは DLL モジュールに格納されます。 適切なハンドルが使用されるように、必ずモジュールの状態を切り替えてください。 次のコードを関数の先頭に追加することで、状態を切り替えることができます。

```cpp
AFX_MANAGE_STATE(AfxGetStaticModuleState( ));
```

このマクロは、現在のモジュールの状態を、 [`AfxGetStaticModuleState`](#afxgetstaticmodulestate) 現在のスコープの末尾までから返された状態と交換します。

モジュールの状態と MFC の詳細については、「 [mfc モジュールの状態データの管理](../managing-the-state-data-of-mfc-modules.md) 」および「 [テクニカルノート 58](../tn058-mfc-module-state-implementation.md)」を参照してください。

> [!NOTE]
> MFC がアセンブリのアクティベーションコンテキストを作成するときに、を使用して [`AfxWinInit`](application-information-and-management.md#afxwininit) コンテキストを作成し、 `AFX_MANAGE_STATE` それをアクティブ化および非アクティブ化します。 また、mfc `AFX_MANAGE_STATE` コードがユーザーの dll によって選択された適切なアクティベーションコンテキストで実行できるようにするために、Mfc dll の静的 mfc ライブラリに対しても有効になっています。 詳細については、「 [MFC モジュール状態でのアクティベーションコンテキストのサポート](../support-for-activation-contexts-in-the-mfc-module-state.md)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:**\<afxstat_.h>

## <a name="a-nameafxoleinitmodule-afxoleinitmodule"></a><a name="afxoleinitmodule"><a/> `AfxOleInitModule`

MFC に動的にリンクされている通常の MFC DLL から OLE をサポートするには、mfc `CWinApp::InitInstance` OLE dll を初期化するために、通常の MFC dll の関数でこの関数を呼び出します。

### <a name="syntax"></a>構文

```cpp
void AFXAPI AfxOleInitModule( );
```

### <a name="remarks"></a>Remarks

MFC OLE DLL は、MFC 拡張 DLL です。MFC 拡張 DLL をチェーンに接続するには `CDynLinkLibrary` 、 `CDynLinkLibrary` それを使用するすべてのモジュールのコンテキストでオブジェクトを作成する必要があります。 `AfxOleInitModule` 通常の mfc dll のコンテキストでオブジェクトを作成し、 `CDynLinkLibrary` `CDynLinkLibrary` 通常の mfc dll のオブジェクトチェーンに接続できるようにします。

OLE コントロールを構築していて、を使用している場合は、のメンバー関数によってを `COleControlModule` 呼び出す必要が `AfxOleInitModule` `InitInstance` `COleControlModule` `AfxOleInitModule` あります。

### <a name="requirements"></a>必要条件

**ヘッダー**: \<afxdll_.h>

## <a name="afxnetinitmodule"></a><a name="afxnetinitmodule"></a> `AfxNetInitModule`

Mfc に動的にリンクされるレギュラー MFC DLL からの MFC ソケットのサポートについては、 `CWinApp::InitInstance` Mfc ソケット dll を初期化するために、通常の MFC dll の関数にこの関数の呼び出しを追加します。

### <a name="syntax"></a>構文

```cpp
void AFXAPI AfxNetInitModule( );
```

### <a name="remarks"></a>Remarks

MFC ソケット DLL は、MFC 拡張 DLL です。MFC 拡張 DLL をチェーンに接続するには `CDynLinkLibrary` 、 `CDynLinkLibrary` それを使用するすべてのモジュールのコンテキストでオブジェクトを作成する必要があります。 `AfxNetInitModule` 通常の mfc dll のコンテキストでオブジェクトを作成し、 `CDynLinkLibrary` `CDynLinkLibrary` 通常の mfc dll のオブジェクトチェーンに接続できるようにします。

### <a name="requirements"></a>必要条件

**ヘッダー:**\<afxdll_.h>

## <a name="afxgetambientactctx"></a><a name="afxgetambientactctx"></a> `AfxGetAmbientActCtx`

この関数を使用して、モジュールごとの状態フラグの現在の状態を取得します。これは、MFC の WinSxS 動作に影響します。

### <a name="syntax"></a>構文

```cpp
BOOL AFXAPI AfxGetAmbientActCtx();
```

### <a name="return-value"></a>戻り値

モジュール状態フラグの現在の値。

### <a name="remarks"></a>注釈

フラグが設定されている場合 (既定)、スレッドが MFC モジュールに入っている場合 (「」 [`AFX_MANAGE_STATE`](#afx_manage_state) を参照)、モジュールのコンテキストがアクティブ化されます。

フラグが設定されていない場合、モジュールのコンテキストはエントリでアクティブ化されません。

モジュールのコンテキストは、多くの場合モジュールリソースに埋め込まれるマニフェストから決定されます。

### <a name="requirements"></a>必要条件

**ヘッダー:**\<afxcomctl32.h>

## <a name="afxgetstaticmodulestate"></a><a name="afxgetstaticmodulestate"></a> `AfxGetStaticModuleState`

この関数を呼び出して、初期化の前にモジュールの状態を設定し、クリーンアップ後に以前のモジュールの状態を復元します。

### <a name="syntax"></a>構文

```cpp
AFX_MODULE_STATE* AFXAPI AfxGetStaticModuleState( );
```

### <a name="return-value"></a>戻り値

構造体へのポインター `AFX_MODULE_STATE` 。

### <a name="remarks"></a>注釈

構造体には、 `AFX_MODULE_STATE` モジュールのグローバルデータ (つまり、プッシュまたはポップされるモジュールの状態の部分) が格納されます。

既定では、MFC はメインアプリケーションのリソースハンドルを使用して、リソーステンプレートを読み込みます。 Dll 内のダイアログボックスを起動する関数など、DLL にエクスポートされた関数がある場合、リソーステンプレートは DLL モジュールに格納されます。 適切なハンドルが使用されるように、必ずモジュールの状態を切り替えてください。 次のコードを関数の先頭に追加することで、状態を切り替えることができます。

```cpp
AFX_MANAGE_STATE(AfxGetStaticModuleState( ));
```

このマクロは、現在のモジュールの状態を、 `AfxGetStaticModuleState` 現在のスコープの末尾までから返された状態と交換します。

モジュールの状態と MFC の詳細については、「 [mfc モジュールの状態データの管理](../managing-the-state-data-of-mfc-modules.md) 」および「 [テクニカルノート 58](../tn058-mfc-module-state-implementation.md)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:**\<afxstat_.h>

## <a name="afxinitextensionmodule"></a><a name="afxinitextensionmodule"></a> `AfxInitExtensionModule`

DLL を初期化するには、MFC 拡張 DLL のでこの関数 `DllMain` を呼び出します。

### <a name="syntax"></a>構文

```cpp
BOOL AFXAPI AfxInitExtensionModule( AFX_EXTENSION_MODULE& state,  HMODULE hModule );
```

### <a name="parameters"></a>パラメーター

*`state`*<br/>
初期化後の MFC 拡張 DLL モジュールの状態を格納する[ `AFX_EXTENSION_MODULE` 構造](afx-extension-module-structure.md)体への参照。 状態には、が入力される前に実行される通常の静的オブジェクト構築の一部として、MFC 拡張 DLL によって初期化されたランタイムクラスオブジェクトのコピーが含まれ `DllMain` ます。

*`hModule`*<br/>
MFC 拡張 DLL モジュールのハンドル。

### <a name="return-value"></a>戻り値

`TRUE` MFC 拡張 DLL が正常に初期化された場合は、それ以外の場合は `FALSE` 。

### <a name="remarks"></a>注釈

次に例を示します。

```cpp
static AFX_EXTENSION_MODULE NVC_MFC_DLLDLL;
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

`AfxInitExtensionModule` DLL の HMODULE のコピーを作成し、DLL のランタイムクラス ( `CRuntimeClass` 構造体) とオブジェクトファクトリ (オブジェクト) をキャプチャして、 `COleObjectFactory` 後でオブジェクトを作成するときに使用し `CDynLinkLibrary` ます。
MFC 拡張 Dll では、関数内で次の2つの処理を行う必要があり `DllMain` ます。

- [`AfxInitExtensionModule`](#afxinitextensionmodule)を呼び出し、戻り値を確認します。

- DLL が `CDynLinkLibrary` [ `CRuntimeClass` 構造体](cruntimeclass-structure.md)オブジェクトをエクスポートする場合、または独自のカスタムリソースがある場合は、オブジェクトを作成します。

を呼び出すと、 `AfxTermExtensionModule` 各プロセスが mfc 拡張 dll (プロセスが終了したとき、または dll が呼び出しによってアンロードされたときに発生する) からデタッチされたときに mfc 拡張 dll をクリーンアップでき `AfxFreeLibrary` ます。

### <a name="requirements"></a>必要条件

**ヘッダー:**\<afxdll_.h>

## <a name="afxsetambientactctx"></a><a name="afxsetambientactctx"></a> `AfxSetAmbientActCtx`

モジュールごとの状態フラグを設定するには、この関数を使用します。これは、MFC の WinSxS 動作に影響します。

### <a name="syntax"></a>構文

```cpp
void AFXAPI AfxSetAmbientActCtx(BOOL bSet);
```

### <a name="parameters"></a>パラメーター

*`bSet`*<br/>
モジュール状態フラグの新しい値。

### <a name="remarks"></a>注釈

フラグが設定されている場合 (既定)、スレッドが MFC モジュールに入っている場合 (「」 [`AFX_MANAGE_STATE`](#afx_manage_state) を参照)、モジュールのコンテキストがアクティブ化されます。
フラグが設定されていない場合、モジュールのコンテキストはエントリでアクティブ化されません。
モジュールのコンテキストは、多くの場合モジュールリソースに埋め込まれるマニフェストから決定されます。

### <a name="example"></a>例

```cpp
BOOL CMFCListViewApp::InitInstance()
{
   AfxSetAmbientActCtx(FALSE);
   // Remainder of function definition omitted.
}
```

### <a name="requirements"></a>必要条件

**ヘッダー:**\<afxcomctl32.h>

## <a name="afxtermextensionmodule"></a><a name="afxtermextensionmodule"></a> `AfxTermExtensionModule`

この関数を呼び出して、各プロセスが DLL からデタッチされたときに mfc 拡張 DLL をクリーンアップできるようにします (プロセスが終了したとき、または DLL が呼び出しによってアンロードされたときに発生し `AfxFreeLibrary` ます)。

### <a name="syntax"></a>構文

```cpp
void AFXAPI AfxTermExtensionModule( AFX_EXTENSION_MODULE& state, BOOL bAll = FALSE );
```

### <a name="parameters"></a>パラメーター

*`state`*<br/>
[`AFX_EXTENSION_MODULE`](afx-extension-module-structure.md)MFC 拡張 DLL モジュールの状態を格納している構造体への参照。

*`bAll`*<br/>
TRUE の場合は、すべての MFC 拡張 DLL モジュールをクリーンアップします。 それ以外の場合は、現在の DLL モジュールだけをクリーンアップします。

### <a name="remarks"></a>注釈

`AfxTermExtensionModule` モジュールにアタッチされているすべてのローカルストレージを削除し、メッセージマップキャッシュからエントリを削除します。 次に例を示します。

```cpp
static AFX_EXTENSION_MODULE NVC_MFC_DLLDLL;
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

アプリケーションで MFC 拡張 Dll を動的に読み込んで解放する場合は、必ずを呼び出してください `AfxTermExtensionModule` 。 ほとんどの MFC 拡張 Dll は動的に読み込まれないため (通常はインポートライブラリを使用してリンクされているため)、の呼び出しは `AfxTermExtensionModule` 通常必要ありません。

MFC 拡張 Dll では、を呼び出す必要があり [`AfxInitExtensionModule`](#afxinitextensionmodule) `DllMain` ます。 DLL がオブジェクトをエクスポートする場合 [`CRuntimeClass`](cruntimeclass-structure.md) 、または独自のカスタムリソースがある場合は、でオブジェクトを作成する必要もあり `CDynLinkLibrary` `DllMain` ます。

### <a name="requirements"></a>必要条件

**ヘッダー:**\<afxdll_.h>

## <a name="see-also"></a>関連項目

[マクロとグローバル](mfc-macros-and-globals.md)<br/>
[`AfxMessageBox`](cstring-formatting-and-message-box-display.md#afxmessagebox)<br/>
[MFC モジュールの状態データの管理](../managing-the-state-data-of-mfc-modules.md)<br/>
