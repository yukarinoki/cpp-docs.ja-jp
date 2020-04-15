---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- COleControlContainer
- AFXOCC/COleControlContainer
- AFXOCC/COleControlContainer::COleControlContainer
- AFXOCC/COleControlContainer::AttachControlSite
- AFXOCC/COleControlContainer::BroadcastAmbientPropertyChange
- AFXOCC/COleControlContainer::CheckDlgButton
- AFXOCC/COleControlContainer::CheckRadioButton
- AFXOCC/COleControlContainer::CreateControl
- AFXOCC/COleControlContainer::CreateOleFont
- AFXOCC/COleControlContainer::FindItem
- AFXOCC/COleControlContainer::FreezeAllEvents
- AFXOCC/COleControlContainer::GetAmbientProp
- AFXOCC/COleControlContainer::GetDlgItem
- AFXOCC/COleControlContainer::GetDlgItemInt
- AFXOCC/COleControlContainer::GetDlgItemText
- AFXOCC/COleControlContainer::HandleSetFocus
- AFXOCC/COleControlContainer::HandleWindowlessMessage
- AFXOCC/COleControlContainer::IsDlgButtonChecked
- AFXOCC/COleControlContainer::OnPaint
- AFXOCC/COleControlContainer::OnUIActivate
- AFXOCC/COleControlContainer::OnUIDeactivate
- AFXOCC/COleControlContainer::ScrollChildren
- AFXOCC/COleControlContainer::SendDlgItemMessage
- AFXOCC/COleControlContainer::SetDlgItemInt
- AFXOCC/COleControlContainer::SetDlgItemText
- AFXOCC/COleControlContainer::m_crBack
- AFXOCC/COleControlContainer::m_crFore
- AFXOCC/COleControlContainer::m_listSitesOrWnds
- AFXOCC/COleControlContainer::m_nWindowlessControls
- AFXOCC/COleControlContainer::m_pOleFont
- AFXOCC/COleControlContainer::m_pSiteCapture
- AFXOCC/COleControlContainer::m_pSiteFocus
- AFXOCC/COleControlContainer::m_pSiteUIActive
- AFXOCC/COleControlContainer::m_pWnd
- AFXOCC/COleControlContainer::m_siteMap
helpviewer_keywords:
- COleControlContainer [MFC], COleControlContainer
- COleControlContainer [MFC], AttachControlSite
- COleControlContainer [MFC], BroadcastAmbientPropertyChange
- COleControlContainer [MFC], CheckDlgButton
- COleControlContainer [MFC], CheckRadioButton
- COleControlContainer [MFC], CreateControl
- COleControlContainer [MFC], CreateOleFont
- COleControlContainer [MFC], FindItem
- COleControlContainer [MFC], FreezeAllEvents
- COleControlContainer [MFC], GetAmbientProp
- COleControlContainer [MFC], GetDlgItem
- COleControlContainer [MFC], GetDlgItemInt
- COleControlContainer [MFC], GetDlgItemText
- COleControlContainer [MFC], HandleSetFocus
- COleControlContainer [MFC], HandleWindowlessMessage
- COleControlContainer [MFC], IsDlgButtonChecked
- COleControlContainer [MFC], OnPaint
- COleControlContainer [MFC], OnUIActivate
- COleControlContainer [MFC], OnUIDeactivate
- COleControlContainer [MFC], ScrollChildren
- COleControlContainer [MFC], SendDlgItemMessage
- COleControlContainer [MFC], SetDlgItemInt
- COleControlContainer [MFC], SetDlgItemText
- COleControlContainer [MFC], m_crBack
- COleControlContainer [MFC], m_crFore
- COleControlContainer [MFC], m_listSitesOrWnds
- COleControlContainer [MFC], m_nWindowlessControls
- COleControlContainer [MFC], m_pOleFont
- COleControlContainer [MFC], m_pSiteCapture
- COleControlContainer [MFC], m_pSiteFocus
- COleControlContainer [MFC], m_pSiteUIActive
- COleControlContainer [MFC], m_pWnd
- COleControlContainer [MFC], m_siteMap
ms.assetid: f7ce9246-0fb7-4f07-a83a-6c2390d0fdf8
ms.openlocfilehash: b1737b2ac114181a4245fff027b756ca30b64129
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366178"
---
# <a name="colecontrolcontainer-class"></a>クラス

ActiveX コントロールのコントロール コンテナーとして機能します。

## <a name="syntax"></a>構文

```
class COleControlContainer : public CCmdTarget
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[コントロール コンテナ::コントロールコンテナ](#colecontrolcontainer)|`COleControlContainer` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[コントロール コンテナ::コントロールサイトのアタッチ](#attachcontrolsite)|コンテナーによってホストされるコントロール サイトを作成します。|
|[コントロールコンテナ::ブロードキャストアンビエントプロパティ変更](#broadcastambientpropertychange)|アンビエント プロパティが変更されたことを、ホストされているすべてのコントロールに通知します。|
|[コントロールコンテナ::チェックドルグボタン](#checkdlgbutton)|指定したボタン コントロールを変更します。|
|[コントロールコンテナ::チェックラジオボタン](#checkradiobutton)|グループの指定されたラジオ ボタンを選択します。|
|[コントロールコンテナ::コントロールの作成](#createcontrol)|ホストされた ActiveX コントロールを作成します。|
|[コントロール コンテナ::Ole フォントの作成](#createolefont)|OLE フォントを作成します。|
|[コントロールコンテナ::アイテムを検索します。](#finditem)|指定したコントロールのカスタム サイトを返します。|
|[コントロールコンテナ::フリーズオールイベント](#freezeallevents)|コントロール サイトがイベントを受け付けるかどうかを判断します。|
|[コントロールコンテナ::アンビエントプロップ](#getambientprop)|指定したアンビエント プロパティを取得します。|
|[コントロールコンテナ::ゲットドルグアイテム](#getdlgitem)|指定されたダイアログ コントロールを取得します。|
|[コントロールコンテナ::ゲットドルグアイテムイント](#getdlgitemint)|指定されたダイアログ コントロールの値を取得します。|
|[コントロールコンテナ::テキストを取得します。](#getdlgitemtext)|指定されたダイアログ コントロールのキャプションを取得します。|
|[コントロールコンテナ::ハンドルセットフォーカス](#handlesetfocus)|コンテナーがWM_SETFOCUSメッセージを処理するかどうかを決定します。|
|[ウィンドウなしのメッセージを処理します。](#handlewindowlessmessage)|ウィンドウなしのコントロールに送信されたメッセージを処理します。|
|[コントロールコンテナ::IsDlgボタンチェック](#isdlgbuttonchecked)|指定したボタンの状態を確認します。|
|[コントロールコンテナ::オンペイント](#onpaint)|コンテナーの一部を再描画するために呼び出されます。|
|[コントロールコンテナ::オンUIアクティベート](#onuiactivate)|コントロールがインプレース アクティブ化されるときに呼び出されます。|
|[コントロールコンテナ::オンUI非アクティブ化](#onuideactivate)|コントロールが非アクティブ化されるときに呼び出されます。|
|[コントロールコンテナ::スクロールチルドレン](#scrollchildren)|子ウィンドウからスクロール メッセージを受信したときに、フレームワークによって呼び出されます。|
|[コントロール コンテナ::メッセージ](#senddlgitemmessage)|指定されたコントロールにメッセージを送信します。|
|[コントロールコンテナ::セットドルグアイテムイント](#setdlgitemint)|指定したコントロールの値を設定します。|
|[コントロールコンテナ::テキストを設定します。](#setdlgitemtext)|指定したコントロールのテキストを設定します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[コントロールコンテナ::m_crBack](#m_crback)|コンテナーの背景色。|
|[コントロールコンテナ::m_crFore](#m_crfore)|コンテナーの前景色。|
|[コントロールコンテナ::m_listSitesOrWnds](#m_listsitesorwnds)|サポートされているコントロール サイトの一覧。|
|[コントロール コンテナ::m_nWindowlessControls](#m_nwindowlesscontrols)|ホストされたウィンドウなしコントロールの数。|
|[コントロールコンテナ::m_pOleFont](#m_polefont)|カスタム コントロール サイトの OLE フォントへのポインター。|
|[コントロール コンテナ::m_pSiteCapture](#m_psitecapture)|キャプチャ コントロール サイトへのポインター。|
|[コントロールコンテナ::m_pSiteFocus](#m_psitefocus)|現在入力フォーカスを持っているコントロールへのポインター。|
|[コントロールコンテナ::m_pSiteUIActive](#m_psiteuiactive)|現在埋め込み先でアクティブにされているコントロールへのポインター。|
|[コントロールコンテナ::m_pWnd](#m_pwnd)|コントロール コンテナーを実装するウィンドウへのポインター。|
|[コントロールコンテナ::m_siteMap](#m_sitemap)|サイト マップ。|

## <a name="remarks"></a>解説

これは、 によって実装される 1 つ以上の ActiveX コントロール`COleControlSite`サイトのサポートを提供することによって行われます。 `COleControlContainer`は、含まれている ActiveX コントロールがインプレース項目としての条件を満たすことを可能にする[、IOleInPlaceFrame](/windows/win32/api/oleidl/nn-oleidl-ioleinplaceframe)インターフェイスと[IOleContainer](/windows/win32/api/oleidl/nn-oleidl-iolecontainer)インターフェイスを完全に実装します。

通常、このクラスは、1 つ`COccManager`以上`COleControlSite`の ActiveX コントロールのカスタム サイトを持つカスタム ActiveX コントロール コンテナーと組み合わせて、および実装するために使用されます。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleControlContainer`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxocc.h

## <a name="colecontrolcontainerattachcontrolsite"></a><a name="attachcontrolsite"></a>コントロール コンテナ::コントロールサイトのアタッチ

コントロール サイトを作成およびアタッチするために、フレームワークによって呼び出されます。

```
virtual void AttachControlSite(
    CWnd* pWnd,
    UINT nIDC = 0);

void AttachControlSite(
    CWnd* pWnd,
    UINT nIDC = 0);
```

### <a name="parameters"></a>パラメーター

*Pwnd*<br/>
`CWnd` オブジェクトを指すポインターです。

*nIDC*<br/>
アタッチするコントロールの ID。

### <a name="remarks"></a>解説

このプロセスをカスタマイズする場合は、この関数をオーバーライドします。

> [!NOTE]
> MFC ライブラリに静的にリンクしている場合は、この関数の最初の形式を使用します。 MFC ライブラリに動的にリンクしている場合は、2 番目のフォームを使用します。

## <a name="colecontrolcontainerbroadcastambientpropertychange"></a><a name="broadcastambientpropertychange"></a>コントロールコンテナ::ブロードキャストアンビエントプロパティ変更

アンビエント プロパティが変更されたことを、ホストされているすべてのコントロールに通知します。

```
virtual void BroadcastAmbientPropertyChange(DISPID dispid);
```

### <a name="parameters"></a>パラメーター

*Dispid*<br/>
変更されるアンビエント プロパティのディスパッチ ID。

### <a name="remarks"></a>解説

この関数は、アンビエント プロパティの値が変更されたときに、フレームワークによって呼び出されます。 この動作をカスタマイズするには、この関数をオーバーライドします。

## <a name="colecontrolcontainercheckdlgbutton"></a><a name="checkdlgbutton"></a>コントロールコンテナ::チェックドルグボタン

ボタンの現在の状態を変更します。

```
virtual void CheckDlgButton(
    int nIDButton,
    UINT nCheck);
```

### <a name="parameters"></a>パラメーター

*NIDボタン*<br/>
変更するボタンの ID。

*nチェック*<br/>
ボタンの状態を指定します。 以下のいずれかを指定できます。

- BST_CHECKED ボタンの状態をチェック済みに設定します。

- BST_INDETERMINATE ボタンの状態をグレー表示に設定し、不確定な状態を示します。 この値は、ボタンにBS_3STATEまたはBS_AUTO3STATEスタイルがある場合にのみ使用します。

- BST_UNCHECKED ボタンの状態をクリアに設定します。

## <a name="colecontrolcontainercheckradiobutton"></a><a name="checkradiobutton"></a>コントロールコンテナ::チェックラジオボタン

グループ内の指定されたラジオ ボタンを選択し、グループ内の残りのボタンをクリアします。

```
virtual void CheckRadioButton(
    int nIDFirstButton,
    int nIDLastButton,
    int nIDCheckButton);
```

### <a name="parameters"></a>パラメーター

*最初のボタン*<br/>
グループ内の最初のラジオ ボタンの識別子を指定します。

*ラストボタン*<br/>
グループ内の最後のラジオ ボタンの識別子を指定します。

*ボタンをクリックします。*<br/>
チェックするラジオボタンの識別子を指定します。

## <a name="colecontrolcontainercolecontrolcontainer"></a><a name="colecontrolcontainer"></a>コントロール コンテナ::コントロールコンテナ

`COleControlContainer` オブジェクトを構築します。

```
explicit COleControlContainer(CWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

*Pwnd*<br/>
コントロール コンテナーの親ウィンドウへのポインター。

### <a name="remarks"></a>解説

オブジェクトが正常に作成されたら、 に呼び出しを指定してカスタム`AttachControlSite`コントロール サイトを追加します。

## <a name="colecontrolcontainercreatecontrol"></a><a name="createcontrol"></a>コントロールコンテナ::コントロールの作成

指定した`COleControlSite`オブジェクトによってホストされる ActiveX コントロールを作成します。

```
BOOL CreateControl(
    CWnd* pWndCtrl,
    REFCLSID clsid,
    LPCTSTR lpszWindowName,
    DWORD dwStyle,
    const RECT& rect,
    UINT nID,
    CFile* pPersist =NULL,
    BOOL bStorage =FALSE,
    BSTR bstrLicKey =NULL,
    COleControlSite** ppNewSite =NULL);

BOOL CreateControl(
    CWnd* pWndCtrl,
    REFCLSID clsid,
    LPCTSTR lpszWindowName,
    DWORD dwStyle,
    const POINT* ppt,
    const SIZE* psize,
    UINT nID,
    CFile* pPersist =NULL,
    BOOL bStorage =FALSE,
    BSTR bstrLicKey =NULL,
    COleControlSite** ppNewSite =NULL);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
コントロールを表すウィンドウ オブジェクトへのポインター。

*Clsid*<br/>
コントロールの一意のクラス ID。

*名前をクリックします。*<br/>
コントロールに表示されるテキストへのポインター。 コントロールの Caption プロパティまたは Text プロパティの値を設定します (存在する場合)。 NULL の場合、コントロールの Caption プロパティまたは Text プロパティは変更されません。

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

*新しいサイト*<br/>
作成されるコントロールをホストする既存のコントロール サイトへのポインター。 既定値は NULL で、新しいコントロール サイトが自動的に作成され、新しいコントロールにアタッチされることを示します。

*Ppt*<br/>
コントロールの左上隅を`POINT`含む構造体へのポインター。 コントロールのサイズは、 *psize*の値によって決まります。 *ppt*値と*psize*値は、コントロールのサイズと位置を指定するオプションの方法です。

*Psize*<br/>
コントロールのサイズを`SIZE`格納する構造体へのポインター。 左上隅は *、 ppt*の値によって決まります。 *ppt*値と*psize*値は、コントロールのサイズと位置を指定するオプションの方法です。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

でサポート`CreateControl`されている Windows *dwStyle*フラグのサブセットのみ。

- WS_VISIBLE 最初に表示されるウィンドウを作成します。 通常のウィンドウのように、コントロールをすぐに表示する場合は必須です。

- WS_DISABLED最初に無効になっているウィンドウを作成します。 無効なウィンドウはユーザーからの入力を受け取ることができません。 コントロールに Enabled プロパティがある場合に設定できます。

- WS_BORDER 細い線の境界線を持つウィンドウを作成します。 コントロールに BorderStyle プロパティがある場合に設定できます。

- WS_GROUP コントロールのグループの最初のコントロールを指定します。 ユーザーは、方向キーを使用して、グループ内のコントロールから次のコントロールにキーボード フォーカスを変更できます。 最初のコントロールの後にWS_GROUPスタイルで定義されたすべてのコントロールが同じグループに属します。 WS_GROUPスタイルの次のコントロールは、グループを終了し、次のグループを開始します。

- WS_TABSTOPユーザーが Tab キーを押したときにキーボード フォーカスを受け取ることができるコントロールを指定します。 Tab キーを押すと、キーボード フォーカスがWS_TABSTOPスタイルの次のコントロールに変更されます。

2 番目のオーバーロードを使用して、既定のサイズのコントロールを作成します。

## <a name="colecontrolcontainercreateolefont"></a><a name="createolefont"></a>コントロール コンテナ::Ole フォントの作成

OLE フォントを作成します。

```
void CreateOleFont(CFont* pFont);
```

### <a name="parameters"></a>パラメーター

*フォント*<br/>
コントロール コンテナーで使用されるフォントへのポインター。

## <a name="colecontrolcontainerfinditem"></a><a name="finditem"></a>コントロールコンテナ::アイテムを検索します。

指定した項目をホストするカスタム サイトを検索します。

```
virtual COleControlSite* FindItem(UINT nID) const;
```

### <a name="parameters"></a>パラメーター

*nID*<br/>
見つかる項目の識別子。

### <a name="return-value"></a>戻り値

指定した項目のカスタム サイトへのポインター。

## <a name="colecontrolcontainerfreezeallevents"></a><a name="freezeallevents"></a>コントロールコンテナ::フリーズオールイベント

コンテナーが、アタッチされたコントロール サイトからのイベントを無視するか、受け入れるかどうかを決定します。

```
void FreezeAllEvents(BOOL bFreeze);
```

### <a name="parameters"></a>パラメーター

*bフリーズ*<br/>
イベントが処理される場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

> [!NOTE]
> コントロールコンテナーによって要求された場合、コントロールはイベントの発生を停止する必要はありません。 このイベントは引き続き実行できますが、後続のすべてのイベントはコントロール コンテナによって無視されます。

## <a name="colecontrolcontainergetambientprop"></a><a name="getambientprop"></a>コントロールコンテナ::アンビエントプロップ

指定したアンビエント プロパティの値を取得します。

```
virtual BOOL GetAmbientProp(
    COleControlSite* pSite,
    DISPID dispid,
    VARIANT* pvarResult);
```

### <a name="parameters"></a>パラメーター

*サイト*<br/>
アンビエント プロパティの取得元となるコントロール サイトへのポインター。

*Dispid*<br/>
目的のアンビエント プロパティのディスパッチ ID。

*結果*<br/>
アンビエント プロパティの値へのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

## <a name="colecontrolcontainergetdlgitem"></a><a name="getdlgitem"></a>コントロールコンテナ::ゲットドルグアイテム

ダイアログ ボックスまたはその他のウィンドウ内の指定されたコントロールまたは子ウィンドウへのポインターを取得します。

```
virtual CWnd* GetDlgItem(int nID) const;

virtual void GetDlgItem(
    int nID,
    HWND* phWnd) const;
```

### <a name="parameters"></a>パラメーター

*nID*<br/>
取得するダイアログ項目の識別子。

*phWnd*<br/>
指定されたダイアログ項目のウィンドウ オブジェクトのハンドルへのポインター。

### <a name="return-value"></a>戻り値

ダイアログ項目のウィンドウへのポインター。

## <a name="colecontrolcontainergetdlgitemint"></a><a name="getdlgitemint"></a>コントロールコンテナ::ゲットドルグアイテムイント

指定されたコントロールの翻訳済みテキストの値を取得します。

```
virtual UINT GetDlgItemInt(
    int nID,
    BOOL* lpTrans,
    BOOL bSigned) const;
```

### <a name="parameters"></a>パラメーター

*nID*<br/>
コントロールの識別子。

*lpTrans*<br/>
関数の成功/失敗値を受け取るブール変数へのポインタ (TRUE は成功を示し、FALSE は失敗を示します)。

*b署名済み*<br/>
関数が最初にマイナス記号のテキストを調べ、見つかった場合は符号付き整数値を返すかどうかを指定します。 *bSigned*パラメーターが TRUE の場合、取得する値が符号付き整数値であることを指定して、戻り値を**int**型にキャストします。 拡張エラー情報を取得するには[、GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)を呼び出します。

### <a name="return-value"></a>戻り値

成功した場合 *、lpTrans*によって示される変数は TRUE に設定され、戻り値はコントロール テキストの変換された値になります。

関数が失敗した場合 *、lpTrans*が指す変数は FALSE に設定され、戻り値は 0 になります。 ゼロは変換可能な値であるため、戻り値がゼロの場合は失敗を示すものではありません。

*lpTrans*が NULL の場合、関数は成功または失敗に関する情報を返しません。

### <a name="remarks"></a>解説

この関数は、テキストの先頭にある余分なスペースを取り除き、10 進数の数字を変換することによって、取得したテキストを変換します。 この関数は、テキストの末尾に達するか、または数字以外の文字を検出すると、変換を停止します。

変換された値が INT_MAX (符号付き数値の場合) より大きい場合、または UINT_MAX (符号なしの数値の場合) を超える場合、この関数はゼロを返します。

## <a name="colecontrolcontainergetdlgitemtext"></a><a name="getdlgitemtext"></a>コントロールコンテナ::テキストを取得します。

指定されたコントロールのテキストを取得します。

```
virtual int GetDlgItemText(
    int nID,
    LPTSTR lpStr,
    int nMaxCount) const;
```

### <a name="parameters"></a>パラメーター

*nID*<br/>
コントロールの識別子。

*Lpstr*<br/>
コントロールのテキストへのポインター。

*カウントカウント*<br/>
*lpStr*が指すバッファーにコピーする文字列の最大長を文字数で指定します。 文字列の長さが制限を超えた場合、文字列は切り捨てられます。

### <a name="return-value"></a>戻り値

関数が成功した場合、戻り値は、バッファーにコピーされる文字数を指定します。

関数が失敗した場合は、0 を返します。 拡張エラー情報を取得するには[、GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)を呼び出します。

## <a name="colecontrolcontainerhandlesetfocus"></a><a name="handlesetfocus"></a>コントロールコンテナ::ハンドルセットフォーカス

コンテナーがWM_SETFOCUSメッセージを処理するかどうかを決定します。

```
virtual BOOL HandleSetFocus();
```

### <a name="return-value"></a>戻り値

コンテナーがWM_SETFOCUSメッセージを処理する場合は 0 以外の値。それ以外の場合は 0。

## <a name="colecontrolcontainerhandlewindowlessmessage"></a><a name="handlewindowlessmessage"></a>ウィンドウなしのメッセージを処理します。

ウィンドウなしコントロールのウィンドウ メッセージを処理します。

```
virtual BOOL HandleWindowlessMessage(
    UINT message,
    WPARAM wParam,
    LPARAM lParam,
    LRESULT* plResult);
```

### <a name="parameters"></a>パラメーター

*メッセージ*<br/>
Windows によって提供されるウィンドウ メッセージの識別子。

*wParam*<br/>
メッセージのパラメータ。Windows によって提供されます。 追加のメッセージ固有の情報を指定します。 このパラメーターの内容は、*メッセージ*・パラメーターの値によって異なります。

*lParam*<br/>
メッセージのパラメータ。Windows によって提供されます。 追加のメッセージ固有の情報を指定します。 このパラメーターの内容は、*メッセージ*・パラメーターの値によって異なります。

*結果を返します。*<br/>
ウィンドウ結果コード。 メッセージ処理の結果を指定し、送信されるメッセージに依存します。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

ウィンドウなしのコントロール メッセージの処理をカスタマイズするには、この関数をオーバーライドします。

## <a name="colecontrolcontainerisdlgbuttonchecked"></a><a name="isdlgbuttonchecked"></a>コントロールコンテナ::IsDlgボタンチェック

指定したボタンの状態を確認します。

```
virtual UINT IsDlgButtonChecked(int nIDButton) const;
```

### <a name="parameters"></a>パラメーター

*NIDボタン*<br/>
ボタン コントロールの識別子。

### <a name="return-value"></a>戻り値

BS_AUTOCHECKBOX、BS_AUTORADIOBUTTON、BS_AUTO3STATE、BS_CHECKBOX、BS_RADIOBUTTON、またはBS_3STATEスタイルで作成されたボタンからの戻り値。 以下のいずれかを指定できます。

- BST_CHECKEDボタンがチェックされます。

- BST_INDETERMINATE ボタンは灰色で表示され、不確定な状態を示します (ボタンにBS_3STATEまたはBS_AUTO3STATEスタイルがある場合にのみ適用されます)。

- BST_UNCHECKED ボタンがクリアされます。

### <a name="remarks"></a>解説

ボタンが 3 状態コントロールの場合、メンバー関数は、淡色表示、チェック、またはどちらも淡色表示になっているかどうかを判断します。

## <a name="colecontrolcontainerm_crback"></a><a name="m_crback"></a>コントロールコンテナ::m_crBack

コンテナーの背景色。

```
COLORREF m_crBack;
```

## <a name="colecontrolcontainerm_crfore"></a><a name="m_crfore"></a>コントロールコンテナ::m_crFore

コンテナーの前景色。

```
COLORREF m_crFore;
```

## <a name="colecontrolcontainerm_listsitesorwnds"></a><a name="m_listsitesorwnds"></a>コントロールコンテナ::m_listSitesOrWnds

コンテナーによってホストされるコントロール サイトの一覧。

```
CTypedPtrList<CPtrList, COleControlSiteOrWnd*> m_listSitesOrWnds;
```

## <a name="colecontrolcontainerm_nwindowlesscontrols"></a><a name="m_nwindowlesscontrols"></a>コントロール コンテナ::m_nWindowlessControls

コントロール コンテナーによってホストされるウィンドウなしコントロールの数。

```
int m_nWindowlessControls;
```

## <a name="colecontrolcontainerm_polefont"></a><a name="m_polefont"></a>コントロールコンテナ::m_pOleFont

カスタム コントロール サイトの OLE フォントへのポインター。

```
LPFONTDISP m_pOleFont;
```

## <a name="colecontrolcontainerm_psitecapture"></a><a name="m_psitecapture"></a>コントロール コンテナ::m_pSiteCapture

キャプチャ コントロール サイトへのポインター。

```
COleControlSite* m_pSiteCapture;
```

## <a name="colecontrolcontainerm_psitefocus"></a><a name="m_psitefocus"></a>コントロールコンテナ::m_pSiteFocus

現在入力フォーカスを持っているコントロール サイトへのポインター。

```
COleControlSite* m_pSiteFocus;
```

## <a name="colecontrolcontainerm_psiteuiactive"></a><a name="m_psiteuiactive"></a>コントロールコンテナ::m_pSiteUIActive

埋め込み場所でアクティブにされたコントロール サイトへのポインター。

```
COleControlSite* m_pSiteUIActive;
```

## <a name="colecontrolcontainerm_pwnd"></a><a name="m_pwnd"></a>コントロールコンテナ::m_pWnd

コンテナーに関連付けられているウィンドウ オブジェクトへのポインター。

```
CWnd* m_pWnd;
```

## <a name="colecontrolcontainerm_sitemap"></a><a name="m_sitemap"></a>コントロールコンテナ::m_siteMap

サイト マップ。

```
CMapPtrToPtr m_siteMap;
```

## <a name="colecontrolcontaineronpaint"></a><a name="onpaint"></a>コントロールコンテナ::オンペイント

WM_PAINT要求を処理するために、フレームワークによって呼び出されます。

```
virtual BOOL OnPaint(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
コンテナーによって使用されるデバイス コンテキストへのポインター。

### <a name="return-value"></a>戻り値

メッセージが処理された場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

描画プロセスをカスタマイズするには、この関数をオーバーライドします。

## <a name="colecontrolcontaineronuiactivate"></a><a name="onuiactivate"></a>コントロールコンテナ::オンUIアクティベート

*pSite*が指すコントロール サイトがインプレースでアクティブ化されるときに、フレームワークによって呼び出されます。

```
virtual void OnUIActivate(COleControlSite* pSite);
```

### <a name="parameters"></a>パラメーター

*サイト*<br/>
埋め込み位置でアクティブ化されるコントロール サイトへのポインター。

### <a name="remarks"></a>解説

インプレース アクティブ化とは、コンテナーのメイン メニューがインプレース複合メニューに置き換えられることを意味します。

## <a name="colecontrolcontaineronuideactivate"></a><a name="onuideactivate"></a>コントロールコンテナ::オンUI非アクティブ化

*pSite*が指すコントロール サイトが非アクティブ化されるときにフレームワークによって呼び出されます。

```
virtual void OnUIDeactivate(COleControlSite* pSite);
```

### <a name="parameters"></a>パラメーター

*サイト*<br/>
非アクティブ化しようとしているコントロール サイトへのポインター。

### <a name="remarks"></a>解説

この通知を受け取ると、コンテナーはユーザー インターフェイスを再インストールし、フォーカスを取る必要があります。

## <a name="colecontrolcontainerscrollchildren"></a><a name="scrollchildren"></a>コントロールコンテナ::スクロールチルドレン

子ウィンドウからスクロール メッセージを受信したときに、フレームワークによって呼び出されます。

```
virtual void ScrollChildren(
    int dx,
    int dy);
```

### <a name="parameters"></a>パラメーター

*Dx*<br/>
x 軸に沿ってスクロールする量 (ピクセル単位)。

*Dy*<br/>
y 軸に沿ってスクロールする量 (ピクセル単位)。

## <a name="colecontrolcontainersenddlgitemmessage"></a><a name="senddlgitemmessage"></a>コントロール コンテナ::メッセージ

指定されたコントロールにメッセージを送信します。

```
virtual LRESULT SendDlgItemMessage(
    int nID,
    UINT message,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>パラメーター

*nID*<br/>
メッセージを受信するコントロールの識別子を指定します。

*メッセージ*<br/>
送信するメッセージを指定します。

*wParam*<br/>
追加のメッセージ固有の情報を指定します。

*lParam*<br/>
追加のメッセージ固有の情報を指定します。

## <a name="colecontrolcontainersetdlgitemint"></a><a name="setdlgitemint"></a>コントロールコンテナ::セットドルグアイテムイント

ダイアログ ボックス内のコントロールのテキストを、指定した整数値の文字列形式に設定します。

```
virtual void SetDlgItemInt(
    int nID,
    UINT nValue,
    BOOL bSigned);
```

### <a name="parameters"></a>パラメーター

*nID*<br/>
コントロールの識別子。

*n値*<br/>
表示される整数値。

*b署名済み*<br/>
*nValue*パラメーターが符号付きか符号なしかを指定します。 このパラメーターが TRUE の場合 *、nValue*は署名されます。 このパラメーターが TRUE で*nValue*がゼロより小さい場合、文字列の最初の桁の前にマイナス記号が付けられます。 このパラメータが FALSE の場合 *、nValue*は符号なしになります。

## <a name="colecontrolcontainersetdlgitemtext"></a><a name="setdlgitemtext"></a>コントロールコンテナ::テキストを設定します。

*lpszString*に含まれるテキストを使用して、指定されたコントロールのテキストを設定します。

```
virtual void SetDlgItemText(
    int nID,
    LPCTSTR lpszString);
```

### <a name="parameters"></a>パラメーター

*nID*<br/>
コントロールの識別子。

*文字列*<br/>
コントロールのテキストへのポインター。

## <a name="see-also"></a>関連項目

[CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/colecontrolsite-class.md)<br/>
[COccManager クラス](../../mfc/reference/coccmanager-class.md)
