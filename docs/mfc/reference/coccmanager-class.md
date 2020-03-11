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
ms.openlocfilehash: c2a49e3396879e5f1e0864ab5342b57541c6b36c
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2020
ms.locfileid: "78865939"
---
# <a name="coccmanager-class"></a>COccManager クラス

`COleControlContainer` オブジェクトと `COleControlSite` オブジェクトによって実装されるさまざまなカスタム コントロール サイトを管理します。

## <a name="syntax"></a>構文

```
class COccManager : public CNoTrackObject
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|Name|説明|
|----------|-----------------|
|[COccManager:: CreateContainer](#createcontainer)|`COleContainer` オブジェクトを作成します。|
|[COccManager:: CreateDlgControls](#createdlgcontrols)|関連付けられている `COleContainer` オブジェクトによってホストされる ActiveX コントロールを作成します。|
|[COccManager:: CreateSite](#createsite)|`COleClientSite` オブジェクトを作成します。|
|[COccManager:: GetDefBtnCode](#getdefbtncode)|既定のボタンのコードを取得します。|
|[COccManager::IsDialogMessage](#isdialogmessage)|ダイアログメッセージの対象を決定します。|
|[COccManager::IsLabelControl](#islabelcontrol)|指定したコントロールがラベルコントロールであるかどうかを判断します。|
|[COccManager::IsMatchingMnemonic](#ismatchingmnemonic)|現在のニーモニックが、指定されたコントロールのニーモニックと一致するかどうかを判断します。|
|[COccManager:: OnEvent](#onevent)|指定されたイベントの処理を試みます。|
|[COccManager::P ostCreateDialog](#postcreatedialog)|ダイアログの作成時に割り当てられたリソースを解放します。|
|[COccManager::P reCreateDialog](#precreatedialog)|ActiveX コントロールのダイアログテンプレートを処理します。|
|[COccManager:: SetDefaultButton](#setdefaultbutton)|指定したコントロールの既定の状態を切り替えます。|
|[COccManager:: Splitのテンプレート](#splitdialogtemplate)|指定されたダイアログテンプレートのコモンコントロールから、既存の ActiveX コントロールを分離します。|

## <a name="remarks"></a>コメント

基底クラスである `CNoTrackObject`は、ドキュメントに記載されていない基本クラスです (AFXTLS にあります)。H)。 MFC フレームワークによって使用されるように設計された `CNoTrackObject` クラスから派生したクラスは、メモリリーク検出から除外されます。 `CNoTrackObject`から直接派生させることはお勧めしません。

## <a name="inheritance-hierarchy"></a>継承階層

`CNoTrackObject`

`COccManager`

## <a name="requirements"></a>要件

**ヘッダー:** afxocc

##  <a name="createcontainer"></a>COccManager:: CreateContainer

コントロールコンテナーを作成するために、フレームワークによって呼び出されます。

```
virtual COleControlContainer* CreateContainer(CWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

*pWnd*<br/>
カスタムサイトコンテナーに関連付けられたウィンドウオブジェクトへのポインター。

### <a name="return-value"></a>戻り値

新しく作成されたコンテナーへのポインター。それ以外の場合は NULL。

### <a name="remarks"></a>コメント

カスタムサイトの作成の詳細については、「 [COleControlContainer:: AttachControlSite](../../mfc/reference/colecontrolcontainer-class.md#attachcontrolsite)」を参照してください。

##  <a name="createdlgcontrols"></a>COccManager:: CreateDlgControls

*Poccの info*パラメーターによって指定された ActiveX コントロールを作成するには、この関数を呼び出します。

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
ダイアログオブジェクトの親へのポインター。

*lpszResourceName*<br/>
作成されるリソースの名前。

*Poccの情報*<br/>
ダイアログオブジェクトの作成に使用されるダイアログテンプレートへのポインター。

*lpResource*<br/>
リソースへのポインター。

### <a name="return-value"></a>戻り値

コントロールが正常に作成された場合は0以外の。それ以外の場合は0。

##  <a name="createsite"></a>COccManager:: CreateSite

*PCtrlCont*が指すコンテナーによってホストされるコントロールサイトを作成するために、フレームワークによって呼び出されます。

```
virtual COleControlSite* CreateSite(COleControlContainer* pCtrlCont);
```

### <a name="parameters"></a>パラメーター

*pCtrlCont*<br/>
新しいコントロールサイトをホストしているコントロールコンテナーへのポインター。

### <a name="return-value"></a>戻り値

新しく作成されたコントロールサイトへのポインター。

### <a name="remarks"></a>コメント

[COleControlSite](../../mfc/reference/colecontrolsite-class.md)派生クラスを使用して、カスタムコントロールサイトを作成するには、この関数をオーバーライドします。

各コントロールコンテナーは、複数のサイトをホストできます。 `CreateSite`の複数の呼び出しを使用して、追加のサイトを作成します。

##  <a name="getdefbtncode"></a>COccManager:: GetDefBtnCode

コントロールが既定のプッシュボタンであるかどうかを判断するには、この関数を呼び出します。

```
static DWORD AFX_CDECL GetDefBtnCode(CWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

*pWnd*<br/>
ボタンコントロールを格納しているウィンドウオブジェクト。

### <a name="return-value"></a>戻り値

次のいずれかの値:

- DLGC_DEFPUSHBUTTON コントロールは、ダイアログの既定のボタンです。

- DLGC_UNDEFPUSHBUTTON コントロールは、ダイアログの既定のボタンではありません。

- **0**コントロールはボタンではありません。

##  <a name="isdialogmessage"></a>COccManager::IsDialogMessage

指定されたダイアログボックスに対してメッセージが意図されているかどうかを判断するためにフレームワークによって呼び出されます。メッセージがの場合は、メッセージを処理します。

```
virtual BOOL IsDialogMessage(
    CWnd* pWndDlg,
    LPMSG lpMsg);
```

### <a name="parameters"></a>パラメーター

*pWndDlg*<br/>
メッセージの目的のターゲットダイアログへのポインター。

*lpMsg*<br/>
確認するメッセージが格納されている `MSG` 構造体へのポインター。

### <a name="return-value"></a>戻り値

メッセージが処理される場合は0以外の。それ以外の場合は0。

### <a name="remarks"></a>コメント

`IsDialogMessage` の既定の動作では、キーボードメッセージを確認し、対応するダイアログボックスの選択に変換します。 たとえば、TAB キーを押すと、次のコントロールまたはコントロールグループが選択されます。

指定したダイアログに送信されるメッセージに対してカスタム動作を提供するには、この関数をオーバーライドします。

##  <a name="islabelcontrol"></a>COccManager::IsLabelControl

指定したコントロールがラベルコントロールであるかどうかを判断するには、この関数を呼び出します。

```
static BOOL AFX_CDECL IsLabelControl(CWnd* pWnd);
static BOOL AFX_CDECL IsLabelControl(COleControlSiteOrWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

*pWnd*<br/>
コントロールを格納しているウィンドウへのポインター。

### <a name="return-value"></a>戻り値

コントロールがラベルの場合は0以外の。それ以外の場合は0

### <a name="remarks"></a>コメント

ラベルコントロールとは、順序の次のコントロールに対するラベルのように機能するコントロールです。

##  <a name="ismatchingmnemonic"></a>COccManager::IsMatchingMnemonic

現在のニーモニックがコントロールによって表されるものと一致するかどうかを判断するには、この関数を呼び出します。

```
static BOOL AFX_CDECL IsMatchingMnemonic(
    CWnd* pWnd,
    LPMSG lpMsg);

static BOOL AFX_CDECL IsMatchingMnemonic(
    COleControlSiteOrWnd* pWnd,
    LPMSG lpMsg);
```

### <a name="parameters"></a>パラメーター

*pWnd*<br/>
コントロールを格納しているウィンドウへのポインター。

*lpMsg*<br/>
一致するニーモニックを格納しているメッセージへのポインター。

### <a name="return-value"></a>戻り値

ニーモニックがコントロールと一致する場合は0以外の。それ以外の場合は0

### <a name="remarks"></a>コメント

##  <a name="onevent"></a>COccManager:: OnEvent

指定されたイベントを処理するためにフレームワークによって呼び出されます。

```
virtual BOOL OnEvent(
    CCmdTarget* pCmdTarget,
    UINT idCtrl,
    AFX_EVENT* pEvent,
    AFX_CMDHANDLERINFO* pHandlerInfo);
```

### <a name="parameters"></a>パラメーター

*pCmdTarget*<br/>
イベントを処理しようとしている `CCmdTarget` オブジェクトへのポインター

*idCtrl*<br/>
コントロールのリソース ID。

*pEvent*<br/>
処理されているイベント。

*pHandlerInfo*<br/>
NULL でない場合は、コマンドをディスパッチするのではなく、`AFX_CMDHANDLERINFO` 構造体の `pTarget` と `pmf` メンバーを `OnEvent` ます。 通常、このパラメーターは NULL にする必要があります。

### <a name="return-value"></a>戻り値

イベントが処理された場合は0以外の値。それ以外の場合は0。

### <a name="remarks"></a>コメント

既定のイベント処理プロセスをカスタマイズするには、この関数をオーバーライドします。

##  <a name="precreatedialog"></a>COccManager::P reCreateDialog

実際のダイアログボックスを作成する前に、ActiveX コントロールのダイアログテンプレートを処理するためにフレームワークによって呼び出されます。

```
virtual const DLGTEMPLATE* PreCreateDialog(
    _AFX_OCC_DIALOG_INFO* pOccDialogInfo,
    const DLGTEMPLATE* pOrigTemplate);
```

### <a name="parameters"></a>パラメーター

*Poccの情報*<br/>
ダイアログテンプレートおよびダイアログでホストされている ActiveX コントロールに関する情報を格納している `_AFX_OCC_DIALOG_INFO` 構造体。

*pOrigTemplate*<br/>
ダイアログボックスの作成に使用するダイアログテンプレートへのポインター。

### <a name="return-value"></a>戻り値

ダイアログボックスの作成に使用されるダイアログテンプレート構造体へのポインター。

### <a name="remarks"></a>コメント

既定の動作では、`SplitDialogTemplate`を呼び出し、ActiveX コントロールが存在するかどうかを確認してから、結果のダイアログテンプレートを返します。

ActiveX コントロールをホストするダイアログボックスを作成するプロセスをカスタマイズするには、この関数をオーバーライドします。

##  <a name="postcreatedialog"></a>COccManager::P ostCreateDialog

ダイアログテンプレートに割り当てられたメモリを解放するために、フレームワークによって呼び出されます。

```
virtual void PostCreateDialog(_AFX_OCC_DIALOG_INFO* pOccDialogInfo);
```

### <a name="parameters"></a>パラメーター

*Poccの情報*<br/>
ダイアログテンプレートおよびダイアログでホストされている ActiveX コントロールに関する情報を格納している `_AFX_OCC_DIALOG_INFO` 構造体。

### <a name="remarks"></a>コメント

このメモリは `SplitDialogTemplate`への呼び出しによって割り当てられており、ダイアログボックスの任意のホスト型 ActiveX コントロールに使用されていました。

この関数をオーバーライドして、ダイアログボックスオブジェクトによって使用されるリソースをクリーンアップするプロセスをカスタマイズします。

##  <a name="setdefaultbutton"></a>COccManager:: SetDefaultButton

コントロールを既定のボタンとして設定するには、この関数を呼び出します。

```
static void AFX_CDECL SetDefaultButton(
    CWnd* pWnd,
    BOOL bDefault);
```

### <a name="parameters"></a>パラメーター

*pWnd*<br/>
コントロールを格納しているウィンドウへのポインター。

*bDefault*<br/>
コントロールが既定のボタンになる場合は0以外の値。それ以外の場合は0。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>コメント

> [!NOTE]
>  コントロールには OLEMISC_ACTSLIKEBUTTON ステータスビットが設定されている必要があります。 OLEMISC フラグの詳細については、Windows SDK の[OLEMISC](/windows/win32/api/oleidl/ne-oleidl-olemisc)のトピックを参照してください。

##  <a name="splitdialogtemplate"></a>COccManager:: Splitのテンプレート

コモンダイアログコントロールから ActiveX コントロールを分割するために、フレームワークによって呼び出されます。

```
virtual DLGTEMPLATE* SplitDialogTemplate(
    const DLGTEMPLATE* pTemplate,
    DLGITEMTEMPLATE** ppOleDlgItems);
```

### <a name="parameters"></a>パラメーター

*pTemplate*<br/>
検査するダイアログテンプレートへのポインター。

*ppOleDlgItems*<br/>
ActiveX コントロールであるダイアログボックス項目へのポインターのリスト。

### <a name="return-value"></a>戻り値

非 ActiveX コントロールのみを含むダイアログテンプレート構造体へのポインター。 ActiveX コントロールが存在しない場合は、NULL が返されます。

### <a name="remarks"></a>コメント

ActiveX コントロールが見つかると、テンプレートが分析され、非 ActiveX コントロールのみを含む新しいテンプレートが作成されます。 このプロセス中に見つかった ActiveX コントロールは、 *ppOleDlgItems*に追加されます。

テンプレートに ActiveX コントロールがない場合は、NULL が返され*ます。*

> [!NOTE]
>  新しいテンプレートに割り当てられたメモリは、`PostCreateDialog` 関数で解放されます。

このプロセスをカスタマイズするには、この関数をオーバーライドします。

## <a name="see-also"></a>参照

[階層図](../../mfc/hierarchy-chart.md)<br/>
[COleControlSite クラス](../../mfc/reference/colecontrolsite-class.md)<br/>
[COleControlContainer クラス](../../mfc/reference/colecontrolcontainer-class.md)
