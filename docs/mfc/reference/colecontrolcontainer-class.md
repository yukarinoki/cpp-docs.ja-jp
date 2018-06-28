---
title: メンバー クラス |Microsoft ドキュメント
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
ms.openlocfilehash: 0b59a1ef4d1a70063c15b7de41963abc60dd341a
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37041930"
---
# <a name="colecontrolcontainer-class"></a>メンバー クラス
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
|[COleControlContainer::BroadcastAmbientPropertyChange](#broadcastambientpropertychange)|アンビエント プロパティが変更されたホストされるすべてのコントロールに通知します。|  
|[COleControlContainer::CheckDlgButton](#checkdlgbutton)|指定したボタン コントロールを変更します。|  
|[COleControlContainer::CheckRadioButton](#checkradiobutton)|グループの指定されたオプション ボタンを選択します。|  
|[COleControlContainer::CreateControl](#createcontrol)|ホストされている ActiveX コントロールを作成します。|  
|[COleControlContainer::CreateOleFont](#createolefont)|OLE フォントを作成します。|  
|[COleControlContainer::FindItem](#finditem)|指定されたコントロールのカスタムのサイトを返します。|  
|[COleControlContainer::FreezeAllEvents](#freezeallevents)|コントロール サイトがイベントを受け入れるかどうかを判断します。|  
|[COleControlContainer::GetAmbientProp](#getambientprop)|指定されたアンビエント プロパティを取得します。|  
|[COleControlContainer::GetDlgItem](#getdlgitem)|指定されたダイアログのコントロールを取得します。|  
|[COleControlContainer::GetDlgItemInt](#getdlgitemint)|指定されたダイアログ コントロールの値を取得します。|  
|[COleControlContainer::GetDlgItemText](#getdlgitemtext)|指定されたダイアログ コントロールのキャプションを取得します。|  
|[COleControlContainer::HandleSetFocus](#handlesetfocus)|コンテナーが WM_SETFOCUS メッセージを処理するかどうかを判断します。|  
|[COleControlContainer::HandleWindowlessMessage](#handlewindowlessmessage)|ウィンドウなしのコントロールに送信されたメッセージを処理します。|  
|[COleControlContainer::IsDlgButtonChecked](#isdlgbuttonchecked)|指定したボタンの状態を判断します。|  
|[COleControlContainer::OnPaint](#onpaint)|コンテナーの一部を再描画に呼び出されます。|  
|[COleControlContainer::OnUIActivate](#onuiactivate)|コントロールが、インプレース アクティブ化すると呼び出されます。|  
|[COleControlContainer::OnUIDeactivate](#onuideactivate)|コントロールが非アクティブ化すると呼び出されます。|  
|[COleControlContainer::ScrollChildren](#scrollchildren)|子ウィンドウからスクロール メッセージを受け取ったときに、フレームワークによって呼び出されます。|  
|[COleControlContainer::SendDlgItemMessage](#senddlgitemmessage)|指定されたコントロールにメッセージを送信します。|  
|[COleControlContainer::SetDlgItemInt](#setdlgitemint)|指定したコントロールの値を設定します。|  
|[COleControlContainer::SetDlgItemText](#setdlgitemtext)|指定したコントロールのテキストを設定します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[COleControlContainer::m_crBack](#m_crback)|コンテナーの背景色です。|  
|[COleControlContainer::m_crFore](#m_crfore)|コンテナーの前景色です。|  
|[COleControlContainer::m_listSitesOrWnds](#m_listsitesorwnds)|サポートされているコントロールのサイトの一覧。|  
|[COleControlContainer::m_nWindowlessControls](#m_nwindowlesscontrols)|ホストされているウィンドウなしのコントロールの数。|  
|[COleControlContainer::m_pOleFont](#m_polefont)|カスタム コントロール サイトの OLE フォントへのポインター。|  
|[COleControlContainer::m_pSiteCapture](#m_psitecapture)|キャプチャ コントロール サイトへのポインター。|  
|[COleControlContainer::m_pSiteFocus](#m_psitefocus)|現在入力フォーカス コントロールへのポインター。|  
|[COleControlContainer::m_pSiteUIActive](#m_psiteuiactive)|現在、インプレース アクティブ化されているコントロールへのポインター。|  
|[COleControlContainer::m_pWnd](#m_pwnd)|コントロールのコンテナーを実装するウィンドウへのポインター。|  
|[COleControlContainer::m_siteMap](#m_sitemap)|サイト マップします。|  
  
## <a name="remarks"></a>Remarks  
 これは、1 つ以上の ActiveX コントロール サイトをサポートすることで (によって実装される`COleControlSite`)。 `COleControlContainer` 完全に実装する、 [IOleInPlaceFrame](http://msdn.microsoft.com/library/windows/desktop/ms692770)と[IOleContainer](http://msdn.microsoft.com/library/windows/desktop/ms690103)インターフェイス、埋め込み先アイテムとして、必要条件を満たすために格納されている ActiveX コントロールを許可します。  
  
 一般的には、このクラスと組み合わせて使用`COccManager`と`COleControlSite`を 1 つ以上の ActiveX コントロールのカスタムのサイトと、カスタムの ActiveX コントロール コンテナーを実装します。  
  
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
 *pWnd*  
 ポインター、`CWnd`オブジェクト。  
  
 *各*  
 アタッチする、コントロールの ID。  
  
### <a name="remarks"></a>Remarks  
 このプロセスをカスタマイズする場合は、この関数をオーバーライドします。  
  
> [!NOTE]
>  MFC ライブラリに静的にリンクしている場合は、この関数の最初のフォームを使用します。 MFC ライブラリに動的にリンクしている場合は、2 番目の形式を使用します。  
  
##  <a name="broadcastambientpropertychange"></a>  COleControlContainer::BroadcastAmbientPropertyChange  
 アンビエント プロパティが変更されたホストされるすべてのコントロールに通知します。  
  
```  
virtual void BroadcastAmbientPropertyChange(DISPID dispid);
```  
  
### <a name="parameters"></a>パラメーター  
 *dispid*  
 変更されたアンビエント プロパティのディスパッチ ID。  
  
### <a name="remarks"></a>Remarks  
 アンビエント プロパティに値が変更されたときに、この関数は、フレームワークによって呼び出されます。 この動作をカスタマイズするには、この関数をオーバーライドします。  
  
##  <a name="checkdlgbutton"></a>  COleControlContainer::CheckDlgButton  
 ボタンの現在の状態を変更します。  
  
```  
virtual void CheckDlgButton(
    int nIDButton,  
    UINT nCheck);
```  
  
### <a name="parameters"></a>パラメーター  
 *nIDButton*  
 変更するボタンの ID。  
  
 *nCheck*  
 ボタンの状態を指定します。 次のいずれかの値を指定します。  
  
- **BST_CHECKED**ボタンの状態をオフに設定します。  
  
- **BST_INDETERMINATE**灰色表示されている、不確定な状態を示すボタンの状態を設定します。 このボタンは場合にのみ、この値を使用して、 **BS_3STATE**または**BS_AUTO3STATE**スタイル。  
  
- **設定されている**ボタンの状態をオフに設定します。  
  
##  <a name="checkradiobutton"></a>  COleControlContainer::CheckRadioButton  
 グループ内の指定されたオプション ボタンを選択し、グループ内の残りのボタンをクリアします。  
  
```  
virtual void CheckRadioButton(
    int nIDFirstButton,  
    int nIDLastButton,  
    int nIDCheckButton);
```  
  
### <a name="parameters"></a>パラメーター  
 *nIDFirstButton*  
 グループ内の最初のラジオ ボタンの識別子を指定します。  
  
 *nIDLastButton*  
 グループ内の最後のオプション ボタンの識別子を指定します。  
  
 *nIDCheckButton*  
 チェックするラジオ ボタンの識別子を指定します。  
  
##  <a name="colecontrolcontainer"></a>  COleControlContainer::COleControlContainer  
 `COleControlContainer` オブジェクトを構築します。  
  
```  
explicit COleControlContainer(CWnd* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 *pWnd*  
 コントロールのコンテナーの親ウィンドウへのポインター。  
  
### <a name="remarks"></a>Remarks  
 オブジェクトが正常に作成される追加のカスタム コントロール サイトへの呼び出しが`AttachControlSite`です。  
  
##  <a name="createcontrol"></a>  COleControlContainer::CreateControl  
 指定したによってホストされている、ActiveX コントロールを作成`COleControlSite`オブジェクト。  
  
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
 *pWndCtrl*  
 コントロールを表す window オブジェクトへのポインター。  
  
 *clsid*  
 コントロールの一意のクラス ID。  
  
 *したとき*  
 コントロールに表示されるテキストへのポインター。 (該当する場合) は、コントロールのキャプションまたはテキストのプロパティの値を設定します。 場合**NULL**コントロールのキャプションまたはテキストのプロパティは変更されません。  
  
 *dwStyle*  
 Windows のスタイルです。 使用できるスタイルは、下に表示されます、**解説**セクションです。  
  
 *rect*  
 コントロールのサイズと位置を指定します。 いずれかになります、`CRect`オブジェクトまたは`RECT`構造体。  
  
 *nID*  
 コントロールの子ウィンドウ ID を指定します  
  
 *pPersist*  
 ポインター、`CFile`コントロールの永続的な状態を格納します。 既定値は**NULL**、コントロール自体の初期化を永続的な記憶域からの状態を復元することがなくすることを示すです。 ない場合**NULL**へのポインターである必要があります、 `CFile`-、ストリームとストレージのどちらかの形式でのコントロールの永続的なデータを含むオブジェクトを派生します。 このデータは、クライアントの以前のライセンス認証で保存されている可能性があります。 `CFile`他のデータを含めることができますが、読み取り/書き込みを指すポインターへの呼び出し時に永続的なデータの最初のバイトに設定する必要があります`CreateControl`です。  
  
 *bStorage*  
 示すかどうかのデータ*pPersist*として解釈する必要があります`IStorage`または`IStream`データ。 場合内のデータ*pPersist* 、記憶域は、 *bStorage*する必要があります**TRUE**です。 場合内のデータ*pPersist*ストリーム、 *bStorage*する必要があります**FALSE**です。 既定値は**FALSE**です。  
  
 *bstrLicKey*  
 省略可能なライセンス キー データ。 このデータは、実行時ライセンス キーが必要なコントロールを作成するためにのみ必要です。 コントロールは、ライセンスをサポートする場合を正常にコントロールを作成するためのライセンス キーを指定する必要があります。 既定値は**NULL**です。  
  
 *ppNewSite*  
 作成されるコントロールをホストする既存のコントロール サイトへのポインター。 既定値は**NULL**、新しいコントロール サイトが自動的に作成され、新しいコントロールにアタッチされていることを示すです。  
  
 *ppt*  
 ポインター、**ポイント**コントロールの左上隅を格納する構造体。 コントロールのサイズの値によって決まります*psize*です。 *Ppt*と*psize*値は、コントロールの位置とサイズを指定する省略可能なメソッドです。  
  
 *psize*  
 ポインター、**サイズ**コントロールのサイズを格納する構造体。 左上隅の値によって決まります*ppt*です。 *Ppt*と*psize*値は、コントロールの位置とサイズを指定する省略可能なメソッドです。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 Windows のサブセットのみ*dwStyle*はフラグによって`CreateControl`:  
  
- **WS_VISIBLE**が最初に表示するウィンドウを作成します。 通常のウィンドウと同様に、すぐに表示するコントロールをするかどうかに必要です。  
  
- **WS_DISABLED**最初に無効になっているウィンドウを作成します。 無効になっているウィンドウは、ユーザーから入力を受け取ることはできません。 コントロールは Enabled プロパティを持つ場合、設定できます。  
  
- **WS_BORDER**細い境界線でウィンドウを作成します。 コントロールに BorderStyle プロパティが設定されている場合、設定できます。  
  
- **WS_GROUP**コントロールのグループの最初のコントロールを指定します。 ユーザーを変更できますキーボード フォーカス、グループ内の 1 つのコントロールから、次への方向キーを使用しています。 定義されているすべてのコントロール、 **WS_GROUP**後、同じグループに属している、最初のコントロールのスタイルを設定します。 [次へ] のコントロールに、 **WS_GROUP**スタイルは、グループを終了し、[次へ] のグループを開始します。  
  
- **WS_TABSTOP**ユーザーが TAB キーを押すと、キーボード フォーカスを受信できるコントロールを指定します。 次のコントロールにキーボード フォーカスを移した TAB キーを押して、 **WS_TABSTOP**スタイル。  
  
 コントロールの既定のサイズを作成するのにには、2 番目のオーバー ロードを使用します。  
  
##  <a name="createolefont"></a>  COleControlContainer::CreateOleFont  
 OLE フォントを作成します。  
  
```  
void CreateOleFont(CFont* pFont);
```  
  
### <a name="parameters"></a>パラメーター  
 *pFont*  
 コントロールのコンテナーで使用されるフォントへのポインター。  
  
##  <a name="finditem"></a>  COleControlContainer::FindItem  
 カスタム ホストするサイトを指定した項目を検索します。  
  
```  
virtual COleControlSite* FindItem(UINT nID) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *nID*  
 検索するアイテムの識別子。  
  
### <a name="return-value"></a>戻り値  
 指定した項目のカスタムのサイトへのポインター。  
  
##  <a name="freezeallevents"></a>  COleControlContainer::FreezeAllEvents  
 かどうか、コンテナーは、関連付けられたコントロールのサイトからのイベントを無視するか、ライセンス条項に同意を決定します。  
  
```  
void FreezeAllEvents(BOOL bFreeze);
```  
  
### <a name="parameters"></a>パラメーター  
 *bFreeze*  
 イベントが処理される場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
  
> [!NOTE]
>  コントロールは、コントロール コンテナーによって要求された場合は、イベントを発生させるを停止する必要はありません。 起動処理を続行できますが、コントロール コンテナーですべての後続のイベントは無視されます。  
  
##  <a name="getambientprop"></a>  COleControlContainer::GetAmbientProp  
 指定されたアンビエント プロパティの値を取得します。  
  
```  
virtual BOOL GetAmbientProp(
    COleControlSite* pSite,  
    DISPID dispid,  
    VARIANT* pvarResult);
```  
  
### <a name="parameters"></a>パラメーター  
 *pSite*  
 アンビエント プロパティの取得元となるコントロール サイトへのポインター。  
  
 *dispid*  
 目的のアンビエント プロパティのディスパッチ ID。  
  
 *pVarResult*  
 アンビエント プロパティの値へのポインター。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
##  <a name="getdlgitem"></a>  COleControlContainer::GetDlgItem  
 ダイアログ ボックスで指定されたコントロールまたは子ウィンドウまたはその他のウィンドウへのポインターを取得します。  
  
```  
virtual CWnd* GetDlgItem(int nID) const;  
  
virtual void GetDlgItem(
    int nID,  
    HWND* phWnd) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *nID*  
 取得する ダイアログの項目の識別子。  
  
 *phWnd*  
 指定したダイアログ アイテムのウィンドウのオブジェクトのハンドルへのポインター。  
  
### <a name="return-value"></a>戻り値  
 項目のダイアログのウィンドウへのポインター。  
  
##  <a name="getdlgitemint"></a>  COleControlContainer::GetDlgItemInt  
 指定されたコントロールの翻訳済みテキストの値を取得します。  
  
```  
virtual UINT GetDlgItemInt(
    int nID,  
    BOOL* lpTrans,  
    BOOL bSigned) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *nID*  
 コントロールの識別子。  
  
 *lpTrans*  
 関数の成功/失敗の値を受信するブール値変数へのポインター ( **TRUE**は成功を示し**FALSE**失敗を示します)。  
  
 *bSigned*  
 関数は、必要があります、先頭にマイナス記号のテキストを調べるし、見つかった場合は、符号付き整数値を返すかどうかを指定します。 場合、 *bSigned*パラメーターは**TRUE**、戻り値を取得する値が符号付き整数値を指定するキャスト、 **int**型です。 拡張エラー情報を取得する呼び出し[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)です。  
  
### <a name="return-value"></a>戻り値  
 かどうかは成功すると、変数が指す*lpTrans*に設定されている**TRUE**、戻り値は、コントロール テキストの翻訳済みの値とします。  
  
 関数が失敗した場合、変数が指す*lpTrans*に設定されている**FALSE**、戻り値は 0 です。 0 が使用できる翻訳された値であるため、戻り値が 0 を単独で示しませんエラーに注意してください。  
  
 場合*lpTrans*は**NULL**関数が成功または失敗に関する情報を返しません。  
  
### <a name="remarks"></a>Remarks  
 関数は、テキストの先頭にある余分なスペースを削除し、10 進変換することによって取得されたテキストを変換します。 関数は、テキストの末尾に到達または数値以外の文字を検出したときの変換を停止します。  
  
 変換された値がより大きい場合、この関数は 0 を返します**INT_MAX**の符号付き数値または**UINT_MAX** (の符号なし数値)。  
  
##  <a name="getdlgitemtext"></a>  COleControlContainer::GetDlgItemText  
 指定されたコントロールのテキストを取得します。  
  
```  
virtual int GetDlgItemText(
    int nID,  
    LPTSTR lpStr,  
    int nMaxCount) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *nID*  
 コントロールの識別子。  
  
 *lpStr*  
 コントロールのテキストへのポインター。  
  
 *nMaxCount*  
 指すバッファーにコピーする文字列の文字の最大の長さを示す*lpStr*です。 文字列の長さが、制限を超える場合、文字列は切り捨てられます。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合、戻り値は、終端の null 文字を含まない、バッファーにコピーされた文字数を指定します。  
  
 関数が失敗した場合は、0 を返します。 拡張エラー情報を取得する呼び出し[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)です。  
  
##  <a name="handlesetfocus"></a>  COleControlContainer::HandleSetFocus  
 コンテナーが WM_SETFOCUS メッセージを処理するかどうかを判断します。  
  
```  
virtual BOOL HandleSetFocus();
```  
  
### <a name="return-value"></a>戻り値  
 コンテナーが WM_SETFOCUS メッセージを処理する場合は 0 以外。それ以外の場合 0 を返します。  
  
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
 *message*  
 Windows によって提供される、ウィンドウ メッセージの識別子。  
  
 *wParam*  
 メッセージのパラメーターWindows によって提供されます。 その他のメッセージに固有の情報を指定します。 このパラメーターの内容がの値に依存する、*メッセージ*パラメーター。  
  
 *lParam*  
 メッセージのパラメーターWindows によって提供されます。 その他のメッセージに固有の情報を指定します。 このパラメーターの内容がの値に依存する、*メッセージ*パラメーター。  
  
 *plResult*  
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
 *nIDButton*  
 ボタン コントロールの識別子。  
  
### <a name="return-value"></a>戻り値  
 作成したボタンからの戻り値、 **BS_AUTOCHECKBOX**、 **BS_AUTORADIOBUTTON**、 **BS_AUTO3STATE**、 **BS_CHECKBOX**、**BS_RADIOBUTTON**、または**BS_3STATE**スタイル。 次のいずれかの値を指定します。  
  
- **BST_CHECKED**ボタンがオンになっています。  
  
- **BST_INDETERMINATE**不確定な状態を示す、ボタンが淡色表示 (にこのボタンは場合にのみ適用されます、 **BS_3STATE**または**BS_AUTO3STATE**スタイル)。  
  
- **設定されている**ボタンは無効です。  
  
### <a name="remarks"></a>Remarks  
 メンバー関数は、決定かどうか、淡色表示になり、チェックすると、ボタンが 3 つの状態コントロールの場合は、またはどちらもします。  
  
##  <a name="m_crback"></a>  COleControlContainer::m_crBack  
 コンテナーの背景色です。  
  
```  
COLORREF m_crBack;  
```  
  
##  <a name="m_crfore"></a>  COleControlContainer::m_crFore  
 コンテナーの前景色です。  
  
```  
COLORREF m_crFore;  
```  
  
##  <a name="m_listsitesorwnds"></a>  COleControlContainer::m_listSitesOrWnds  
 コンテナーによってホストされるコントロールのサイトの一覧。  
  
```  
CTypedPtrList<CPtrList, COleControlSiteOrWnd*> m_listSitesOrWnds;  
```  
  
##  <a name="m_nwindowlesscontrols"></a>  COleControlContainer::m_nWindowlessControls  
 コントロールのコンテナーでホストされているウィンドウなしのコントロールの数。  
  
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
 現在入力フォーカス コントロール サイトへのポインター。  
  
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
 *pDC*  
 コンテナーで使用されるデバイス コンテキストへのポインター。  
  
### <a name="return-value"></a>戻り値  
 メッセージが処理された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 描画プロセスをカスタマイズするには、この関数をオーバーライドします。  
  
##  <a name="onuiactivate"></a>  COleControlContainer::OnUIActivate  
 フレームワークによって呼び出されますとコントロール サイトを指す*pSite*をインプレース アクティブ化します。  
  
```  
virtual void OnUIActivate(COleControlSite* pSite);
```  
  
### <a name="parameters"></a>パラメーター  
 *pSite*  
 インプレース アクティブ化するコントロール サイトへのポインター。  
  
### <a name="remarks"></a>Remarks  
 インプレース アクティブ化は、コンテナーのメイン メニューが、インプレース コンポジット メニューに置き換えられることを意味します。  
  
##  <a name="onuideactivate"></a>  COleControlContainer::OnUIDeactivate  
 フレームワークによって呼び出されるときコントロール サイトを指す*pSite*が非アクティブ化しようとしています。  
  
```  
virtual void OnUIDeactivate(COleControlSite* pSite);
```  
  
### <a name="parameters"></a>パラメーター  
 *pSite*  
 非アクティブにするコントロール サイトへのポインター。  
  
### <a name="remarks"></a>Remarks  
 この通知を受信すると、コンテナーは、ユーザー インターフェイスを再インストールされ、フォーカスを移す必要があります。  
  
##  <a name="scrollchildren"></a>  COleControlContainer::ScrollChildren  
 子ウィンドウからスクロール メッセージを受け取ったときに、フレームワークによって呼び出されます。  
  
```  
virtual void ScrollChildren(
    int dx,  
    int dy);
```  
  
### <a name="parameters"></a>パラメーター  
 *dx*  
 X 軸方向のスクロールの (ピクセル単位) の量。  
  
 *dy*  
 Y 軸方向のスクロールの (ピクセル単位) の量。  
  
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
 *nID*  
 メッセージを受信するコントロールの識別子を指定します。  
  
 *message*  
 送信するメッセージを指定します。  
  
 *wParam*  
 その他のメッセージに固有の情報を指定します。  
  
 *lParam*  
 その他のメッセージに固有の情報を指定します。  
  
##  <a name="setdlgitemint"></a>  COleControlContainer::SetDlgItemInt  
 指定した整数値の文字列形式にダイアログ ボックスで、コントロールのテキストを設定します。  
  
```  
virtual void SetDlgItemInt(
    int nID,  
    UINT nValue,  
    BOOL bSigned);
```  
  
### <a name="parameters"></a>パラメーター  
 *nID*  
 コントロールの識別子。  
  
 *値*  
 表示される整数値。  
  
 *bSigned*  
 指定するかどうか、*値*パラメーターが符号付きまたは符号なし。 このパラメーターは場合**TRUE**、*値*が署名されています。 このパラメーターは、する場合**TRUE**と*値*マイナス記号は、文字列の最初の桁の前に配置を 0 未満です。 このパラメーターが場合**FALSE**、*値*が署名されていません。  
  
##  <a name="setdlgitemtext"></a>  COleControlContainer::SetDlgItemText  
 含まれているテキストを使用して、指定したコントロールのテキストを設定*lpszString*です。  
  
```  
virtual void SetDlgItemText(
    int nID,  
    LPCTSTR lpszString);
```  
  
### <a name="parameters"></a>パラメーター  
 *nID*  
 コントロールの識別子。  
  
 *lpszString*  
 コントロールのテキストへのポインター。  
  
## <a name="see-also"></a>関連項目  
 [CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [メンバー クラス](../../mfc/reference/colecontrolsite-class.md)   
 [COccManager クラス](../../mfc/reference/coccmanager-class.md)
