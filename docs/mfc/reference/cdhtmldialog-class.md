---
title: CDHtmlDialog クラス
ms.date: 03/27/2019
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
ms.openlocfilehash: bda980c26f9791e1d4f03026f7e118e69a4ab881
ms.sourcegitcommit: 309dc532f13242854b47759cef846de59bb807f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2019
ms.locfileid: "58565806"
---
# <a name="cdhtmldialog-class"></a>CDHtmlDialog クラス

HTML を使用して、ダイアログ ボックスを作成するために使用ダイアログ リソースをユーザー インターフェイスを実装するのではなく。

## <a name="syntax"></a>構文

```
class CDHtmlDialog : public CDialog, public CDHtmlEventSink
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CDHtmlDialog::CDHtmlDialog](#cdhtmldialog)|CDHtmlDialog オブジェクトを構築します。|
|[CDHtmlDialog::~CDHtmlDialog](#_dtorcdhtmldialog)|CDHtmlDialog オブジェクトを破棄します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CDHtmlDialog::CanAccessExternal](#canaccessexternal)|オーバーライド可能なコントロールのサイトの外部のディスパッチを読み込むページ上のスクリプト オブジェクトがアクセスできるかどうかを表示するアクセス チェックとして呼び出されます。 ディスパッチの安全なスクリプトまたは現在のゾーンのいずれかでスクリプトを実行しても安全でないオブジェクトは、ことを確認することを確認します。|
|[CDHtmlDialog::CreateControlSite](#createcontrolsite)|Overridable は、ダイアログの WebBrowser コントロールをホストするコントロール サイトのインスタンスを作成するために使用します。|
|[CDHtmlDialog::DDX_DHtml_AxControl](#ddx_dhtml_axcontrol)|メンバー変数と、HTML ページ上の ActiveX コントロールのプロパティ値の間でデータを交換します。|
|[CDHtmlDialog::DDX_DHtml_CheckBox](#ddx_dhtml_checkbox)|メンバー変数と、HTML ページ上のチェック ボックス間でデータを交換します。|
|[CDHtmlDialog::DDX_DHtml_ElementText](#ddx_dhtml_elementtext)|メンバー変数と、HTML ページの任意の HTML 要素プロパティ間でデータを交換します。|
|[CDHtmlDialog::DDX_DHtml_Radio](#ddx_dhtml_radio)|メンバー変数と HTML ページのオプション ボタンの間でデータを交換します。|
|[CDHtmlDialog::DDX_DHtml_SelectIndex](#ddx_dhtml_selectindex)|取得または HTML ページのリスト ボックスのインデックスを設定します。|
|[CDHtmlDialog::DDX_DHtml_SelectString](#ddx_dhtml_selectstring)|取得または HTML ページの (現在のインデックスに基づく)、リスト ボックス項目の表示テキストを設定します。|
|[CDHtmlDialog::DDX_DHtml_SelectValue](#ddx_dhtml_selectvalue)|取得または HTML ページの (現在のインデックスに基づく)、リスト ボックス項目の値を設定します。|
|[CDHtmlDialog::DestroyModeless](#destroymodeless)|モードレス ダイアログ ボックスを破棄します。|
|[CDHtmlDialog::EnableModeless](#enablemodeless)|モードレス ダイアログ ボックスを有効にします。|
|[CDHtmlDialog::FilterDataObject](#filterdataobject)|ホストされているブラウザーによって作成されたクリップボード データ オブジェクトをフィルター処理するダイアログを使用できます。|
|[CDHtmlDialog::GetControlDispatch](#getcontroldispatch)|取得、 `IDispatch` HTML ドキュメントに埋め込まれている ActiveX コントロールのインターフェイス。|
|[CDHtmlDialog::GetControlProperty](#getcontrolproperty)|指定した ActiveX コントロールの要求のプロパティを取得します。|
|[CDHtmlDialog::GetCurrentUrl](#getcurrenturl)|現在のドキュメントに関連付けられている Uniform Resource Locator (URL) を取得します。|
|[CDHtmlDialog::GetDHtmlDocument](#getdhtmldocument)|現在読み込まれている HTML ドキュメントの IHTMLDocument2 インターフェイスを取得します。|
|[CDHtmlDialog::GetDropTarget](#getdroptarget)|別の方法を指定するダイアログを許可する、ドロップ先として使用されているときに、コンテナー内の WebBrowser コントロールによって呼び出されます[IDropTarget](/windows/desktop/api/oleidl/nn-oleidl-idroptarget)します。|
|[CDHtmlDialog::GetElement](#getelement)|HTML 要素のインターフェイスを取得します。|
|[CDHtmlDialog::GetElementHtml](#getelementhtml)|取得、 `innerHTML` HTML 要素のプロパティ。|
|[CDHtmlDialog::GetElementInterface](#getelementinterface)|HTML 要素から要求されたインターフェイス ポインターを取得します。|
|[CDHtmlDialog::GetElementProperty](#getelementproperty)|HTML 要素のプロパティの値を取得します。|
|[CDHtmlDialog::GetElementText](#getelementtext)|取得、 `innerText` HTML 要素のプロパティ。|
|[CDHtmlDialog::GetEvent](#getevent)|取得、`IHTMLEventObj`現在のイベント オブジェクトへのポインター。|
|[CDHtmlDialog::GetExternal](#getexternal)|ホストの取得`IDispatch`インターフェイス。|
|[CDHtmlDialog::GetHostInfo](#gethostinfo)|ホストの UI 機能を取得します。|
|[CDHtmlDialog::GetOptionKeyPath](#getoptionkeypath)|ユーザー設定が格納されているレジストリ キーを取得します。|
|[CDHtmlDialog::HideUI](#hideui)|ホストの UI を非表示にします。|
|[CDHtmlDialog::IsExternalDispatchSafe](#isexternaldispatchsafe)|示すかどうか、ホストの`IDispatch`インターフェイスはスクリプトを実行します。|
|[CDHtmlDialog::LoadFromResource](#loadfromresource)|WebBrowser コントロールには、指定したリソースを読み込みます。|
|[CDHtmlDialog::Navigate](#navigate)|指定した URL に移動します。|
|[CDHtmlDialog::OnBeforeNavigate](#onbeforenavigate)|ナビゲーション イベントが発生する前に、フレームワークによって呼び出されます。|
|[CDHtmlDialog::OnDocumentComplete](#ondocumentcomplete)|ドキュメントが READYSTATE_COMPLETE 状態に達したときにアプリケーションに通知するためにフレームワークによって呼び出されます。|
|[CDHtmlDialog::OnDocWindowActivate](#ondocwindowactivate)|ドキュメント ウィンドウがアクティブ化または非アクティブ化されたときに、フレームワークによって呼び出されます。|
|[CDHtmlDialog::OnFrameWindowActivate](#onframewindowactivate)|フレーム ウィンドウをアクティブ化または非アクティブ化されたときに、フレームワークによって呼び出されます。|
|[CDHtmlDialog::OnInitDialog](#oninitdialog)|WM_INITDIALOG メッセージへの応答で呼び出されます。|
|[CDHtmlDialog::OnNavigateComplete](#onnavigatecomplete)|ナビゲーション イベントが完了した後に、フレームワークによって呼び出されます。|
|[CDHtmlDialog::ResizeBorder](#resizeborder)|境界領域のサイズを変更する必要があるオブジェクトに警告します。|
|[CDHtmlDialog::SetControlProperty](#setcontrolproperty)|ActiveX コントロールのプロパティを新しい値に設定します。|
|[CDHtmlDialog::SetElementHtml](#setelementhtml)|セット、 `innerHTML` HTML 要素のプロパティ。|
|[CDHtmlDialog::SetElementProperty](#setelementproperty)|HTML 要素のプロパティを設定します。|
|[CDHtmlDialog::SetElementText](#setelementtext)|セット、 `innerText` HTML 要素のプロパティ。|
|[CDHtmlDialog::SetExternalDispatch](#setexternaldispatch)|ホストの設定`IDispatch`インターフェイス。|
|[CDHtmlDialog::SetHostFlags](#sethostflags)|ホストの UI のフラグを設定します。|
|[CDHtmlDialog::ShowContextMenu](#showcontextmenu)|コンテキスト メニューが表示されるときに呼び出されます。|
|[CDHtmlDialog::ShowUI](#showui)|ホストの UI を示しています。|
|[CDHtmlDialog::TranslateAccelerator](#translateaccelerator)|メニューのアクセラレータ キー メッセージを処理するには、呼び出されます。|
|[CDHtmlDialog::TranslateUrl](#translateurl)|読み込まれる URL を変更するには、呼び出されます。|
|[CDHtmlDialog::UpdateUI](#updateui)|コマンドの状態が変更されたホストに通知と呼ばれます。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CDHtmlDialog::m_bUseHtmlTitle](#m_busehtmltitle)|ダイアログのキャプションとして HTML ドキュメントのタイトルを使用するかどうかを示します。|
|[CDHtmlDialog::m_nHtmlResID](#m_nhtmlresid)|表示するリソース ID の HTML リソース。|
|[CDHtmlDialog::m_pBrowserApp](#m_pbrowserapp)|Web ブラウザー アプリケーションへのポインター。|
|[CDHtmlDialog::m_spHtmlDoc](#m_sphtmldoc)|HTML ドキュメントへのポインター。|
|[CDHtmlDialog::m_strCurrentUrl](#m_strcurrenturl)|現在の URL。|
|[CDHtmlDialog::m_szHtmlResID](#m_szhtmlresid)|HTML のリソース ID の文字列バージョン|

## <a name="remarks"></a>Remarks

`CDHtmlDialog` いずれか、HTML リソースから表示する HTML または URL を読み込むことができます。

`CDHtmlDialog` できますも行うデータとを交換し HTML コントロール ボタンのクリックしてなど、HTML のコントロールからイベントを処理します。

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

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdhtml.h

##  <a name="ddx_dhtml_helper_macros"></a>  DDX_DHtml Helper マクロ

DDX_DHtml helper マクロでは、一般的に使用される HTML ページ上のコントロールのプロパティに簡単にアクセスできるようにします。

### <a name="data-exchange-macros"></a>データ エクス チェンジに関するマクロ

|||
|-|-|
|[DDX_DHtml_ElementValue](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_elementvalue)|設定または選択したコントロールの Value プロパティを取得します。|
|[DDX_DHtml_ElementInnerText](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_elementinnertext)|設定または現在の要素の開始と終了タグの間のテキストを取得します。|
|[DDX_DHtml_ElementInnerHtml](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_elementinnerhtml)|設定または現在の要素の開始と終了タグの間での HTML を取得します。|
|[DDX_DHtml_Anchor_Href](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_anchor_href)|設定または変換先の URL またはアンカー ポイントを取得します。|
|[DDX_DHtml_Anchor_Target](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_anchor_target)|設定またはターゲット ウィンドウまたはフレームを取得します。|
|[DDX_DHtml_Img_Src](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_img_src)|設定またはイメージまたはドキュメント内のビデオ クリップの名前を取得します。|
|[DDX_DHtml_Frame_Src](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_frame_src)|設定または関連付けられているフレームの URL を取得します。|
|[DDX_DHtml_IFrame_Src](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_iframe_src)|設定または関連付けられているフレームの URL を取得します。|

##  <a name="canaccessexternal"></a>  CDHtmlDialog::CanAccessExternal

オーバーライド可能なコントロールのサイトの外部のディスパッチを読み込むページ上のスクリプト オブジェクトがアクセスできるかどうかを表示するアクセス チェックとして呼び出されます。 ディスパッチの安全なスクリプトまたは現在のゾーンのいずれかでスクリプトを実行しても安全でないオブジェクトは、ことを確認することを確認します。

```
virtual BOOL CanAccessExternal();
```

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

##  <a name="cdhtmldialog"></a>  CDHtmlDialog::CDHtmlDialog

リソースに基づく動的 HTML ダイアログを構築します。

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

*lpszTemplateName*<br/>
ダイアログ ボックスのテンプレート リソースの名前を表す null で終わる文字列。

*szHtmlResID*<br/>
HTML のリソースの名前を表す null で終わる文字列。

*pParentWnd*<br/>
親またはオーナー ウィンドウ オブジェクトへのポインター (型の[CWnd](../../mfc/reference/cwnd-class.md)) ダイアログ オブジェクトが属しています。 NULL の場合、ダイアログ オブジェクトの親ウィンドウは、アプリケーションのメイン ウィンドウに設定されます。

*nIDTemplate*<br/>
ダイアログ ボックスのテンプレート リソースの ID 番号が含まれています。

*nHtmlResID*<br/>
HTML リソースの ID 番号が含まれています。

### <a name="remarks"></a>Remarks

コンス トラクターの 2 番目の形式は、テンプレート名を使用して、ダイアログ リソースへのアクセスを提供します。 コンス トラクターの 3 番目のフォームは、リソースのテンプレートの ID を使用して、ダイアログ リソースへのアクセスを提供します。 通常、ID が始まり、 **idd _** プレフィックス。

##  <a name="_dtorcdhtmldialog"></a>  CDHtmlDialog::~CDHtmlDialog

CDHtmlDialog オブジェクトを破棄します。

```
virtual ~CDHtmlDialog();
```

### <a name="remarks"></a>Remarks

[に](../../mfc/reference/cwnd-class.md#destroywindow)メンバー関数は、によって作成されるモードレス ダイアログ ボックスを破棄するために使用する必要があります[CDialog::Create](../../mfc/reference/cdialog-class.md#create)します。

##  <a name="createcontrolsite"></a>  CDHtmlDialog::CreateControlSite

Overridable は、ダイアログの WebBrowser コントロールをホストするコントロール サイトのインスタンスを作成するために使用します。

```
virtual BOOL CreateControlSite(
    COleControlContainer* pContainer,
    COleControlSite** ppSite,
    UINT /* nID */,
    REFCLSID /* clsid */);
```

### <a name="parameters"></a>パラメーター

*pContainer*<br/>
ポインター、 [COleControlContainer](../../mfc/reference/colecontrolcontainer-class.md)オブジェクト

*ppSite*<br/>
ポインターへのポインターを[COleControlSite](../../mfc/reference/colecontrolsite-class.md)します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

コントロール サイト クラスのインスタンスを返すには、このメンバー関数をオーバーライドすることができます。

##  <a name="ddx_dhtml_axcontrol"></a>  CDHtmlDialog::DDX_DHtml_AxControl

メンバー変数と、HTML ページ上の ActiveX コントロールのプロパティ値の間でデータを交換します。

```
void DDX_DHtml_AxControl(
    CDataExchange* pDX,
    LPCTSTR szId,
    DISPID dispId,
    VARIANT& var);

void DDX_DHtml_AxControl(
    CDataExchange* pDX,
    LPCTSTR szId,
    LPCTSTR szPropName,
    VARIANT& var);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
ポインターを[CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクト。

*szId*<br/>
ActiveX コントロールの HTML ソース内のオブジェクト タグの ID パラメーターの値。

*dispId*<br/>
データを交換するプロパティのディスパッチ ID。

*szPropName*<br/>
プロパティの名前。

*var*<br/>
バリアント型のデータ メンバー、 [COleVariant](../../mfc/reference/colevariant-class.md)、または[CComVariant](../../atl/reference/ccomvariant-class.md)、ActiveX コントロールのプロパティと交換する値を保持しています。

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

*pDX*<br/>
ポインターを[CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクト。

*szId*<br/>
HTML コントロールの ID パラメーターに指定した値。

*value*<br/>
交換する値。

### <a name="example"></a>例

[!code-cpp[NVC_MFCHtmlHttp#2](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_2.cpp)]

##  <a name="ddx_dhtml_elementtext"></a>  CDHtmlDialog::DDX_DHtml_ElementText

メンバー変数と、HTML ページの任意の HTML 要素プロパティ間でデータを交換します。

```
void DDX_DHtml_ElementText(
    CDataExchange* pDX,
    LPCTSTR szId,
    DISPID dispId,
    CString& value);

void DDX_DHtml_ElementText(
    CDataExchange* pDX,
    LPCTSTR szId,
    DISPID dispId,
    short& value);

void DDX_DHtml_ElementText(
    CDataExchange* pDX,
    LPCTSTR szId,
    DISPID dispId,
    int& value);

void DDX_DHtml_ElementText(
    CDataExchange* pDX,
    LPCTSTR szId,
    DISPID dispId,
    long& value);

void DDX_DHtml_ElementText(
    CDataExchange* pDX,
    LPCTSTR szId,
    DISPID dispId,
    DWORD& value);

void DDX_DHtml_ElementText(
    CDataExchange* pDX,
    LPCTSTR szId,
    DISPID dispId,
    float& value);

void DDX_DHtml_ElementText(
    CDataExchange* pDX,
    LPCTSTR szId,
    DISPID dispId,
    double& value);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
ポインターを[CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクト。

*szId*<br/>
HTML コントロールの ID パラメーターに指定した値。

*dispId*<br/>
データを交換する HTML 要素のディスパッチ ID。

*value*<br/>
交換する値。

##  <a name="ddx_dhtml_radio"></a>  CDHtmlDialog::DDX_DHtml_Radio

メンバー変数と HTML ページのオプション ボタンの間でデータを交換します。

```
void DDX_DHtml_Radio(
    CDataExchange* pDX,
    LPCTSTR szId,
    long& value);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
ポインターを[CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクト。

*szId*<br/>
HTML コントロールの ID パラメーターに指定した値。

*value*<br/>
交換する値。

##  <a name="ddx_dhtml_selectindex"></a>  CDHtmlDialog::DDX_DHtml_SelectIndex

取得または HTML ページのリスト ボックスのインデックスを設定します。

```
void DDX_DHtml_SelectIndex(
    CDataExchange* pDX,
    LPCTSTR szId,
    long& value);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
ポインターを[CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクト。

*szId*<br/>
HTML コントロールの指定した値`id`パラメーター。

*value*<br/>
交換する値。

##  <a name="ddx_dhtml_selectstring"></a>  CDHtmlDialog::DDX_DHtml_SelectString

取得または HTML ページの (現在のインデックスに基づく)、リスト ボックス項目の表示テキストを設定します。

```
void DDX_DHtml_SelectString(
    CDataExchange* pDX,
    LPCTSTR szId,
    CString& value);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
ポインターを[CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクト。

*szId*<br/>
HTML コントロールの ID パラメーターに指定した値。

*value*<br/>
交換する値。

##  <a name="ddx_dhtml_selectvalue"></a>  CDHtmlDialog::DDX_DHtml_SelectValue

取得または HTML ページの (現在のインデックスに基づく)、リスト ボックス項目の値を設定します。

```
void DDX_DHtml_SelectValue(
    CDataExchange* pDX,
    LPCTSTR szId,
    CString& value);
```

### <a name="parameters"></a>パラメーター

*pDX*<br/>
ポインターを[CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクト。

*szId*<br/>
HTML コントロールの ID パラメーターに指定した値。

*value*<br/>
交換する値。

### <a name="example"></a>例

[!code-cpp[NVC_MFCHtmlHttp#3](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_3.cpp)]

##  <a name="destroymodeless"></a>  CDHtmlDialog::DestroyModeless

モードレス ダイアログ ボックスからのデタッチ、`CDHtmlDialog`オブジェクトおよびオブジェクトを破棄します。

```
void DestroyModeless();
```

##  <a name="enablemodeless"></a>  CDHtmlDialog::EnableModeless

モードレス ダイアログ ボックスを有効にします。

```
STDMETHOD(EnableModeless)(BOOL fEnable);
```

### <a name="parameters"></a>パラメーター

*fEnable*<br/>
参照してください*fEnable*で[IDocHostUIHandler::EnableModeless](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753253\(v=vs.85\)) Windows SDK に含まれています。

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

### <a name="remarks"></a>Remarks

このメンバー関数は CDHtmlDialog の実装の[IDocHostUIHandler::EnableModeless](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753253\(v=vs.85\))」の説明に従って、Windows SDK。

##  <a name="filterdataobject"></a>  CDHtmlDialog::FilterDataObject

ホストされているブラウザーによって作成されたクリップボード データ オブジェクトをフィルター処理するダイアログを使用できます。

```
STDMETHOD(FilterDataObject)(
    IDataObject* pDO,
    IDataObject** ppDORet);
```

### <a name="parameters"></a>パラメーター

*pDO*<br/>
参照してください*pDO*で[IDocHostUIHandler::FilterDataObject](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753254\(v=vs.85\)) Windows SDK に含まれています。

*ppDORet*<br/>
参照してください*ppDORet*で`IDocHostUIHandler::FilterDataObject`Windows SDK に含まれています。

### <a name="return-value"></a>戻り値

S_FALSE を返します。

### <a name="remarks"></a>Remarks

このメンバー関数は CDHtmlDialog の実装の[IDocHostUIHandler::FilterDataObject](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753254\(v=vs.85\))」の説明に従って、Windows SDK。

##  <a name="getcontroldispatch"></a>  CDHtmlDialog::GetControlDispatch

取得、 `IDispatch` ActiveX コントロールのインターフェイスによって返される HTML ドキュメントに埋め込まれている[GetDHtmlDocument](#getdhtmldocument)します。

```
HRESULT GetControlDispatch(
    LPCTSTR szId,
    IDispatch** ppdisp);
```

### <a name="parameters"></a>パラメーター

*szId*<br/>
ActiveX コントロールの HTML ID。

*ppdisp*<br/>
`IDispatch`インターフェイス コントロールの場合、Web ページが見つかりません。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

##  <a name="getcontrolproperty"></a>  CDHtmlDialog::GetControlProperty

指定した ActiveX コントロールの要求のプロパティを取得します。

```
VARIANT GetControlProperty(
    LPCTSTR szId,
    LPCTSTR szPropName);

VARIANT GetControlProperty(
    LPCTSTR szId,
    DISPID dispId);

VARIANT GetControlProperty(
    IDispatch* pdispControl,
    DISPID dispId);
```

### <a name="parameters"></a>パラメーター

*szId*<br/>
ActiveX コントロールの HTML ID。

*szPropName*<br/>
現在のユーザーの既定のロケールのプロパティの名前。

*pdispControl*<br/>
`IDispatch` ActiveX コントロールのポインター。

*dispId*<br/>
プロパティのディスパッチ ID。

### <a name="return-value"></a>戻り値

コントロールまたはプロパティを存在しない場合は、要求されたプロパティまたは空のバリアントを含むバリアント。

### <a name="remarks"></a>Remarks

オーバー ロードには、下部にある最も効率的なを上部にある最も非効率的なから一覧が表示されます。

##  <a name="getcurrenturl"></a>  CDHtmlDialog::GetCurrentUrl

現在のドキュメントに関連付けられている Uniform Resource Locator (URL) を取得します。

```
void GetCurrentUrl(CString& szUrl);
```

### <a name="parameters"></a>パラメーター

*szUrl*<br/>
A [CString](../../atl-mfc-shared/reference/cstringt-class.md)を取得する URL を含むオブジェクト。

##  <a name="getdhtmldocument"></a>  CDHtmlDialog::GetDHtmlDocument

取得、 [IHTMLDocument2](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752574\(v=vs.85\))現在読み込まれている HTML ドキュメントのインターフェイス。

```
HRESULT GetDHtmlDocument(IHTMLDocument2 **pphtmlDoc);
```

### <a name="parameters"></a>パラメーター

*\*\*pphtmlDoc* HTML ドキュメントへのポインターへのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT です。 成功した場合は、S_OK を返します。

##  <a name="getdroptarget"></a>  CDHtmlDialog::GetDropTarget

別の方法を指定するダイアログを許可する、ドロップ先として使用されているときに、コンテナー内の WebBrowser コントロールによって呼び出されます[IDropTarget](/windows/desktop/api/oleidl/nn-oleidl-idroptarget)します。

```
STDMETHOD(GetDropTarget)(
    IDropTarget* pDropTarget,
    IDropTarget** ppDropTarget);
```

### <a name="parameters"></a>パラメーター

*pDropTarget*<br/>
参照してください*pDropTarget*で[IDocHostUIHandler::GetDropTarget](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753255\(v=vs.85\)) Windows SDK に含まれています。

*ppDropTarget*<br/>
参照してください*ppDropTarget*で`IDocHostUIHandler::GetDropTarget`Windows SDK に含まれています。

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

### <a name="remarks"></a>Remarks

このメンバー関数は CDHtmlDialog の実装の[IDocHostUIHandler::GetDropTarget](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753255\(v=vs.85\))」の説明に従って、Windows SDK。

##  <a name="getelement"></a>  CDHtmlDialog::GetElement

指定された HTML 要素のインターフェイスを返します*szElementId*します。

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

*szElementId*<br/>
HTML 要素の ID。

*ppdisp*<br/>
`IDispatch`要求された要素または要素のコレクションへのポインター。

*pbCollection*<br/>
によって表されるオブジェクトであるかどうかを示すブール値*ppdisp*が 1 つの要素または要素のコレクション。

*pphtmlElement*<br/>
`IHTMLElement`要求された要素へのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

条件である可能性があります指定された ID を持つ 1 つ以上の要素を処理する必要がある場合は、最初のオーバー ロードを使用します。 返されるインターフェイス ポインターがコレクションまたは 1 つの項目にするかどうかを確認するのには、最後のパラメーターを使用できます。 照会するインターフェイス ポインターがコレクションにある場合、`IHTMLElementCollection`を使用してその`item`順序位置で要素を参照するプロパティ。

2 番目のオーバー ロードは、ページに同じ ID を持つ 1 つ以上の要素がある場合は失敗します。

##  <a name="getelementhtml"></a>  CDHtmlDialog::GetElementHtml

取得、`innerHTML`プロパティによって識別される HTML 要素の*szElementId*します。

```
BSTR GetElementHtml(LPCTSTR szElementId);
```

### <a name="parameters"></a>パラメーター

*szElementId*<br/>
HTML 要素の ID。

### <a name="return-value"></a>戻り値

`innerHTML`プロパティによって識別される HTML 要素の*szElementId*要素が見つからなかった場合は null です。

##  <a name="getelementinterface"></a>  CDHtmlDialog::GetElementInterface

によって識別される HTML 要素から要求されたインターフェイス ポインターを取得します。 *szElementId*します。

```
template <class Q> HRESULT GetElementInterface(
    LPCTSTR szElementId,
    Q** ppvObj);

HRESULT GetElementInterface(
    LPCTSTR szElementId,
    REFIID refiid,
    void** ppvObj);
```

### <a name="parameters"></a>パラメーター

*szElementId*<br/>
HTML 要素の ID。

*ppvObj*<br/>
アドレスのポインター、要素が見つからない場合に、要求されたインターフェイス ポインターが格納されると、クエリは成功します。

*refiid*<br/>
要求されたインターフェイスの ID (IID) のインターフェイスです。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="example"></a>例

[!code-cpp[NVC_MFCHtmlHttp#4](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_4.cpp)]

##  <a name="getelementproperty"></a>  CDHtmlDialog::GetElementProperty

によって識別されたプロパティの値を取得*dispId*で識別される HTML 要素から*szElementId*します。

```
VARIANT GetElementProperty(
    LPCTSTR szElementId,
    DISPID dispId);
```

### <a name="parameters"></a>パラメーター

*szElementId*<br/>
HTML 要素の ID。

*dispId*<br/>
プロパティのディスパッチ ID。

### <a name="return-value"></a>戻り値

プロパティまたはプロパティまたは要素を存在しない場合は空のバリアントの値。

##  <a name="getelementtext"></a>  CDHtmlDialog::GetElementText

取得、`innerText`プロパティによって識別される HTML 要素の*szElementId*します。

```
BSTR GetElementText(LPCTSTR szElementId);
```

### <a name="parameters"></a>パラメーター

*szElementId*<br/>
HTML 要素の ID。

### <a name="return-value"></a>戻り値

`innerText`プロパティによって識別される HTML 要素の*szElementId*プロパティまたは要素を存在しない場合は null です。

##  <a name="getevent"></a>  CDHtmlDialog::GetEvent

返します、`IHTMLEventObj`現在のイベント オブジェクトへのポインター。

```
HRESULT GetEvent(IHTMLEventObj** ppEventObj);
```

### <a name="parameters"></a>パラメーター

*ppEventObj*<br/>
入力されます。 ポインターのアドレス、`IHTMLEventObj`インターフェイス ポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

この関数は、DHTML のイベント ハンドラー内からのみ呼び出す必要があります。

##  <a name="getexternal"></a>  CDHtmlDialog::GetExternal

ホストの取得`IDispatch`インターフェイス。

```
STDMETHOD(GetExternal)(IDispatch** ppDispatch);
```

### <a name="parameters"></a>パラメーター

*ppDispatch*<br/>
参照してください*ppDispatch*で[IDocHostUIHandler::GetExternal](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753256\(v=vs.85\)) Windows SDK に含まれています。

### <a name="return-value"></a>戻り値

エラーの成功時または E_NOTIMPL に S_OK を返します。

### <a name="remarks"></a>Remarks

このメンバー関数は CDHtmlDialog の実装の[IDocHostUIHandler::GetExternal](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753256\(v=vs.85\))」の説明に従って、Windows SDK。

##  <a name="gethostinfo"></a>  CDHtmlDialog::GetHostInfo

ホストの UI 機能を取得します。

```
STDMETHOD(GetHostInfo)(DOCHOSTUIINFO* pInfo);
```

### <a name="parameters"></a>パラメーター

*pInfo*<br/>
参照してください*pInfo*で[IDocHostUIHandler::GetHostInfo](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753257\(v=vs.85\)) Windows SDK に含まれています。

### <a name="return-value"></a>戻り値

S_OK を返します。

### <a name="remarks"></a>Remarks

このメンバー関数は CDHtmlDialog の実装の[IDocHostUIHandler::GetHostInfo](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753257\(v=vs.85\))」の説明に従って、Windows SDK。

##  <a name="getoptionkeypath"></a>  CDHtmlDialog::GetOptionKeyPath

ユーザー設定が格納されているレジストリ キーを取得します。

```
STDMETHOD(GetOptionKeyPath)(
    LPOLESTR* pchKey,
    DWORD dw);
```

### <a name="parameters"></a>パラメーター

*pchKey*<br/>
参照してください*pchKey*で[IDocHostUIHandler::GetOptionKeyPath](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753258\(v=vs.85\)) Windows SDK に含まれています。

*dw*<br/>
参照してください*dw*で`IDocHostUIHandler::GetOptionKeyPath`Windows SDK にします。

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

### <a name="remarks"></a>Remarks

このメンバー関数は CDHtmlDialog の実装の[IDocHostUIHandler::GetOptionKeyPath](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753258\(v=vs.85\))」の説明に従って、Windows SDK。

##  <a name="hideui"></a>  CDHtmlDialog::HideUI

ホストの UI を非表示にします。

```
STDMETHOD(HideUI)(void);
```

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

### <a name="remarks"></a>Remarks

このメンバー関数は CDHtmlDialog の実装の[IDocHostUIHandler::HideUI](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753259\(v=vs.85\))」の説明に従って、Windows SDK。

##  <a name="isexternaldispatchsafe"></a>  CDHtmlDialog::IsExternalDispatchSafe

示すかどうか、ホストの`IDispatch`インターフェイスはスクリプトを実行します。

```
virtual BOOL IsExternalDispatchSafe();
```

### <a name="return-value"></a>戻り値

FALSE を返します。

##  <a name="loadfromresource"></a>  CDHtmlDialog::LoadFromResource

DHTML ダイアログで WebBrowser コントロールには、指定したリソースを読み込みます。

```
BOOL LoadFromResource(LPCTSTR lpszResource);
BOOL LoadFromResource(UINT nRes);
```

### <a name="parameters"></a>パラメーター

*lpszResource*<br/>
読み込むリソースの名前を含む文字列へのポインター。

*nRes*<br/>
読み込むリソースの ID。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、それ以外の場合は FALSE。

##  <a name="m_busehtmltitle"></a>  CDHtmlDialog::m_bUseHtmlTitle

ダイアログのキャプションとして HTML ドキュメントのタイトルを使用するかどうかを示します。

```
BOOL m_bUseHtmlTitle;
```

### <a name="remarks"></a>Remarks

場合**m**_ **bUseHtmlTitle**が true の場合、ダイアログのキャプションに HTML ドキュメントのタイトルを設定します。 ダイアログ リソースにキャプションを使用する場合は、します。

##  <a name="m_nhtmlresid"></a>  CDHtmlDialog::m_nHtmlResID

表示するリソース ID の HTML リソース。

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

現在の URL。

```
CString m_strCurrentUrl;
```

##  <a name="m_szhtmlresid"></a>  CDHtmlDialog::m_szHtmlResID

HTML のリソース ID の文字列バージョン

```
LPTSTR m_szHtmlResID;
```

### <a name="example"></a>例

[!code-cpp[NVC_MFCHtmlHttp#6](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_6.cpp)]

##  <a name="navigate"></a>  CDHtmlDialog::Navigate

指定された URL で識別されるリソースに移動する*lpszURL*します。

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

*lpszURL*<br/>
対象とする URL を含む文字列へのポインター。

*dwFlags*<br/>
履歴の一覧にリソースを追加するかどうか、キャッシュからキャッシュに読み取り/書き込みをするかどうかと、新しいウィンドウで、リソースを表示するかどうかを指定する変数のフラグ。 変数で定義される値の組み合わせとすることができます、[変数には](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768360\(v=vs.85\))列挙体。

*lpszTargetFrameName*<br/>
リソースを表示するフレームの名前を含む文字列へのポインター。

*lpszHeaders*<br/>
サーバーに送信する HTTP ヘッダーを指定する値へのポインター。 これらのヘッダーは、Internet Explorer の既定のヘッダーに追加されます。 ヘッダーは、サーバー、サーバー、または状態コードに渡されるデータの種類のために必要なアクションとして、このような情報を指定できます。 このパラメーターには、URL は HTTP URL ではない場合は無視されます。

*lpvPostData*<br/>
トランザクションの HTTP POST を送信するデータへのポインター。 たとえば、POST のトランザクションは、HTML フォームによって収集されたデータの送信に使用されます。 このパラメーターが任意の post データを指定しない場合`Navigate`HTTP GET のトランザクションを発行します。 このパラメーターには、URL は HTTP URL ではない場合は無視されます。

*dwPostDataLen*<br/>
トランザクションの HTTP POST を送信するデータ。 たとえば、POST のトランザクションは、HTML フォームによって収集されたデータの送信に使用されます。 このパラメーターが任意の post データを指定しない場合`Navigate`HTTP GET のトランザクションを発行します。 このパラメーターには、URL は HTTP URL ではない場合は無視されます。

##  <a name="onbeforenavigate"></a>  CDHtmlDialog::OnBeforeNavigate

ナビゲーションが発生する前にイベントを発生させるために、フレームワークによって呼び出されます。

```
virtual void OnBeforeNavigate(
    LPDISPATCH pDisp,
    LPCTSTR szUrl);
```

### <a name="parameters"></a>パラメーター

*pDisp*<br/>
`IDispatch` オブジェクトへのポインター。

*szUrl*<br/>
移動する URL を含む文字列へのポインター。

##  <a name="ondocumentcomplete"></a>  CDHtmlDialog::OnDocumentComplete

ドキュメントが READYSTATE_COMPLETE 状態を達成したとき、アプリケーションに通知するためにフレームワークによって呼び出されます。

```
virtual void OnDocumentComplete(
    LPDISPATCH pDisp,
    LPCTSTR szUrl);
```

### <a name="parameters"></a>パラメーター

*pDisp*<br/>
`IDispatch` オブジェクトへのポインター。

*szUrl*<br/>
移動した先の URL を含む文字列へのポインター。

##  <a name="ondocwindowactivate"></a>  CDHtmlDialog::OnDocWindowActivate

ドキュメント ウィンドウがアクティブ化または非アクティブ化されたときに、フレームワークによって呼び出されます。

```
STDMETHOD(OnDocWindowActivate)(BOOL fActivate);
```

### <a name="parameters"></a>パラメーター

*fActivate*<br/>
参照してください*fActivate*で[IDocHostUIHandler::OnDocWindowActivate](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753261\(v=vs.85\)) Windows SDK に含まれています。

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

### <a name="remarks"></a>Remarks

このメンバー関数は CDHtmlDialog の実装の[IDocHostUIHandler::OnDocWindowActivate](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753261\(v=vs.85\))」の説明に従って、Windows SDK。

##  <a name="onframewindowactivate"></a>  CDHtmlDialog::OnFrameWindowActivate

フレーム ウィンドウをアクティブ化または非アクティブ化されたときに、フレームワークによって呼び出されます。

```
STDMETHOD(OnFrameWindowActivate)(BOOL fActivate);
```

### <a name="parameters"></a>パラメーター

*fActivate*<br/>
参照してください*fActivate*で[IDocHostUIHandler::OnFrameWindowActivate](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753262\(v=vs.85\)) Windows SDK に含まれています。

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

### <a name="remarks"></a>Remarks

このメンバー関数は CDHtmlDialog の実装の[IDocHostUIHandler::OnFrameWindowActivate](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753262\(v=vs.85\))」の説明に従って、Windows SDK。

##  <a name="oninitdialog"></a>  CDHtmlDialog::OnInitDialog

WM_INITDIALOG メッセージへの応答で呼び出されます。

```
virtual BOOL OnInitDialog();
```

### <a name="return-value"></a>戻り値

既定の実装では、TRUE を返します。

### <a name="remarks"></a>Remarks

中に、ダイアログ ボックスにこのメッセージが送信される、 `Create`、 `CreateIndirect`、または`DoModal`呼び出しで、ダイアログ ボックスを表示する直前に発生します。

ダイアログ ボックスの初期化時に、特別な処理を実行する必要がある場合は、このメンバー関数をオーバーライドします。 オーバーライドされたバージョンでは、基本クラスを呼び出す最初`OnInitDialog`が、その戻り値を無視します。 通常は、オーバーライドされたメンバー関数から TRUE を返します。

Windows の呼び出し、`OnInitDialog`メッセージ マップを通じてため必要はありませんメッセージ マップ エントリのこのメンバー関数ではなく、標準のグローバル ダイアログ ボックス プロシージャに共通するすべての Microsoft Foundation Class ライブラリ ダイアログ ボックスを通過して機能します。

##  <a name="onnavigatecomplete"></a>  CDHtmlDialog::OnNavigateComplete

指定された URL への移動が完了した後に、フレームワークによって呼び出されます。

```
virtual void OnNavigateComplete(
    LPDISPATCH pDisp,
    LPCTSTR szUrl);
```

### <a name="parameters"></a>パラメーター

*pDisp*<br/>
`IDispatch` オブジェクトへのポインター。

*szUrl*<br/>
移動した先の URL を含む文字列へのポインター。

##  <a name="resizeborder"></a>  CDHtmlDialog::ResizeBorder

境界領域のサイズを変更する必要があるオブジェクトに警告します。

```
STDMETHOD(ResizeBorder)(
    LPCRECT prcBorder,
    IOleInPlaceUIWindow* pUIWindow,
    BOOL fRameWindow);
```

### <a name="parameters"></a>パラメーター

*prcBorder*<br/>
参照してください*prcBorder*で[IDocHostUIHandler::ResizeBorder](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753263\(v=vs.85\)) Windows SDK に含まれています。

*pUIWindow*<br/>
参照してください*pUIWindow*で`IDocHostUIHandler::ResizeBorder`Windows SDK に含まれています。

*fFrameWindow*<br/>
参照してください*fFrameWindow*で`IDocHostUIHandler::ResizeBorder`Windows SDK に含まれています。

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

##  <a name="setcontrolproperty"></a>  CDHtmlDialog::SetControlProperty

ActiveX コントロールのプロパティを新しい値に設定します。

```
void SetControlProperty(
    LPCTSTR szElementId,
    DISPID dispId,
    VARIANT* pVar);

void SetControlProperty(
    IDispatch* pdispControl,
    DISPID dispId,
    VARIANT* pVar);

void SetControlProperty(
    LPCTSTR szElementId,
    LPCTSTR szPropName,
    VARIANT* pVar);
```

### <a name="parameters"></a>パラメーター

*szElementId*<br/>
ActiveX コントロールの HTML ID。

*dispId*<br/>
設定するプロパティのディスパッチ ID。

*pVar*<br/>
新しいプロパティ値を含むバリアント型へのポインター。

*pdispControl*<br/>
ActiveX コントロールへのポインター`IDispatch`インターフェイス。

*szPropName*<br/>
設定するプロパティの名前を表す文字列です。

##  <a name="setelementhtml"></a>  CDHtmlDialog::SetElementHtml

セット、 `innerHTML` HTML 要素のプロパティ。

```
void SetElementHtml(
    LPCTSTR szElementId,
    BSTR bstrText);

void SetElementHtml(
    IUnknown* punkElem,
    BSTR bstrText);
```

### <a name="parameters"></a>パラメーター

*szElementId*<br/>
HTML 要素の ID。

*bstrText*<br/>
`innerHTML` プロパティの新しい値。

*punkElem*<br/>
`IUnknown` HTML 要素のポインター。

##  <a name="setelementproperty"></a>  CDHtmlDialog::SetElementProperty

HTML 要素のプロパティを設定します。

```
void SetElementProperty(
    LPCTSTR szElementId,
    DISPID dispId,
    VARIANT* pVar);
```

### <a name="parameters"></a>パラメーター

*szElementId*<br/>
HTML 要素の ID。

*dispId*<br/>
設定するプロパティのディスパッチ ID。

*pVar*<br/>
プロパティの新しい値。

##  <a name="setelementtext"></a>  CDHtmlDialog::SetElementText

セット、 `innerText` HTML 要素のプロパティ。

```
void SetElementText(
    LPCTSTR szElementId,
    BSTR bstrText);

void SetElementText(
    IUnknown* punkElem,
    BSTR bstrText);
```

### <a name="parameters"></a>パラメーター

*szElementId*<br/>
HTML 要素の ID。

*bstrText*<br/>
`innerText` プロパティの新しい値。

*punkElem*<br/>
`IUnknown` HTML 要素のポインター。

##  <a name="setexternaldispatch"></a>  CDHtmlDialog::SetExternalDispatch

ホストの設定`IDispatch`インターフェイス。

```
void SetExternalDispatch(IDispatch* pdispExternal);
```

### <a name="parameters"></a>パラメーター

*pdispExternal*<br/>
新しい`IDispatch`インターフェイス。

##  <a name="sethostflags"></a>  CDHtmlDialog::SetHostFlags

ホスト UI フラグを設定します。

```
void SetHostFlags(DWORD dwFlags);
```

### <a name="parameters"></a>パラメーター

*dwFlags*<br/>
使用可能な値は、次を参照してください。 [DOCHOSTUIFLAG](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753277\(v=vs.85\)) Windows SDK に含まれています。

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

*dwID*<br/>
参照してください*dwID*で[IDocHostUIHandler::ShowContextMenu](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753264\(v=vs.85\)) Windows SDK に含まれています。

*ppt*<br/>
参照してください*ppt*で`IDocHostUIHandler::ShowContextMenu`Windows SDK にします。

*pcmdtReserved*<br/>
参照してください*pcmdtReserved*で`IDocHostUIHandler::ShowContextMenu`Windows SDK に含まれています。

*pdispReserved*<br/>
参照してください*pdispReserved*で`IDocHostUIHandler::ShowContextMenu`Windows SDK に含まれています。

### <a name="return-value"></a>戻り値

S_FALSE を返します。

### <a name="remarks"></a>Remarks

このメンバー関数は CDHtmlDialog の実装の[IDocHostUIHandler::ShowContextMenu](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753264\(v=vs.85\))」の説明に従って、Windows SDK。

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

*dwID*<br/>
参照してください*dwID*で[IDocHostUIHandler::ShowUI](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753265\(v=vs.85\)) Windows SDK に含まれています。

*pActiveObject*<br/>
参照してください*d pActiveObject*で`IDocHostUIHandler::ShowUI`Windows SDK に含まれています。

*pCommandTarget*<br/>
参照してください*pCommandTarget*で`IDocHostUIHandler::ShowUI`Windows SDK に含まれています。

*pFrame*<br/>
参照してください*pFrame*で`IDocHostUIHandler::ShowUI`Windows SDK に含まれています。

*pDoc*<br/>
参照してください*pDoc*で`IDocHostUIHandler::ShowUI`Windows SDK に含まれています。

### <a name="return-value"></a>戻り値

S_FALSE を返します。

### <a name="remarks"></a>Remarks

このメンバー関数は CDHtmlDialog の実装の[IDocHostUIHandler::ShowUI](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753265\(v=vs.85\))」の説明に従って、Windows SDK。

##  <a name="translateaccelerator"></a>  CDHtmlDialog::TranslateAccelerator

メニューのアクセラレータ キー メッセージを処理するには、呼び出されます。

```
STDMETHOD(TranslateAccelerator)(
    LPMSG lpMsg,
    const GUID* pguidCmdGroup,
    DWORD nCmdID);
```

### <a name="parameters"></a>パラメーター

*lpMsg*<br/>
参照してください*lpMsg*で[IDocHostUIHandler::TranslateAccelerator](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753266\(v=vs.85\)) Windows SDK に含まれています。

*pguidCmdGroup*<br/>
参照してください*pguidCmdGroup*で`IDocHostUIHandler::TranslateAccelerator`Windows SDK に含まれています。

*nCmdID*<br/>
参照してください*nCmdID*で`IDocHostUIHandler::TranslateAccelerator`Windows SDK に含まれています。

### <a name="return-value"></a>戻り値

S_FALSE を返します。

### <a name="remarks"></a>Remarks

このメンバー関数は CDHtmlDialog の実装の[IDocHostUIHandler::TranslateAccelerator](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753266\(v=vs.85\))」の説明に従って、Windows SDK。

##  <a name="translateurl"></a>  CDHtmlDialog::TranslateUrl

読み込まれる URL を変更するには、呼び出されます。

```
STDMETHOD(TranslateUrl)(
    DWORD dwTranslate,
    OLECHAR* pchURLIn,
    OLECHAR** ppchURLOut);
```

### <a name="parameters"></a>パラメーター

*dwTranslate*<br/>
参照してください*dwTranslate*で[IDocHostUIHandler::TranslateUrl](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753267\(v=vs.85\)) Windows SDK に含まれています。

*pchURLIn*<br/>
参照してください*pchURLIn*で`IDocHostUIHandler::TranslateUrl`Windows SDK に含まれています。

*ppchURLOut*<br/>
参照してください*ppchURLOut*で`IDocHostUIHandler::TranslateUrl`Windows SDK に含まれています。

### <a name="return-value"></a>戻り値

S_FALSE を返します。

### <a name="remarks"></a>Remarks

このメンバー関数は CDHtmlDialog の実装の[IDocHostUIHandler::TranslateUrl](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753267\(v=vs.85\))」の説明に従って、Windows SDK。

##  <a name="updateui"></a>  CDHtmlDialog::UpdateUI

コマンドの状態が変更されたホストに通知と呼ばれます。

```
STDMETHOD(UpdateUI)(void);
```

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

### <a name="remarks"></a>Remarks

このメンバー関数は CDHtmlDialog の実装の[IDocHostUIHandler::UpdateUI](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753268\(v=vs.85\))」の説明に従って、Windows SDK。

## <a name="see-also"></a>関連項目

[MFC サンプル DHtmlExplore](../../visual-cpp-samples.md)<br/>
[DDX_DHtml Helper マクロ](#ddx_dhtml_helper_macros)<br/>
[階層図](../../mfc/hierarchy-chart.md)
