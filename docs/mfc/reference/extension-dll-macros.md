---
title: マクロと関数を Dll を管理する |Microsoft ドキュメント
ms.custom: ''
ms.date: 04/03/2017
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- module macros in MFC
ms.assetid: 303f4161-cb5e-4099-81ad-acdb11aa60fb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e5e79556bf6e3ae92f7a8d4975dbd30f199e2ca8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="macros-and-functions-for-managing-dlls"></a>マクロと Dll を管理するための関数

|||
|-|-|
|[AFX_EXT_CLASS](#afx_ext_class)]|クラスをエクスポートします。|
|[AFX_MANAGE_STATE](#afx_manage_state)|DLL でエクスポートされた関数を保護します。|
|[AfxOleInitModule](#afxoleinitmodule)|MFC と動的にリンクされている標準 MFC DLL から OLE サポートを提供します。|
|[AfxNetInitModule](#afxnetinitmodule)|MFC と動的にリンクされている標準 MFC DLL から MFC ソケットのサポートを提供します。|
|[AfxGetAmbientActCtx](#afxgetambientactctx)|各モジュールの状態フラグの現在の状態を取得します。|
|[AfxGetStaticModuleState](#afxgetstaticmodulestate)|初期化前に、または後のクリーンアップに以前のモジュール状態を復元するモジュールの状態を設定します。|
|[AfxInitExtensionModule]()#afxinitextensionmodule|DLL を初期化します。|
|[AfxSetAmbientActCtx](#afxsetambientactctx)|MFC の WinSxS 動作に影響を与える、モジュールごとの状態フラグを設定します。|
|[AfxTermExtensionModule]()#afxtermextensionmodule)|MFC クリーンアップするには MFC 拡張 DLL の各プロセスは、DLL からデタッチするときにします。|


## <a name="afx_ext_class"></a>  AFX_EXT_CLASS
[MFC 拡張 Dll](../../build/extension-dlls.md)マクロを使用して**AFX_EXT_CLASS**をエクスポートするクラスです。 MFC 拡張 DLL にリンクする実行可能ファイルでは、マクロを使用してクラスをインポートします。  
   
### <a name="remarks"></a>コメント  
 **AFX_EXT_CLASS**マクロ、MFC 拡張 DLL をビルドするために使用するファイルは、DLL にリンクする実行可能ファイルで使用できる、同じヘッダー。  
  
 DLL のヘッダー ファイルを追加、 **AFX_EXT_CLASS**キーワードを次のように、クラスの宣言に。  
  
```cpp
class AFX_EXT_CLASS CMyClass : public CDocument
{
// <body of class>
};
``` 
  
 詳細については、次を参照してください。[エクスポートとインポートを使用して AFX_EXT_CLASS](../../build/exporting-and-importing-using-afx-ext-class.md)です。  
   
### <a name="requirements"></a>要件  
 ヘッダー: **afxv_** dll.h  
   
## <a name="afx_manage_state"></a>  AFX_MANAGE_STATE
DLL でエクスポートされた関数を保護するには、このマクロを呼び出します。  
   
### <a name="syntax"></a>構文    
```
AFX_MANAGE_STATE(AFX_MODULE_STATE* pModuleState )  
```
### <a name="parameters"></a>パラメーター  
 `pModuleState`  
 ポインター、`AFX_MODULE_STATE`構造体。  
   
### <a name="remarks"></a>コメント  
 このマクロが呼び出されると、`pModuleState`即時の残りの有効なモジュールの状態を含むスコープです。 スコープから離れると、以前の有効なモジュールの状態は自動的に復元されます。    
 `AFX_MODULE_STATE`構造体には、モジュールには、プッシュまたはポップされているモジュールの状態の部分は、グローバルなデータが含まれています。    
 既定では、MFC では、メイン アプリケーションのリソース ハンドルを使用して、リソース テンプレートを読み込みます。 DLL 内のダイアログ ボックスを起動するなどの DLL にエクスポートされた関数がある場合、このテンプレートは DLL モジュールに実際に格納されます。 適切なハンドルを使用するモジュールの状態を切り替える必要があります。 関数の先頭に次のコードを追加することで、これを行うことができます。    
```cpp
AFX_MANAGE_STATE(AfxGetStaticModuleState( ));

```
 モジュールの現在の状態から返された状態と交換この[AfxGetStaticModuleState](#afxgetstaticmodulestate)現在のスコープが終了するまでです。    
 モジュールの状態と MFC の詳細についてを参照してください「の管理モジュールの状態データの MFC モジュール」[ドキュメントを新規に作成する、Windows、およびビュー](../creating-new-documents-windows-and-views.md)と[テクニカル ノート 58](../tn058-mfc-module-state-implementation.md)です。    
> [!NOTE]
>  MFC では、アセンブリのアクティベーション コンテキストを作成するときに使用して[AfxWinInit](#afxwininit)コンテキストを作成して`AFX_MANAGE_STATE`アクティブ化および非アクティブ化します。 なお`AFX_MANAGE_STATE`MFC コード ユーザー DLL によって選択されている適切なライセンス認証のコンテキストで実行を許可するために静的の MFC ライブラリと MFC Dll に対してを有効にします。 詳細については、次を参照してください。 [MFC モジュール状態でのアクティベーション コンテキスト サポート](../support-for-activation-contexts-in-the-mfc-module-state.md)です。     
### <a name="requirements"></a>要件  
 **ヘッダー:** afxstat_.h  
   
### <a name="see-also"></a>関連項目  
 [AfxGetStaticModuleState](#afxgetstaticmodulestate)

## <a name="a-nameafxoleinitmodulea-afxoleinitmodule"></a><a name="afxoleinitmodule"><a/> AfxOleInitModule
MFC と動的にリンクされている標準 MFC DLL から OLE サポートをこの関数を呼び出して、正規の MFC DLL の`CWinApp::InitInstance`MFC OLE DLL を初期化します。  
   
### <a name="syntax"></a>構文    
```
void AFXAPI AfxOleInitModule( );  
```  
   
### <a name="remarks"></a>コメント  
 MFC OLE DLL が MFC 拡張 DLL です。MFC 拡張 DLL にワイヤード (有線) を取得するため、 **CDynLinkLibrary**チェーンを作成する必要があります、 **CDynLinkLibrary**を利用することのすべてのモジュールのコンテキスト内のオブジェクト。 `AfxOleInitModule` 作成、 **CDynLinkLibrary**にワイヤード (有線) を取得できるように、正規の MFC DLL のコンテキストでオブジェクト、 **CDynLinkLibrary**オブジェクトの標準の MFC DLL のチェーン。  
  
 OLE コントロールを構築してを使用している場合`COleControlModule`、呼び出す必要はありません**AfxOleInitModule**ため、`InitInstance`メンバー関数の`COleControlModule`呼び出し`AfxOleInitModule`です。  
   
### <a name="requirements"></a>要件  
 **ヘッダー**: < afxdll_.h >  
   
### <a name="see-also"></a>関連項目  
 [マクロとグローバル](mfc-macros-and-globals.md)   
 [AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox)

## <a name="afxnetinitmodule"></a>  AfxNetInitModule
MFC ソケットは、MFC と動的にリンクされている標準 MFC DLL からサポート、標準 MFC dll のこの関数に対する呼び出しを追加**場合は**MFC ソケットの DLL を初期化します。  
   
### <a name="syntax"></a>構文    
```
void AFXAPI AfxNetInitModule( );  
```  
   
### <a name="remarks"></a>コメント  
 MFC ソケットの DLL が MFC 拡張 DLL です。MFC 拡張 DLL にワイヤード (有線) を取得するため、 **CDynLinkLibrary**チェーンを作成する必要があります、 **CDynLinkLibrary**を利用することのすべてのモジュールのコンテキスト内のオブジェクト。 `AfxNetInitModule` 作成、 **CDynLinkLibrary**にワイヤード (有線) を取得できるように、正規の MFC DLL のコンテキストでオブジェクト、 **CDynLinkLibrary**オブジェクトの標準の MFC DLL のチェーン。  
   
### <a name="requirements"></a>要件  
 **ヘッダー:** < afxdll_.h >  
   
### <a name="see-also"></a>関連項目  
 [マクロとグローバル](mfc-macros-and-globals.md)   
 [AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox)

## <a name="afxgetambientactctx"></a> AfxGetAmbientActCtx
MFC の WinSxS 動作に影響を与える各モジュールの状態フラグの現在の状態を取得するのにには、この関数を使用します。  
   
### <a name="syntax"></a>構文    
```  
BOOL AFXAPI AfxGetAmbientActCtx();   
```  
   
### <a name="return-value"></a>戻り値  
 モジュールの状態フラグの現在値。  
   
### <a name="remarks"></a>コメント  
 フラグが設定する (既定値) とスレッドが、MFC のモジュールに入った (を参照してください[AFX_MANAGE_STATE](#afx_manage_state))、モジュールのコンテキストがアクティブにします。  
  
 フラグが設定されていない場合、モジュールのコンテキストはエントリをアクティブ化されていません。  
  
 モジュールのコンテキストは、通常モジュール リソースに埋め込まれて、自らのマニフェストから決定されます。  
   
### <a name="requirements"></a>要件  
 **ヘッダー:** afxcomctl32.h  
   
### <a name="see-also"></a>関連項目  
 [マクロとグローバル](mfc-macros-and-globals.md)   
 [AFX_MANAGE_STATE](#afx_manage_state)   
 [MFC モジュールの状態データを管理します。](../managing-the-state-data-of-mfc-modules.md)   
 [AfxSetAmbientActCtx](#setambientactctx)
 
## <a name="afxgetstaticmodulestate"></a> AfxGetStaticModuleState
初期化の前にモジュールの状態を設定およびクリーンアップの後に以前のモジュール状態の復元をこの関数を呼び出します。  
   
### <a name="syntax"></a>構文    
```
AFX_MODULE_STATE* AFXAPI AfxGetStaticModuleState( );  
```  
   
### <a name="return-value"></a>戻り値  
 ポインター、`AFX_MODULE_STATE`構造体。  
   
### <a name="remarks"></a>コメント  
 `AFX_MODULE_STATE`構造体には、モジュールには、プッシュまたはポップされているモジュールの状態の部分は、グローバルなデータが含まれています。  
  
 既定では、MFC では、メイン アプリケーションのリソース ハンドルを使用して、リソース テンプレートを読み込みます。 DLL 内のダイアログ ボックスを起動するなどの DLL にエクスポートされた関数がある場合、このテンプレートは DLL モジュールに実際に格納されます。 適切なハンドルを使用するモジュールの状態を切り替える必要があります。 関数の先頭に次のコードを追加することで、これを行うことができます。  
  
```cpp
AFX_MANAGE_STATE(AfxGetStaticModuleState( ));

```
  
 モジュールの現在の状態から返された状態と交換この`AfxGetStaticModuleState`現在のスコープが終了するまでです。  
  
 モジュールの状態と MFC の詳細についてを参照してください「の管理モジュールの状態データの MFC モジュール」[ドキュメントを新規に作成する、Windows、およびビュー](../creating-new-documents-windows-and-views.md)と[テクニカル ノート 58](../tn058-mfc-module-state-implementation.md)です。  
   
### <a name="requirements"></a>要件  
 **ヘッダー:** afxstat_.h  
   

## <a name="afxinitextensionmodule"></a> AfxInitExtensionModule
MFC 拡張 DLL のでこの関数の呼び出し`DllMain`DLL を初期化します。  
   
### <a name="syntax"></a>構文    
```
BOOL AFXAPI AfxInitExtensionModule( AFX_EXTENSION_MODULE& state,  HMODULE hModule );  
```
### <a name="parameters"></a>パラメーター  
 `state`  
 参照、 [AFX_EXTENSION_MODULE 構造体](afx-extension-module-structure.md)初期化後に、MFC 拡張 DLL のモジュールの状態を格納する構造。 状態には、通常の静的オブジェクトの構築の前に実行の一部としてに MFC 拡張 DLL が初期化されたランタイム クラスのオブジェクトのコピーが含まれています。`DllMain`を入力します。  
  
 `hModule`  
 MFC 拡張 DLL のモジュールのハンドル。  
   
### <a name="return-value"></a>戻り値  
 **TRUE** MFC 拡張 DLL が正常に初期化されている、それ以外の場合は**FALSE**です。  
   
### <a name="remarks"></a>コメント  
 例えば:  
  
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

```
  
 `AfxInitExtensionModule` DLL のコピーを作成**HMODULE** DLL のランタイム クラスをキャプチャし、(`CRuntimeClass`構造体) のオブジェクト ファクトリだけでなく (`COleObjectFactory`オブジェクト) 使用するときに後で、 **CDynLinkLibrary**オブジェクトを作成します。    
 MFC 拡張 Dll で次の 2 つを行う必要性、`DllMain`関数。    
-   呼び出す[AfxInitExtensionModule](#_mfc_afxinitextensionmodule)戻り値を確認します。   
-   作成、 **CDynLinkLibrary**オブジェクトの DLL をエクスポートするかどうかは[CRuntimeClass 構造](cruntimeclass-structure.md)独自のカスタム リソースまたはオブジェクトします。    
 呼び出すことができます`AfxTermExtensionModule`各プロセスは、MFC 拡張 DLL からデタッチするときに、MFC 拡張 DLL をクリーンアップする (プロセスが終了すると、かの結果として、DLL がアンロードされたときに発生する、`AfxFreeLibrary`呼び出します)。     

### <a name="requirements"></a>要件  
 **ヘッダー:** afxdll_.h     

### <a name="see-also"></a>関連項目  
 [マクロとグローバル](mfc-macros-and-globals.md)   
 [AfxTermExtensionModule](#afxtermextensionmodule)

 ## <a name="afxsetambientactctx"></a>  AfxSetAmbientActCtx
MFC の WinSxS 動作に影響は、モジュールの状態フラグを設定するのにには、この関数を使用します。  
   
### <a name="syntax"></a>構文  
  ```
   void AFXAPI AfxSetAmbientActCtx( BOOL bSet  
);  
```
### <a name="parameters"></a>パラメーター  
 `bSet`  
 モジュールの状態フラグの新しい値。  
   
### <a name="remarks"></a>コメント  
 フラグが設定する (既定値) とスレッドが、MFC のモジュールに入った (を参照してください[AFX_MANAGE_STATE](#afx_manage_state))、モジュールのコンテキストがアクティブにします。    
 フラグが設定されていない場合、モジュールのコンテキストはエントリをアクティブ化されていません。    
 モジュールのコンテキストは、通常モジュール リソースに埋め込まれて、自らのマニフェストから決定されます。  
   
### <a name="example"></a>例  
 ```cpp
BOOL CMFCListViewApp::InitInstance()
{
   AfxSetAmbientActCtx(FALSE);
   // Remainder of function definition omitted.
```
   
### <a name="requirements"></a>要件  
 **ヘッダー:** afxcomctl32.h  
   
### <a name="see-also"></a>関連項目  
 [マクロとグローバル](mfc-macros-and-globals.md)   
 [AfxGetAmbientActCtx](#afxgetambientactctx)   
 [AFX_MANAGE_STATE](#afx_manage_state)   
 [MFC モジュールの状態データの管理](../managing-the-state-data-of-mfc-modules.md) 

## <a name="afxtermextensionmodule"></a>  AfxTermExtensionModule

拡張を許可する MFC クリーンアップするには、MFC DLL の各プロセスは、DLL からデタッチするときにこの関数を呼び出します (動作は、プロセスが終了したとき、またはの結果として、DLL がアンロードされたときに、`AfxFreeLibrary`呼び出します)。  
   
### <a name="syntax"></a>構文  
  ```
void AFXAPI AfxTermExtensionModule(  AFX_EXTENSION_MODULE& state,  BOOL bAll  = FALSE );  
```
### <a name="parameters"></a>パラメーター  
 `state`  
 参照、 [AFX_EXTENSION_MODULE](afx-extension-module-structure.md) MFC 拡張 DLL のモジュールの状態を格納する構造体。  
  
 *ボール*  
 場合**TRUE**クリーンアップ、すべての MFC 拡張 DLL のモジュール。 それ以外の場合、クリーンアップが現在の DLL のモジュールのみです。  
   
### <a name="remarks"></a>コメント  
 `AfxTermExtensionModule` モジュールに接続されている任意のローカル ストレージを削除し、メッセージ マップ キャッシュからすべてのエントリを削除します。 例えば:  
  
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
  
 場合は、アプリケーションを読み込んでし、MFC 拡張 Dll を動的に解放を必ず呼び出して`AfxTermExtensionModule`です。 ほとんどの MFC 拡張 Dll が動的に読み込まれていないため (通常は、リンクされている、インポート ライブラリを使用して) への呼び出し`AfxTermExtensionModule`通常必要はありません。  
  
 MFC 拡張 Dll を呼び出す必要があります[AfxInitExtensionModule](#afxinitextensionmodule)でその`DllMain`です。 DLL エクスポートする場合[CRuntimeClass](cruntimeclass-structure.md)が独自のカスタム リソースまたはオブジェクトを作成する必要があります、 **CDynLinkLibrary**オブジェクトに`DllMain`です。  
   
### <a name="requirements"></a>要件  
 **ヘッダー:** afxdll_.h  
   
### <a name="see-also"></a>関連項目  
 [マクロとグローバル](mfc-macros-and-globals.md)   
 [AfxInitExtensionModule](#afxinitextensionmodule)
 




