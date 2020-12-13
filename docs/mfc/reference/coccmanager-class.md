---
description: '詳細情報: COccManager クラス'
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
ms.openlocfilehash: 8acd39825f7f842a266a4b1dbf187ba4f7f9b5ca
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331431"
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
|[COccManager:: CreateContainer](#createcontainer)|`COleContainer` オブジェクトを作成します。|
|[COccManager:: CreateDlgControls](#createdlgcontrols)|関連付けられたオブジェクトによってホストされる ActiveX コントロールを作成し `COleContainer` ます。|
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

## <a name="remarks"></a>解説

基本クラスは、ドキュメントに記載されていない `CNoTrackObject` 基本クラス (AFXTLS にあります) です。H)。 MFC フレームワークによって使用されるように設計されたクラスでは、クラスから派生したクラス `CNoTrackObject` はメモリリーク検出から除外されます。 から直接派生させることはお勧め `CNoTrackObject` しません。

## <a name="inheritance-hierarchy"></a>継承階層

`CNoTrackObject`

`COccManager`

## <a name="requirements"></a>要件

**ヘッダー:** afxocc

## <a name="coccmanagercreatecontainer"></a><a name="createcontainer"></a> COccManager:: CreateContainer

コントロールコンテナーを作成するために、フレームワークによって呼び出されます。

```
virtual COleControlContainer* CreateContainer(CWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

*pWnd*<br/>
カスタムサイトコンテナーに関連付けられたウィンドウオブジェクトへのポインター。

### <a name="return-value"></a>戻り値

新しく作成されたコンテナーへのポインター。それ以外の場合は NULL。

### <a name="remarks"></a>解説

カスタムサイトの作成の詳細については、「 [COleControlContainer:: AttachControlSite](../../mfc/reference/colecontrolcontainer-class.md#attachcontrolsite)」を参照してください。

## <a name="coccmanagercreatedlgcontrols"></a><a name="createdlgcontrols"></a> COccManager:: CreateDlgControls

*Poccの info* パラメーターによって指定された ActiveX コントロールを作成するには、この関数を呼び出します。

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

## <a name="coccmanagercreatesite"></a><a name="createsite"></a> COccManager:: CreateSite

*PCtrlCont* が指すコンテナーによってホストされるコントロールサイトを作成するために、フレームワークによって呼び出されます。

```
virtual COleControlSite* CreateSite(COleControlContainer* pCtrlCont);
```

### <a name="parameters"></a>パラメーター

*pCtrlCont*<br/>
新しいコントロールサイトをホストしているコントロールコンテナーへのポインター。

### <a name="return-value"></a>戻り値

新しく作成されたコントロールサイトへのポインター。

### <a name="remarks"></a>解説

[COleControlSite](../../mfc/reference/colecontrolsite-class.md)派生クラスを使用して、カスタムコントロールサイトを作成するには、この関数をオーバーライドします。

各コントロールコンテナーは、複数のサイトをホストできます。 を複数回呼び出す場合は、追加のサイトを作成 `CreateSite` します。

## <a name="coccmanagergetdefbtncode"></a><a name="getdefbtncode"></a> COccManager:: GetDefBtnCode

コントロールが既定のプッシュボタンであるかどうかを判断するには、この関数を呼び出します。

```
static DWORD AFX_CDECL GetDefBtnCode(CWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

*pWnd*<br/>
ボタンコントロールを格納しているウィンドウオブジェクト。

### <a name="return-value"></a>戻り値

次のいずれかの値です。

- DLGC_DEFPUSHBUTTON コントロールは、ダイアログの既定のボタンです。

- DLGC_UNDEFPUSHBUTTON コントロールは、ダイアログの既定のボタンではありません。

- **0** コントロールはボタンではありません。

## <a name="coccmanagerisdialogmessage"></a><a name="isdialogmessage"></a> COccManager::IsDialogMessage

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
`MSG`確認するメッセージが格納されている構造体へのポインター。

### <a name="return-value"></a>戻り値

メッセージが処理される場合は0以外の。それ以外の場合は0。

### <a name="remarks"></a>解説

の既定の動作で `IsDialogMessage` は、キーボードメッセージを確認し、対応するダイアログボックスの選択に変換します。 たとえば、TAB キーを押すと、次のコントロールまたはコントロールグループが選択されます。

指定したダイアログに送信されるメッセージに対してカスタム動作を提供するには、この関数をオーバーライドします。

## <a name="coccmanagerislabelcontrol"></a><a name="islabelcontrol"></a> COccManager::IsLabelControl

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

### <a name="remarks"></a>解説

ラベルコントロールとは、順序の次のコントロールに対するラベルのように機能するコントロールです。

## <a name="coccmanagerismatchingmnemonic"></a><a name="ismatchingmnemonic"></a> COccManager::IsMatchingMnemonic

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

### <a name="remarks"></a>解説

## <a name="coccmanageronevent"></a><a name="onevent"></a> COccManager:: OnEvent

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
`CCmdTarget`イベントを処理しようとしているオブジェクトへのポインター。

*idCtrl*<br/>
コントロールのリソース ID。

*pEvent*<br/>
処理されているイベント。

*pHandlerInfo*<br/>
NULL でない場合は、 `OnEvent` `pTarget` コマンドを `pmf` ディスパッチするのではなく、構造体のメンバーとメンバーをに入力し `AFX_CMDHANDLERINFO` ます。 通常、このパラメーターは NULL にする必要があります。

### <a name="return-value"></a>戻り値

イベントが処理された場合は0以外の値。それ以外の場合は0。

### <a name="remarks"></a>解説

既定のイベント処理プロセスをカスタマイズするには、この関数をオーバーライドします。

## <a name="coccmanagerprecreatedialog"></a><a name="precreatedialog"></a> COccManager::P reCreateDialog

実際のダイアログボックスを作成する前に、ActiveX コントロールのダイアログテンプレートを処理するためにフレームワークによって呼び出されます。

```
virtual const DLGTEMPLATE* PreCreateDialog(
    _AFX_OCC_DIALOG_INFO* pOccDialogInfo,
    const DLGTEMPLATE* pOrigTemplate);
```

### <a name="parameters"></a>パラメーター

*Poccの情報*<br/>
ダイアログ `_AFX_OCC_DIALOG_INFO` テンプレートおよびダイアログでホストされている ActiveX コントロールに関する情報を格納している構造体。

*pOrigTemplate*<br/>
ダイアログボックスの作成に使用するダイアログテンプレートへのポインター。

### <a name="return-value"></a>戻り値

ダイアログボックスの作成に使用されるダイアログテンプレート構造体へのポインター。

### <a name="remarks"></a>解説

既定の動作では、が呼び出さ `SplitDialogTemplate` れ、ActiveX コントロールが存在するかどうかが確認された後、結果のダイアログテンプレートが返されます。

ActiveX コントロールをホストするダイアログボックスを作成するプロセスをカスタマイズするには、この関数をオーバーライドします。

## <a name="coccmanagerpostcreatedialog"></a><a name="postcreatedialog"></a> COccManager::P ostCreateDialog

ダイアログテンプレートに割り当てられたメモリを解放するために、フレームワークによって呼び出されます。

```
virtual void PostCreateDialog(_AFX_OCC_DIALOG_INFO* pOccDialogInfo);
```

### <a name="parameters"></a>パラメーター

*Poccの情報*<br/>
ダイアログ `_AFX_OCC_DIALOG_INFO` テンプレートおよびダイアログでホストされている ActiveX コントロールに関する情報を格納している構造体。

### <a name="remarks"></a>解説

このメモリは、の呼び出しによって割り当てられ、 `SplitDialogTemplate` ダイアログボックスの任意のホスト型 ActiveX コントロールに使用されていました。

この関数をオーバーライドして、ダイアログボックスオブジェクトによって使用されるリソースをクリーンアップするプロセスをカスタマイズします。

## <a name="coccmanagersetdefaultbutton"></a><a name="setdefaultbutton"></a> COccManager:: SetDefaultButton

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

### <a name="remarks"></a>解説

> [!NOTE]
> コントロールには OLEMISC_ACTSLIKEBUTTON ステータスビットが設定されている必要があります。 OLEMISC フラグの詳細については、Windows SDK の [OLEMISC](/windows/win32/api/oleidl/ne-oleidl-olemisc) のトピックを参照してください。

## <a name="coccmanagersplitdialogtemplate"></a><a name="splitdialogtemplate"></a> COccManager:: Splitのテンプレート

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

### <a name="remarks"></a>解説

ActiveX コントロールが見つかると、テンプレートが分析され、非 ActiveX コントロールのみを含む新しいテンプレートが作成されます。 このプロセス中に見つかった ActiveX コントロールは、 *ppOleDlgItems* に追加されます。

テンプレートに ActiveX コントロールがない場合は、NULL が返され *ます。*

> [!NOTE]
> 新しいテンプレートに割り当てられたメモリは、関数で解放され `PostCreateDialog` ます。

このプロセスをカスタマイズするには、この関数をオーバーライドします。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[COleControlSite クラス](../../mfc/reference/colecontrolsite-class.md)<br/>
[COleControlContainer クラス](../../mfc/reference/colecontrolcontainer-class.md)
