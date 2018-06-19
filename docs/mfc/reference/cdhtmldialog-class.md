---
title: CDHtmlDialog クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDHtmlDialog
- AFXDHTML/CDHtmlDialog
- AFXDHTML/CDHtmlDialog::CDHtmlDialog
- AFXDHTML/CDHtmlDialog::CanAccessExternal
- AFXDHTML/CDHtmlDialog::CreateControlSite
- AFXDHTML/CDHtmlDialog::DDX_DHtml_AxControl
- AFXDHTML/CDHtmlDialog::DDX_DHtml_CheckBox
- AFXDHTML/CDHtmlDialog::DDX_DHtml_ElementText
- AFXDHTML/CDHtmlDialog::DDX_DHtml_Radio
- AFXDHTML/CDHtmlDialog::DDX_DHtml_SelectIndex
- AFXDHTML/CDHtmlDialog::DDX_DHtml_SelectString
- AFXDHTML/CDHtmlDialog::DDX_DHtml_SelectValue
- AFXDHTML/CDHtmlDialog::DestroyModeless
- AFXDHTML/CDHtmlDialog::EnableModeless
- AFXDHTML/CDHtmlDialog::FilterDataObject
- AFXDHTML/CDHtmlDialog::GetControlDispatch
- AFXDHTML/CDHtmlDialog::GetControlProperty
- AFXDHTML/CDHtmlDialog::GetCurrentUrl
- AFXDHTML/CDHtmlDialog::GetDHtmlDocument
- AFXDHTML/CDHtmlDialog::GetDropTarget
- AFXDHTML/CDHtmlDialog::GetElement
- AFXDHTML/CDHtmlDialog::GetElementHtml
- AFXDHTML/CDHtmlDialog::GetElementInterface
- AFXDHTML/CDHtmlDialog::GetElementProperty
- AFXDHTML/CDHtmlDialog::GetElementText
- AFXDHTML/CDHtmlDialog::GetEvent
- AFXDHTML/CDHtmlDialog::GetExternal
- AFXDHTML/CDHtmlDialog::GetHostInfo
- AFXDHTML/CDHtmlDialog::GetOptionKeyPath
- AFXDHTML/CDHtmlDialog::HideUI
- AFXDHTML/CDHtmlDialog::IsExternalDispatchSafe
- AFXDHTML/CDHtmlDialog::LoadFromResource
- AFXDHTML/CDHtmlDialog::Navigate
- AFXDHTML/CDHtmlDialog::OnBeforeNavigate
- AFXDHTML/CDHtmlDialog::OnDocumentComplete
- AFXDHTML/CDHtmlDialog::OnDocWindowActivate
- AFXDHTML/CDHtmlDialog::OnFrameWindowActivate
- AFXDHTML/CDHtmlDialog::OnInitDialog
- AFXDHTML/CDHtmlDialog::OnNavigateComplete
- AFXDHTML/CDHtmlDialog::ResizeBorder
- AFXDHTML/CDHtmlDialog::SetControlProperty
- AFXDHTML/CDHtmlDialog::SetElementHtml
- AFXDHTML/CDHtmlDialog::SetElementProperty
- AFXDHTML/CDHtmlDialog::SetElementText
- AFXDHTML/CDHtmlDialog::SetExternalDispatch
- AFXDHTML/CDHtmlDialog::SetHostFlags
- AFXDHTML/CDHtmlDialog::ShowContextMenu
- AFXDHTML/CDHtmlDialog::ShowUI
- AFXDHTML/CDHtmlDialog::TranslateAccelerator
- AFXDHTML/CDHtmlDialog::TranslateUrl
- AFXDHTML/CDHtmlDialog::UpdateUI
- AFXDHTML/CDHtmlDialog::m_bUseHtmlTitle
- AFXDHTML/CDHtmlDialog::m_nHtmlResID
- AFXDHTML/CDHtmlDialog::m_pBrowserApp
- AFXDHTML/CDHtmlDialog::m_spHtmlDoc
- AFXDHTML/CDHtmlDialog::m_strCurrentUrl
- AFXDHTML/CDHtmlDialog::m_szHtmlResID
dev_langs:
- C++
helpviewer_keywords:
- CDHtmlDialog [MFC], CDHtmlDialog
- CDHtmlDialog [MFC], CanAccessExternal
- CDHtmlDialog [MFC], CreateControlSite
- CDHtmlDialog [MFC], DDX_DHtml_AxControl
- CDHtmlDialog [MFC], DDX_DHtml_CheckBox
- CDHtmlDialog [MFC], DDX_DHtml_ElementText
- CDHtmlDialog [MFC], DDX_DHtml_Radio
- CDHtmlDialog [MFC], DDX_DHtml_SelectIndex
- CDHtmlDialog [MFC], DDX_DHtml_SelectString
- CDHtmlDialog [MFC], DDX_DHtml_SelectValue
- CDHtmlDialog [MFC], DestroyModeless
- CDHtmlDialog [MFC], EnableModeless
- CDHtmlDialog [MFC], FilterDataObject
- CDHtmlDialog [MFC], GetControlDispatch
- CDHtmlDialog [MFC], GetControlProperty
- CDHtmlDialog [MFC], GetCurrentUrl
- CDHtmlDialog [MFC], GetDHtmlDocument
- CDHtmlDialog [MFC], GetDropTarget
- CDHtmlDialog [MFC], GetElement
- CDHtmlDialog [MFC], GetElementHtml
- CDHtmlDialog [MFC], GetElementInterface
- CDHtmlDialog [MFC], GetElementProperty
- CDHtmlDialog [MFC], GetElementText
- CDHtmlDialog [MFC], GetEvent
- CDHtmlDialog [MFC], GetExternal
- CDHtmlDialog [MFC], GetHostInfo
- CDHtmlDialog [MFC], GetOptionKeyPath
- CDHtmlDialog [MFC], HideUI
- CDHtmlDialog [MFC], IsExternalDispatchSafe
- CDHtmlDialog [MFC], LoadFromResource
- CDHtmlDialog [MFC], Navigate
- CDHtmlDialog [MFC], OnBeforeNavigate
- CDHtmlDialog [MFC], OnDocumentComplete
- CDHtmlDialog [MFC], OnDocWindowActivate
- CDHtmlDialog [MFC], OnFrameWindowActivate
- CDHtmlDialog [MFC], OnInitDialog
- CDHtmlDialog [MFC], OnNavigateComplete
- CDHtmlDialog [MFC], ResizeBorder
- CDHtmlDialog [MFC], SetControlProperty
- CDHtmlDialog [MFC], SetElementHtml
- CDHtmlDialog [MFC], SetElementProperty
- CDHtmlDialog [MFC], SetElementText
- CDHtmlDialog [MFC], SetExternalDispatch
- CDHtmlDialog [MFC], SetHostFlags
- CDHtmlDialog [MFC], ShowContextMenu
- CDHtmlDialog [MFC], ShowUI
- CDHtmlDialog [MFC], TranslateAccelerator
- CDHtmlDialog [MFC], TranslateUrl
- CDHtmlDialog [MFC], UpdateUI
- CDHtmlDialog [MFC], m_bUseHtmlTitle
- CDHtmlDialog [MFC], m_nHtmlResID
- CDHtmlDialog [MFC], m_pBrowserApp
- CDHtmlDialog [MFC], m_spHtmlDoc
- CDHtmlDialog [MFC], m_strCurrentUrl
- CDHtmlDialog [MFC], m_szHtmlResID
ms.assetid: 3f941c85-87e1-4f0f-9cc5-ffee8498b312
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6259ee783f6964f3a4f7bd6db31688fc77c2aa26
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33377008"
---
# <a name="cdhtmldialog-class"></a>CDHtmlDialog クラス
HTML を使用するダイアログ ボックスの作成に使用されるユーザー インターフェイスの実装にダイアログ リソースではなくです。  
  
## <a name="syntax"></a>構文  
  
```  
class CDHtmlDialog : public CDialog, public CDHtmlEventSink  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CDHtmlDialog::CDHtmlDialog](#cdhtmldialog)|CDHtmlDialog オブジェクトを構築します。|  
|[CDHtmlDialog:: ~ CDHtmlDialog](#cdhtmldialog__~cdhtmldialog)|CDHtmlDialog オブジェクトを破棄します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDHtmlDialog::CanAccessExternal](#canaccessexternal)|オーバーライド可能なコントロール サイトの外部のディスパッチをページで読み込まれたスクリプトのオブジェクトがアクセスできるかどうかを表示するアクセス チェックとして呼び出されます。 ディスパッチが安全なスクリプトまたは現在のゾーンのいずれかでは、スクリプトを実行しても安全ではないオブジェクトのことを確認することを確認します。|  
|[CDHtmlDialog::CreateControlSite](#createcontrolsite)|Overridable は、ダイアログに WebBrowser コントロールをホストするコントロール サイトのインスタンスを作成するために使用します。|  
|[CDHtmlDialog::DDX_DHtml_AxControl](#ddx_dhtml_axcontrol)|メンバー変数と、HTML ページ上の ActiveX コントロールのプロパティの値の間でデータを交換します。|  
|[CDHtmlDialog::DDX_DHtml_CheckBox](#ddx_dhtml_checkbox)|メンバー変数と、HTML ページ上のチェック ボックス間でデータを交換します。|  
|[CDHtmlDialog::DDX_DHtml_ElementText](#ddx_dhtml_elementtext)|メンバー変数と、HTML ページの任意の HTML 要素プロパティ間でデータを交換します。|  
|[CDHtmlDialog::DDX_DHtml_Radio](#ddx_dhtml_radio)|メンバー変数と、HTML ページのオプション ボタンの間でデータを交換します。|  
|[CDHtmlDialog::DDX_DHtml_SelectIndex](#ddx_dhtml_selectindex)|取得または HTML ページで、ボックスの一覧のインデックスを設定します。|  
|[CDHtmlDialog::DDX_DHtml_SelectString](#ddx_dhtml_selectstring)|取得またはリスト ボックス エントリ (現在のインデックスに基づく) の表示テキストを HTML ページに設定します。|  
|[CDHtmlDialog::DDX_DHtml_SelectValue](#ddx_dhtml_selectvalue)|取得または HTML ページの (現在のインデックスに基づく) リスト ボックス エントリの値を設定します。|  
|[CDHtmlDialog::DestroyModeless](#destroymodeless)|モードレス ダイアログ ボックスを破棄します。|  
|[CDHtmlDialog::EnableModeless](#enablemodeless)|モードレス ダイアログ ボックスを有効にします。|  
|[CDHtmlDialog::FilterDataObject](#filterdataobject)|ホストされているブラウザーによって作成されたクリップボード データ オブジェクトをフィルター処理するダイアログ ボックスを使用できます。|  
|[CDHtmlDialog::GetControlDispatch](#getcontroldispatch)|取得、 `IDispatch` ActiveX コントロールのインターフェイスは、HTML ドキュメントに埋め込まれています。|  
|[CDHtmlDialog::GetControlProperty](#getcontrolproperty)|指定された ActiveX コントロールの要求されたプロパティを取得します。|  
|[CDHtmlDialog::GetCurrentUrl](#getcurrenturl)|現在のドキュメントに関連付けられている Uniform Resource Locator (URL) を取得します。|  
|[CDHtmlDialog::GetDHtmlDocument](#getdhtmldocument)|現在読み込まれている HTML ドキュメントの IHTMLDocument2 インターフェイスを取得します。|  
|[CDHtmlDialog::GetDropTarget](#getdroptarget)|代替のダイアログを許可する、ドロップ先として使用されているときに、コンテナー内の WebBrowser コントロールによって呼び出されます[IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679)です。|  
|[CDHtmlDialog::GetElement](#getelement)|HTML 要素のインターフェイスを取得します。|  
|[CDHtmlDialog::GetElementHtml](#getelementhtml)|取得、 **innerHTML** HTML 要素のプロパティです。|  
|[CDHtmlDialog::GetElementInterface](#getelementinterface)|HTML 要素から要求されたインターフェイス ポインターを取得します。|  
|[CDHtmlDialog::GetElementProperty](#getelementproperty)|HTML 要素のプロパティの値を取得します。|  
|[CDHtmlDialog::GetElementText](#getelementtext)|取得、 **innerText** HTML 要素のプロパティです。|  
|[CDHtmlDialog::GetEvent](#getevent)|取得、 **IHTMLEventObj**現在のイベント オブジェクトへのポインター。|  
|[CDHtmlDialog::GetExternal](#getexternal)|ホストの取得`IDispatch`インターフェイスです。|  
|[CDHtmlDialog::GetHostInfo](#gethostinfo)|ホストの UI 機能を取得します。|  
|[CDHtmlDialog::GetOptionKeyPath](#getoptionkeypath)|ユーザー設定が格納されているレジストリ キーを取得します。|  
|[CDHtmlDialog::HideUI](#hideui)|ホストの UI を非表示にします。|  
|[CDHtmlDialog::IsExternalDispatchSafe](#isexternaldispatchsafe)|示すかどうか、ホストの`IDispatch`インターフェイスはスクリプトを実行しても安全です。|  
|[CDHtmlDialog::LoadFromResource](#loadfromresource)|WebBrowser コントロールに、指定されたリソースを読み込みます。|  
|[CDHtmlDialog::Navigate](#navigate)|指定された URL に移動します。|  
|[CDHtmlDialog::OnBeforeNavigate](#onbeforenavigate)|ナビゲーション イベントが発生する前に、フレームワークによって呼び出されます。|  
|[CDHtmlDialog::OnDocumentComplete](#ondocumentcomplete)|ドキュメントに達したとき、アプリケーションに通知するためにフレームワークによって呼び出される、`READYSTATE_COMPLETE`状態です。|  
|[CDHtmlDialog::OnDocWindowActivate](#ondocwindowactivate)|ドキュメント ウィンドウがアクティブ化または非アクティブ化されたときに、フレームワークによって呼び出されます。|  
|[CDHtmlDialog::OnFrameWindowActivate](#onframewindowactivate)|フレーム ウィンドウがアクティブ化または非アクティブ化されたときに、フレームワークによって呼び出されます。|  
|[CDHtmlDialog::OnInitDialog](#oninitdialog)|応答と呼ばれる、 **WM_INITDIALOG**メッセージ。|  
|[CDHtmlDialog::OnNavigateComplete](#onnavigatecomplete)|ナビゲーション イベントが完了した後に、フレームワークによって呼び出されます。|  
|[CDHtmlDialog::ResizeBorder](#resizeborder)|境界領域のサイズを変更する必要があるオブジェクトに警告します。|  
|[CDHtmlDialog::SetControlProperty](#setcontrolproperty)|新しい値には、ActiveX コントロールのプロパティを設定します。|  
|[CDHtmlDialog::SetElementHtml](#setelementhtml)|セット、 **innerHTML** HTML 要素のプロパティです。|  
|[CDHtmlDialog::SetElementProperty](#setelementproperty)|HTML 要素のプロパティを設定します。|  
|[CDHtmlDialog::SetElementText](#setelementtext)|セット、 **innerText** HTML 要素のプロパティです。|  
|[CDHtmlDialog::SetExternalDispatch](#setexternaldispatch)|ホストの設定`IDispatch`インターフェイスです。|  
|[CDHtmlDialog::SetHostFlags](#sethostflags)|ホストの UI のフラグを設定します。|  
|[CDHtmlDialog::ShowContextMenu](#showcontextmenu)|コンテキスト メニューが表示されるときに呼び出されます。|  
|[CDHtmlDialog::ShowUI](#showui)|ホストの UI を示しています。|  
|[CDHtmlDialog::TranslateAccelerator](#translateaccelerator)|メニュー アクセス キーのメッセージを処理するには、呼び出されます。|  
|[CDHtmlDialog::TranslateUrl](#translateurl)|読み込む URL を変更するには、呼び出されます。|  
|[CDHtmlDialog::UpdateUI](#updateui)|コマンドの状態が変更されたホストに通知と呼ばれます。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CDHtmlDialog::m_bUseHtmlTitle](#m_busehtmltitle)|HTML ドキュメントのタイトルをダイアログのキャプションとして使用するかどうかを示します。|  
|[CDHtmlDialog::m_nHtmlResID](#m_nhtmlresid)|リソースを表示するリソースを HTML の ID です。|  
|[CDHtmlDialog::m_pBrowserApp](#m_pbrowserapp)|Web ブラウザー アプリケーションへのポインター。|  
|[CDHtmlDialog::m_spHtmlDoc](#m_sphtmldoc)|HTML ドキュメントへのポインター。|  
|[CDHtmlDialog::m_strCurrentUrl](#m_strcurrenturl)|現在の URL です。|  
|[CDHtmlDialog::m_szHtmlResID](#m_szhtmlresid)|HTML リソース ID の文字列バージョン|  
  
## <a name="remarks"></a>コメント  
 **CDHtmlDialog** HTML、HTML リソースのいずれかから表示するか、URL に読み込むことができます。  
  
 `CDHtmlDialog` できますもはデータの HTML コントロールと交換し、ボタンのクリックしてなど、HTML コントロールからイベントを処理します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDHtmlSinkHandlerBase2`  
  
 `CDHtmlSinkHandlerBase1`  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDHtmlSinkHandler`  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CDHtmlEventSink`  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 `CDHtmlDialog`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdhtml.h  
  
##  <a name="ddx_dhtml_helper_macros"></a>  DDX_DHtml ヘルパー マクロ  
 DDX_DHtml ヘルパー マクロでは、一般的に使用される HTML ページ上のコントロールのプロパティに簡単にアクセスできるようにします。  
  
### <a name="data-exchange-macros"></a>データ交換マクロ  
  
|||  
|-|-|  
|[DDX_DHtml_ElementValue](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_elementvalue)|設定または選択コントロールからプロパティ値を取得します。|  
|[DDX_DHtml_ElementInnerText](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_elementinnertext)|設定または現在の要素の開始と終了タグの間のテキストを取得します。|  
|[DDX_DHtml_ElementInnerHtml](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_elementinnerhtml)|設定または現在の要素の開始と終了タグの間の HTML を取得します。|  
|[DDX_DHtml_Anchor_Href](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_anchor_href)|設定またはコピー先の URL またはアンカー ポイントを取得します。|  
|[DDX_DHtml_Anchor_Target](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_anchor_target)|設定またはターゲット ウィンドウまたはフレームを取得します。|  
|[DDX_DHtml_Img_Src](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_img_src)|設定またはイメージまたはドキュメント内のビデオ クリップの名前を取得します。|  
|[DDX_DHtml_Frame_Src](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_frame_src)|設定または関連するフレームの URL を取得します。|  
|[DDX_DHtml_IFrame_Src](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_iframe_src)|設定または関連するフレームの URL を取得します。|  
  
##  <a name="canaccessexternal"></a>  CDHtmlDialog::CanAccessExternal  
 オーバーライド可能なコントロール サイトの外部のディスパッチをページで読み込まれたスクリプトのオブジェクトがアクセスできるかどうかを表示するアクセス チェックとして呼び出されます。 ディスパッチが安全なスクリプトまたは現在のゾーンのいずれかでは、スクリプトを実行しても安全ではないオブジェクトのことを確認することを確認します。  
  
```  
virtual BOOL CanAccessExternal();
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
##  <a name="cdhtmldialog"></a>  CDHtmlDialog::CDHtmlDialog  
 リソースに基づく動的な HTML のダイアログを構築します。  
  
```  
CDHtmlDialog();

 
CDHtmlDialog(
    LPCTSTR lpszTemplateName,  
    LPCTSTR szHtmlResID,  
    CWnd *pParentWnd = NULL);

 
CDHtmlDialog(
    UINT nIDTemplate,  
    UINT nHtmlResID = 0,  
    CWnd *pParentWnd = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszTemplateName`  
 ダイアログ テンプレート リソースの名前を表す null で終わる文字列。  
  
 `szHtmlResID`  
 HTML リソースの名前を表す null で終わる文字列。  
  
 `pParentWnd`  
 親またはオーナー ウィンドウのオブジェクトへのポインター (型の[CWnd](../../mfc/reference/cwnd-class.md)) ダイアログ オブジェクトが属しています。 場合は**NULL**、ダイアログ オブジェクトの親ウィンドウがアプリケーションのメイン ウィンドウに設定します。  
  
 `nIDTemplate`  
 ダイアログ テンプレート リソースの ID 番号が含まれています。  
  
 `nHtmlResID`  
 HTML リソースの ID 番号が含まれています。  
  
### <a name="remarks"></a>コメント  
 コンス トラクターの 2 番目の形式は、テンプレート名を使用して、ダイアログ リソースへのアクセスを提供します。 コンス トラクターの 3 番目の形式は、リソース テンプレートの ID を使用して、ダイアログ リソースへのアクセスを提供します。 通常、ID が始まる、**文字列の先頭**プレフィックス。  
  
##  <a name="_dtorcdhtmldialog"></a>  CDHtmlDialog:: ~ CDHtmlDialog  
 CDHtmlDialog オブジェクトを破棄します。  
  
```  
virtual ~CDHtmlDialog();
```  
  
### <a name="remarks"></a>コメント  
 [に](../../mfc/reference/cwnd-class.md#destroywindow)メンバー関数は、によって作成されるモードレス ダイアログ ボックスを破棄するために使用する必要があります[CDialog::Create](../../mfc/reference/cdialog-class.md#create)です。  
  
##  <a name="createcontrolsite"></a>  CDHtmlDialog::CreateControlSite  
 Overridable は、ダイアログに WebBrowser コントロールをホストするコントロール サイトのインスタンスを作成するために使用します。  
  
```  
virtual BOOL CreateControlSite(
    COleControlContainer* pContainer,  
    COleControlSite** ppSite,  
    UINT /* nID */,  
    REFCLSID /* clsid */);
```  
  
### <a name="parameters"></a>パラメーター  
 `pContainer`  
 ポインター、[メンバー](../../mfc/reference/colecontrolcontainer-class.md)オブジェクト  
  
 `ppSite`  
 ポインターへのポインター、[メンバー](../../mfc/reference/colecontrolsite-class.md)です。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 コントロール サイト クラスのインスタンスを返すには、このメンバー関数をオーバーライドすることができます。  
  
##  <a name="ddx_dhtml_axcontrol"></a>  CDHtmlDialog::DDX_DHtml_AxControl  
 メンバー変数と、HTML ページ上の ActiveX コントロールのプロパティの値の間でデータを交換します。  
  
```  
void DDX_DHtml_AxControl(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    DISPID dispid,  
    VARIANT& var);

 
void DDX_DHtml_AxControl(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    LPCTSTR szPropName,  
    VARIANT& var);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクト。  
  
 `szId`  
 ActiveX コントロールの HTML ソース内に object タグの ID パラメーターの値です。  
  
 `dispid`  
 データを交換するプロパティのディスパッチ ID。  
  
 `szPropName`  
 プロパティの名前。  
  
 `var`  
 データ メンバーの型の`VARIANT`、 [COleVariant](../../mfc/reference/colevariant-class.md)、または[CComVariant](../../atl/reference/ccomvariant-class.md)、ActiveX コントロールのプロパティと交換される値を保持します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCHtmlHttp#1](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_1.cpp)]  
  
##  <a name="ddx_dhtml_checkbox"></a>  CDHtmlDialog::DDX_DHtml_CheckBox  
 メンバー変数と、HTML ページ上のチェック ボックス間でデータを交換します。  
  
```  
void DDX_DHtml_CheckBox(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    int& value);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクト。  
  
 `szId`  
 HTML コントロールの ID パラメーターの指定した値。  
  
 *値*  
 交換される値。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCHtmlHttp#2](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_2.cpp)]  
  
##  <a name="ddx_dhtml_elementtext"></a>  CDHtmlDialog::DDX_DHtml_ElementText  
 メンバー変数と、HTML ページの任意の HTML 要素プロパティ間でデータを交換します。  
  
```  
void DDX_DHtml_ElementText(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    DISPID dispid,  
    CString& value);

 
void DDX_DHtml_ElementText(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    DISPID dispid,  
    short& value);

 
void DDX_DHtml_ElementText(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    DISPID dispid,  
    int& value);

 
void DDX_DHtml_ElementText(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    DISPID dispid,  
    long& value);

 
void DDX_DHtml_ElementText(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    DISPID dispid,  
    DWORD& value);

 
void DDX_DHtml_ElementText(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    DISPID dispid,  
    float& value);

 
void DDX_DHtml_ElementText(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    DISPID dispid,  
    double& value);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクト。  
  
 `szId`  
 HTML コントロールの ID パラメーターの指定した値。  
  
 *dispid*  
 データを交換する HTML 要素のディスパッチ ID。  
  
 *値*  
 交換される値。  
  
##  <a name="ddx_dhtml_radio"></a>  CDHtmlDialog::DDX_DHtml_Radio  
 メンバー変数と、HTML ページのオプション ボタンの間でデータを交換します。  
  
```  
void DDX_DHtml_Radio(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    long& value);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクト。  
  
 `szId`  
 HTML コントロールの ID パラメーターの指定した値。  
  
 *値*  
 交換される値。  
  
##  <a name="ddx_dhtml_selectindex"></a>  CDHtmlDialog::DDX_DHtml_SelectIndex  
 取得または HTML ページで、ボックスの一覧のインデックスを設定します。  
  
```  
void DDX_DHtml_SelectIndex(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    long& value);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクト。  
  
 `szId`  
 HTML コントロールの id パラメーターの指定した値。  
  
 *値*  
 交換される値。  
  
##  <a name="ddx_dhtml_selectstring"></a>  CDHtmlDialog::DDX_DHtml_SelectString  
 取得またはリスト ボックス エントリ (現在のインデックスに基づく) の表示テキストを HTML ページに設定します。  
  
```  
void DDX_DHtml_SelectString(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    CString& value);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクト。  
  
 `szId`  
 HTML コントロールの ID パラメーターの指定した値。  
  
 *値*  
 交換される値。  
  
##  <a name="ddx_dhtml_selectvalue"></a>  CDHtmlDialog::DDX_DHtml_SelectValue  
 取得または HTML ページの (現在のインデックスに基づく) リスト ボックス エントリの値を設定します。  
  
```  
void DDX_DHtml_SelectValue(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    CString& value);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクト。  
  
 `szId`  
 HTML コントロールの ID パラメーターの指定した値。  
  
 *値*  
 交換される値。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCHtmlHttp#3](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_3.cpp)]  
  
##  <a name="destroymodeless"></a>  CDHtmlDialog::DestroyModeless  
 モードレス ダイアログ ボックスの関連付けを解除、`CDHtmlDialog`オブジェクトおよびオブジェクトを破棄します。  
  
```  
void DestroyModeless();
```  
  
##  <a name="enablemodeless"></a>  CDHtmlDialog::EnableModeless  
 モードレス ダイアログ ボックスを有効にします。  
  
```  
STDMETHOD(EnableModeless)(BOOL fEnable);
```  
  
### <a name="parameters"></a>パラメーター  
 `fEnable`  
 参照してください`fEnable`で[IDocHostUIHandler::EnableModeless](https://msdn.microsoft.com/library/aa753253.aspx) Windows SDK にします。  
  
### <a name="return-value"></a>戻り値  
 返します**E_NOTIMPL**です。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数が CDHtmlDialog の実装の[IDocHostUIHandler::EnableModeless](https://msdn.microsoft.com/library/aa753253.aspx)Windows SDK で説明されている。  
  
##  <a name="filterdataobject"></a>  CDHtmlDialog::FilterDataObject  
 ホストされているブラウザーによって作成されたクリップボード データ オブジェクトをフィルター処理するダイアログ ボックスを使用できます。  
  
```  
STDMETHOD(FilterDataObject)(
    IDataObject* pDO,  
    IDataObject** ppDORet);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDO`  
 参照してください`pDO`で[IDocHostUIHandler::FilterDataObject](https://msdn.microsoft.com/library/aa753254.aspx) Windows SDK にします。  
  
 `ppDORet`  
 参照してください`ppDORet`で**IDocHostUIHandler::FilterDataObject** Windows SDK にします。  
  
### <a name="return-value"></a>戻り値  
 返します**S_FALSE**です。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数が CDHtmlDialog の実装の[IDocHostUIHandler::FilterDataObject](https://msdn.microsoft.com/library/aa753254.aspx)Windows SDK で説明されている。  
  
##  <a name="getcontroldispatch"></a>  CDHtmlDialog::GetControlDispatch  
 取得、 `IDispatch` ActiveX コントロールのインターフェイスは、によって返された HTML ドキュメントに埋め込まれている[GetDHtmlDocument](#getdhtmldocument)です。  
  
```  
HRESULT GetControlDispatch(
    LPCTSTR szId,  
    IDispatch** ppdisp);
```  
  
### <a name="parameters"></a>パラメーター  
 `szId`  
 ActiveX コントロールの HTML ID です。  
  
 *ppdisp*  
 `IDispatch`コントロールのインターフェイスの場合、Web ページに記載します。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
##  <a name="getcontrolproperty"></a>  CDHtmlDialog::GetControlProperty  
 指定された ActiveX コントロールの要求されたプロパティを取得します。  
  
```  
VARIANT GetControlProperty(
    LPCTSTR szId,  
    LPCTSTR szPropName);

 
VARIANT GetControlProperty(
    LPCTSTR szId,  
    DISPID dispid);

 
VARIANT GetControlProperty(
    IDispatch* pdispControl,  
    DISPID dispid);
```  
  
### <a name="parameters"></a>パラメーター  
 `szId`  
 ActiveX コントロールの HTML ID です。  
  
 `szPropName`  
 現在のユーザーの既定のロケールでは、プロパティの名前。  
  
 `pdispControl`  
 `IDispatch` ActiveX コントロールのポインター。  
  
 `dispid`  
 プロパティのディスパッチ ID。  
  
### <a name="return-value"></a>戻り値  
 コントロールまたはプロパティが見つからなかった場合に、要求されたプロパティ、または空のバリアントを含むバリアント型。  
  
### <a name="remarks"></a>コメント  
 オーバー ロードには、下部にある最も効率的なを上部にある最も非効率的なから一覧が表示されます。  
  
##  <a name="getcurrenturl"></a>  CDHtmlDialog::GetCurrentUrl  
 現在のドキュメントに関連付けられている Uniform Resource Locator (URL) を取得します。  
  
```  
void GetCurrentUrl(CString& szUrl);
```  
  
### <a name="parameters"></a>パラメーター  
 `szUrl`  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md)を取得する URL を含むオブジェクト。  
  
##  <a name="getdhtmldocument"></a>  CDHtmlDialog::GetDHtmlDocument  
 取得、 [IHTMLDocument2](https://msdn.microsoft.com/library/aa752574.aspx)現在読み込まれている HTML ドキュメント上のインターフェイスです。  
  
```  
HRESULT GetDHtmlDocument(IHTMLDocument2 **pphtmlDoc);
```  
  
### <a name="parameters"></a>パラメーター  
 *\*\*pphtmlDoc*  
 HTML ドキュメントへのポインターへのポインター。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT`。 正常に終了した場合は `S_OK` を返します。  
  
##  <a name="getdroptarget"></a>  CDHtmlDialog::GetDropTarget  
 代替のダイアログを許可する、ドロップ先として使用されているときに、コンテナー内の WebBrowser コントロールによって呼び出されます[IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679)です。  
  
```  
STDMETHOD(GetDropTarget)(
    IDropTarget* pDropTarget,  
    IDropTarget** ppDropTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDropTarget`  
 参照してください`pDropTarget`で[IDocHostUIHandler::GetDropTarget](https://msdn.microsoft.com/library/aa753255.aspx) Windows SDK にします。  
  
 `ppDropTarget`  
 参照してください`ppDropTarget`で**IDocHostUIHandler::GetDropTarget** Windows SDK にします。  
  
### <a name="return-value"></a>戻り値  
 返します**E_NOTIMPL**です。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数が CDHtmlDialog の実装の[IDocHostUIHandler::GetDropTarget](https://msdn.microsoft.com/library/aa753255.aspx)Windows SDK で説明されている。  
  
##  <a name="getelement"></a>  CDHtmlDialog::GetElement  
 指定された HTML 要素のインターフェイスを返します`szElementId`です。  
  
```  
HRESULT GetElement(
    LPCTSTR szElementId,  
    IDispatch** ppdisp,  
    BOOL* pbCollection = NULL);

 
HRESULT GetElement(
    LPCTSTR szElementId,  
    IHTMLElement** pphtmlElement);
```  
  
### <a name="parameters"></a>パラメーター  
 `szElementId`  
 HTML 要素の ID。  
  
 *ppdisp*  
 `IDispatch`要求された要素または要素のコレクションへのポインター。  
  
 *pbCollection*  
 A **BOOL**によって表されるオブジェクトであるかどうかを示す*ppdisp*が 1 つの要素または要素のコレクション。  
  
 *pphtmlElement*  
 **IHTMLElement**要求された要素へのポインター。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 条件である可能性があります指定された ID を持つ複数の要素を処理する必要がある場合は、最初のオーバー ロードを使用します。 最後のパラメーターを使用すると、1 つのアイテムまたはコレクションには、返されたインターフェイス ポインターかどうかを確認します。 インターフェイス ポインターがオンの場合、コレクションを照会できます、**指している**を使用してその**項目**順序位置で要素を参照するプロパティです。  
  
 2 番目のオーバー ロードは、ページに同じ ID を持つ 2 つ以上の要素が存在しない場合は失敗します。  
  
##  <a name="getelementhtml"></a>  CDHtmlDialog::GetElementHtml  
 取得、 **innerHTML**プロパティによって識別される HTML 要素の`szElementId`します。  
  
```  
BSTR GetElementHtml(LPCTSTR szElementId);
```  
  
### <a name="parameters"></a>パラメーター  
 `szElementId`  
 HTML 要素の ID。  
  
### <a name="return-value"></a>戻り値  
 **InnerHTML**プロパティによって識別される HTML 要素の`szElementId`または**NULL**場合は、要素が見つかりませんでした。  
  
##  <a name="getelementinterface"></a>  CDHtmlDialog::GetElementInterface  
 によって識別される HTML 要素から要求されたインターフェイス ポインターを取得`szElementId`です。  
  
```  
template <class Q> HRESULT GetElementInterface(
    LPCTSTR szElementId,  
    Q** ppvObj);

 
HRESULT GetElementInterface(
    LPCTSTR szElementId,  
    REFIID riid,  
    void** ppvObj);
```  
  
### <a name="parameters"></a>パラメーター  
 `szElementId`  
 HTML 要素の ID。  
  
 `ppvObj`  
 アドレス ポインターを要素が見つかった場合に、要求されたインターフェイス ポインターを格納して、クエリは成功します。  
  
 `riid`  
 要求されたインターフェイスの ID (IID) のインターフェイスです。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCHtmlHttp#4](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_4.cpp)]  
  
##  <a name="getelementproperty"></a>  CDHtmlDialog::GetElementProperty  
 によって識別されたプロパティの値を取得`dispid`で識別される HTML 要素から`szElementId`です。  
  
```  
VARIANT GetElementProperty(
    LPCTSTR szElementId,  
    DISPID dispid);
```  
  
### <a name="parameters"></a>パラメーター  
 `szElementId`  
 HTML 要素の ID。  
  
 `dispid`  
 プロパティのディスパッチ ID。  
  
### <a name="return-value"></a>戻り値  
 プロパティまたはプロパティまたは要素が見つからなかった場合は空のバリアントの値。  
  
##  <a name="getelementtext"></a>  CDHtmlDialog::GetElementText  
 取得、 **innerText**プロパティによって識別される HTML 要素の`szElementId`します。  
  
```  
BSTR GetElementText(LPCTSTR szElementId);
```  
  
### <a name="parameters"></a>パラメーター  
 `szElementId`  
 HTML 要素の ID。  
  
### <a name="return-value"></a>戻り値  
 **InnerText**プロパティによって識別される HTML 要素の`szElementId`または**NULL**プロパティまたは要素が見つからなかった場合です。  
  
##  <a name="getevent"></a>  CDHtmlDialog::GetEvent  
 返します、 **IHTMLEventObj**現在のイベント オブジェクトへのポインター。  
  
```  
HRESULT GetEvent(IHTMLEventObj** ppEventObj);
```  
  
### <a name="parameters"></a>パラメーター  
 `ppEventObj`  
 入力されます。 ポインターのアドレス、 **IHTMLEventObj**インターフェイス ポインター。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 この関数は、DHTML イベント ハンドラー内からのみ呼び出す必要があります。  
  
##  <a name="getexternal"></a>  CDHtmlDialog::GetExternal  
 ホストの取得`IDispatch`インターフェイスです。  
  
```  
STDMETHOD(GetExternal)(IDispatch** ppDispatch);
```  
  
### <a name="parameters"></a>パラメーター  
 *ppDispatch*  
 参照してください*ppDispatch*で[IDocHostUIHandler::GetExternal](https://msdn.microsoft.com/library/aa753256.aspx) Windows SDK に含まれています。  
  
### <a name="return-value"></a>戻り値  
 返します`S_OK`成功した場合または**E_NOTIMPL**エラー発生時にします。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数が CDHtmlDialog の実装の[IDocHostUIHandler::GetExternal](https://msdn.microsoft.com/library/aa753256.aspx)Windows SDK で説明されている。  
  
##  <a name="gethostinfo"></a>  CDHtmlDialog::GetHostInfo  
 ホストの UI 機能を取得します。  
  
```  
STDMETHOD(GetHostInfo)(DOCHOSTUIINFO* pInfo);
```  
  
### <a name="parameters"></a>パラメーター  
 `pInfo`  
 参照してください`pInfo`で[IDocHostUIHandler::GetHostInfo](https://msdn.microsoft.com/library/aa753257.aspx) Windows SDK にします。  
  
### <a name="return-value"></a>戻り値  
 `S_OK` を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数が CDHtmlDialog の実装の[IDocHostUIHandler::GetHostInfo](https://msdn.microsoft.com/library/aa753257.aspx)Windows SDK で説明されている。  
  
##  <a name="getoptionkeypath"></a>  CDHtmlDialog::GetOptionKeyPath  
 ユーザー設定が格納されているレジストリ キーを取得します。  
  
```  
STDMETHOD(GetOptionKeyPath)(
    LPOLESTR* pchKey,  
    DWORD dw);
```  
  
### <a name="parameters"></a>パラメーター  
 `pchKey`  
 参照してください`pchKey`で[IDocHostUIHandler::GetOptionKeyPath](https://msdn.microsoft.com/library/aa753258.aspx) Windows SDK にします。  
  
 `dw`  
 参照してください`dw`で**IDocHostUIHandler::GetOptionKeyPath** Windows SDK にします。  
  
### <a name="return-value"></a>戻り値  
 返します**E_NOTIMPL**です。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数が CDHtmlDialog の実装の[IDocHostUIHandler::GetOptionKeyPath](https://msdn.microsoft.com/library/aa753258.aspx)Windows SDK で説明されている。  
  
##  <a name="hideui"></a>  CDHtmlDialog::HideUI  
 ホストの UI を非表示にします。  
  
```  
STDMETHOD(HideUI)(void);
```  
  
### <a name="return-value"></a>戻り値  
 返します**E_NOTIMPL**です。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数が CDHtmlDialog の実装の[IDocHostUIHandler::HideUI](https://msdn.microsoft.com/library/aa753259.aspx)Windows SDK で説明されている。  
  
##  <a name="isexternaldispatchsafe"></a>  CDHtmlDialog::IsExternalDispatchSafe  
 示すかどうか、ホストの`IDispatch`インターフェイスはスクリプトを実行しても安全です。  
  
```  
virtual BOOL IsExternalDispatchSafe();
```  
  
### <a name="return-value"></a>戻り値  
 返します**FALSE**です。  
  
##  <a name="loadfromresource"></a>  CDHtmlDialog::LoadFromResource  
 WebBrowser コントロール DHTML ダイアログ ボックスに、指定されたリソースを読み込みます。  
  
```  
BOOL LoadFromResource(LPCTSTR lpszResource);  
BOOL LoadFromResource(UINT nRes);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszResource`  
 読み込むリソースの名前を含む文字列へのポインター。  
  
 `nRes`  
 読み込むリソースの ID。  
  
### <a name="return-value"></a>戻り値  
 **TRUE**成功した場合は**FALSE**です。  
  
##  <a name="m_busehtmltitle"></a>  CDHtmlDialog::m_bUseHtmlTitle  
 HTML ドキュメントのタイトルをダイアログのキャプションとして使用するかどうかを示します。  
  
```  
BOOL m_bUseHtmlTitle;  
```  
  
### <a name="remarks"></a>コメント  
 場合**m**_ **bUseHtmlTitle**は**true**ダイアログのタイトルは、HTML ドキュメントのタイトルと同じです。 それ以外の場合に、ダイアログ リソースにキャプションを使用します。  
  
##  <a name="m_nhtmlresid"></a>  CDHtmlDialog::m_nHtmlResID  
 リソースを表示するリソースを HTML の ID です。  
  
```  
UINT m_nHtmlResID;  
```  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCHtmlHttp#5](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_5.cpp)]  
  
##  <a name="m_pbrowserapp"></a>  CDHtmlDialog::m_pBrowserApp  
 Web ブラウザー アプリケーションへのポインター。  
  
```  
CComPtr <IWebBrowser2> m_pBrowserApp;  
```  
  
##  <a name="m_sphtmldoc"></a>  CDHtmlDialog::m_spHtmlDoc  
 HTML ドキュメントへのポインター。  
  
```  
CComPtr<IHTMLDocument2> m_spHtmlDoc;  
```  
  
##  <a name="m_strcurrenturl"></a>  CDHtmlDialog::m_strCurrentUrl  
 現在の URL です。  
  
```  
CString m_strCurrentUrl;  
```  
  
##  <a name="m_szhtmlresid"></a>  CDHtmlDialog::m_szHtmlResID  
 HTML リソース ID の文字列バージョン  
  
```  
LPTSTR m_szHtmlResID;  
```  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCHtmlHttp#6](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_6.cpp)]  
  
##  <a name="navigate"></a>  CDHtmlDialog::Navigate  
 指定された URL で識別されるリソースに移動`lpszURL`です。  
  
```  
void Navigate(
    LPCTSTR lpszURL,  
    DWORD dwFlags = 0,  
    LPCTSTR lpszTargetFrameName = NULL,  
    LPCTSTR lpszHeaders = NULL,  
    LPVOID lpvPostData = NULL,  
    DWORD dwPostDataLen = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszURL`  
 対象とする URL を含む文字列へのポインター。  
  
 `dwFlags`  
 履歴リストにリソースを追加するかどうか、キャッシュから書き込み/読み取りキャッシュをするかどうかと、新しいウィンドウで、リソースを表示するかどうかを指定する変数のフラグです。 変数がで定義される値の組み合わせを指定できます、[変数には](https://msdn.microsoft.com/library/aa768360.aspx)列挙します。  
  
 `lpszTargetFrameName`  
 リソースを表示するフレームの名前を表す文字列へのポインター。  
  
 `lpszHeaders`  
 サーバーに送信する HTTP ヘッダーを指定する値へのポインター。 これらのヘッダーは、既定の Internet Explorer のヘッダーに追加されます。 ヘッダーは、サーバー、サーバー、またはそのステータス コードに渡されるデータの種類の必要な操作として、このような情報を指定できます。 このパラメーターには、URL は HTTP URL ではない場合は無視されます。  
  
 `lpvPostData`  
 HTTP POST のトランザクションに送信するデータへのポインター。 たとえば、HTML フォームによって収集されたデータを送信する POST トランザクションが使用します。 このパラメーターに任意の投稿データが指定されていない場合**移動**HTTP GET トランザクションを発行します。 このパラメーターには、URL は HTTP URL ではない場合は無視されます。  
  
 `dwPostDataLen`  
 HTTP POST のトランザクションに送信するデータ。 たとえば、HTML フォームによって収集されたデータを送信する POST トランザクションが使用します。 このパラメーターに任意の投稿データが指定されていない場合**移動**HTTP GET トランザクションを発行します。 URL が HTTP の URL ではない場合、このパラメーターは無視されます。  
  
##  <a name="onbeforenavigate"></a>  CDHtmlDialog::OnBeforeNavigate  
 ナビゲーションが発生する前に、イベントが発生するために、フレームワークによって呼び出されます。  
  
```  
virtual void OnBeforeNavigate(
    LPDISPATCH pDisp,  
    LPCTSTR szUrl);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDisp`  
 `IDispatch` オブジェクトへのポインター。  
  
 `szUrl`  
 移動先の URL を含む文字列へのポインター。  
  
##  <a name="ondocumentcomplete"></a>  CDHtmlDialog::OnDocumentComplete  
 ドキュメントを達成したとき、アプリケーションに通知するためにフレームワークによって呼び出される、`READYSTATE_COMPLETE`状態です。  
  
```  
virtual void OnDocumentComplete(
    LPDISPATCH pDisp,  
    LPCTSTR szUrl);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDisp`  
 `IDispatch` オブジェクトへのポインター。  
  
 `szUrl`  
 移動先の URL を含む文字列へのポインター。  
  
##  <a name="ondocwindowactivate"></a>  CDHtmlDialog::OnDocWindowActivate  
 ドキュメント ウィンドウがアクティブ化または非アクティブ化されたときに、フレームワークによって呼び出されます。  
  
```  
STDMETHOD(OnDocWindowActivate)(BOOL fActivate);
```  
  
### <a name="parameters"></a>パラメーター  
 `fActivate`  
 参照してください`fActivate`で[IDocHostUIHandler::OnDocWindowActivate](https://msdn.microsoft.com/library/aa753261.aspx) Windows SDK にします。  
  
### <a name="return-value"></a>戻り値  
 返します**E_NOTIMPL**です。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数が CDHtmlDialog の実装の[IDocHostUIHandler::OnDocWindowActivate](https://msdn.microsoft.com/library/aa753261.aspx)Windows SDK で説明されている。  
  
##  <a name="onframewindowactivate"></a>  CDHtmlDialog::OnFrameWindowActivate  
 フレーム ウィンドウがアクティブ化または非アクティブ化されたときに、フレームワークによって呼び出されます。  
  
```  
STDMETHOD(OnFrameWindowActivate)(BOOL fActivate);
```  
  
### <a name="parameters"></a>パラメーター  
 `fActivate`  
 参照してください`fActivate`で[IDocHostUIHandler::OnFrameWindowActivate](https://msdn.microsoft.com/library/aa753262.aspx) Windows SDK にします。  
  
### <a name="return-value"></a>戻り値  
 返します**E_NOTIMPL**です。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数が CDHtmlDialog の実装の[IDocHostUIHandler::OnFrameWindowActivate](https://msdn.microsoft.com/library/aa753262.aspx)Windows SDK で説明されている。  
  
##  <a name="oninitdialog"></a>  CDHtmlDialog::OnInitDialog  
 応答と呼ばれる、 **WM_INITDIALOG**メッセージ。  
  
```  
virtual BOOL OnInitDialog();
```  
  
### <a name="return-value"></a>戻り値  
 既定の実装を返します**TRUE**です。  
  
### <a name="remarks"></a>コメント  
 中に、ダイアログ ボックスにこのメッセージは送信、**作成**、 `CreateIndirect`、または`DoModal`呼び出しで、ダイアログ ボックスを表示する直前に発生します。  
  
 ダイアログ ボックスが初期化されたときに、特別な処理を実行する必要がある場合は、このメンバー関数をオーバーライドします。 オーバーライドされたバージョンでは、基底クラスを呼び出して最初`OnInitDialog`が、その戻り値を無視します。 通常戻ります**TRUE**オーバーライドされたメンバー関数から。  
  
 Windows の呼び出し、`OnInitDialog`メッセージ マップを通じてようにする必要はありませんメッセージ マップ エントリのこのメンバー関数ではなく、すべての Microsoft Foundation Class ライブラリ ダイアログ ボックスに共通の標準のグローバル ダイアログ ボックス プロシージャで機能します。  
  
##  <a name="onnavigatecomplete"></a>  CDHtmlDialog::OnNavigateComplete  
 指定された URL への移動が完了した後に、フレームワークによって呼び出されます。  
  
```  
virtual void OnNavigateComplete(
    LPDISPATCH pDisp,  
    LPCTSTR szUrl);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDisp`  
 `IDispatch` オブジェクトへのポインター。  
  
 `szUrl`  
 移動先の URL を含む文字列へのポインター。  
  
##  <a name="resizeborder"></a>  CDHtmlDialog::ResizeBorder  
 境界領域のサイズを変更する必要があるオブジェクトに警告します。  
  
```  
STDMETHOD(ResizeBorder)(
    LPCRECT prcBorder,  
    IOleInPlaceUIWindow* pUIWindow,  
    BOOL fRameWindow);
```  
  
### <a name="parameters"></a>パラメーター  
 `prcBorder`  
 参照してください`prcBorder`で[IDocHostUIHandler::ResizeBorder](https://msdn.microsoft.com/library/aa753263.aspx) Windows SDK にします。  
  
 `pUIWindow`  
 参照してください`pUIWindow`で**IDocHostUIHandler::ResizeBorder** Windows SDK にします。  
  
 `fFrameWindow`  
 参照してください*fFrameWindow*で**IDocHostUIHandler::ResizeBorder** Windows SDK に含まれています。  
  
### <a name="return-value"></a>戻り値  
 返します**E_NOTIMPL**です。  
  
##  <a name="setcontrolproperty"></a>  CDHtmlDialog::SetControlProperty  
 新しい値には、ActiveX コントロールのプロパティを設定します。  
  
```  
void SetControlProperty(
    LPCTSTR szElementId,  
    DISPID dispid,  
    VARIANT* pVar);

 
void SetControlProperty(
    IDispatch* pdispControl,  
    DISPID dispid,  
    VARIANT* pVar);

 
void SetControlProperty(
    LPCTSTR szElementId,  
    LPCTSTR szPropName,  
    VARIANT* pVar);
```  
  
### <a name="parameters"></a>パラメーター  
 `szElementId`  
 ActiveX コントロールの HTML ID です。  
  
 `dispid`  
 設定するプロパティのディスパッチ ID。  
  
 *pVar*  
 ポインター、**バリアント**新しいプロパティ値を格納します。  
  
 `pdispControl`  
 ActiveX コントロールへのポインター`IDispatch`インターフェイスです。  
  
 `szPropName`  
 設定するプロパティの名前を含む文字列です。  
  
##  <a name="setelementhtml"></a>  CDHtmlDialog::SetElementHtml  
 セット、 **innerHTML** HTML 要素のプロパティです。  
  
```  
void SetElementHtml(
    LPCTSTR szElementId,  
    BSTR bstrText);

 
void SetElementHtml(
    IUnknown* punkElem,  
    BSTR bstrText);
```  
  
### <a name="parameters"></a>パラメーター  
 `szElementId`  
 HTML 要素の ID。  
  
 `bstrText`  
 新しい値、 **innerHTML**プロパティです。  
  
 `punkElem`  
 **IUnknown**の HTML 要素を指すポインターです。  
  
##  <a name="setelementproperty"></a>  CDHtmlDialog::SetElementProperty  
 HTML 要素のプロパティを設定します。  
  
```  
void SetElementProperty(
    LPCTSTR szElementId,  
    DISPID dispid,  
    VARIANT* pVar);
```  
  
### <a name="parameters"></a>パラメーター  
 `szElementId`  
 HTML 要素の ID。  
  
 `dispid`  
 設定するプロパティのディスパッチ ID。  
  
 *pVar*  
 プロパティの新しい値。  
  
##  <a name="setelementtext"></a>  CDHtmlDialog::SetElementText  
 セット、 **innerText** HTML 要素のプロパティです。  
  
```  
void SetElementText(
    LPCTSTR szElementId,  
    BSTR bstrText);

 
void SetElementText(
    IUnknown* punkElem,  
    BSTR bstrText);
```  
  
### <a name="parameters"></a>パラメーター  
 `szElementId`  
 HTML 要素の ID。  
  
 `bstrText`  
 新しい値、 **innerText**プロパティです。  
  
 `punkElem`  
 **IUnknown**の HTML 要素を指すポインターです。  
  
##  <a name="setexternaldispatch"></a>  CDHtmlDialog::SetExternalDispatch  
 ホストの設定`IDispatch`インターフェイスです。  
  
```  
void SetExternalDispatch(IDispatch* pdispExternal);
```  
  
### <a name="parameters"></a>パラメーター  
 *pdispExternal*  
 新しい`IDispatch`インターフェイスです。  
  
##  <a name="sethostflags"></a>  CDHtmlDialog::SetHostFlags  
 ホスト UI フラグを設定します。  
  
```  
void SetHostFlags(DWORD dwFlags);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwFlags`  
 使用可能な値は、次を参照してください。 [DOCHOSTUIFLAG](https://msdn.microsoft.com/library/aa753277.aspx) Windows SDK に含まれています。  
  
##  <a name="showcontextmenu"></a>  CDHtmlDialog::ShowContextMenu  
 コンテキスト メニューが表示されるときに呼び出されます。  
  
```  
STDMETHOD(ShowContextMenu)(
    DWORD dwID,  
    POINT* ppt,  
    IUnknown* pcmdtReserved,  
    IDispatch* pdispReserved);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwID`  
 参照してください`dwID`で[IDocHostUIHandler::ShowContextMenu](https://msdn.microsoft.com/library/aa753264.aspx) Windows SDK にします。  
  
 `ppt`  
 参照してください`ppt`で**IDocHostUIHandler::ShowContextMenu** Windows SDK にします。  
  
 `pcmdtReserved`  
 参照してください`pcmdtReserved`で**IDocHostUIHandler::ShowContextMenu** Windows SDK にします。  
  
 `pdispReserved`  
 参照してください`pdispReserved`で**IDocHostUIHandler::ShowContextMenu** Windows SDK にします。  
  
### <a name="return-value"></a>戻り値  
 返します**S_FALSE**です。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数が CDHtmlDialog の実装の[IDocHostUIHandler::ShowContextMenu](https://msdn.microsoft.com/library/aa753264.aspx)Windows SDK で説明されている。  
  
##  <a name="showui"></a>  CDHtmlDialog::ShowUI  
 ホストの UI を示しています。  
  
```  
STDMETHOD(ShowUI)(
    DWORD dwID,  
    IOleInPlaceActiveObject* pActiveObject,  
    IOleCommandTarget* pCommandTarget,  
    IOleInPlaceFrame* pFrame,  
    IOleInPlaceUIWindow* pDoc);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwID`  
 参照してください`dwID`で[IDocHostUIHandler::ShowUI](https://msdn.microsoft.com/library/aa753265.aspx) Windows SDK にします。  
  
 `pActiveObject`  
 参照してください*d pActiveObject*で**IDocHostUIHandler::ShowUI** Windows SDK に含まれています。  
  
 `pCommandTarget`  
 参照してください`pCommandTarget`で**IDocHostUIHandler::ShowUI** Windows SDK にします。  
  
 `pFrame`  
 参照してください`pFrame`で**IDocHostUIHandler::ShowUI** Windows SDK にします。  
  
 `pDoc`  
 参照してください`pDoc`で**IDocHostUIHandler::ShowUI** Windows SDK にします。  
  
### <a name="return-value"></a>戻り値  
 返します**S_FALSE**です。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数が CDHtmlDialog の実装の[IDocHostUIHandler::ShowUI](https://msdn.microsoft.com/library/aa753265.aspx)Windows SDK で説明されている。  
  
##  <a name="translateaccelerator"></a>  CDHtmlDialog::TranslateAccelerator  
 メニュー アクセス キーのメッセージを処理するには、呼び出されます。  
  
```  
STDMETHOD(TranslateAccelerator)(
    LPMSG lpMsg,  
    const GUID* pguidCmdGroup,  
    DWORD nCmdID);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpMsg`  
 参照してください`lpMsg`で[IDocHostUIHandler::TranslateAccelerator](https://msdn.microsoft.com/library/aa753266.aspx) Windows SDK にします。  
  
 `pguidCmdGroup`  
 参照してください`pguidCmdGroup`で**IDocHostUIHandler::TranslateAccelerator** Windows SDK にします。  
  
 `nCmdID`  
 参照してください`nCmdID`で**IDocHostUIHandler::TranslateAccelerator** Windows SDK にします。  
  
### <a name="return-value"></a>戻り値  
 返します**S_FALSE**です。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数が CDHtmlDialog の実装の[IDocHostUIHandler::TranslateAccelerator](https://msdn.microsoft.com/library/aa753266.aspx)Windows SDK で説明されている。  
  
##  <a name="translateurl"></a>  CDHtmlDialog::TranslateUrl  
 読み込む URL を変更するには、呼び出されます。  
  
```  
STDMETHOD(TranslateUrl)(
    DWORD dwTranslate,  
    OLECHAR* pchURLIn,  
    OLECHAR** ppchURLOut);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwTranslate`  
 参照してください`dwTranslate`で[IDocHostUIHandler::TranslateUrl](https://msdn.microsoft.com/library/aa753267.aspx) Windows SDK にします。  
  
 `pchURLIn`  
 参照してください`pchURLIn`で**IDocHostUIHandler::TranslateUrl** Windows SDK にします。  
  
 `ppchURLOut`  
 参照してください`ppchURLOut`で**IDocHostUIHandler::TranslateUrl** Windows SDK にします。  
  
### <a name="return-value"></a>戻り値  
 返します**S_FALSE**です。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数が CDHtmlDialog の実装の[IDocHostUIHandler::TranslateUrl](https://msdn.microsoft.com/library/aa753267.aspx)Windows SDK で説明されている。  
  
##  <a name="updateui"></a>  CDHtmlDialog::UpdateUI  
 コマンドの状態が変更されたホストに通知と呼ばれます。  
  
```  
STDMETHOD(UpdateUI)(void);
```  
  
### <a name="return-value"></a>戻り値  
 返します**E_NOTIMPL**です。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数が CDHtmlDialog の実装の[IDocHostUIHandler::UpdateUI](https://msdn.microsoft.com/library/aa753268.aspx)Windows SDK で説明されている。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル DHtmlExplore](../../visual-cpp-samples.md)   
 [DDX_DHtml ヘルパー マクロ](#ddx_dhtml_helper_macros)   
 [階層図](../../mfc/hierarchy-chart.md)


