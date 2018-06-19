---
title: CDialogImpl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CDialogImpl
- ATLWIN/ATL::CDialogImpl
- ATLWIN/ATL::Create
- ATLWIN/ATL::DestroyWindow
- ATLWIN/ATL::DoModal
- ATLWIN/ATL::EndDialog
- ATLWIN/ATL::GetDialogProc
- ATLWIN/ATL::MapDialogRect
- ATLWIN/ATL::OnFinalMessage
- ATLWIN/ATL::DialogProc
- ATLWIN/ATL::StartDialogProc
dev_langs:
- C++
helpviewer_keywords:
- dialog boxes, ATL
- CDialogImpl class
ms.assetid: d430bc7b-8a28-4ad3-9507-277bdd2c2c2e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6d4119daf89820de0a835bfbc572cdfbf38c99e8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32365140"
---
# <a name="cdialogimpl-class"></a>CDialogImpl クラス
このクラスは、モーダルまたはモードレス ダイアログ ボックスを作成するためのメソッドを提供します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```  
 
template <class T,  
    class TBase = CWindow>  
    class ATL_NO_VTABLE CDialogImpl : public CDialogImplBaseT<TBase>  
 
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラス、`CDialogImpl`です。  
  
 *TBase*  
 新しいクラスの基本クラスです。 既定の基本クラスは[CWindow](../../atl/reference/cwindow-class.md)です。  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[作成します。](#create)|モードレス ダイアログ ボックスを作成します。|  
|[DestroyWindow](#destroywindow)|モードレス ダイアログ ボックスを破棄します。|  
|[DoModal](#domodal)|モーダル ダイアログ ボックスを作成します。|  
|[EndDialog](#enddialog)|モーダル ダイアログ ボックスを破棄します。|  
  
### <a name="cdialogimplbaset-methods"></a>CDialogImplBaseT メソッド  
  
|||  
|-|-|  
|[GetDialogProc](#getdialogproc)|現在のダイアログ ボックス プロシージャを返します。|  
|[MapDialogRect](#mapdialogrect)|指定した四角形のダイアログ ボックスの単位を画面の単位 (ピクセル単位) にマップします。|  
|[OnFinalMessage](#onfinalmessage)|通常、最後のメッセージの受信後に呼び出される`WM_NCDESTROY`です。|  
  
### <a name="static-functions"></a>静的関数  
  
|||  
|-|-|  
|[DialogProc](#dialogproc)|ダイアログ ボックスに送信されたメッセージを処理します。|  
|[StartDialogProc](#startdialogproc)|ダイアログ ボックスに送信されたメッセージを処理する最初のメッセージが受信したときに呼び出されます。|  
  
## <a name="remarks"></a>コメント  
 `CDialogImpl`モーダルまたはモードレス ダイアログ ボックスを作成することができます。 `CDialogImpl` 既定のメッセージ マップを使用して、適切なハンドラーへのメッセージを送信するためのダイアログ ボックス プロシージャを提供します。  
  
 基底クラスのデストラクター **~ CWindowImplRoot**オブジェクトを破棄する前に、ウィンドウが消去されていることを確認します。  
  
 `CDialogImpl` 派生した**CDialogImplBaseT**、さらにから派生した**CWindowImplRoot**です。  
  
> [!NOTE]
>  クラスを定義する必要があります、 **IDD**ダイアログ テンプレート リソース ID を指定するメンバー たとえば、ATL プロジェクト ウィザードは、クラスに次の行を自動的に追加します。  
  
 [!code-cpp[NVC_ATL_Windowing#41](../../atl/codesnippet/cpp/cdialogimpl-class_1.h)]  
  
 ここで`MyDlg`は、**短い名前**、ウィザードで入力した**名**ページ。  
  
|詳細情報:|解決方法については、|  
|--------------------------------|---------|  
|コントロールの作成|[ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)|  
|ATL ダイアログ ボックスを使用|[ATL ウィンドウ クラス](../../atl/atl-window-classes.md)|  
|ATL プロジェクト ウィザード|[ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)|  
|ダイアログ ボックス|[ダイアログ ボックス](http://msdn.microsoft.com/library/windows/desktop/ms632588)と Windows SDK のそれ以降のトピック|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h  
  
##  <a name="create"></a>  CDialogImpl::Create  
 モードレス ダイアログ ボックスを作成します。  
  
```  
HWND Create(
    HWND hWndParent,  
    LPARAM dwInitParam = NULL );  

HWND Create(
    HWND hWndParent,  
    RECT&, 
    LPARAM dwInitParam = NULL); 
```  
  
### <a name="parameters"></a>パラメーター  
 `hWndParent`  
 [in]オーナー ウィンドウへのハンドル。  
  
 **RECT (&AMP; A)** `rect`  
 [in]A [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)ダイアログのサイズと位置を指定します。  
  
 `dwInitParam`  
 [in]ダイアログ ボックスに渡す値を指定します、 **lParam**のパラメーター、 **WM_INITDIALOG**メッセージ。  
  
### <a name="return-value"></a>戻り値  
 新しく作成されたダイアログ ボックスのハンドルです。  
  
### <a name="remarks"></a>コメント  
 このダイアログ ボックスが自動的に添付、`CDialogImpl`オブジェクト。 モーダル ダイアログ ボックスを作成するには[DoModal](#domodal)です。 上の 2 つ目の上書きでのみ使用[CComControl](../../atl/reference/ccomcontrol-class.md)です。  
  
##  <a name="destroywindow"></a>  CDialogImpl::DestroyWindow  
 モードレス ダイアログ ボックスを破棄します。  
  
```  
 
BOOL DestroyWindow();

 
```  
  
### <a name="return-value"></a>戻り値  
 **TRUE**ダイアログ ボックスが正常に破棄されたそれ以外の場合**FALSE**です。  
  
### <a name="remarks"></a>コメント  
 返します**TRUE**ダイアログ ボックスが正常に破棄されたそれ以外の場合**FALSE**です。  
  
##  <a name="dialogproc"></a>  CDialogImpl::DialogProc  
 この静的関数では、ダイアログ ボックス プロシージャを実装します。  
  
```  
 
static LRESULT CALLBACK DialogProc(
    HWND hWnd,  
    UINT uMsg,  
    WPARAM wParam,  
    LPARAM lParam);

 
```  
  
### <a name="parameters"></a>パラメーター  
 `hWnd`  
 [in]ダイアログ ボックスのハンドルです。  
  
 `uMsg`  
 [in]ダイアログ ボックスに送信されるメッセージ。  
  
 `wParam`  
 [in]その他のメッセージに固有の情報です。  
  
 `lParam`  
 [in]その他のメッセージに固有の情報です。  
  
### <a name="return-value"></a>戻り値  
 **TRUE**メッセージが処理された、それ以外の場合**FALSE**です。  
  
### <a name="remarks"></a>コメント  
 `DialogProc` 適切なハンドラーへのメッセージを送信するためには、既定のメッセージ マップを使用します。  
  
 オーバーライドできます`DialogProc`メッセージを処理するためのさまざまなメカニズムを提供します。  
  
##  <a name="domodal"></a>  CDialogImpl::DoModal  
 モーダル ダイアログ ボックスを作成します。  
  
```   
INT_PTR DoModal(  
    HWND hWndParent = ::GetActiveWindow(),   
    LPARAM dwInitParam = NULL); 
```  
  
### <a name="parameters"></a>パラメーター  
 `hWndParent`  
 [in]オーナー ウィンドウへのハンドル。 既定値は、戻り値の[GetActiveWindow](http://msdn.microsoft.com/library/windows/desktop/ms646292) Win32 関数。  
  
 `dwInitParam`  
 [in]ダイアログ ボックスに渡す値を指定します、 **lParam**のパラメーター、 **WM_INITDIALOG**メッセージ。  
  
### <a name="return-value"></a>戻り値  
 成功した場合の値、`nRetCode`への呼び出しで指定されたパラメーター [EndDialog](#enddialog)です。 それ以外の場合、-1 を返します。  
  
### <a name="remarks"></a>コメント  
 このダイアログ ボックスが自動的に添付、`CDialogImpl`オブジェクト。  
  
 モードレス ダイアログ ボックスを作成するには[作成](#create)です。  
  
##  <a name="enddialog"></a>  CDialogImpl::EndDialog  
 モーダル ダイアログ ボックスを破棄します。  
  
```   
BOOL EndDialog(int nRetCode); 
```  
  
### <a name="parameters"></a>パラメーター  
 `nRetCode`  
 [in]によって返される値[CDialogImpl::DoModal](#domodal)です。  
  
### <a name="return-value"></a>戻り値  
 **TRUE**  ダイアログ ボックスが破棄された、それ以外の場合は**FALSE**です。  
  
### <a name="remarks"></a>コメント  
 `EndDialog` ダイアログ プロシージャを呼び出す必要があります。 Windows がの値を使用して、ダイアログ ボックスの破棄後`nRetCode`の戻り値として`DoModal`、ダイアログ ボックスを作成します。  
  
> [!NOTE]
>  呼び出す必要はありません`EndDialog`モードレス ダイアログ ボックスを破棄します。 呼び出す[CWindow::DestroyWindow](../../atl/reference/cwindow-class.md#destroywindow)代わりにします。  
  
##  <a name="getdialogproc"></a>  CDialogImpl::GetDialogProc  
 返します`DialogProc`、現在のダイアログ ボックス プロシージャです。  
  
```   
virtual WNDPROC GetDialogProc(); 
```  
  
### <a name="return-value"></a>戻り値  
 現在のダイアログ ボックス プロシージャです。  
  
### <a name="remarks"></a>コメント  
 独自のダイアログ プロシージャを置換するには、このメソッドをオーバーライドします。  
  
##  <a name="mapdialogrect"></a>  CDialogImpl::MapDialogRect  
 (Maps) の画面に指定された四角形のダイアログ ボックスの単位の単位 (ピクセル単位) に変換します。  
  
```   
BOOL MapDialogRect(LPRECT lpRect); 
```  
  
### <a name="parameters"></a>パラメーター  
 `lpRect`  
 指す、`CRect`オブジェクトまたは[RECT](../../mfc/reference/rect-structure1.md)更新領域が囲むされる更新プログラムのクライアント座標を受け取る構造体。  
  
### <a name="return-value"></a>戻り値  
 更新プログラムが成功した場合は 0 以外。更新が失敗した場合は 0 を返します。 拡張されたエラー情報を取得するには、`GetLastError` を呼び出します。  
  
### <a name="remarks"></a>コメント  
 関数は、指定した座標を置き換えます`RECT`これにより、構造の作成 ダイアログ ボックスまたはダイアログ ボックス内でコントロールを配置するために使用する変換された座標を使用して構造体します。  
  
##  <a name="onfinalmessage"></a>  CDialogImpl::OnFinalMessage  
 最後のメッセージの受信後に呼び出されます (通常`WM_NCDESTROY`)。  
  
```   
virtual void OnFinalMessage(HWND hWnd); 
```  
  
### <a name="parameters"></a>パラメーター  
 `hWnd`  
 [in]破棄されているウィンドウへのハンドル。  
  
### <a name="remarks"></a>コメント  
 ウィンドウの破棄後にオブジェクトを自動的に削除する場合を呼び出すことに注意してください`delete this;`ここです。  
  
##  <a name="startdialogproc"></a>  CDialogImpl::StartDialogProc  
 ダイアログ ボックスに送信されたメッセージを処理する最初のメッセージを受信すると、1 回だけ呼び出されます。  
  
```   
static LRESULT CALLBACK StartDialogProc(
    HWND hWnd,  
    UINT uMsg,  
    WPARAM wParam,  
    LPARAM lParam); 
```  
  
### <a name="parameters"></a>パラメーター  
 `hWnd`  
 [in]ダイアログ ボックスのハンドルです。  
  
 `uMsg`  
 [in]ダイアログ ボックスに送信されるメッセージ。  
  
 `wParam`  
 [in]その他のメッセージに固有の情報です。  
  
 `lParam`  
 [in]その他のメッセージに固有の情報です。  
  
### <a name="return-value"></a>戻り値  
 ウィンドウ プロシージャです。  
  
### <a name="remarks"></a>コメント  
 最初の呼び出し後`StartDialogProc`、`DialogProc`がダイアログの手順では、およびそれ以上の呼び出しがそこに移動してように設定されています。  
  
## <a name="see-also"></a>関連項目  
 [送るに](message-map-macros-atl.md#begin_msg_map)   
 [クラスの概要](../../atl/atl-class-overview.md)