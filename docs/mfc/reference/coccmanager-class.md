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
ms.openlocfilehash: 5637a4709e90bb14caff3fe4e396487e62e213e1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360363"
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
|[コンテナの作成](#createcontainer)|`COleContainer` オブジェクトを作成します。|
|[コントロールマネージャー::コントロールを作成します。](#createdlgcontrols)|関連付けられた`COleContainer`オブジェクトによってホストされる ActiveX コントロールを作成します。|
|[コクマネージャー::サイトの作成](#createsite)|`COleClientSite` オブジェクトを作成します。|
|[コクマネージャー::ゲットデフBtnコード](#getdefbtncode)|既定のボタンのコードを取得します。|
|[コクマネージャー::メッセージ](#isdialogmessage)|ダイアログ メッセージのターゲットを決定します。|
|[コントロールコントロール](#islabelcontrol)|指定したコントロールがラベル コントロールかどうかを判断します。|
|[コックマネージャー::イストマッチムネモニック](#ismatchingmnemonic)|現在のニーモニックが、指定されたコントロールのニーモニックと一致するかどうかを判断します。|
|[コクマネージャー::オンイベント](#onevent)|指定されたイベントの処理を試みます。|
|[:PostCreateダイアログ](#postcreatedialog)|ダイアログの作成時に割り当てられたリソースを解放します。|
|[:Pを作成します。](#precreatedialog)|ActiveX コントロールのダイアログ テンプレートを処理します。|
|[コントロール マネージャー::既定のボタンを設定します。](#setdefaultbutton)|指定したコントロールの既定の状態を切り替えます。|
|[コントロール マネージャー::スプリットダイアログテンプレート](#splitdialogtemplate)|指定されたダイアログ テンプレートのコモン コントロールから既存の ActiveX コントロールを分離します。|

## <a name="remarks"></a>解説

基本クラスは、`CNoTrackObject`ドキュメント化されていない基本クラスです ( AFXTLS にあります。H). MFC フレームワークで使用するように設計された`CNoTrackObject`クラスは、メモリ リーク検出から除外されます。 から`CNoTrackObject`直接派生することはお勧めしません。

## <a name="inheritance-hierarchy"></a>継承階層

`CNoTrackObject`

`COccManager`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxocc.h

## <a name="coccmanagercreatecontainer"></a><a name="createcontainer"></a>コンテナの作成

コントロール コンテナーを作成するために、フレームワークによって呼び出されます。

```
virtual COleControlContainer* CreateContainer(CWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

*Pwnd*<br/>
カスタム サイト コンテナーに関連付けられているウィンドウ オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

新しく作成されたコンテナーへのポインター。それ以外の場合は NULL。

### <a name="remarks"></a>解説

カスタム サイトの作成の詳細については[、「COleControl コンテナ::接続コントロールサイト](../../mfc/reference/colecontrolcontainer-class.md#attachcontrolsite)」を参照してください。

## <a name="coccmanagercreatedlgcontrols"></a><a name="createdlgcontrols"></a>コントロールマネージャー::コントロールを作成します。

この関数を呼び出して、*パラメーター*で指定された ActiveX コントロールを作成します。

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

*親の子*<br/>
ダイアログ オブジェクトの親へのポインター。

*リソース名*<br/>
作成されるリソースの名前。

*をクリックします。*<br/>
ダイアログ オブジェクトの作成に使用するダイアログ テンプレートへのポインター。

*リソースを指定します。*<br/>
リソースへのポインター。

### <a name="return-value"></a>戻り値

コントロールが正常に作成された場合は 0 以外の値を返します。それ以外の場合は 0。

## <a name="coccmanagercreatesite"></a><a name="createsite"></a>コクマネージャー::サイトの作成

*pCtrlCont*が指すコンテナーによってホストされるコントロール サイトを作成するために、フレームワークによって呼び出されます。

```
virtual COleControlSite* CreateSite(COleControlContainer* pCtrlCont);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
新しいコントロール サイトをホストするコントロール コンテナーへのポインター。

### <a name="return-value"></a>戻り値

新しく作成されたコントロール サイトへのポインター。

### <a name="remarks"></a>解説

この関数をオーバーライドして[、COleControlSite](../../mfc/reference/colecontrolsite-class.md)派生クラスを使用してカスタム コントロール サイトを作成します。

各コントロール コンテナーは複数のサイトをホストできます。 への複数の呼び出し`CreateSite`を持つ追加のサイトを作成します。

## <a name="coccmanagergetdefbtncode"></a><a name="getdefbtncode"></a>コクマネージャー::ゲットデフBtnコード

コントロールが既定のプッシュ ボタンかどうかを調べます。

```
static DWORD AFX_CDECL GetDefBtnCode(CWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

*Pwnd*<br/>
ボタン コントロールを含むウィンドウ オブジェクト。

### <a name="return-value"></a>戻り値

次のいずれかの値:

- DLGC_DEFPUSHBUTTONコントロールは、ダイアログボックスのデフォルトボタンです。

- DLGC_UNDEFPUSHBUTTON コントロールは、ダイアログボックスの既定のボタンではありません。

- **0**コントロールはボタンではありません。

## <a name="coccmanagerisdialogmessage"></a><a name="isdialogmessage"></a>コクマネージャー::メッセージ

指定されたダイアログ ボックスにメッセージが使用されているかどうかを調べ、メッセージが処理される場合は、フレームワークによって呼び出されます。

```
virtual BOOL IsDialogMessage(
    CWnd* pWndDlg,
    LPMSG lpMsg);
```

### <a name="parameters"></a>パラメーター

*pWndDlg*<br/>
メッセージの対象となるダイアログへのポインター。

*をクリックします。*<br/>
検査対象のメッセージ`MSG`を含む構造体へのポインター。

### <a name="return-value"></a>戻り値

メッセージが処理される場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

の既定の`IsDialogMessage`動作では、キーボード メッセージをチェックし、対応するダイアログ ボックスの選択に変換します。 たとえば、Tab キーを押すと、次のコントロールまたはコントロールグループが選択されます。

指定したダイアログに送信されるメッセージに対してカスタム動作を提供するには、この関数をオーバーライドします。

## <a name="coccmanagerislabelcontrol"></a><a name="islabelcontrol"></a>コントロールコントロール

指定したコントロールがラベル コントロールかどうかを調べます。

```
static BOOL AFX_CDECL IsLabelControl(CWnd* pWnd);
static BOOL AFX_CDECL IsLabelControl(COleControlSiteOrWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

*Pwnd*<br/>
コントロールを含むウィンドウへのポインター。

### <a name="return-value"></a>戻り値

コントロールがラベルの場合は 0 以外。それ以外の場合は 0

### <a name="remarks"></a>解説

ラベル コントロールは、順序付けの次のコントロールのラベルのように動作します。

## <a name="coccmanagerismatchingmnemonic"></a><a name="ismatchingmnemonic"></a>コックマネージャー::イストマッチムネモニック

現在のニーモニックがコントロールによって表される値と一致するかどうかを調べます。

```
static BOOL AFX_CDECL IsMatchingMnemonic(
    CWnd* pWnd,
    LPMSG lpMsg);

static BOOL AFX_CDECL IsMatchingMnemonic(
    COleControlSiteOrWnd* pWnd,
    LPMSG lpMsg);
```

### <a name="parameters"></a>パラメーター

*Pwnd*<br/>
コントロールを含むウィンドウへのポインター。

*をクリックします。*<br/>
一致するニーモニックを含むメッセージへのポインター。

### <a name="return-value"></a>戻り値

ニーモニックがコントロールと一致する場合は 0 以外の値を返します。それ以外の場合は 0

### <a name="remarks"></a>解説

## <a name="coccmanageronevent"></a><a name="onevent"></a>コクマネージャー::オンイベント

指定したイベントを処理するために、フレームワークによって呼び出されます。

```
virtual BOOL OnEvent(
    CCmdTarget* pCmdTarget,
    UINT idCtrl,
    AFX_EVENT* pEvent,
    AFX_CMDHANDLERINFO* pHandlerInfo);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
イベントを`CCmdTarget`処理しようとしているオブジェクトへのポインター

*idCtrl*<br/>
コントロールのリソース ID。

*イベント*<br/>
処理されるイベント。

*をクリックします。*<br/>
NULL でない場合`OnEvent`は、コマンドを`pTarget`ディスパッチ`pmf`する代わりに`AFX_CMDHANDLERINFO`、 構造体の メンバーと メンバーを入力します。 通常、このパラメーターは NULL にする必要があります。

### <a name="return-value"></a>戻り値

イベントが処理された場合は 0 以外の値を返します。

### <a name="remarks"></a>解説

既定のイベント処理プロセスをカスタマイズするには、この関数をオーバーライドします。

## <a name="coccmanagerprecreatedialog"></a><a name="precreatedialog"></a>:Pを作成します。

実際のダイアログ ボックスを作成する前に、ActiveX コントロールのダイアログ テンプレートを処理するために、フレームワークによって呼び出されます。

```
virtual const DLGTEMPLATE* PreCreateDialog(
    _AFX_OCC_DIALOG_INFO* pOccDialogInfo,
    const DLGTEMPLATE* pOrigTemplate);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
ダイアログ`_AFX_OCC_DIALOG_INFO`テンプレートとダイアログでホストされている ActiveX コントロールに関する情報を含む構造体。

*テンプレート*<br/>
ダイアログ ボックスの作成に使用するダイアログ テンプレートへのポインター。

### <a name="return-value"></a>戻り値

ダイアログ ボックスの作成に使用するダイアログ テンプレート構造へのポインター。

### <a name="remarks"></a>解説

既定の動作では、 に`SplitDialogTemplate`対して呼び出しが行われ、ActiveX コントロールが存在するかどうかが確認され、結果のダイアログ テンプレートが返されます。

ActiveX コントロールをホストするダイアログ ボックスを作成するプロセスをカスタマイズするには、この関数をオーバーライドします。

## <a name="coccmanagerpostcreatedialog"></a><a name="postcreatedialog"></a>:PostCreateダイアログ

ダイアログ テンプレートに割り当てられたメモリを解放するために、フレームワークによって呼び出されます。

```
virtual void PostCreateDialog(_AFX_OCC_DIALOG_INFO* pOccDialogInfo);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
ダイアログ`_AFX_OCC_DIALOG_INFO`テンプレートとダイアログでホストされている ActiveX コントロールに関する情報を含む構造体。

### <a name="remarks"></a>解説

このメモリは への`SplitDialogTemplate`呼び出しによって割り当てられ、ダイアログ ボックス内のホストされた ActiveX コントロールに対して使用されました。

ダイアログ ボックス オブジェクトで使用されるリソースをクリーンアップするプロセスをカスタマイズするには、この関数をオーバーライドします。

## <a name="coccmanagersetdefaultbutton"></a><a name="setdefaultbutton"></a>コントロール マネージャー::既定のボタンを設定します。

コントロールを既定のボタンとして設定します。

```
static void AFX_CDECL SetDefaultButton(
    CWnd* pWnd,
    BOOL bDefault);
```

### <a name="parameters"></a>パラメーター

*Pwnd*<br/>
コントロールを含むウィンドウへのポインター。

*bデフォルト*<br/>
コントロールが既定のボタンになる場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

> [!NOTE]
> コントロールには、OLEMISC_ACTSLIKEBUTTON状態ビットが設定されている必要があります。 OLEMISC フラグの詳細については、Windows SDK の[「OLEMISC」](/windows/win32/api/oleidl/ne-oleidl-olemisc)を参照してください。

## <a name="coccmanagersplitdialogtemplate"></a><a name="splitdialogtemplate"></a>コントロール マネージャー::スプリットダイアログテンプレート

コモン ダイアログ コントロールから ActiveX コントロールを分割するために、フレームワークによって呼び出されます。

```
virtual DLGTEMPLATE* SplitDialogTemplate(
    const DLGTEMPLATE* pTemplate,
    DLGITEMTEMPLATE** ppOleDlgItems);
```

### <a name="parameters"></a>パラメーター

*テンプレート*<br/>
検査するダイアログ テンプレートへのポインター。

*アイテム*<br/>
ActiveX コントロールであるダイアログ ボックス項目へのポインターの一覧。

### <a name="return-value"></a>戻り値

ActiveX 以外のコントロールだけを含むダイアログ テンプレート構造へのポインター。 ActiveX コントロールが存在しない場合は、NULL が返されます。

### <a name="remarks"></a>解説

ActiveX コントロールが見つかった場合は、テンプレートが分析され、ActiveX 以外のコントロールのみを含む新しいテンプレートが作成されます。 このプロセスで見つかった ActiveX コントロールは *、ppOleDlgItems*に追加されます。

テンプレートに ActiveX コントロールがない場合は、NULL*が返されます。*

> [!NOTE]
> 新しいテンプレートに割り当てられたメモリは、`PostCreateDialog`関数で解放されます。

このプロセスをカスタマイズするには、この関数をオーバーライドします。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/colecontrolsite-class.md)<br/>
[クラス](../../mfc/reference/colecontrolcontainer-class.md)
