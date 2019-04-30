---
title: COccManager クラス
ms.date: 11/04/2016
f1_keywords:
- COccManager
- AFXOCC/COccManager
- AFXOCC/COccManager::CreateContainer
- AFXOCC/COccManager::CreateDlgControls
- AFXOCC/COccManager::CreateSite
- AFXOCC/COccManager::GetDefBtnCode
- AFXOCC/COccManager::IsDialogMessage
- AFXOCC/COccManager::IsLabelControl
- AFXOCC/COccManager::IsMatchingMnemonic
- AFXOCC/COccManager::OnEvent
- AFXOCC/COccManager::PostCreateDialog
- AFXOCC/COccManager::PreCreateDialog
- AFXOCC/COccManager::SetDefaultButton
- AFXOCC/COccManager::SplitDialogTemplate
helpviewer_keywords:
- COccManager [MFC], CreateContainer
- COccManager [MFC], CreateDlgControls
- COccManager [MFC], CreateSite
- COccManager [MFC], GetDefBtnCode
- COccManager [MFC], IsDialogMessage
- COccManager [MFC], IsLabelControl
- COccManager [MFC], IsMatchingMnemonic
- COccManager [MFC], OnEvent
- COccManager [MFC], PostCreateDialog
- COccManager [MFC], PreCreateDialog
- COccManager [MFC], SetDefaultButton
- COccManager [MFC], SplitDialogTemplate
ms.assetid: 7d47aeed-d1ab-48e3-b4cf-d429718e370a
ms.openlocfilehash: a83f58b8de2411577d9fc025f7a8f8dc535ea8b3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388268"
---
# <a name="coccmanager-class"></a>COccManager クラス

`COleControlContainer` オブジェクトと `COleControlSite` オブジェクトによって実装されるさまざまなカスタム コントロール サイトを管理します。

## <a name="syntax"></a>構文

```
class COccManager : public CNoTrackObject
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[COccManager::CreateContainer](#createcontainer)|`COleContainer` オブジェクトを作成します。|
|[COccManager::CreateDlgControls](#createdlgcontrols)|関連付けられているによってホストされている、ActiveX コントロールを作成します`COleContainer`オブジェクト。|
|[COccManager::CreateSite](#createsite)|`COleClientSite` オブジェクトを作成します。|
|[COccManager::GetDefBtnCode](#getdefbtncode)|既定のボタンのコードを取得します。|
|[COccManager::IsDialogMessage](#isdialogmessage)|ダイアログ メッセージのターゲットを決定します。|
|[COccManager::IsLabelControl](#islabelcontrol)|指定したコントロールがラベル コントロールであるかどうかを判断します。|
|[COccManager::IsMatchingMnemonic](#ismatchingmnemonic)|現在のアクセラレータ キーが指定したコントロールのニーモニックと一致するかどうかを決定します。|
|[COccManager::OnEvent](#onevent)|指定したイベントを処理しようとしています。|
|[COccManager::PostCreateDialog](#postcreatedialog)|ダイアログの作成中に割り当てられているリソースを解放します。|
|[COccManager::PreCreateDialog](#precreatedialog)|ActiveX コントロール用のダイアログ テンプレートを処理します。|
|[COccManager::SetDefaultButton](#setdefaultbutton)|指定したコントロールの既定の状態を切り替えます。|
|[COccManager::SplitDialogTemplate](#splitdialogtemplate)|指定されたダイアログのテンプレートでコモン コントロールから既存の ActiveX コントロールを分離します。|

## <a name="remarks"></a>Remarks

基本クラス、 `CNoTrackObject`、(AFXTLS にありますドキュメントに未記載の基本クラスです。H)。 MFC フレームワークによっては、使用するために設計されたから派生したクラス、`CNoTrackObject`クラスはメモリ リークの検出から除外されます。 直接派生させることはお勧めできません`CNoTrackObject`します。

## <a name="inheritance-hierarchy"></a>継承階層

`CNoTrackObject`

`COccManager`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxocc.h

##  <a name="createcontainer"></a>  COccManager::CreateContainer

コントロールのコンテナーを作成するためにフレームワークによって呼び出されます。

```
virtual COleControlContainer* CreateContainer(CWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

*我が物*<br/>
カスタムのサイト コンテナーに関連付けられたウィンドウ オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

新しく作成されたコンテナーへのポインターそれ以外の場合は NULL です。

### <a name="remarks"></a>Remarks

カスタムのサイトを作成する方法の詳細については、次を参照してください。 [COleControlContainer::AttachControlSite](../../mfc/reference/colecontrolcontainer-class.md#attachcontrolsite)します。

##  <a name="createdlgcontrols"></a>  COccManager::CreateDlgControls

指定された ActiveX コントロールを作成するには、この関数を呼び出して、 *pOccDialogInfo*パラメーター。

```
virtual BOOL CreateDlgControls(
    CWnd* pWndParent,
    LPCTSTR lpszResourceName,
    _AFX_OCC_DIALOG_INFO* pOccDialogInfo);

virtual BOOL CreateDlgControls(
    CWnd* pWndParent,
    void* lpResource,
    _AFX_OCC_DIALOG_INFO* pOccDialogInfo);
```

### <a name="parameters"></a>パラメーター

*pWndParent*<br/>
ダイアログ オブジェクトの親へのポインター。

*lpszResourceName*<br/>
作成されるリソースの名前。

*pOccDialogInfo*<br/>
ダイアログ オブジェクトの作成に使用するダイアログ テンプレートへのポインター。

*lpResource*<br/>
リソースへのポインター。

### <a name="return-value"></a>戻り値

コントロールが正常に作成された場合は 0 以外それ以外の場合 0 を返します。

##  <a name="createsite"></a>  COccManager::CreateSite

によって示されるコンテナーにホスト コントロール サイトを作成するためにフレームワークによって呼び出される*pCtrlCont*します。

```
virtual COleControlSite* CreateSite(COleControlContainer* pCtrlCont);
```

### <a name="parameters"></a>パラメーター

*pCtrlCont*<br/>
新しいコントロール サイトをホストしているコントロールのコンテナーへのポインター。

### <a name="return-value"></a>戻り値

新しく作成されたコントロール サイトへのポインター。

### <a name="remarks"></a>Remarks

カスタム コントロールを作成するには、この関数をオーバーライドを使用して、サイト、 [COleControlSite](../../mfc/reference/colecontrolsite-class.md)-クラスを派生します。

各コントロールのコンテナーには、複数のサイトをホストできます。 複数の呼び出しで追加サイトを作成`CreateSite`です。

##  <a name="getdefbtncode"></a>  COccManager::GetDefBtnCode

この関数では、コントロールが既定のプッシュ ボタンかどうかを決定します。

```
static DWORD AFX_CDECL GetDefBtnCode(CWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

*我が物*<br/>
ボタン コントロールを含むウィンドウ オブジェクト。

### <a name="return-value"></a>戻り値

次のいずれかの値です。

- DLGC_DEFPUSHBUTTON コントロールは、ダイアログ ボックスで既定のボタンです。

- DLGC_UNDEFPUSHBUTTON コントロールは、ダイアログ ボックスで既定のボタンではありません。

- **0**コントロールがボタンではありません。

##  <a name="isdialogmessage"></a>  COccManager::IsDialogMessage

メッセージが、指定されたダイアログ ボックスにして場合は、メッセージを処理するかどうかを判断するためにフレームワークによって呼び出されます。

```
virtual BOOL IsDialogMessage(
    CWnd* pWndDlg,
    LPMSG lpMsg);
```

### <a name="parameters"></a>パラメーター

*pWndDlg*<br/>
メッセージの対象となるダイアログへのポインター。

*lpMsg*<br/>
ポインター、`MSG`確認するメッセージを含む構造体。

### <a name="return-value"></a>戻り値

メッセージが処理された場合は 0 以外それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

既定の動作`IsDialogMessage`キーボード メッセージを確認し、対応するダイアログ ボックスの選択に変換します。 たとえば、TAB キーを押すと、[次へ] のコントロールまたはコントロールのグループを選択します。

指定されたダイアログに送信されるメッセージのカスタム動作を指定するには、この関数をオーバーライドします。

##  <a name="islabelcontrol"></a>  COccManager::IsLabelControl

この関数では、指定したコントロールがラベル コントロールかどうかを決定します。

```
static BOOL AFX_CDECL IsLabelControl(CWnd* pWnd);
static BOOL AFX_CDECL IsLabelControl(COleControlSiteOrWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

*我が物*<br/>
コントロールを含むウィンドウへのポインター。

### <a name="return-value"></a>戻り値

コントロールがラベルである場合、0 以外の場合それ以外の場合 0

### <a name="remarks"></a>Remarks

ラベル コントロールは、任意のコントロールは、順序の [次へ] のラベルのように機能する 1 つです。

##  <a name="ismatchingmnemonic"></a>  COccManager::IsMatchingMnemonic

現在のアクセラレータ キーがコントロールによって表されると一致するかどうかを判断するには、この関数を呼び出します。

```
static BOOL AFX_CDECL IsMatchingMnemonic(
    CWnd* pWnd,
    LPMSG lpMsg);

static BOOL AFX_CDECL IsMatchingMnemonic(
    COleControlSiteOrWnd* pWnd,
    LPMSG lpMsg);
```

### <a name="parameters"></a>パラメーター

*我が物*<br/>
コントロールを含むウィンドウへのポインター。

*lpMsg*<br/>
一致するようにニーモニックを含むメッセージへのポインター。

### <a name="return-value"></a>戻り値

ニーモニックがコントロールと一致する場合、0 以外の場合それ以外の場合 0

### <a name="remarks"></a>Remarks

##  <a name="onevent"></a>  COccManager::OnEvent

指定したイベントを処理するためにフレームワークによって呼び出されます。

```
virtual BOOL OnEvent(
    CCmdTarget* pCmdTarget,
    UINT idCtrl,
    AFX_EVENT* pEvent,
    AFX_CMDHANDLERINFO* pHandlerInfo);
```

### <a name="parameters"></a>パラメーター

*pCmdTarget*<br/>
ポインター、`CCmdTarget`オブジェクト イベントを処理しようとしています。

*idCtrl*<br/>
コントロールのリソース ID。

*pEvent*<br/>
処理されるイベント。

*pHandlerInfo*<br/>
NULL 以外の場合`OnEvent`塗りつぶす、`pTarget`と`pmf`のメンバー、`AFX_CMDHANDLERINFO`コマンドをディスパッチするのではなく構造体。 通常、このパラメーターは NULL を指定する必要があります。

### <a name="return-value"></a>戻り値

イベントが処理された場合、それ以外の場合 0 0 以外の値。

### <a name="remarks"></a>Remarks

既定のイベント処理プロセスをカスタマイズするには、この関数をオーバーライドします。

##  <a name="precreatedialog"></a>  COccManager::PreCreateDialog

実際のダイアログ ボックスを作成する前に ActiveX コントロール用のダイアログ テンプレートを処理するためにフレームワークによって呼び出されます。

```
virtual const DLGTEMPLATE* PreCreateDialog(
    _AFX_OCC_DIALOG_INFO* pOccDialogInfo,
    const DLGTEMPLATE* pOrigTemplate);
```

### <a name="parameters"></a>パラメーター

*pOccDialogInfo*<br/>
`_AFX_OCC_DIALOG_INFO`ダイアログ テンプレートと、ダイアログによってホストされているすべての ActiveX コントロールに関する情報を含む構造体。

*pOrigTemplate*<br/>
ダイアログ ボックスの作成に使用するダイアログ テンプレートへのポインター。

### <a name="return-value"></a>戻り値

ダイアログ ボックスを作成するために使用するダイアログ テンプレート構造体へのポインター。

### <a name="remarks"></a>Remarks

既定の動作への呼び出しは、 `SplitDialogTemplate`ActiveX がある場合は、存在するコントロールの特定および結果のダイアログ テンプレートを返します。

ActiveX コントロールのホスト ダイアログ ボックスを作成するプロセスをカスタマイズするには、この関数をオーバーライドします。

##  <a name="postcreatedialog"></a>  COccManager::PostCreateDialog

ダイアログ テンプレートに割り当てられたメモリを解放するためにフレームワークによって呼び出されます。

```
virtual void PostCreateDialog(_AFX_OCC_DIALOG_INFO* pOccDialogInfo);
```

### <a name="parameters"></a>パラメーター

*pOccDialogInfo*<br/>
`_AFX_OCC_DIALOG_INFO`ダイアログ テンプレートと、ダイアログによってホストされているすべての ActiveX コントロールに関する情報を含む構造体。

### <a name="remarks"></a>Remarks

このメモリはへの呼び出しによって割り当てられた`SplitDialogTemplate`、ダイアログ ボックスで、ホストされている ActiveX コントロールに使用されたとします。

ダイアログ ボックスのオブジェクトによって使用されているリソースのクリーンアップのプロセスをカスタマイズするには、この関数をオーバーライドします。

##  <a name="setdefaultbutton"></a>  COccManager::SetDefaultButton

既定のボタンとして設定するには、この関数を呼び出します。

```
static void AFX_CDECL SetDefaultButton(
    CWnd* pWnd,
    BOOL bDefault);
```

### <a name="parameters"></a>パラメーター

*我が物*<br/>
コントロールを含むウィンドウへのポインター。

*bDefault*<br/>
以外の場合は、コントロールが既定のボタンになる必要があります。それ以外の場合 0 を返します。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

> [!NOTE]
>  コントロールには、OLEMISC_ACTSLIKEBUTTON ステータス ビット セットが必要です。 入りますフラグの詳細については、次を参照してください。、[入ります](/windows/desktop/api/oleidl/ne-oleidl-tagolemisc)Windows SDK のトピックです。

##  <a name="splitdialogtemplate"></a>  COccManager::SplitDialogTemplate

コモン ダイアログのコントロールからの ActiveX コントロールを分割するためにフレームワークによって呼び出されます。

```
virtual DLGTEMPLATE* SplitDialogTemplate(
    const DLGTEMPLATE* pTemplate,
    DLGITEMTEMPLATE** ppOleDlgItems);
```

### <a name="parameters"></a>パラメーター

*pTemplate*<br/>
確認するダイアログ テンプレートへのポインター。

*ppOleDlgItems*<br/>
ActiveX コントロールでは、ダイアログ ボックスの項目へのポインターのリスト。

### <a name="return-value"></a>戻り値

非 ActiveX コントロールのみを含むダイアログ テンプレートの構造体へのポインター。 ActiveX コントロールが存在しない場合は、NULL が返されます。

### <a name="remarks"></a>Remarks

すべての ActiveX コントロールが見つかった場合は、テンプレートが分析され、ActiveX 以外のコントロールのみを含む、新しいテンプレートが作成されます。 このプロセス中に見つかったすべての ActiveX コントロールに追加されます*ppOleDlgItems*します。

テンプレート内に ActiveX コントロールがない場合は、NULL が返されます*します。*

> [!NOTE]
>  新しいテンプレートが空き状態に割り当てられるメモリ、`PostCreateDialog`関数。

このプロセスをカスタマイズするには、この関数をオーバーライドします。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[COleControlSite クラス](../../mfc/reference/colecontrolsite-class.md)<br/>
[COleControlContainer クラス](../../mfc/reference/colecontrolcontainer-class.md)
