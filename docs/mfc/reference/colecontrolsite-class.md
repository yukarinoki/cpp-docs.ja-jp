---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- COleControlSite
- AFXOCC/COleControlSite
- AFXOCC/COleControlSite::COleControlSite
- AFXOCC/COleControlSite::BindDefaultProperty
- AFXOCC/COleControlSite::BindProperty
- AFXOCC/COleControlSite::CreateControl
- AFXOCC/COleControlSite::DestroyControl
- AFXOCC/COleControlSite::DoVerb
- AFXOCC/COleControlSite::EnableDSC
- AFXOCC/COleControlSite::EnableWindow
- AFXOCC/COleControlSite::FreezeEvents
- AFXOCC/COleControlSite::GetDefBtnCode
- AFXOCC/COleControlSite::GetDlgCtrlID
- AFXOCC/COleControlSite::GetEventIID
- AFXOCC/COleControlSite::GetExStyle
- AFXOCC/COleControlSite::GetProperty
- AFXOCC/COleControlSite::GetStyle
- AFXOCC/COleControlSite::GetWindowText
- AFXOCC/COleControlSite::InvokeHelper
- AFXOCC/COleControlSite::InvokeHelperV
- AFXOCC/COleControlSite::IsDefaultButton
- AFXOCC/COleControlSite::IsWindowEnabled
- AFXOCC/COleControlSite::ModifyStyle
- AFXOCC/COleControlSite::ModifyStyleEx
- AFXOCC/COleControlSite::MoveWindow
- AFXOCC/COleControlSite::QuickActivate
- AFXOCC/COleControlSite::SafeSetProperty
- AFXOCC/COleControlSite::SetDefaultButton
- AFXOCC/COleControlSite::SetDlgCtrlID
- AFXOCC/COleControlSite::SetFocus
- AFXOCC/COleControlSite::SetProperty
- AFXOCC/COleControlSite::SetPropertyV
- AFXOCC/COleControlSite::SetWindowPos
- AFXOCC/COleControlSite::SetWindowText
- AFXOCC/COleControlSite::ShowWindow
- AFXOCC/COleControlSite::GetControlInfo
- AFXOCC/COleControlSite::m_bIsWindowless
- AFXOCC/COleControlSite::m_ctlInfo
- AFXOCC/COleControlSite::m_dwEventSink
- AFXOCC/COleControlSite::m_dwMiscStatus
- AFXOCC/COleControlSite::m_dwPropNotifySink
- AFXOCC/COleControlSite::m_dwStyle
- AFXOCC/COleControlSite::m_hWnd
- AFXOCC/COleControlSite::m_iidEvents
- AFXOCC/COleControlSite::m_nID
- AFXOCC/COleControlSite::m_pActiveObject
- AFXOCC/COleControlSite::m_pCtrlCont
- AFXOCC/COleControlSite::m_pInPlaceObject
- AFXOCC/COleControlSite::m_pObject
- AFXOCC/COleControlSite::m_pWindowlessObject
- AFXOCC/COleControlSite::m_pWndCtrl
- AFXOCC/COleControlSite::m_rect
helpviewer_keywords:
- COleControlSite [MFC], COleControlSite
- COleControlSite [MFC], BindDefaultProperty
- COleControlSite [MFC], BindProperty
- COleControlSite [MFC], CreateControl
- COleControlSite [MFC], DestroyControl
- COleControlSite [MFC], DoVerb
- COleControlSite [MFC], EnableDSC
- COleControlSite [MFC], EnableWindow
- COleControlSite [MFC], FreezeEvents
- COleControlSite [MFC], GetDefBtnCode
- COleControlSite [MFC], GetDlgCtrlID
- COleControlSite [MFC], GetEventIID
- COleControlSite [MFC], GetExStyle
- COleControlSite [MFC], GetProperty
- COleControlSite [MFC], GetStyle
- COleControlSite [MFC], GetWindowText
- COleControlSite [MFC], InvokeHelper
- COleControlSite [MFC], InvokeHelperV
- COleControlSite [MFC], IsDefaultButton
- COleControlSite [MFC], IsWindowEnabled
- COleControlSite [MFC], ModifyStyle
- COleControlSite [MFC], ModifyStyleEx
- COleControlSite [MFC], MoveWindow
- COleControlSite [MFC], QuickActivate
- COleControlSite [MFC], SafeSetProperty
- COleControlSite [MFC], SetDefaultButton
- COleControlSite [MFC], SetDlgCtrlID
- COleControlSite [MFC], SetFocus
- COleControlSite [MFC], SetProperty
- COleControlSite [MFC], SetPropertyV
- COleControlSite [MFC], SetWindowPos
- COleControlSite [MFC], SetWindowText
- COleControlSite [MFC], ShowWindow
- COleControlSite [MFC], GetControlInfo
- COleControlSite [MFC], m_bIsWindowless
- COleControlSite [MFC], m_ctlInfo
- COleControlSite [MFC], m_dwEventSink
- COleControlSite [MFC], m_dwMiscStatus
- COleControlSite [MFC], m_dwPropNotifySink
- COleControlSite [MFC], m_dwStyle
- COleControlSite [MFC], m_hWnd
- COleControlSite [MFC], m_iidEvents
- COleControlSite [MFC], m_nID
- COleControlSite [MFC], m_pActiveObject
- COleControlSite [MFC], m_pCtrlCont
- COleControlSite [MFC], m_pInPlaceObject
- COleControlSite [MFC], m_pObject
- COleControlSite [MFC], m_pWindowlessObject
- COleControlSite [MFC], m_pWndCtrl
- COleControlSite [MFC], m_rect
ms.assetid: 43970644-5eab-434a-8ba6-56d144ff1e3f
ms.openlocfilehash: 6cf12d017db1a1558b0dd915d9f3ba85894bee19
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366152"
---
# <a name="colecontrolsite-class"></a>クラス

クライアント側のカスタム コントロール インターフェイスをサポートします。

## <a name="syntax"></a>構文

```
class COleControlSite : public CCmdTarget
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[コントロールサイト::コントロールサイト](#colecontrolsite)|`COleControlSite` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[プロパティを指定します。](#binddefaultproperty)|ホストされたコントロールの既定のプロパティをデータ ソースにバインドします。|
|[コントロールサイト::バインドプロパティ](#bindproperty)|ホストされたコントロールのプロパティをデータ ソースにバインドします。|
|[コントロールサイト::コントロールの作成](#createcontrol)|ホストされた ActiveX コントロールを作成します。|
|[コントロールサイト::Dエストロイコントロール](#destroycontrol)|ホストされたコントロールを破棄します。|
|[コントロールサイト::Do動詞](#doverb)|ホストされたコントロールの特定の動詞を実行します。|
|[コントロールサイト::有効化DSC](#enabledsc)|コントロール サイトのデータ ソーシングを有効にします。|
|[コントロールサイト::ウィンドウを有効にする](#enablewindow)|コントロール サイトを有効にします。|
|[コントロールサイト::フリーズイベント](#freezeevents)|コントロール サイトがイベントを受け付けるかどうかを指定します。|
|[コントロールサイト::GetDefBtn コード](#getdefbtncode)|ホストされたコントロールの既定のボタン コードを取得します。|
|[コントロールサイト::取得します。](#getdlgctrlid)|コントロールの識別子を取得します。|
|[コントロールサイト::イベントIID](#geteventiid)|ホストされたコントロールのイベント インターフェイスの ID を取得します。|
|[コントロールサイト::ゲットレックススタイル](#getexstyle)|コントロール サイトの拡張スタイルを取得します。|
|[コントロールサイト::プロパティを取得します。](#getproperty)|ホストされたコントロールの特定のプロパティを取得します。|
|[コントロールサイト::ゲットスタイル](#getstyle)|コントロール サイトのスタイルを取得します。|
|[コントロールサイト::テキストを取得します。](#getwindowtext)|ホストされたコントロールのテキストを取得します。|
|[コントロールサイト::呼び出しヘルパー](#invokehelper)|ホストされたコントロールの特定のメソッドを呼び出します。|
|[コントロールサイト::呼び出しヘルパーV](#invokehelperv)|引数の変数リストを使用して、ホストされたコントロールの特定のメソッドを呼び出します。|
|[コントロールサイト::既定のボタン](#isdefaultbutton)|コントロールがウィンドウの既定のボタンかどうかを判断します。|
|[コントロールサイト::IsWindow が有効です。](#iswindowenabled)|コントロール サイトの表示状態を確認します。|
|[コントロールサイト::スタイルを変更します。](#modifystyle)|コントロール サイトの現在の拡張スタイルを変更します。|
|[コントロールサイト::スタイルを変更します。](#modifystyleex)|コントロール サイトの現在のスタイルを変更します。|
|[コントロールサイト::ウィンドウの移動](#movewindow)|コントロール サイトの位置を変更します。|
|[コントロールサイト::クイックアクティベート](#quickactivate)|ホストされたコントロールをクイックアクティブにします。|
|[プロパティを指定します。](#safesetproperty)|例外をスローすることなく、コントロールのプロパティまたはメソッドを設定します。|
|[コントロールサイト::セットデフォルトボタン](#setdefaultbutton)|ウィンドウの既定のボタンを設定します。|
|[コントロールサイト::セットドアルグCtrlID](#setdlgctrlid)|コントロールの識別子を取得します。|
|[コントロールサイト::セットフォーカス](#setfocus)|フォーカスをコントロール サイトに設定します。|
|[コントロールサイト::プロパティを設定します。](#setproperty)|ホストされたコントロールの特定のプロパティを設定します。|
|[コントロールサイト::セットプロパティV](#setpropertyv)|引数の変数リストを使用して、ホストされたコントロールの特定のプロパティを設定します。|
|[コントロールサイト::セットウィンドウポス](#setwindowpos)|コントロール サイトの位置を設定します。|
|[コントロールサイト::テキストを設定します。](#setwindowtext)|ホストされたコントロールのテキストを設定します。|
|[コントロールサイト::ショーウィンドウ](#showwindow)|コントロール サイトの表示と非表示を切り替えます。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[コントロールサイト::取得コントロール情報](#getcontrolinfo)|ホストされたコントロールのキーボード情報とニーモニックを取得します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[コントロールサイト::m_bIsWindowless](#m_biswindowless)|ホストされたコントロールがウィンドウなしのコントロールかどうかを判断します。|
|[コントロールサイト::m_ctlInfo](#m_ctlinfo)|コントロールのキーボード処理に関する情報が含まれます。|
|[コントロールサイト::m_dwEventSink](#m_dweventsink)|コントロールのコネクション ポイントのクッキー。|
|[コントロールサイト::m_dwMiscStatus](#m_dwmiscstatus)|ホストされたコントロールのその他の状態。|
|[コントロールサイト::m_dwPropNotifySink](#m_dwpropnotifysink)|コントロール`IPropertyNotifySink`のクッキー。|
|[コントロールサイト::m_dwStyle](#m_dwstyle)|ホストされたコントロールのスタイル。|
|[コントロールサイト::m_hWnd](#m_hwnd)|コントロール サイトのハンドル。|
|[コントロールサイト::m_iidEvents](#m_iidevents)|ホストされたコントロールのイベント インターフェイスの ID。|
|[コントロールサイト::m_nID](#m_nid)|ホストされたコントロールの ID。|
|[コントロールサイト::m_pActiveObject](#m_pactiveobject)|ホストされたコントロールの`IOleInPlaceActiveObject`オブジェクトへのポインター。|
|[コントロールサイト::m_pCtrlCont](#m_pctrlcont)|ホストされたコントロールのコンテナー。|
|[コントロールサイト::m_pInPlaceObject](#m_pinplaceobject)|ホストされたコントロールの`IOleInPlaceObject`オブジェクトへのポインター。|
|[コントロールサイト::m_pObject](#m_pobject)|コントロールの`IOleObjectInterface`インターフェイスへのポインター。|
|[コントロールサイト::m_pWindowlessObject](#m_pwindowlessobject)|コントロールの`IOleInPlaceObjectWindowless`インターフェイスへのポインター。|
|[コントロールサイト::m_pWndCtrl](#m_pwndctrl)|ホストされたコントロールのウィンドウ オブジェクトへのポインター。|
|[コントロールサイト::m_rect](#m_rect)|コントロール サイトのサイズ。|

## <a name="remarks"></a>解説

このサポートは、埋め込まれた ActiveX コントロールが、その表示サイトの場所と範囲、モニカー、ユーザー インターフェイス、アンビエント プロパティ、およびそのコンテナによって提供されるその他のリソースに関する情報を取得する主な手段です。 `COleControlSite`インターフェイスを[IOleClientSite](/windows/win32/api/oleidl/nn-oleidl-ioleclientsite)[IOleControlSite](/windows/win32/api/ocidl/nn-ocidl-iolecontrolsite)[IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink)[IOleInPlaceSite](/windows/win32/api/oleidl/nn-oleidl-ioleinplacesite)`IBoundObjectSite`[IRowSetNotify](../../data/oledb/irowsetnotifyimpl-class.md)完全に実装します。 `INotifyDBEvents` さらに、IDispatch インターフェイス (アンビエント プロパティとイベント シンクのサポートを提供する) も実装されています。

を使用して`COleControlSite`ActiveX コントロール サイトを作成するには`COleControlSite`、 からクラスを派生させます。 コンテナ`CWnd`の派生クラス (ダイアログ ボックスなど) では、関数をオーバーライドします`CWnd::CreateControlSite`。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleControlSite`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxocc.h

## <a name="colecontrolsitebinddefaultproperty"></a><a name="binddefaultproperty"></a>プロパティを指定します。

呼び出し元オブジェクトの既定の単純バインド プロパティを、タイプ ライブラリでマークされているように、データ ソース コントロールの DataSource、UserName、Password、および SQL プロパティで定義されている基になるカーソルにバインドします。

```
virtual void BindDefaultProperty(
    DISPID dwDispID,
    VARTYPE vtProp,
    LPCTSTR szFieldName,
    CWnd* pDSCWnd);
```

### <a name="parameters"></a>パラメーター

*ドウドイスID*<br/>
データ ソース コントロールにバインドされるデータ バインド コントロールのプロパティの DISPID を指定します。

*vtプロップ*<br/>
バインドするプロパティの型 (VT_BSTR、VT_VARIANTなど) を指定します。

*フィールド名*<br/>
データ ソース コントロールによって提供されるカーソル内の、プロパティがバインドされる列の名前を指定します。

*pDSCWnd*<br/>
プロパティが`CWnd`バインドされるデータ ソース コントロールをホストする派生オブジェクトへのポインター。

### <a name="remarks"></a>解説

この`CWnd`関数を呼び出すオブジェクトは、データ バインド コントロールである必要があります。

## <a name="colecontrolsitebindproperty"></a><a name="bindproperty"></a>コントロールサイト::バインドプロパティ

データ ソース コントロールの DataSource、UserName、Password、および SQL プロパティで定義されている基になるカーソルに、タイプ ライブラリでマークされている、呼び出し元オブジェクトの単純なバインド プロパティをバインドします。

```
virtual void BindProperty(
    DISPID dwDispId,
    CWnd* pWndDSC);
```

### <a name="parameters"></a>パラメーター

*ドウドイスId*<br/>
データ ソース コントロールにバインドされるデータ バインド コントロールのプロパティの DISPID を指定します。

*をクリックします。*<br/>
プロパティが`CWnd`バインドされるデータ ソース コントロールをホストする派生オブジェクトへのポインター。

### <a name="remarks"></a>解説

この`CWnd`関数を呼び出すオブジェクトは、データ バインド コントロールである必要があります。

## <a name="colecontrolsitecolecontrolsite"></a><a name="colecontrolsite"></a>コントロールサイト::コントロールサイト

新しい `COleControlSite` オブジェクトを構築します。

```
explicit COleControlSite(COleControlContainer* pCtrlCont);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
コントロールのコンテナー (AtiveX コントロールをホストするウィンドウを表す) へのポインター。

### <a name="remarks"></a>解説

この関数は[、COccManager::CreateContainer](../../mfc/reference/coccmanager-class.md#createcontainer)関数によって呼び出されます。 コンテナーの作成のカスタマイズの詳細については[、「COccManager::CreateSite](../../mfc/reference/coccmanager-class.md#createsite)」を参照してください。

## <a name="colecontrolsitecreatecontrol"></a><a name="createcontrol"></a>コントロールサイト::コントロールの作成

オブジェクトによってホストされる ActiveX コントロールを`COleControlSite`作成します。

```
virtual HRESULT CreateControl(
    CWnd* pWndCtrl,
    REFCLSID clsid,
    LPCTSTR lpszWindowName,
    DWORD dwStyle,
    const RECT& rect,
    UINT nID,
    CFile* pPersist = NULL,
    BOOL bStorage = FALSE,
    BSTR bstrLicKey = NULL);

virtual HRESULT CreateControl(
    CWnd* pWndCtrl,
    REFCLSID clsid,
    LPCTSTR lpszWindowName,
    DWORD dwStyle,
    const POINT* ppt,
    const SIZE* psize,
    UINT nID,
    CFile* pPersist = NULL,
    BOOL bStorage = FALSE,
    BSTR bstrLicKey = NULL);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
コントロールを表すウィンドウ オブジェクトへのポインター。

*Clsid*<br/>
コントロールの一意のクラス ID。

*名前をクリックします。*<br/>
コントロールに表示されるテキストへのポインター。 winodw の Caption プロパティまたは Text プロパティ (存在する場合) の値を設定します。

*Dwstyle*<br/>
ウィンドウスタイル。 使用可能なスタイルは **、「解説」** セクションにリストされています。

*Rect*<br/>
コントロールのサイズと位置を指定します。 `CRect`オブジェクトまたは`RECT`構造体のいずれかです。

*nID*<br/>
コントロールの子ウィンドウ ID を指定します。

*pPersist*<br/>
コントロールの永続状態`CFile`を含むポインター。 既定値は NULL で、コントロールが永続ストレージから状態を復元せずに初期化されることを示します。 NULL でない場合は、ストリームまたはストレージのいずれかの形式`CFile`で、コントロールの永続的なデータを含む派生オブジェクトへのポインターにする必要があります。 このデータは、クライアントの以前のアクティブ化で保存されている可能性があります。 他`CFile`のデータを含めることができますが、読み取り/書き込みポインタは、 への呼び出し時に永続`CreateControl`データの最初のバイトに設定されている必要があります。

*ストレージ*<br/>
*pPersist*のデータをデータとして`IStorage`解釈するかどうかを示`IStream`します。 *pPersist*のデータがストレージの場合は *、bStorage*は TRUE にする必要があります。 *pPersist*のデータがストリームの場合は *、bStorage*を FALSE にする必要があります。 既定値は FALSE です。

*をクリックします。*<br/>
オプションのライセンス キー データ。 このデータは、ランタイム ライセンス キーを必要とするコントロールを作成する場合にのみ必要です。 コントロールがライセンスをサポートしている場合は、コントロールを作成するためにライセンス キーを指定する必要があります。 既定値は NULL です。

*Ppt*<br/>
コントロールの左上隅を`POINT`含む構造体へのポインター。 コントロールのサイズは、 *psize*の値によって決まります。 *ppt*値と*psize*値は、コントロールのサイズと位置を指定するオプションの方法です。

*Psize*<br/>
コントロールのサイズを`SIZE`格納する構造体へのポインター。 左上隅は *、 ppt*の値によって決まります。 *ppt*値と*psize*値は、コントロールのサイズと位置を指定するオプションの方法です。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

でサポート`CreateControl`されている Windows *dwStyle*フラグのサブセットのみ。

- WS_VISIBLE 最初に表示されるウィンドウを作成します。 通常のウィンドウのように、コントロールをすぐに表示する場合は必須です。

- WS_DISABLED最初に無効になっているウィンドウを作成します。 無効なウィンドウはユーザーからの入力を受け取ることができません。 コントロールに Enabled プロパティがある場合に設定できます。

- WS_BORDER 細い線の境界線を持つウィンドウを作成します。 コントロールに BorderStyle プロパティがある場合に設定できます。

- WS_GROUP コントロールのグループの最初のコントロールを指定します。 ユーザーは、方向キーを使用して、グループ内のコントロールから次のコントロールにキーボード フォーカスを変更できます。 最初のコントロールの後にWS_GROUPスタイルで定義されたすべてのコントロールが同じグループに属します。 WS_GROUPスタイルの次のコントロールは、グループを終了し、次のグループを開始します。

- WS_TABSTOPユーザーが Tab キーを押したときにキーボード フォーカスを受け取ることができるコントロールを指定します。 Tab キーを押すと、キーボード フォーカスがWS_TABSTOPスタイルの次のコントロールに変更されます。

2 番目のオーバーロードを使用して、既定のサイズのコントロールを作成します。

## <a name="colecontrolsitedestroycontrol"></a><a name="destroycontrol"></a>コントロールサイト::Dエストロイコントロール

`COleControlSite` オブジェクトを破棄します。

```
virtual BOOL DestroyControl();
```

### <a name="return-value"></a>戻り値

成功した場合は 0 以外の値を返します。

### <a name="remarks"></a>解説

完了すると、オブジェクトはメモリから解放され、オブジェクトへのポインターは無効になります。

## <a name="colecontrolsitedoverb"></a><a name="doverb"></a>コントロールサイト::Do動詞

指定した動詞を実行します。

```
virtual HRESULT DoVerb(
    LONG nVerb,
    LPMSG lpMsg = NULL);
```

### <a name="parameters"></a>パラメーター

*nVerb*<br/>
実行する動詞を指定します。 次のいずれかを含めることができます。

|[値]|意味|Symbol|
|-----------|-------------|------------|
|0|主動詞|OLEIVERB_PRIMARY|
|-1|二次動詞|(なし)|
|1|編集するオブジェクトを表示します。|OLEIVERB_SHOW|
|-2|別のウィンドウで項目を編集します。|OLEIVERB_OPEN|
|-3|オブジェクトを非表示にします。|OLEIVERB_HIDE|
|-4|コントロールをインプレースでアクティブにします。|OLEIVERB_UIACTIVATE|
|-5|ユーザー インターフェイス要素を追加せずに、コントロールをインプレースでアクティブにします。|OLEIVERB_INPLACEACTIVATE|
|-7|コントロールのプロパティを表示します。|OLEIVERB_PROPERTIES|

*をクリックします。*<br/>
項目がアクティブ化される原因となったメッセージへのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

この関数は、コントロールの`IOleObject`インターフェイスを通じて直接呼び出し、指定された動詞を実行します。 この関数呼び出しの結果として例外がスローされた場合、HRESULT エラー コードが返されます。

詳細については、次を[:D参照してください。](/windows/win32/api/oleidl/nf-oleidl-ioleobject-doverb)

## <a name="colecontrolsiteenabledsc"></a><a name="enabledsc"></a>コントロールサイト::有効化DSC

コントロール サイトのデータ ソーシングを有効にします。

```
virtual void EnableDSC();
```

### <a name="remarks"></a>解説

コントロール サイトのデータ ソースを有効にし、初期化するために、フレームワークによって呼び出されます。 カスタマイズされた動作を提供するには、この関数をオーバーライドします。

## <a name="colecontrolsiteenablewindow"></a><a name="enablewindow"></a>コントロールサイト::ウィンドウを有効にする

コントロール サイトへのマウス入力とキーボード入力を有効または無効にします。

```
virtual BOOL EnableWindow(BOOL bEnable);
```

### <a name="parameters"></a>パラメーター

*b 有効にする*<br/>
ウィンドウ入力を有効にする場合は TRUE を有効または無効にするかどうかを指定します。

### <a name="return-value"></a>戻り値

ウィンドウが以前に無効になっている場合は 0 以外の値を返します。

## <a name="colecontrolsitefreezeevents"></a><a name="freezeevents"></a>コントロールサイト::フリーズイベント

コントロール サイトがコントロールから発生したイベントを処理するか無視するかを指定します。

```
void FreezeEvents(BOOL bFreeze);
```

### <a name="parameters"></a>パラメーター

*bフリーズ*<br/>
コントロール サイトにおけるイベントの受け取りを中止するかどうかを指定します。 コントロールがイベントを受け付けない場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

*bFreeze*が TRUE の場合、コントロール サイトはコントロールに対して、イベントの発生を停止するように要求します。 *bFreeze*が FALSE の場合、コントロール サイトはコントロールにイベントの発生を継続するように要求します。

> [!NOTE]
> コントロールは、コントロール サイトから要求された場合にイベントの発生を停止する必要はありません。 このイベントは引き続き起動できますが、後続のすべてのイベントはコントロール サイトによって無視されます。

## <a name="colecontrolsitegetcontrolinfo"></a><a name="getcontrolinfo"></a>コントロールサイト::取得コントロール情報

コントロールのキーボードニーモニックおよびキーボードの動作に関する情報を取得します。

```
void GetControlInfo();
```

### <a name="remarks"></a>解説

情報は[、COleControlSite::m_ctlInfo](#m_ctlinfo)に格納されます。

## <a name="colecontrolsitegetdefbtncode"></a><a name="getdefbtncode"></a>コントロールサイト::GetDefBtn コード

コントロールが既定のプッシュ ボタンかどうかを判断します。

```
DWORD GetDefBtnCode();
```

### <a name="return-value"></a>戻り値

次の値のいずれかです。

- DLGC_DEFPUSHBUTTONコントロールは、ダイアログボックスのデフォルトボタンです。

- DLGC_UNDEFPUSHBUTTON コントロールは、ダイアログボックスの既定のボタンではありません。

- **0**コントロールはボタンではありません。

## <a name="colecontrolsitegetdlgctrlid"></a><a name="getdlgctrlid"></a>コントロールサイト::取得します。

コントロールの識別子を取得します。

```
virtual int GetDlgCtrlID() const;
```

### <a name="return-value"></a>戻り値

コントロールのダイアログ項目識別子。

## <a name="colecontrolsitegeteventiid"></a><a name="geteventiid"></a>コントロールサイト::イベントIID

コントロールの既定のイベント インターフェイスへのポインターを取得します。

```
BOOL GetEventIID(IID* piid);
```

### <a name="parameters"></a>パラメーター

*ピッド*<br/>
インターフェイス ID へのポインター。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外の値を返します。 正常に実行された*場合、piid*にはコントロールの既定のイベント インターフェイスのインターフェイス ID が格納されます。

## <a name="colecontrolsitegetexstyle"></a><a name="getexstyle"></a>コントロールサイト::ゲットレックススタイル

ウィンドウの拡張スタイルを取得します。

```
virtual DWORD GetExStyle() const;
```

### <a name="return-value"></a>戻り値

コントロール ウィンドウの拡張スタイル。

### <a name="remarks"></a>解説

通常のスタイルを取得するには[、COleControlSite::GetStyle](#getstyle)を呼び出します。

## <a name="colecontrolsitegetproperty"></a><a name="getproperty"></a>コントロールサイト::プロパティを取得します。

*dwDispID*で指定されたコントロール プロパティを取得します。

```
virtual void GetProperty(
    DISPID dwDispID,
    VARTYPE vtProp,
    void* pvProp) const;
```

### <a name="parameters"></a>パラメーター

*ドウドイスID*<br/>
取得するコントロールの既定`IDispatch`のインターフェイスで見つかったプロパティのディスパッチ ID を識別します。

*vtプロップ*<br/>
取得するプロパティの型を指定します。 使用できる値については、 [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)の「解説」をご覧ください。

*pv プロップ*<br/>
プロパティ値を受け取る変数のアドレス。 vtProp で指定された型*vtProp*と一致する必要があります。

### <a name="remarks"></a>解説

値は*pvProp*を介して返されます。

## <a name="colecontrolsitegetstyle"></a><a name="getstyle"></a>コントロールサイト::ゲットスタイル

コントロール サイトのスタイルを取得します。

```
virtual DWORD GetStyle() const;
```

### <a name="return-value"></a>戻り値

ウィンドウのスタイル。

### <a name="remarks"></a>解説

使用できる値の一覧については、「 [Windows のスタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)」を参照してください。 コントロール サイトの拡張スタイルを取得するには[、COleControlSite::GetExStyle](#getexstyle)を呼び出します。

## <a name="colecontrolsitegetwindowtext"></a><a name="getwindowtext"></a>コントロールサイト::テキストを取得します。

コントロールの現在のテキストを取得します。

```
virtual void GetWindowText(CString& str) const;
```

### <a name="parameters"></a>パラメーター

*Str*<br/>
コントロールの現在の`CString`テキストを含むオブジェクトへの参照。

### <a name="remarks"></a>解説

コントロールが [キャプション] ストック プロパティをサポートしている場合、この値が返されます。 Caption ストック プロパティがサポートされていない場合、Text プロパティの値が返されます。

## <a name="colecontrolsiteinvokehelper"></a><a name="invokehelper"></a>コントロールサイト::呼び出しヘルパー

*で*指定されたコンテキストで*dwDispID*で指定されたメソッドまたはプロパティを呼び出します。

```
virtual void AFX_CDECL InvokeHelper(
    DISPID dwDispID,
    WORD wFlags,
    VARTYPE vtRet,
    void* pvRet,
    const BYTE* pbParamInfo, ...);
```

### <a name="parameters"></a>パラメーター

*ドウドイスID*<br/>
呼び出されるコントロールのインターフェイスで見つかったプロパティまたはメソッドの`IDispatch`ディスパッチ ID を識別します。

*wフラグ*<br/>
IDispatch::Invoke 呼び出しのコンテキストを記述するフラグ。 可能な*wFlags*値`IDispatch::Invoke`については、Windows SDK を参照してください。

*vtRet*<br/>
戻り値の型を指定します。 使用できる値については、 [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)の「解説」をご覧ください。

*pvRet*<br/>
プロパティ値または戻り値を受け取る変数のアドレス。 *vtRet*で指定された型と一致する必要があります。

*パラムインフォ*<br/>
*pbParamInfo*に続くパラメーターの型を指定する、null で終わるバイトの文字列へのポインター。 使用できる値については、 [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)の「解説」をご覧ください。

*...*<br/>
パラメーターの変数リスト、 *pbParamInfo*で指定された型のリスト。

### <a name="remarks"></a>解説

*pbParamInfo*パラメーターは、メソッドまたはプロパティに渡されるパラメーターの型を指定します。 引数の変数一覧は、構文宣言では、... で表されます。

この関数は、パラメーターを VARIANTARG 値に変換し、`IDispatch::Invoke`コントロールのメソッドを呼び出します。 `IDispatch::Invoke` の呼び出しに失敗すると、この関数は、例外をスローします。 によって`IDispatch::Invoke`返される状態コードが`DISP_E_EXCEPTION`の場合、この関数は`COleDispatchException`オブジェクトをスローします`COleException`。

## <a name="colecontrolsiteinvokehelperv"></a><a name="invokehelperv"></a>コントロールサイト::呼び出しヘルパーV

*で*指定されたコンテキストで*dwDispID*で指定されたメソッドまたはプロパティを呼び出します。

```
virtual void InvokeHelperV(
    DISPID dwDispID,
    WORD wFlags,
    VARTYPE vtRet,
    void* pvRet,
    const BYTE* pbParamInfo,
    va_list argList);
```

### <a name="parameters"></a>パラメーター

*ドウドイスID*<br/>
呼び出されるコントロールのインターフェイスで見つかったプロパティまたはメソッドの`IDispatch`ディスパッチ ID を識別します。

*wフラグ*<br/>
IDispatch::Invoke 呼び出しのコンテキストを記述するフラグ。

*vtRet*<br/>
戻り値の型を指定します。 使用できる値については、 [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)の「解説」をご覧ください。

*pvRet*<br/>
プロパティ値または戻り値を受け取る変数のアドレス。 *vtRet*で指定された型と一致する必要があります。

*パラムインフォ*<br/>
*pbParamInfo*に続くパラメーターの型を指定する、null で終わるバイトの文字列へのポインター。 使用できる値については、 [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)の「解説」をご覧ください。

*Arglist*<br/>
可変引数リストへのポインター。

### <a name="remarks"></a>解説

*pbParamInfo*パラメーターは、メソッドまたはプロパティに渡されるパラメーターの型を指定します。 呼び出されるメソッドまたはプロパティの追加パラメーターは *、va_list*パラメーターを使用して渡すことができます。

通常、この関数は によって`COleControlSite::InvokeHelper`呼び出されます。

## <a name="colecontrolsiteisdefaultbutton"></a><a name="isdefaultbutton"></a>コントロールサイト::既定のボタン

コントロールが既定のボタンかどうかを判断します。

```
BOOL IsDefaultButton();
```

### <a name="return-value"></a>戻り値

コントロールがウィンドウの既定のボタンの場合は 0 以外の値を返します。

## <a name="colecontrolsiteiswindowenabled"></a><a name="iswindowenabled"></a>コントロールサイト::IsWindow が有効です。

コントロール サイトが有効かどうかを判断します。

```
virtual BOOL IsWindowEnabled() const;
```

### <a name="return-value"></a>戻り値

コントロールが有効な場合は 0 以外の値を返します。

### <a name="remarks"></a>解説

値は、コントロールの "有効" ストック プロパティから取得されます。

## <a name="colecontrolsitem_biswindowless"></a><a name="m_biswindowless"></a>コントロールサイト::m_bIsWindowless

オブジェクトがウィンドウなしのコントロールかどうかを判断します。

```
BOOL m_bIsWindowless;
```

### <a name="remarks"></a>解説

コントロールにウィンドウがない場合は 0 以外の値を返します。

## <a name="colecontrolsitem_ctlinfo"></a><a name="m_ctlinfo"></a>コントロールサイト::m_ctlInfo

キーボード入力がコントロールによって処理される方法に関する情報。

```
CONTROLINFO m_ctlInfo;
```

### <a name="remarks"></a>解説

この情報は[、CONTROLINFO](/windows/win32/api/ocidl/ns-ocidl-controlinfo)構造体に格納されます。

## <a name="colecontrolsitem_dweventsink"></a><a name="m_dweventsink"></a>コントロールサイト::m_dwEventSink

コントロールのイベント シンクからの接続ポイントの Cookie を格納します。

```
DWORD m_dwEventSink;
```

## <a name="colecontrolsitem_dwmiscstatus"></a><a name="m_dwmiscstatus"></a>コントロールサイト::m_dwMiscStatus

コントロールに関するその他の情報が含まれています。

```
DWORD m_dwMiscStatus;
```

### <a name="remarks"></a>解説

詳細については、Windows SDK[の「OLEMISC」](/windows/win32/api/oleidl/ne-oleidl-olemisc)を参照してください。

## <a name="colecontrolsitem_dwpropnotifysink"></a><a name="m_dwpropnotifysink"></a>コントロールサイト::m_dwPropNotifySink

[クッキー](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink)が含まれています。

```
DWORD m_dwPropNotifySink;
```

## <a name="colecontrolsitem_dwstyle"></a><a name="m_dwstyle"></a>コントロールサイト::m_dwStyle

コントロールのウィンドウ スタイルを格納します。

```
DWORD m_dwStyle;
```

## <a name="colecontrolsitem_hwnd"></a><a name="m_hwnd"></a>コントロールサイト::m_hWnd

コントロールの HWND を格納します。

```
HWND m_hWnd;
```

## <a name="colecontrolsitem_iidevents"></a><a name="m_iidevents"></a>コントロールサイト::m_iidEvents

コントロールの既定のイベント シンク インターフェイスのインターフェイス ID が含まれています。

```
IID m_iidEvents;
```

## <a name="colecontrolsitem_nid"></a><a name="m_nid"></a>コントロールサイト::m_nID

コントロールのダイアログ 項目 ID が含まれます。

```
UINT m_nID;
```

## <a name="colecontrolsitem_pactiveobject"></a><a name="m_pactiveobject"></a>コントロールサイト::m_pActiveObject

コントロールの[インターフェイス](/windows/win32/api/oleidl/nn-oleidl-ioleinplaceactiveobject)が含まれています。

```
LPOLEINPLACEACTIVEOBJECT m_pActiveObject;
```

## <a name="colecontrolsitem_pctrlcont"></a><a name="m_pctrlcont"></a>コントロールサイト::m_pCtrlCont

コントロールのコンテナー (フォームを表す) を格納します。

```
COleControlContainer* m_pCtrlCont;
```

## <a name="colecontrolsitem_pinplaceobject"></a><a name="m_pinplaceobject"></a>コントロールサイト::m_pInPlaceObject

コントロールの`IOleInPlaceObject`[インターフェイス](/windows/win32/api/oleidl/nn-oleidl-ioleinplaceobject)が含まれています。

```
LPOLEINPLACEOBJECT m_pInPlaceObject;
```

## <a name="colecontrolsitem_pobject"></a><a name="m_pobject"></a>コントロールサイト::m_pObject

コントロールの`IOleObjectInterface`インターフェイスを格納します。

```
LPOLEOBJECT m_pObject;
```

## <a name="colecontrolsitem_pwindowlessobject"></a><a name="m_pwindowlessobject"></a>コントロールサイト::m_pWindowlessObject

コントロールの`IOleInPlaceObjectWindowless`[ウィンドウなし](/windows/win32/api/ocidl/nn-ocidl-ioleinplaceobjectwindowless)インターフェイスが含まれています。

```
IOleInPlaceObjectWindowless* m_pWindowlessObject;
```

## <a name="colecontrolsitem_pwndctrl"></a><a name="m_pwndctrl"></a>コントロールサイト::m_pWndCtrl

コントロール自体を表す`CWnd`オブジェクトへのポインターを格納します。

```
CWnd* m_pWndCtrl;
```

## <a name="colecontrolsitem_rect"></a><a name="m_rect"></a>コントロールサイト::m_rect

コンテナーのウィンドウを基準にしたコントロールの境界を格納します。

```
CRect m_rect;
```

## <a name="colecontrolsitemodifystyle"></a><a name="modifystyle"></a>コントロールサイト::スタイルを変更します。

コントロールのスタイルを変更します。

```
virtual BOOL ModifyStyle(
    DWORD dwRemove,
    DWORD dwAdd,
    UINT nFlags);
```

### <a name="parameters"></a>パラメーター

*dw削除*<br/>
現在のウィンドウ スタイルから削除するスタイル。

*dwAdd*<br/>
現在のウィンドウ スタイルから追加するスタイル。

*Nflags*<br/>
ウィンドウの位置指定フラグ。 使用可能な値の一覧については、Windows SDK の[SetWindowPos](/windows/win32/api/winuser/nf-winuser-setwindowpos)関数を参照してください。

### <a name="return-value"></a>戻り値

スタイルが変更された場合は 0 以外の値を返します。

### <a name="remarks"></a>解説

コントロールのストックの有効なプロパティは、WS_DISABLEDの設定に一致するように変更されます。 コントロールのストックボーダースタイルプロパティは、WS_BORDERに対して要求された設定に一致するように変更されます。 他のすべてのスタイルは、コントロールのウィンドウ ハンドルに直接適用されます (存在する場合)。

コントロールのウィンドウ スタイルを変更します。 追加または削除するスタイルは、ビットごとの OR ( &#124; ) 演算子を使用して組み合わせることができます。 使用可能なウィンドウ スタイルについては、Windows SDK の[CreateWindow](/windows/win32/api/winuser/nf-winuser-createwindoww)関数を参照してください。

*nFlags が*0`ModifyStyle`以外の場合は、Win32 関数`SetWindowPos`を呼び出し *、nFlags*と次の 4 つのフラグを組み合わせてウィンドウを再描画します。

- SWP_NOSIZE 現在のサイズを保持します。

- SWP_NOMOVE 現在の位置を保持します。

- SWP_NOZORDER 現在の Z オーダーを保持します。

- SWP_NOACTIVATE ウィンドウをアクティブにしません。

ウィンドウの拡張スタイルを変更するには[、ModifyStyleEx](#modifystyleex)を呼び出します。

## <a name="colecontrolsitemodifystyleex"></a><a name="modifystyleex"></a>コントロールサイト::スタイルを変更します。

コントロールの拡張スタイルを変更します。

```
virtual BOOL ModifyStyleEx(
    DWORD dwRemove,
    DWORD dwAdd,
    UINT nFlags);
```

### <a name="parameters"></a>パラメーター

*dw削除*<br/>
現在のウィンドウ スタイルから削除する拡張スタイル。

*dwAdd*<br/>
現在のウィンドウ スタイルから追加する拡張スタイル。

*Nflags*<br/>
ウィンドウの位置指定フラグ。 使用可能な値の一覧については、Windows SDK の[SetWindowPos](/windows/win32/api/winuser/nf-winuser-setwindowpos)関数を参照してください。

### <a name="return-value"></a>戻り値

スタイルが変更された場合は 0 以外の値を返します。

### <a name="remarks"></a>解説

コントロールのストック外観プロパティは、WS_EX_CLIENTEDGEの設定に合わせて変更されます。 他のすべての拡張ウィンドウ スタイルは、コントロールのウィンドウ ハンドルに直接適用されます (存在する場合)。

コントロール サイト オブジェクトのウィンドウ拡張スタイルを変更します。 追加または削除するスタイルは、ビットごとの OR ( &#124; ) 演算子を使用して組み合わせることができます。 使用可能なウィンドウ スタイルの詳細については、Windows SDK の[CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw)関数を参照してください。

*nFlags が*0`ModifyStyleEx`以外の場合は、Win32 関数`SetWindowPos`を呼び出し *、nFlags*と次の 4 つのフラグを組み合わせてウィンドウを再描画します。

- SWP_NOSIZE 現在のサイズを保持します。

- SWP_NOMOVE 現在の位置を保持します。

- SWP_NOZORDER 現在の Z オーダーを保持します。

- SWP_NOACTIVATE ウィンドウをアクティブにしません。

ウィンドウの拡張スタイルを変更するには[、ModifyStyle](#modifystyle)を呼び出します。

## <a name="colecontrolsitemovewindow"></a><a name="movewindow"></a>コントロールサイト::ウィンドウの移動

コントロールの位置を変更します。

```
virtual void MoveWindow(
    int x,
    int y,
    int nWidth,
    int nHeight);
```

### <a name="parameters"></a>パラメーター

*X*<br/>
ウィンドウの左側の新しい位置。

*Y*<br/>
ウィンドウの上部の新しい位置。

*n幅*<br/>
ウィンドウの新しい幅

*nHeight*<br/>
ウィンドウの新しい高さ。

## <a name="colecontrolsitequickactivate"></a><a name="quickactivate"></a>コントロールサイト::クイックアクティベート

クイックは、含まれているコントロールをアクティブにします。

```
virtual BOOL QuickActivate();
```

### <a name="return-value"></a>戻り値

コントロール サイトがアクティブ化された場合は 0 以外の値を返します。

### <a name="remarks"></a>解説

この関数は、ユーザーがコントロールの作成プロセスをオーバーライドする場合にのみ呼び出す必要があります。

メソッド`IPersist*::Load`と`IPersist*::InitNew`メソッドは、クイック アクティベーションが発生した後に呼び出す必要があります。 コントロールは、クイック アクティブ化中にコンテナーのシンクへの接続を確立する必要があります。 ただし、これらの接続は、呼び`IPersist*::Load`出`IPersist*::InitNew`されるまでは存続しません。

## <a name="colecontrolsitesafesetproperty"></a><a name="safesetproperty"></a>プロパティを指定します。

*dwDispID*で指定されたコントロール プロパティを設定します。

```
virtual BOOL AFX_CDECL SafeSetProperty(
    DISPID dwDispID,
    VARTYPE vtProp, ...);
```

### <a name="parameters"></a>パラメーター

*ドウドイスID*<br/>
コントロールのインターフェイスで見つかったプロパティまたはメソッドの`IDispatch`ディスパッチ ID を識別します。

*vtプロップ*<br/>
設定するプロパティの種類を指定します。 使用できる値については、 [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)の「解説」をご覧ください。

*...*<br/>
*vtProp*で指定された型の単一のパラメーター。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

> [!NOTE]
> と`SetProperty``SetPropertyV`は異なり、 (存在しないプロパティを設定しようとするなど) エラーが発生した場合、例外はスローされません。

## <a name="colecontrolsitesetdefaultbutton"></a><a name="setdefaultbutton"></a>コントロールサイト::セットデフォルトボタン

コントロールを既定のボタンとして設定します。

```
void SetDefaultButton(BOOL bDefault);
```

### <a name="parameters"></a>パラメーター

*bデフォルト*<br/>
コントロールが既定のボタンになる場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

> [!NOTE]
> コントロールには、OLEMISC_ACTSLIKEBUTTON状態ビットが設定されている必要があります。

## <a name="colecontrolsitesetdlgctrlid"></a><a name="setdlgctrlid"></a>コントロールサイト::セットドアルグCtrlID

コントロールのダイアログ項目識別子の値を変更します。

```
virtual int SetDlgCtrlID(int nID);
```

### <a name="parameters"></a>パラメーター

*nID*<br/>
新しい識別子の値。

### <a name="return-value"></a>戻り値

成功した場合は、ウィンドウの前のダイアログ項目識別子。それ以外の場合は 0。

### <a name="remarks"></a>解説

## <a name="colecontrolsitesetfocus"></a><a name="setfocus"></a>コントロールサイト::セットフォーカス

フォーカスをコントロールに設定します。

```
virtual CWnd* SetFocus();
virtual CWnd* SetFocus(LPMSG lpmsg);
```

### <a name="parameters"></a>パラメーター

*lpmsg*<br/>
[MSG 構造体](/windows/win32/api/winuser/ns-winuser-msg)へのポインタ。 この構造体には、現在のコントロール`SetFocus`サイトに含まれるコントロールの要求をトリガーする Windows メッセージが含まれています。

### <a name="return-value"></a>戻り値

以前フォーカスを持っていたウィンドウへのポインター。

## <a name="colecontrolsitesetproperty"></a><a name="setproperty"></a>コントロールサイト::プロパティを設定します。

*dwDispID*で指定されたコントロール プロパティを設定します。

```
virtual void AFX_CDECL SetProperty(
    DISPID dwDispID,
    VARTYPE vtProp, ...);
```

### <a name="parameters"></a>パラメーター

*ドウドイスID*<br/>
コントロールのインターフェイスで見つかったプロパティまたはメソッドの`IDispatch`ディスパッチ ID を識別します。

*vtプロップ*<br/>
設定するプロパティの種類を指定します。 使用できる値については、 [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)の「解説」をご覧ください。

*...*<br/>
*vtProp*で指定された型の単一のパラメーター。

### <a name="remarks"></a>解説

エラー`SetProperty`が発生すると、例外がスローされます。

例外の種類は、プロパティまたはメソッドを設定しようとする試行の戻り値によって決まります。 戻り値が`DISP_E_EXCEPTION`の場合`COleDispatchExcpetion`は a がスローされます。それ以外`COleException`の場合は.

## <a name="colecontrolsitesetpropertyv"></a><a name="setpropertyv"></a>コントロールサイト::セットプロパティV

*dwDispID*で指定されたコントロール プロパティを設定します。

```
virtual void SetPropertyV(
    DISPID dwDispID,
    VARTYPE vtProp,
    va_list argList);
```

### <a name="parameters"></a>パラメーター

*ドウドイスID*<br/>
コントロールのインターフェイスで見つかったプロパティまたはメソッドの`IDispatch`ディスパッチ ID を識別します。

*vtプロップ*<br/>
設定するプロパティの種類を指定します。 使用できる値については、 [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)の「解説」をご覧ください。

*Arglist*<br/>
引数リストへのポインター。

### <a name="remarks"></a>解説

呼び出されるメソッドまたはプロパティの追加パラメーターは *、arg_list*パラメーターを使用して渡すことができます。 エラー`SetProperty`が発生すると、例外がスローされます。

例外の種類は、プロパティまたはメソッドを設定しようとする試行の戻り値によって決まります。 戻り値が`DISP_E_EXCEPTION`の場合`COleDispatchExcpetion`は a がスローされます。それ以外`COleException`の場合は.

## <a name="colecontrolsitesetwindowpos"></a><a name="setwindowpos"></a>コントロールサイト::セットウィンドウポス

コントロール サイトのサイズ、位置、および Z の順序を設定します。

```
virtual BOOL SetWindowPos(
    const CWnd* pWndInsertAfter,
    int x,
    int y,
    int cx,
    int cy,
    UINT nFlags);
```

### <a name="parameters"></a>パラメーター

*後に挿入します。*<br/>
ウィンドウへのポインター。

*X*<br/>
ウィンドウの左側の新しい位置。

*Y*<br/>
ウィンドウの上部の新しい位置。

*Cx*<br/>
ウィンドウの新しい幅

*Cy*<br/>
ウィンドウの新しい高さ。

*Nflags*<br/>
ウィンドウのサイズ変更と配置フラグを指定します。 可能な値については、Windows SDK の[SetWindowPos](/windows/win32/api/winuser/nf-winuser-setwindowpos)の解説セクションを参照してください。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外の値を返します。

## <a name="colecontrolsitesetwindowtext"></a><a name="setwindowtext"></a>コントロールサイト::テキストを設定します。

コントロール サイトのテキストを設定します。

```
virtual void SetWindowText(LPCTSTR lpszString);
```

### <a name="parameters"></a>パラメーター

*文字列*<br/>
新しいタイトルまたはコントロール テキストとして使用される null で終わる文字列へのポインター。

### <a name="remarks"></a>解説

この関数は、最初に Caption ストック プロパティの設定を試みます。 キャプションのストック プロパティがサポートされていない場合、Text プロパティが代わりに設定されます。

## <a name="colecontrolsiteshowwindow"></a><a name="showwindow"></a>コントロールサイト::ショーウィンドウ

ウィンドウの表示状態を設定します。

```
virtual BOOL ShowWindow(int nCmdShow);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
コントロール サイトの表示方法を指定します。 次のいずれかの値を指定する必要があります。

- SW_HIDE このウィンドウを非表示にして、アクティブ化を別のウィンドウに渡します。

- SW_MINIMIZE ウィンドウを最小化し、システムのリストの最上位ウィンドウをアクティブにします。

- SW_RESTORE ウィンドウをアクティブにして表示します。 ウィンドウが最小化または最大化されている場合、Windows は元のサイズと位置に戻します。

- SW_SHOW ウィンドウをアクティブにし、現在のサイズと位置に表示します。

- SW_SHOWMAXIMIZED ウィンドウをアクティブにして最大化されたウィンドウとして表示します。

- SW_SHOWMINIMIZED ウィンドウをアクティブにして、アイコンとして表示します。

- SW_SHOWMINNOACTIVE ウィンドウをアイコンで表示します。 現在アクティブなウィンドウはアクティブなままです。

- SW_SHOWNA ウィンドウを現在の状態で表示します。 現在アクティブなウィンドウはアクティブなままです。

- SW_SHOWNOACTIVATE ウィンドウを最新のサイズと位置で表示します。 現在アクティブなウィンドウはアクティブなままです。

- SW_SHOWNORMAL ウィンドウをアクティブにして表示します。 ウィンドウが最小化または最大化されている場合、Windows は元のサイズと位置に戻します。

### <a name="return-value"></a>戻り値

ウィンドウが以前に表示されていた場合は 0 以外の値を返します。ウィンドウが以前に非表示であった場合は 0。

## <a name="see-also"></a>関連項目

[CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/colecontrolcontainer-class.md)
