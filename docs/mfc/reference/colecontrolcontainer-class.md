---
title: COleControlContainer クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cd45453dd4d70424b47f74e46d0bd5f948f75499
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50077700"
---
# <a name="colecontrolcontainer-class"></a>COleControlContainer クラス

ActiveX コントロールのコントロール コンテナーとして機能します。

## <a name="syntax"></a>構文

```
class COleControlContainer : public CCmdTarget
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[COleControlContainer::COleControlContainer](#colecontrolcontainer)|`COleControlContainer` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[COleControlContainer::AttachControlSite](#attachcontrolsite)|コントロール サイトをコンテナーにホストを作成します。|
|[COleControlContainer::BroadcastAmbientPropertyChange](#broadcastambientpropertychange)|すべてホストされるコントロールをアンビエント プロパティが変更されたことを通知します。|
|[COleControlContainer::CheckDlgButton](#checkdlgbutton)|指定したボタン コントロールを変更します。|
|[COleControlContainer::CheckRadioButton](#checkradiobutton)|グループの指定したオプション ボタンを選択します。|
|[COleControlContainer::CreateControl](#createcontrol)|ホストされている ActiveX コントロールを作成します。|
|[COleControlContainer::CreateOleFont](#createolefont)|OLE フォントを作成します。|
|[COleControlContainer::FindItem](#finditem)|指定したコントロールのカスタムのサイトを返します。|
|[COleControlContainer::FreezeAllEvents](#freezeallevents)|コントロールのサイトがイベントを受け入れるかどうかを決定します。|
|[COleControlContainer::GetAmbientProp](#getambientprop)|指定されたアンビエント プロパティを取得します。|
|[COleControlContainer::GetDlgItem](#getdlgitem)|指定されたダイアログのコントロールを取得します。|
|[COleControlContainer::GetDlgItemInt](#getdlgitemint)|指定されたダイアログ コントロールの値を取得します。|
|[COleControlContainer::GetDlgItemText](#getdlgitemtext)|指定したダイアログ コントロールのキャプションを取得します。|
|[COleControlContainer::HandleSetFocus](#handlesetfocus)|コンテナーが WM_SETFOCUS メッセージを処理するかどうかを決定します。|
|[COleControlContainer::HandleWindowlessMessage](#handlewindowlessmessage)|ウィンドウなしのコントロールに送信されるメッセージを処理します。|
|[COleControlContainer::IsDlgButtonChecked](#isdlgbuttonchecked)|指定したボタンの状態を判断します。|
|[COleControlContainer::OnPaint](#onpaint)|コンテナーの一部を再描画に呼び出されます。|
|[COleControlContainer::OnUIActivate](#onuiactivate)|コントロールがインプレース アクティブ化すると呼び出されます。|
|[COleControlContainer::OnUIDeactivate](#onuideactivate)|コントロールが非アクティブ化されると呼び出されます。|
|[COleControlContainer::ScrollChildren](#scrollchildren)|子ウィンドウからスクロール メッセージを受信するときに、フレームワークによって呼び出されます。|
|[COleControlContainer::SendDlgItemMessage](#senddlgitemmessage)|指定されたコントロールにメッセージを送信します。|
|[COleControlContainer::SetDlgItemInt](#setdlgitemint)|指定したコントロールの値を設定します。|
|[COleControlContainer::SetDlgItemText](#setdlgitemtext)|指定したコントロールのテキストを設定します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[COleControlContainer::m_crBack](#m_crback)|コンテナーの背景色。|
|[COleControlContainer::m_crFore](#m_crfore)|コンテナーの前景色。|
|[COleControlContainer::m_listSitesOrWnds](#m_listsitesorwnds)|サポートされているコントロールのサイトの一覧。|
|[COleControlContainer::m_nWindowlessControls](#m_nwindowlesscontrols)|ホストされているウィンドウなしのコントロールの数。|
|[COleControlContainer::m_pOleFont](#m_polefont)|カスタム コントロール サイトの OLE フォントへのポインター。|
|[COleControlContainer::m_pSiteCapture](#m_psitecapture)|キャプチャ コントロール サイトへのポインター。|
|[COleControlContainer::m_pSiteFocus](#m_psitefocus)|現在入力フォーカスがコントロールへのポインター。|
|[COleControlContainer::m_pSiteUIActive](#m_psiteuiactive)|インプレース アクティブ化は、現在のコントロールへのポインター。|
|[COleControlContainer::m_pWnd](#m_pwnd)|コントロールのコンテナーを実装するウィンドウへのポインター。|
|[COleControlContainer::m_siteMap](#m_sitemap)|サイト マップします。|

## <a name="remarks"></a>Remarks

これは、1 つ以上の ActiveX コントロール サイトをサポートすることで (によって実装される`COleControlSite`)。 `COleControlContainer` 完全に実装、 [IOleInPlaceFrame](/windows/desktop/api/oleidl/nn-oleidl-ioleinplaceframe)と[IOleContainer](/windows/desktop/api/oleidl/nn-oleidl-iolecontainer)インプレース項目として、必要条件を満たすために格納されている ActiveX コントロールのインターフェイス。

このクラスを組み合わせて使用する一般的には、`COccManager`と`COleControlSite`1 つ以上の ActiveX コントロールのカスタムのサイトで、カスタムの ActiveX コントロール コンテナーを実装します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleControlContainer`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxocc.h

##  <a name="attachcontrolsite"></a>  COleControlContainer::AttachControlSite

作成し、コントロールのサイトに接続するためにフレームワークによって呼び出されます。

```
virtual void AttachControlSite(
    CWnd* pWnd,
    UINT nIDC = 0);

void AttachControlSite(
    CWnd* pWnd,
    UINT nIDC = 0);
```

### <a name="parameters"></a>パラメーター

*我が物*<br/>
`CWnd` オブジェクトへのポインター。

*各*<br/>
アタッチされるコントロールの ID。

### <a name="remarks"></a>Remarks

このプロセスをカスタマイズする場合は、この関数をオーバーライドします。

> [!NOTE]
>  MFC ライブラリに静的にリンクしている場合は、この関数の最初のフォームを使用します。 MFC ライブラリに動的にリンクしている場合は、2 番目の形式を使用します。

##  <a name="broadcastambientpropertychange"></a>  COleControlContainer::BroadcastAmbientPropertyChange

すべてホストされるコントロールをアンビエント プロパティが変更されたことを通知します。

```
virtual void BroadcastAmbientPropertyChange(DISPID dispid);
```

### <a name="parameters"></a>パラメーター

*dispid*<br/>
変更されたアンビエント プロパティのディスパッチ ID。

### <a name="remarks"></a>Remarks

この関数は、アンビエント プロパティの値が変更されたときにフレームワークによって呼び出されます。 この動作をカスタマイズするには、この関数をオーバーライドします。

##  <a name="checkdlgbutton"></a>  COleControlContainer::CheckDlgButton

ボタンの現在の状態を変更します。

```
virtual void CheckDlgButton(
    int nIDButton,
    UINT nCheck);
```

### <a name="parameters"></a>パラメーター

*nIDButton*<br/>
変更するボタンの ID。

*確認してください。*<br/>
ボタンの状態を指定します。 次のいずれかの値を指定します。

- BST_CHECKED セットにボタンの状態がチェックされます。

- BST_INDETERMINATE セット グレーで表示されるボタンの状態を中間の状態を示します。 ボタンに BS_3STATE または BS_AUTO3STATE スタイルがある場合にのみ、この値を使用します。

- 設定されているセットをボタンの状態がクリアされます。

##  <a name="checkradiobutton"></a>  COleControlContainer::CheckRadioButton

グループの指定されたオプション ボタンを選択し、グループ内の残りのボタンをクリアします。

```
virtual void CheckRadioButton(
    int nIDFirstButton,
    int nIDLastButton,
    int nIDCheckButton);
```

### <a name="parameters"></a>パラメーター

*nIDFirstButton*<br/>
グループ内の最初のラジオ ボタンの識別子を指定します。

*nIDLastButton*<br/>
グループ内の最後のラジオ ボタンの識別子を指定します。

*nIDCheckButton*<br/>
チェックするラジオ ボタンの識別子を指定します。

##  <a name="colecontrolcontainer"></a>  COleControlContainer::COleControlContainer

`COleControlContainer` オブジェクトを構築します。

```
explicit COleControlContainer(CWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

*我が物*<br/>
コントロールのコンテナーの親ウィンドウへのポインター。

### <a name="remarks"></a>Remarks

オブジェクトが正常に作成されると、追加のカスタム コントロール サイトへの呼び出しを`AttachControlSite`します。

##  <a name="createcontrol"></a>  COleControlContainer::CreateControl

指定したによってホストされている ActiveX コントロールを作成します`COleControlSite`オブジェクト。

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

*pWndCtrl*<br/>
コントロールを表す window オブジェクトへのポインター。

*clsid*<br/>
コントロールの一意のクラス ID。

*したとき*<br/>
コントロールに表示されるテキストへのポインター。 (指定されている場合) は、コントロールのキャプションまたはテキストのプロパティの値を設定します。 NULL の場合、コントロールのキャプションまたはテキストのプロパティは変更されません。

*dwStyle*<br/>
Windows のスタイル。 使用可能なスタイルは、下に表示されます、**解説**セクション。

*rect*<br/>
コントロールのサイズと位置を指定します。 いずれかのことができます、`CRect`オブジェクトまたは`RECT`構造体。

*nID*<br/>
コントロールの子ウィンドウ ID を指定します

*pPersist*<br/>
ポインターを`CFile`コントロールの永続的な状態を格納します。 既定値は、null の場合、コントロール自体の初期化を任意の永続的なストレージからの状態を復元しないことを示すです。 ポインターである必要があります、NULL でない場合、 `CFile`-ストリームまたはストレージのいずれかの形式で、コントロールの永続的なデータを格納しているオブジェクトを派生します。 クライアントの以前のライセンス認証でこのデータが保存された可能性があります。 `CFile` 、他のデータを含めることができますが、読み取り/書き込みを指すポインターへの呼び出し時に永続的なデータの最初のバイトに設定する必要がありますがある`CreateControl`します。

*bStorage*<br/>
示すかどうかのデータ*pPersist*として解釈する必要があります`IStorage`または`IStream`データ。 場合内のデータ*pPersist* 、ストレージには、 *bStorage* TRUE にする必要があります。 場合内のデータ*pPersist*ストリーム、 *bStorage* FALSE にする必要があります。 既定値は FALSE です。

*bstrLicKey*<br/>
省略可能なライセンス キーのデータ。 このデータは、ランタイム ライセンス キーが必要なコントロールの作成にのみ必要です。 コントロールでは、ライセンスをサポートする場合を正常にコントロールを作成するためのライセンス キーを提供する必要があります。 既定値は、NULL です。

*ppNewSite*<br/>
作成されるコントロールをホストする既存のコントロール サイトへのポインター。 既定値は、null の場合、新しいコントロールのサイトが自動的に作成され、新しいコントロールにアタッチされていることを示すです。

*ppt*<br/>
ポインターを`POINT`コントロールの左上隅を含む構造体。 コントロールのサイズの値によって決まります*psize*します。 *Ppt*と*psize*値は、コントロールの位置とサイズを指定するオプションのメソッド。

*psize*<br/>
ポインターを`SIZE`コントロールのサイズを含む構造体。 左上隅の値によって決まります*ppt*します。 *Ppt*と*psize*値は、コントロールの位置とサイズを指定するオプションのメソッド。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

Windows のサブセットのみ*dwStyle*でフラグがサポートされる`CreateControl`:

- WS_VISIBLE は、最初に表示されているウィンドウを作成します。 通常のウィンドウと同様に、すぐに表示されるコントロールをするかどうかに必要です。

- WS_DISABLED は、最初に無効になっているウィンドウを作成します。 無効のウィンドウでは、ユーザーから入力を受け取ることはできません。 コントロールは、Enabled プロパティに設定できます。

- WS_BORDER では、細い境界線でウィンドウを作成します。 コントロールが BorderStyle プロパティに設定できます。

- WS_GROUP では、コントロールのグループの最初のコントロールを指定します。 ユーザーに変更できますキーボード フォーカス グループ内の 1 つのコントロールから、次の方向キーを使用しています。 最初のコントロールが同じグループに属している後に WS_GROUP スタイルで定義されたすべてのコントロール。 WS_GROUP スタイルでは、次のコントロールは、グループを終了し、[次へ] のグループを開始します。

- WS_TABSTOP は、コントロール、ユーザーが TAB キーを押したときにキーボード フォーカスを受け取ることができますを指定します。 TAB キーを押して WS_TABSTOP スタイルの次のコントロールにキーボード フォーカスを変更します。

コントロールの既定のサイズを作成するのにには、2 番目のオーバー ロードを使用します。

##  <a name="createolefont"></a>  COleControlContainer::CreateOleFont

OLE フォントを作成します。

```
void CreateOleFont(CFont* pFont);
```

### <a name="parameters"></a>パラメーター

*pFont*<br/>
コントロールのコンテナーで使用されるフォントへのポインター。

##  <a name="finditem"></a>  COleControlContainer::FindItem

指定した項目をホストするカスタムのサイトを検索します。

```
virtual COleControlSite* FindItem(UINT nID) const;
```

### <a name="parameters"></a>パラメーター

*nID*<br/>
検索するアイテムの識別子。

### <a name="return-value"></a>戻り値

指定した項目のカスタムのサイトへのポインター。

##  <a name="freezeallevents"></a>  COleControlContainer::FreezeAllEvents

かどうか、コンテナーは、関連付けられたコントロールのサイトからのイベントを無視するか、同意によって決まります。

```
void FreezeAllEvents(BOOL bFreeze);
```

### <a name="parameters"></a>パラメーター

*bFreeze*<br/>
イベントが処理される場合は 0 以外それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

> [!NOTE]
>  コントロールは、コントロール コンテナーによって要求された場合のイベントの発生を停止する必要はありません。 起動処理を続行できますが、後続のすべてのイベントは、コントロール コンテナーで無視されます。

##  <a name="getambientprop"></a>  COleControlContainer::GetAmbientProp

指定されたアンビエント プロパティの値を取得します。

```
virtual BOOL GetAmbientProp(
    COleControlSite* pSite,
    DISPID dispid,
    VARIANT* pvarResult);
```

### <a name="parameters"></a>パラメーター

*pSite*<br/>
アンビエント プロパティの取得元となるコントロール サイトへのポインター。

*dispid*<br/>
目的のアンビエント プロパティのディスパッチ ID。

*pVarResult*<br/>
アンビエント プロパティの値へのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

##  <a name="getdlgitem"></a>  COleControlContainer::GetDlgItem

ダイアログ ボックスで指定したコントロールまたは子ウィンドウまたはその他のウィンドウへのポインターを取得します。

```
virtual CWnd* GetDlgItem(int nID) const;

virtual void GetDlgItem(
    int nID,
    HWND* phWnd) const;
```

### <a name="parameters"></a>パラメーター

*nID*<br/>
取得する ダイアログの項目の識別子。

*phWnd*<br/>
指定されたダイアログの項目のウィンドウ オブジェクトのハンドルへのポインター。

### <a name="return-value"></a>戻り値

項目のダイアログのウィンドウへのポインター。

##  <a name="getdlgitemint"></a>  COleControlContainer::GetDlgItemInt

指定されたコントロールの翻訳されたテキストの値を取得します。

```
virtual UINT GetDlgItemInt(
    int nID,
    BOOL* lpTrans,
    BOOL bSigned) const;
```

### <a name="parameters"></a>パラメーター

*nID*<br/>
コントロールの識別子です。

*lpTrans*<br/>
関数の成功/失敗の値を受信するブール値変数へのポインター (成功を true、FALSE がエラーを示します)。

*bSigned*<br/>
関数が先頭にマイナス記号のテキストを確認し、いずれか見つかった場合は、符号付き整数値を返すかどうかを指定します。 場合、 *bSigned*パラメーターが TRUE、戻り値をキャストを取得する値が符号付き整数値を指定する、 **int**型。 拡張エラー情報を取得するには呼び出します[GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360)します。

### <a name="return-value"></a>戻り値

かどうかは成功すると、変数が指す*lpTrans*を TRUE に設定されていると、戻り値はコントロールのテキストの翻訳された値。

関数が失敗した場合、変数が指す*lpTrans*を FALSE に設定されていると、戻り値は 0。 0 が使用可能な翻訳された値であるため、戻り値が 0 を単独で示しませんエラーに注意してください。

場合*lpTrans*が null の場合、成功または失敗に関する情報を返しません。

### <a name="remarks"></a>Remarks

関数は、テキストの先頭に余分なスペースを削除し、10 進数字に変換し、取得したテキストを変換します。 関数は、テキストの末尾に到達または数値以外の文字が検出されたときの変換を停止します。

変換された値が INT_MAX (符号付き数値の場合) または (符号なし数値) の UINT_MAX より大きい場合、この関数は 0 を返します。

##  <a name="getdlgitemtext"></a>  COleControlContainer::GetDlgItemText

指定されたコントロールのテキストを取得します。

```
virtual int GetDlgItemText(
    int nID,
    LPTSTR lpStr,
    int nMaxCount) const;
```

### <a name="parameters"></a>パラメーター

*nID*<br/>
コントロールの識別子です。

*lpStr*<br/>
コントロールのテキストへのポインター。

*nMaxCount*<br/>
指すバッファーにコピーする文字列の文字で最大の長さを指定します。 *lpStr*します。 文字列の長さの上限を超えている場合は、文字列は切り捨てられます。

### <a name="return-value"></a>戻り値

関数が成功した場合、戻り値は、終端の null 文字を含まない、バッファーにコピーされた文字数を指定します。

関数が失敗した場合は、0 を返します。 拡張エラー情報を取得するには呼び出します[GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360)します。

##  <a name="handlesetfocus"></a>  COleControlContainer::HandleSetFocus

コンテナーが WM_SETFOCUS メッセージを処理するかどうかを決定します。

```
virtual BOOL HandleSetFocus();
```

### <a name="return-value"></a>戻り値

コンテナーが WM_SETFOCUS メッセージを処理する場合、0 以外の場合それ以外の場合 0 を返します。

##  <a name="handlewindowlessmessage"></a>  COleControlContainer::HandleWindowlessMessage

ウィンドウなしのコントロールのウィンドウ メッセージを処理します。

```
virtual BOOL HandleWindowlessMessage(
    UINT message,
    WPARAM wParam,
    LPARAM lParam,
    LRESULT* plResult);
```

### <a name="parameters"></a>パラメーター

*message*<br/>
Windows によって提供される、ウィンドウ メッセージの識別子。

*wParam*<br/>
メッセージのパラメーターWindows によって提供されます。 追加のメッセージに固有の情報を指定します。 このパラメーターの内容は、の値によって異なります、*メッセージ*パラメーター。

*lParam*<br/>
メッセージのパラメーターWindows によって提供されます。 追加のメッセージに固有の情報を指定します。 このパラメーターの内容は、の値によって異なります、*メッセージ*パラメーター。

*plResult*<br/>
Windows の結果コード。 メッセージの処理の結果を指定し、送信メッセージに依存します。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

ウィンドウなしのコントロール メッセージの処理をカスタマイズするには、この関数をオーバーライドします。

##  <a name="isdlgbuttonchecked"></a>  COleControlContainer::IsDlgButtonChecked

指定したボタンの状態を判断します。

```
virtual UINT IsDlgButtonChecked(int nIDButton) const;
```

### <a name="parameters"></a>パラメーター

*nIDButton*<br/>
ボタン コントロールの識別子。

### <a name="return-value"></a>戻り値

BS_AUTOCHECKBOX、BS_AUTORADIOBUTTON、BS_AUTO3STATE、BS_CHECKBOX、BS_RADIOBUTTON、または BS_3STATE スタイルで作成したボタンから戻り値。 次のいずれかの値を指定します。

- BST_CHECKED ボタンがチェックされます。

- BST_INDETERMINATE ボタンは淡色表示 (ボタンに BS_3STATE または BS_AUTO3STATE スタイルがある場合にのみ適用されます)、中間の状態を示します。

- 設定されているボタンはクリアされます。

### <a name="remarks"></a>Remarks

メンバー関数は、決定かどうか、淡色表示をオンになっているボタンが 3 つの状態のコントロールの場合、またはどちらもします。

##  <a name="m_crback"></a>  COleControlContainer::m_crBack

コンテナーの背景色。

```
COLORREF m_crBack;
```

##  <a name="m_crfore"></a>  COleControlContainer::m_crFore

コンテナーの前景色。

```
COLORREF m_crFore;
```

##  <a name="m_listsitesorwnds"></a>  COleControlContainer::m_listSitesOrWnds

コンテナーでホストされているコントロールのサイトの一覧。

```
CTypedPtrList<CPtrList, COleControlSiteOrWnd*> m_listSitesOrWnds;
```

##  <a name="m_nwindowlesscontrols"></a>  COleControlContainer::m_nWindowlessControls

コントロール コンテナーでホストされているウィンドウなしのコントロールの数。

```
int m_nWindowlessControls;
```

##  <a name="m_polefont"></a>  COleControlContainer::m_pOleFont

カスタム コントロール サイトの OLE フォントへのポインター。

```
LPFONTDISP m_pOleFont;
```

##  <a name="m_psitecapture"></a>  COleControlContainer::m_pSiteCapture

キャプチャ コントロール サイトへのポインター。

```
COleControlSite* m_pSiteCapture;
```

##  <a name="m_psitefocus"></a>  COleControlContainer::m_pSiteFocus

現在入力フォーカスがコントロール サイトへのポインター。

```
COleControlSite* m_pSiteFocus;
```

##  <a name="m_psiteuiactive"></a>  COleControlContainer::m_pSiteUIActive

インプレース アクティブ化は、コントロール サイトへのポインター。

```
COleControlSite* m_pSiteUIActive;
```

##  <a name="m_pwnd"></a>  COleControlContainer::m_pWnd

コンテナーに関連付けられたウィンドウ オブジェクトへのポインター。

```
CWnd* m_pWnd;
```

##  <a name="m_sitemap"></a>  COleControlContainer::m_siteMap

サイト マップします。

```
CMapPtrToPtr m_siteMap;
```

##  <a name="onpaint"></a>  COleControlContainer::OnPaint

WM_PAINT 要求を処理するためにフレームワークによって呼び出されます。

```
virtual BOOL OnPaint(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
コンテナーで使用されるデバイス コンテキストへのポインター。

### <a name="return-value"></a>戻り値

メッセージが処理された場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

描画プロセスをカスタマイズするには、この関数をオーバーライドします。

##  <a name="onuiactivate"></a>  COleControlContainer::OnUIActivate

フレームワークによって呼び出されますがコントロールのサイトの指すとき*pSite*をインプレース アクティブ化します。

```
virtual void OnUIActivate(COleControlSite* pSite);
```

### <a name="parameters"></a>パラメーター

*pSite*<br/>
インプレース アクティブ化するコントロール サイトへのポインター。

### <a name="remarks"></a>Remarks

インプレース アクティブ化は、コンテナーのメイン メニューは、インプレースのコンポジット メニューに置き換えられますことを意味します。

##  <a name="onuideactivate"></a>  COleControlContainer::OnUIDeactivate

フレームワークによって呼び出されますが、コントロール サイトの指すときに*pSite*が非アクティブ化しようとしています。

```
virtual void OnUIDeactivate(COleControlSite* pSite);
```

### <a name="parameters"></a>パラメーター

*pSite*<br/>
非アクティブ化するコントロール サイトへのポインター。

### <a name="remarks"></a>Remarks

この通知が受信したときに、コンテナーは、ユーザー インターフェイスを再インストールされ、フォーカスを取得する必要があります。

##  <a name="scrollchildren"></a>  COleControlContainer::ScrollChildren

子ウィンドウからスクロール メッセージを受信するときに、フレームワークによって呼び出されます。

```
virtual void ScrollChildren(
    int dx,
    int dy);
```

### <a name="parameters"></a>パラメーター

*dx*<br/>
X 軸に沿ってスクロールの (ピクセル単位) の量。

*dy*<br/>
Y 軸に沿ってスクロールの (ピクセル単位) の量。

##  <a name="senddlgitemmessage"></a>  COleControlContainer::SendDlgItemMessage

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

*message*<br/>
送信されるメッセージを指定します。

*wParam*<br/>
追加のメッセージに固有の情報を指定します。

*lParam*<br/>
追加のメッセージに固有の情報を指定します。

##  <a name="setdlgitemint"></a>  COleControlContainer::SetDlgItemInt

指定した整数値の文字列形式のダイアログ ボックスで、コントロールのテキストを設定します。

```
virtual void SetDlgItemInt(
    int nID,
    UINT nValue,
    BOOL bSigned);
```

### <a name="parameters"></a>パラメーター

*nID*<br/>
コントロールの識別子です。

*値*<br/>
表示される整数値。

*bSigned*<br/>
指定するかどうか、*値*パラメーターの符号付きまたは符号なし。 このパラメーターが TRUE の場合*値*署名されます。 このパラメーターが TRUE の場合と*値*マイナス記号は、文字列の最初の桁の前に配置を 0 未満です。 このパラメーターが FALSE の場合*値*が署名されていません。

##  <a name="setdlgitemtext"></a>  COleControlContainer::SetDlgItemText

含まれているテキストを使用して、指定したコントロールのテキストを設定*lpszString*します。

```
virtual void SetDlgItemText(
    int nID,
    LPCTSTR lpszString);
```

### <a name="parameters"></a>パラメーター

*nID*<br/>
コントロールの識別子です。

*lpszString*<br/>
コントロールのテキストへのポインター。

## <a name="see-also"></a>関連項目

[CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[COleControlSite クラス](../../mfc/reference/colecontrolsite-class.md)<br/>
[COccManager クラス](../../mfc/reference/coccmanager-class.md)
