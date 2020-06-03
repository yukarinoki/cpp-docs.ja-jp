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
ms.openlocfilehash: e2e4306320c52b8276d915848dfa6e460982c92b
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753374"
---
# <a name="cdhtmldialog-class"></a>CDHtmlDialog クラス

ユーザー インターフェイスを実装するためにダイアログ リソースではなく HTML を使用するダイアログ ボックスを作成するために使用されます。

## <a name="syntax"></a>構文

```
class CDHtmlDialog : public CDialog, public CDHtmlEventSink
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[ダイアログ](#cdhtmldialog)|オブジェクトを作成します。|
|[ダイアログ](#_dtorcdhtmldialog)|オブジェクトを破棄します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ダイアログ::アクセス外部](#canaccessexternal)|読み込まれたページのスクリプト オブジェクトがコントロール サイトの外部ディスパッチにアクセスできるかどうかを確認するためにアクセス チェックとして呼び出されるオーバーライド可能。 ディスパッチがスクリプトに対して安全であるか、現在のゾーンでスクリプト作成が安全でないオブジェクトを許可しているかどうかを確認します。|
|[コントロールサイトの作成](#createcontrolsite)|ダイアログで WebBrowser コントロールをホストするコントロール サイト インスタンスを作成するために使用されるオーバーライド可能です。|
|[ダイアログ::DDX_DHtml_アクスコントロール](#ddx_dhtml_axcontrol)|メンバー変数と HTML ページ上の ActiveX コントロールのプロパティ値との間でデータを交換します。|
|[チェック ボックスを:D](#ddx_dhtml_checkbox)|メンバー変数と HTML ページのチェック ボックスの間でデータを交換します。|
|[:DDX_DHtml_要素テキスト](#ddx_dhtml_elementtext)|メンバー変数と HTML ページ上の HTML 要素プロパティとの間でデータを交換します。|
|[ダイアログ:D](#ddx_dhtml_radio)|メンバー変数と HTML ページのラジオ ボタンの間でデータを交換します。|
|[ダイアログ::DDX_DHtml_インデックスを選択します。](#ddx_dhtml_selectindex)|HTML ページ上のリスト ボックスのインデックスを取得または設定します。|
|[:DDX_DHtml_選択文字列](#ddx_dhtml_selectstring)|HTML ページのリスト ボックス エントリの表示テキストを現在のインデックスに基づいて取得または設定します。|
|[ダイアログ ボックス::DDX_DHtml_選択値](#ddx_dhtml_selectvalue)|HTML ページのリスト ボックス エントリの値を取得または設定します ( 現在のインデックスに基づく ) 。|
|[ダイアログ::Dエストロイモードレス](#destroymodeless)|モードレス ダイアログ ボックスを破棄します。|
|[ダイアログ::モードレスを有効にする](#enablemodeless)|モードレス ダイアログ ボックスを有効にします。|
|[フィルターデータオブジェクト](#filterdataobject)|ダイアログボックスで、ホストされたブラウザによって作成されたクリップボード データ オブジェクトをフィルタ処理できます。|
|[をクリックします。](#getcontroldispatch)|HTML ドキュメント`IDispatch`に埋め込まれた ActiveX コントロールのインターフェイスを取得します。|
|[プロパティを取得します。](#getcontrolproperty)|指定した ActiveX コントロールの要求されたプロパティを取得します。|
|[ダイアログ::取得カレントUrl](#getcurrenturl)|現在のドキュメントに関連付けられている統一リソース ロケーター (URL) を取得します。|
|[ドキュメントを取得します。](#getdhtmldocument)|現在読み込まれている HTML ドキュメントの IHTMLDocument2 インターフェイスを取得します。|
|[ダイアログ::ドロップターゲット](#getdroptarget)|含まれている WebBrowser コントロールがドロップ ターゲットとして使用されているときに呼び出され、ダイアログが代替[IDropTarget](/windows/win32/api/oleidl/nn-oleidl-idroptarget)を提供できるようにします。|
|[ダイアログ::取得要素](#getelement)|HTML 要素のインターフェイスを取得します。|
|[ダイアログ::ゲットエレメントHtml](#getelementhtml)|HTML 要素`innerHTML`のプロパティを取得します。|
|[インターフェイスを取得します。](#getelementinterface)|HTML 要素から要求されたインターフェイス ポインターを取得します。|
|[プロパティを取得します。](#getelementproperty)|HTML 要素のプロパティの値を取得します。|
|[テキストを取得します。](#getelementtext)|HTML 要素`innerText`のプロパティを取得します。|
|[ダイアログ::イベントを取得します。](#getevent)|現在の`IHTMLEventObj`イベント オブジェクトへのポインターを取得します。|
|[ダイアログ::外部を取得します。](#getexternal)|ホストのインターフェイスを`IDispatch`取得します。|
|[ダイアログ::ホスト情報を取得します。](#gethostinfo)|ホストの UI 機能を取得します。|
|[ダイアログ::ゲットオプションキーパス](#getoptionkeypath)|ユーザー設定が格納されるレジストリ キーを取得します。|
|[ダイアログ::ハイドイ](#hideui)|ホストの UI を非表示にします。|
|[ダイアログ::Is外部ディスパッチセーフ](#isexternaldispatchsafe)|ホストの`IDispatch`インターフェイスがスクリプトに対して安全かどうかを示します。|
|[リソースから読み込む](#loadfromresource)|指定したリソースを WebBrowser コントロールに読み込みます。|
|[ダイアログ::ナビゲート](#navigate)|指定した URL に移動します。|
|[ダイアログ::オン・フォア・ナビゲート](#onbeforenavigate)|ナビゲーション イベントが発生する前に、フレームワークによって呼び出されます。|
|[ドキュメント完了](#ondocumentcomplete)|ドキュメントがREADYSTATE_COMPLETE状態になったときにアプリケーションに通知するために、フレームワークによって呼び出されます。|
|[ダイアログ::オンドックウィンドウアクティブ](#ondocwindowactivate)|ドキュメント ウィンドウがアクティブまたは非アクティブになったときに、フレームワークによって呼び出されます。|
|[ダイアログ::オンフレームウィンドウアクティブ](#onframewindowactivate)|フレーム ウィンドウがアクティブまたは非アクティブになったときに、フレームワークによって呼び出されます。|
|[ダイアログ](#oninitdialog)|WM_INITDIALOG メッセージに応答して呼び出されます。|
|[ダイアログ::オンナビゲートコンプリート](#onnavigatecomplete)|ナビゲーション イベントが完了した後に、フレームワークによって呼び出されます。|
|[ウィンドウのサイズを変更します。](#resizeborder)|オブジェクトに対して、境界領域のサイズを変更する必要があることを警告します。|
|[プロパティを設定します。](#setcontrolproperty)|ActiveX コントロールのプロパティを新しい値に設定します。|
|[ダイアログ::セットエレメントHtml](#setelementhtml)|HTML`innerHTML`要素のプロパティを設定します。|
|[プロパティを設定します。](#setelementproperty)|HTML 要素のプロパティを設定します。|
|[ダイアログ::テキストを設定します。](#setelementtext)|HTML`innerText`要素のプロパティを設定します。|
|[ダイアログ::外部ディスパッチを設定します。](#setexternaldispatch)|ホストのインターフェイスを`IDispatch`設定します。|
|[ダイアログ::セットホストフラグ](#sethostflags)|ホストの UI フラグを設定します。|
|[ダイアログ::コンテキストメニューを表示します。](#showcontextmenu)|コンテキスト メニューが表示されようとしているときに呼び出されます。|
|[ダイアログ::ショーUI](#showui)|ホストの UI を表示します。|
|[ダイアログ::変換アクセラレータ](#translateaccelerator)|メニュー アクセラレータ キー メッセージを処理するために呼び出されます。|
|[ダイアログ::翻訳Url](#translateurl)|読み込む URL を変更するために呼び出されます。|
|[ダイアログ::アップデートUI](#updateui)|コマンドの状態が変更されたことをホストに通知するために呼び出されます。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[ダイアログ::m_bUseHtmlTitle](#m_busehtmltitle)|HTML ドキュメントのタイトルをダイアログ キャプションとして使用するかどうかを示します。|
|[ダイアログ::m_nHtmlResID](#m_nhtmlresid)|表示される HTML リソースのリソース ID。|
|[ダイアログ::m_pBrowserApp](#m_pbrowserapp)|Web ブラウザー アプリケーションへのポインター。|
|[ダイアログ::m_spHtmlDoc](#m_sphtmldoc)|HTML ドキュメントへのポインター。|
|[ダイアログ::m_strCurrentUrl](#m_strcurrenturl)|現在の URL。|
|[ダイアログ::m_szHtmlResID](#m_szhtmlresid)|HTML リソース ID の文字列バージョンです。|

## <a name="remarks"></a>解説

`CDHtmlDialog`は、HTML リソースまたは URL から表示される HTML を読み込むことができます。

`CDHtmlDialog`また、HTML コントロールとデータ交換を行い、ボタンのクリックなどの HTML コントロールからのイベントを処理することもできます。

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

## <a name="ddx_dhtml-helper-macros"></a><a name="ddx_dhtml_helper_macros"></a>DDX_DHtmlヘルパー マクロ

DDX_DHtml ヘルパー マクロを使用すると、HTML ページ上のコントロールの一般的に使用されるプロパティに簡単にアクセスできます。

### <a name="data-exchange-macros"></a>データ交換マクロ

|||
|-|-|
|[DDX_DHtml_ElementValue](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_elementvalue)|選択したコントロールから Value プロパティを設定または取得します。|
|[DDX_DHtml_ElementInnerText](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_elementinnertext)|現在の要素の開始タグと終了タグの間のテキストを設定または取得します。|
|[DDX_DHtml_ElementInnerHtml](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_elementinnerhtml)|現在の要素の開始タグと終了タグの間の HTML を設定または取得します。|
|[DDX_DHtml_Anchor_Href](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_anchor_href)|リンク先 URL またはアンカー ポイントを設定または取得します。|
|[DDX_DHtml_Anchor_Target](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_anchor_target)|ターゲット ウィンドウまたはフレームを設定または取得します。|
|[DDX_DHtml_Img_Src](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_img_src)|ドキュメント内のイメージまたはビデオ クリップの名前を設定または取得します。|
|[DDX_DHtml_Frame_Src](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_frame_src)|関連付けられたフレームの URL を設定または取得します。|
|[DDX_DHtml_IFrame_Src](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_iframe_src)|関連付けられたフレームの URL を設定または取得します。|

## <a name="cdhtmldialogcanaccessexternal"></a><a name="canaccessexternal"></a>ダイアログ::アクセス外部

読み込まれたページのスクリプト オブジェクトがコントロール サイトの外部ディスパッチにアクセスできるかどうかを確認するためにアクセス チェックとして呼び出されるオーバーライド可能。 ディスパッチがスクリプトに対して安全であるか、現在のゾーンでスクリプト作成が安全でないオブジェクトを許可しているかどうかを確認します。

```
virtual BOOL CanAccessExternal();
```

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

## <a name="cdhtmldialogcdhtmldialog"></a><a name="cdhtmldialog"></a>ダイアログ

リソースベースのダイナミック HTML ダイアログ ボックスを構築します。

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

*テンプレート名*<br/>
ダイアログ ボックス テンプレート リソースの名前である null で終わる文字列。

*を返します。*<br/>
HTML リソースの名前である null で終わる文字列。

*pParentWnd*<br/>
ダイアログ オブジェクトが属する親ウィンドウ オブジェクトまたはオーナー ウィンドウ オブジェクト ( [CWnd](../../mfc/reference/cwnd-class.md)型 ) へのポインター。 NULL の場合、ダイアログ オブジェクトの親ウィンドウはメイン アプリケーション ウィンドウに設定されます。

*テンプレート*<br/>
ダイアログ ボックス テンプレート リソースの ID 番号を格納します。

*を返します。*<br/>
HTML リソースの ID 番号を格納します。

### <a name="remarks"></a>解説

コンストラクタの 2 番目の形式では、テンプレート名を使用してダイアログ リソースにアクセスできます。 コンストラクタの 3 番目の形式では、リソース テンプレートの ID を使用してダイアログ リソースにアクセスできます。 通常、ID は**IDD_** プレフィックスで始まります。

## <a name="cdhtmldialogcdhtmldialog"></a><a name="_dtorcdhtmldialog"></a>ダイアログ

オブジェクトを破棄します。

```
virtual ~CDHtmlDialog();
```

### <a name="remarks"></a>解説

[CWnd::DestroyWindow](../../mfc/reference/cwnd-class.md#destroywindow)メンバー関数は[、CDialog::Create](../../mfc/reference/cdialog-class.md#create)によって作成されたモードレス ダイアログ ボックスを破棄するために使用する必要があります。

## <a name="cdhtmldialogcreatecontrolsite"></a><a name="createcontrolsite"></a>コントロールサイトの作成

ダイアログで WebBrowser コントロールをホストするコントロール サイト インスタンスを作成するために使用されるオーバーライド可能です。

```
virtual BOOL CreateControlSite(
    COleControlContainer* pContainer,
    COleControlSite** ppSite,
    UINT /* nID */,
    REFCLSID /* clsid */);
```

### <a name="parameters"></a>パラメーター

*pContainer*<br/>
[オブジェクトへの](../../mfc/reference/colecontrolcontainer-class.md)ポインター

*ppSite*<br/>
へのポインターへのポインター[です](../../mfc/reference/colecontrolsite-class.md)。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

このメンバー関数をオーバーライドして、独自のコントロール サイト クラスのインスタンスを返すことができます。

## <a name="cdhtmldialogddx_dhtml_axcontrol"></a><a name="ddx_dhtml_axcontrol"></a>ダイアログ::DDX_DHtml_アクスコントロール

メンバー変数と HTML ページ上の ActiveX コントロールのプロパティ値との間でデータを交換します。

```cpp
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

*Pdx*<br/>
[オブジェクト](../../mfc/reference/cdataexchange-class.md)へのポインター。

*szId*<br/>
ActiveX コントロールの HTML ソース内のオブジェクト タグの ID パラメータの値。

*Dispid*<br/>
データを交換するプロパティのディスパッチ ID。

*を使用します。*<br/>
プロパティの名前。

*var*<br/>
ActiveX コントロール プロパティと交換される値を保持するバリアント型[、COleVariant](../../mfc/reference/colevariant-class.md)型、または[CComVariant](../../atl/reference/ccomvariant-class.md)型のデータ メンバー。

### <a name="example"></a>例

[!code-cpp[NVC_MFCHtmlHttp#1](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_1.cpp)]

## <a name="cdhtmldialogddx_dhtml_checkbox"></a><a name="ddx_dhtml_checkbox"></a>チェック ボックスを:D

メンバー変数と HTML ページのチェック ボックスの間でデータを交換します。

```cpp
void DDX_DHtml_CheckBox(
    CDataExchange* pDX,
    LPCTSTR szId,
    int& value);
```

### <a name="parameters"></a>パラメーター

*Pdx*<br/>
[オブジェクト](../../mfc/reference/cdataexchange-class.md)へのポインター。

*szId*<br/>
HTML コントロールの ID パラメーターに指定した値。

*value*<br/>
交換される値。

### <a name="example"></a>例

[!code-cpp[NVC_MFCHtmlHttp#2](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_2.cpp)]

## <a name="cdhtmldialogddx_dhtml_elementtext"></a><a name="ddx_dhtml_elementtext"></a>:DDX_DHtml_要素テキスト

メンバー変数と HTML ページ上の HTML 要素プロパティとの間でデータを交換します。

```cpp
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

*Pdx*<br/>
[オブジェクト](../../mfc/reference/cdataexchange-class.md)へのポインター。

*szId*<br/>
HTML コントロールの ID パラメーターに指定した値。

*Dispid*<br/>
データを交換する HTML 要素のディスパッチ ID。

*value*<br/>
交換される値。

## <a name="cdhtmldialogddx_dhtml_radio"></a><a name="ddx_dhtml_radio"></a>ダイアログ:D

メンバー変数と HTML ページのラジオ ボタンの間でデータを交換します。

```cpp
void DDX_DHtml_Radio(
    CDataExchange* pDX,
    LPCTSTR szId,
    long& value);
```

### <a name="parameters"></a>パラメーター

*Pdx*<br/>
[オブジェクト](../../mfc/reference/cdataexchange-class.md)へのポインター。

*szId*<br/>
HTML コントロールの ID パラメーターに指定した値。

*value*<br/>
交換される値。

## <a name="cdhtmldialogddx_dhtml_selectindex"></a><a name="ddx_dhtml_selectindex"></a>ダイアログ::DDX_DHtml_インデックスを選択します。

HTML ページ上のリスト ボックスのインデックスを取得または設定します。

```cpp
void DDX_DHtml_SelectIndex(
    CDataExchange* pDX,
    LPCTSTR szId,
    long& value);
```

### <a name="parameters"></a>パラメーター

*Pdx*<br/>
[オブジェクト](../../mfc/reference/cdataexchange-class.md)へのポインター。

*szId*<br/>
HTML コントロールの`id`パラメーターに指定した値。

*value*<br/>
交換される値。

## <a name="cdhtmldialogddx_dhtml_selectstring"></a><a name="ddx_dhtml_selectstring"></a>:DDX_DHtml_選択文字列

HTML ページのリスト ボックス エントリの表示テキストを現在のインデックスに基づいて取得または設定します。

```cpp
void DDX_DHtml_SelectString(
    CDataExchange* pDX,
    LPCTSTR szId,
    CString& value);
```

### <a name="parameters"></a>パラメーター

*Pdx*<br/>
[オブジェクト](../../mfc/reference/cdataexchange-class.md)へのポインター。

*szId*<br/>
HTML コントロールの ID パラメーターに指定した値。

*value*<br/>
交換される値。

## <a name="cdhtmldialogddx_dhtml_selectvalue"></a><a name="ddx_dhtml_selectvalue"></a>ダイアログ ボックス::DDX_DHtml_選択値

HTML ページのリスト ボックス エントリの値を取得または設定します ( 現在のインデックスに基づく ) 。

```cpp
void DDX_DHtml_SelectValue(
    CDataExchange* pDX,
    LPCTSTR szId,
    CString& value);
```

### <a name="parameters"></a>パラメーター

*Pdx*<br/>
[オブジェクト](../../mfc/reference/cdataexchange-class.md)へのポインター。

*szId*<br/>
HTML コントロールの ID パラメーターに指定した値。

*value*<br/>
交換される値。

### <a name="example"></a>例

[!code-cpp[NVC_MFCHtmlHttp#3](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_3.cpp)]

## <a name="cdhtmldialogdestroymodeless"></a><a name="destroymodeless"></a>ダイアログ::Dエストロイモードレス

モードレス ダイアログ ボックスをオブジェクトから`CDHtmlDialog`切り離し、オブジェクトを破棄します。

```cpp
void DestroyModeless();
```

## <a name="cdhtmldialogenablemodeless"></a><a name="enablemodeless"></a>ダイアログ::モードレスを有効にする

モードレス ダイアログ ボックスを有効にします。

```
STDMETHOD(EnableModeless)(BOOL fEnable);
```

### <a name="parameters"></a>パラメーター

*f有効*<br/>
Windows SDK の*fEnable*を参照[してください](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753253\(v=vs.85\))。

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、CDHtmlDialog の[IDocHostUIHandler::EnableModeless](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753253\(v=vs.85\))の実装です。

## <a name="cdhtmldialogfilterdataobject"></a><a name="filterdataobject"></a>フィルターデータオブジェクト

ダイアログボックスで、ホストされたブラウザによって作成されたクリップボード データ オブジェクトをフィルタ処理できます。

```
STDMETHOD(FilterDataObject)(
    IDataObject* pDO,
    IDataObject** ppDORet);
```

### <a name="parameters"></a>パラメーター

*Pdo*<br/>
Windows SDK の*pDO*を参照してください。 [IDocHostUIHandler::FilterDataObject](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753254\(v=vs.85\))

*ppDOReT*<br/>
の *「」の「ppDORet」*`IDocHostUIHandler::FilterDataObject`を参照してください。

### <a name="return-value"></a>戻り値

S_FALSEを返します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明[されているように](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753254\(v=vs.85\))、CDHtmlDialog の実装です。

## <a name="cdhtmldialoggetcontroldispatch"></a><a name="getcontroldispatch"></a>をクリックします。

によって返される`IDispatch`HTML ドキュメントに埋め込まれている ActiveX コントロールのインターフェイス[を取得します](#getdhtmldocument)。

```
HRESULT GetControlDispatch(
    LPCTSTR szId,
    IDispatch** ppdisp);
```

### <a name="parameters"></a>パラメーター

*szId*<br/>
ActiveX コントロールの HTML ID。

*ppdisp*<br/>
Web`IDispatch`ページで見つかった場合のコントロールのインターフェイス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

## <a name="cdhtmldialoggetcontrolproperty"></a><a name="getcontrolproperty"></a>プロパティを取得します。

指定した ActiveX コントロールの要求されたプロパティを取得します。

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

*を使用します。*<br/>
現在のユーザーの既定のロケールにあるプロパティの名前。

*コントロール*<br/>
ActiveX コントロールの`IDispatch`ポインター。

*Dispid*<br/>
プロパティのディスパッチ ID。

### <a name="return-value"></a>戻り値

要求されたプロパティを含むバリアント、またはコントロールまたはプロパティが見つからない場合は空のバリアント。

### <a name="remarks"></a>解説

オーバーロードは、最も効率の低い順から最も効率的な一番下にリストされています。

## <a name="cdhtmldialoggetcurrenturl"></a><a name="getcurrenturl"></a>ダイアログ::取得カレントUrl

現在のドキュメントに関連付けられている統一リソース ロケーター (URL) を取得します。

```cpp
void GetCurrentUrl(CString& szUrl);
```

### <a name="parameters"></a>パラメーター

*スズUrl*<br/>
取得する URL を含む[CString](../../atl-mfc-shared/reference/cstringt-class.md)オブジェクト。

## <a name="cdhtmldialoggetdhtmldocument"></a><a name="getdhtmldocument"></a>ドキュメントを取得します。

現在読み込まれている HTML ドキュメントの[IHTMLDocument2](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752574\(v=vs.85\))インターフェイスを取得します。

```
HRESULT GetDHtmlDocument(IHTMLDocument2 **pphtmlDoc);
```

### <a name="parameters"></a>パラメーター

*\*ド\*ク*HTML ドキュメントへのポインターへのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT。 成功した場合S_OK返します。

## <a name="cdhtmldialoggetdroptarget"></a><a name="getdroptarget"></a>ダイアログ::ドロップターゲット

含まれている WebBrowser コントロールがドロップ ターゲットとして使用されているときに呼び出され、ダイアログが代替[IDropTarget](/windows/win32/api/oleidl/nn-oleidl-idroptarget)を提供できるようにします。

```
STDMETHOD(GetDropTarget)(
    IDropTarget* pDropTarget,
    IDropTarget** ppDropTarget);
```

### <a name="parameters"></a>パラメーター

*ターゲット*<br/>
Windows SDK の*p ドロップターゲット*を参照[してください](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753255\(v=vs.85\))。

*ターゲット*<br/>
Windows SDK`IDocHostUIHandler::GetDropTarget`*の「ppDropTarget」* を参照してください。

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、CDHtmlDialog の[IDocHostUIHandler::GetDropTarget](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753255\(v=vs.85\))の実装です。

## <a name="cdhtmldialoggetelement"></a><a name="getelement"></a>ダイアログ::取得要素

で指定された HTML 要素のインターフェイス*を*返します。

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

*をクリックします。*<br/>
HTML 要素の ID。

*ppdisp*<br/>
要求`IDispatch`された要素または要素のコレクションへのポインター。

*pbコレクション*<br/>
*ppdisp*で表されるオブジェクトが単一の要素であるか、要素のコレクションであるかを示す BOOL。

*要素*<br/>
要求`IHTMLElement`された要素へのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

指定した ID を持つ要素が複数ある可能性がある条件を処理する必要がある場合は、最初のオーバーロードを使用します。 最後のパラメーターを使用して、返されたインターフェイス ポインターがコレクションまたは単一の項目のどちらを指しているかを調べます。 インターフェイス ポインターがコレクション上にある場合は、 を`IHTMLElementCollection`クエリし、その`item`プロパティを使用して要素を序数の位置で参照できます。

ページ内に同じ ID を持つ要素が複数ある場合、2 番目のオーバーロードは失敗します。

## <a name="cdhtmldialoggetelementhtml"></a><a name="getelementhtml"></a>ダイアログ::ゲットエレメントHtml

によって識別される`innerHTML`HTML 要素のプロパティ*を取得します*。

```
BSTR GetElementHtml(LPCTSTR szElementId);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
HTML 要素の ID。

### <a name="return-value"></a>戻り値

要素`innerHTML`が見つからない場合は *、szElementId*または NULL で識別される HTML 要素のプロパティ。

## <a name="cdhtmldialoggetelementinterface"></a><a name="getelementinterface"></a>インターフェイスを取得します。

要求されたインターフェイス ポインターを*取得*します。

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

*をクリックします。*<br/>
HTML 要素の ID。

*Ppvobj*<br/>
要素が見つかり、クエリが成功した場合に、要求されたインターフェイス ポインターで埋められるポインターのアドレス。

*Refiid*<br/>
要求されたインターフェイスのインターフェイス ID (IID)。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="example"></a>例

[!code-cpp[NVC_MFCHtmlHttp#4](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_4.cpp)]

## <a name="cdhtmldialoggetelementproperty"></a><a name="getelementproperty"></a>プロパティを取得します。

によって識別される HTML 要素から*dispId*によって識別されるプロパティ*の値を*取得します。

```
VARIANT GetElementProperty(
    LPCTSTR szElementId,
    DISPID dispId);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
HTML 要素の ID。

*Dispid*<br/>
プロパティのディスパッチ ID。

### <a name="return-value"></a>戻り値

プロパティまたは要素が見つからない場合は、プロパティの値または空のバリアント。

## <a name="cdhtmldialoggetelementtext"></a><a name="getelementtext"></a>テキストを取得します。

によって識別される`innerText`HTML 要素のプロパティ*を取得します*。

```
BSTR GetElementText(LPCTSTR szElementId);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
HTML 要素の ID。

### <a name="return-value"></a>戻り値

`innerText`プロパティまたは要素が見つからない場合は *、szElementId*または NULL で識別される HTML 要素のプロパティ。

## <a name="cdhtmldialoggetevent"></a><a name="getevent"></a>ダイアログ::イベントを取得します。

現在の`IHTMLEventObj`イベント オブジェクトへのポインターを返します。

```
HRESULT GetEvent(IHTMLEventObj** ppEventObj);
```

### <a name="parameters"></a>パラメーター

*を使用します。*<br/>
インターフェイス ポインターで埋め込まれるポインターの`IHTMLEventObj`アドレス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

この関数は、DHTML イベント ハンドラ内からのみ呼び出してください。

## <a name="cdhtmldialoggetexternal"></a><a name="getexternal"></a>ダイアログ::外部を取得します。

ホストのインターフェイスを`IDispatch`取得します。

```
STDMETHOD(GetExternal)(IDispatch** ppDispatch);
```

### <a name="parameters"></a>パラメーター

*ディスパッチ*<br/>
Windows SDK[の](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753256\(v=vs.85\))*ppDispatch*を参照してください。

### <a name="return-value"></a>戻り値

成功のS_OKを返し、失敗した場合にE_NOTIMPLします。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、CDHtmlDialog の[IDocHostUIHandler::GetExternal](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753256\(v=vs.85\))の実装です。

## <a name="cdhtmldialoggethostinfo"></a><a name="gethostinfo"></a>ダイアログ::ホスト情報を取得します。

ホストの UI 機能を取得します。

```
STDMETHOD(GetHostInfo)(DOCHOSTUIINFO* pInfo);
```

### <a name="parameters"></a>パラメーター

*Pinfo*<br/>
次の*トピック*を参照[してください](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753257\(v=vs.85\))。

### <a name="return-value"></a>戻り値

S_OKを返します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明[されているように](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753257\(v=vs.85\))、CDHtmlDialog の実装です。

## <a name="cdhtmldialoggetoptionkeypath"></a><a name="getoptionkeypath"></a>ダイアログ::ゲットオプションキーパス

ユーザー設定が格納されるレジストリ キーを取得します。

```
STDMETHOD(GetOptionKeyPath)(
    LPOLESTR* pchKey,
    DWORD dw);
```

### <a name="parameters"></a>パラメーター

*pchキー*<br/>
次の*トピック*を参照[してください](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753258\(v=vs.85\))。

*dw*<br/>
Windows SDK`IDocHostUIHandler::GetOptionKeyPath`の*dw*を参照してください。

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明[されているように](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753258\(v=vs.85\))、CDHtmlDialog の実装です。

## <a name="cdhtmldialoghideui"></a><a name="hideui"></a>ダイアログ::ハイドイ

ホストの UI を非表示にします。

```
STDMETHOD(HideUI)(void);
```

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、CDHtmlDialog の[IDocHostUIHandler::HideUI](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753259\(v=vs.85\))の実装です。

## <a name="cdhtmldialogisexternaldispatchsafe"></a><a name="isexternaldispatchsafe"></a>ダイアログ::Is外部ディスパッチセーフ

ホストの`IDispatch`インターフェイスがスクリプトに対して安全かどうかを示します。

```
virtual BOOL IsExternalDispatchSafe();
```

### <a name="return-value"></a>戻り値

FALSE を返します。

## <a name="cdhtmldialogloadfromresource"></a><a name="loadfromresource"></a>リソースから読み込む

指定したリソースを DHTML ダイアログの WebBrowser コントロールに読み込みます。

```
BOOL LoadFromResource(LPCTSTR lpszResource);
BOOL LoadFromResource(UINT nRes);
```

### <a name="parameters"></a>パラメーター

*リソース*<br/>
読み込むリソースの名前を含む文字列へのポインター。

*nRes*<br/>
読み込むリソースの ID です。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、それ以外の場合は FALSE。

## <a name="cdhtmldialogm_busehtmltitle"></a><a name="m_busehtmltitle"></a>ダイアログ::m_bUseHtmlTitle

HTML ドキュメントのタイトルをダイアログ キャプションとして使用するかどうかを示します。

```
BOOL m_bUseHtmlTitle;
```

### <a name="remarks"></a>解説

**m**_ **bUseHtmlTitle**が TRUE の場合、ダイアログ キャプションは HTML ドキュメントのタイトルと同じに設定されます。それ以外の場合は、ダイアログ リソースのキャプションが使用されます。

## <a name="cdhtmldialogm_nhtmlresid"></a><a name="m_nhtmlresid"></a>ダイアログ::m_nHtmlResID

表示される HTML リソースのリソース ID。

```
UINT m_nHtmlResID;
```

### <a name="example"></a>例

[!code-cpp[NVC_MFCHtmlHttp#5](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_5.cpp)]

## <a name="cdhtmldialogm_pbrowserapp"></a><a name="m_pbrowserapp"></a>ダイアログ::m_pBrowserApp

Web ブラウザー アプリケーションへのポインター。

```
CComPtr <IWebBrowser2> m_pBrowserApp;
```

## <a name="cdhtmldialogm_sphtmldoc"></a><a name="m_sphtmldoc"></a>ダイアログ::m_spHtmlDoc

HTML ドキュメントへのポインター。

```
CComPtr<IHTMLDocument2> m_spHtmlDoc;
```

## <a name="cdhtmldialogm_strcurrenturl"></a><a name="m_strcurrenturl"></a>ダイアログ::m_strCurrentUrl

現在の URL。

```
CString m_strCurrentUrl;
```

## <a name="cdhtmldialogm_szhtmlresid"></a><a name="m_szhtmlresid"></a>ダイアログ::m_szHtmlResID

HTML リソース ID の文字列バージョンです。

```
LPTSTR m_szHtmlResID;
```

### <a name="example"></a>例

[!code-cpp[NVC_MFCHtmlHttp#6](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_6.cpp)]

## <a name="cdhtmldialognavigate"></a><a name="navigate"></a>ダイアログ::ナビゲート

*lpszURL*で指定された URL で識別されるリソースに移動します。

```cpp
void Navigate(
    LPCTSTR lpszURL,
    DWORD dwFlags = 0,
    LPCTSTR lpszTargetFrameName = NULL,
    LPCTSTR lpszHeaders = NULL,
    LPVOID lpvPostData = NULL,
    DWORD dwPostDataLen = 0);
```

### <a name="parameters"></a>パラメーター

*を指定します。*<br/>
対象とする URL を含む文字列へのポインター。

*dwFlags*<br/>
リソースを履歴リストに追加するかどうか、キャッシュに読み込むか、キャッシュから書き込むか、およびリソースを新しいウィンドウに表示するかどうかを指定する変数のフラグ。 変数は、[ブラウザーの定数](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768360\(v=vs.85\))の列挙体によって定義された値の組み合わせであることができます。

*フレーム名*<br/>
リソースを表示するフレームの名前を含む文字列へのポインター。

*ヘッダー*<br/>
サーバーに送信する HTTP ヘッダーを指定する値へのポインター。 これらのヘッダーは、既定の Internet Explorer ヘッダーに追加されます。 ヘッダーは、サーバーに必要なアクション、サーバーに渡されるデータの種類、状態コードなどの情報を指定できます。 URL が HTTP URL でない場合、このパラメーターは無視されます。

*データ*<br/>
HTTP POST トランザクションで送信するデータへのポインター。 たとえば、POST トランザクションは、HTML フォームによって収集されたデータを送信するために使用されます。 このパラメーターでポスト・データが指定されていない場合`Navigate`は、HTTP GET トランザクションを発行します。 URL が HTTP URL でない場合、このパラメーターは無視されます。

*を使用します。*<br/>
HTTP POST トランザクションで送信するデータ。 たとえば、POST トランザクションは、HTML フォームによって収集されたデータを送信するために使用されます。 このパラメーターでポスト・データが指定されていない場合`Navigate`は、HTTP GET トランザクションを発行します。 URL が HTTP URL でない場合、このパラメーターは無視されます。

## <a name="cdhtmldialogonbeforenavigate"></a><a name="onbeforenavigate"></a>ダイアログ::オン・フォア・ナビゲート

ナビゲーションが発生する前にイベントを発生させるために、フレームワークによって呼び出されます。

```
virtual void OnBeforeNavigate(
    LPDISPATCH pDisp,
    LPCTSTR szUrl);
```

### <a name="parameters"></a>パラメーター

*pDisp*<br/>
`IDispatch` オブジェクトへのポインター。

*スズUrl*<br/>
移動先の URL を含む文字列へのポインター。

## <a name="cdhtmldialogondocumentcomplete"></a><a name="ondocumentcomplete"></a>ドキュメント完了

ドキュメントがREADYSTATE_COMPLETE状態になったときにアプリケーションに通知するために、フレームワークによって呼び出されます。

```
virtual void OnDocumentComplete(
    LPDISPATCH pDisp,
    LPCTSTR szUrl);
```

### <a name="parameters"></a>パラメーター

*pDisp*<br/>
`IDispatch` オブジェクトへのポインター。

*スズUrl*<br/>
移動先の URL を含む文字列へのポインター。

## <a name="cdhtmldialogondocwindowactivate"></a><a name="ondocwindowactivate"></a>ダイアログ::オンドックウィンドウアクティブ

ドキュメント ウィンドウがアクティブまたは非アクティブになったときに、フレームワークによって呼び出されます。

```
STDMETHOD(OnDocWindowActivate)(BOOL fActivate);
```

### <a name="parameters"></a>パラメーター

*fアクティブ化*<br/>
次*を参照*してください[IDocHostUIHandler::OnDocWindowActivate](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753261\(v=vs.85\))。

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、CDHtmlDialog[の実装](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753261\(v=vs.85\))です。

## <a name="cdhtmldialogonframewindowactivate"></a><a name="onframewindowactivate"></a>ダイアログ::オンフレームウィンドウアクティブ

フレーム ウィンドウがアクティブまたは非アクティブになったときに、フレームワークによって呼び出されます。

```
STDMETHOD(OnFrameWindowActivate)(BOOL fActivate);
```

### <a name="parameters"></a>パラメーター

*fアクティブ化*<br/>
次*を参照*してください[IDocHostUIHandler::OnFrameWindowActivate](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753262\(v=vs.85\))。

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、CDHtmlDialog[の実装](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753262\(v=vs.85\))です。

## <a name="cdhtmldialogoninitdialog"></a><a name="oninitdialog"></a>ダイアログ

WM_INITDIALOG メッセージに応答して呼び出されます。

```
virtual BOOL OnInitDialog();
```

### <a name="return-value"></a>戻り値

既定の実装では TRUE が返されます。

### <a name="remarks"></a>解説

このメッセージは、 `Create`、または`CreateIndirect``DoModal`、 の呼び出し中に、ダイアログ ボックスが表示される直前に表示されます。

ダイアログ ボックスの初期化時に特別な処理を実行する必要がある場合は、このメンバー関数をオーバーライドします。 オーバーライドされたバージョンでは、まず基本クラス`OnInitDialog`を呼び出しますが、戻り値は無視します。 通常、オーバーライドされたメンバー関数から TRUE を返します。

Windows は`OnInitDialog`、メッセージ マップではなく、すべての Microsoft Foundation クラス ライブラリ ダイアログ ボックスに共通する標準のグローバル ダイアログ ボックス プロシージャを使用して関数を呼び出すため、このメンバー関数にメッセージ マップ エントリは必要ありません。

## <a name="cdhtmldialogonnavigatecomplete"></a><a name="onnavigatecomplete"></a>ダイアログ::オンナビゲートコンプリート

指定した URL へのナビゲーションが完了した後に、フレームワークによって呼び出されます。

```
virtual void OnNavigateComplete(
    LPDISPATCH pDisp,
    LPCTSTR szUrl);
```

### <a name="parameters"></a>パラメーター

*pDisp*<br/>
`IDispatch` オブジェクトへのポインター。

*スズUrl*<br/>
移動先の URL を含む文字列へのポインター。

## <a name="cdhtmldialogresizeborder"></a><a name="resizeborder"></a>ウィンドウのサイズを変更します。

オブジェクトに対して、境界領域のサイズを変更する必要があることを警告します。

```
STDMETHOD(ResizeBorder)(
    LPCRECT prcBorder,
    IOleInPlaceUIWindow* pUIWindow,
    BOOL fRameWindow);
```

### <a name="parameters"></a>パラメーター

*プルクボーダー*<br/>
Windows SDK の *「プルクボーダー* [」を](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753263\(v=vs.85\))参照してください。

*ウィンドウ*<br/>
の「*ウィンドウ」*`IDocHostUIHandler::ResizeBorder`を参照してください。

*ウィンドウ*<br/>
Windows SDK の`IDocHostUIHandler::ResizeBorder`*「fFrameWindow」* を参照してください。

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

## <a name="cdhtmldialogsetcontrolproperty"></a><a name="setcontrolproperty"></a>プロパティを設定します。

ActiveX コントロールのプロパティを新しい値に設定します。

```cpp
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

*をクリックします。*<br/>
ActiveX コントロールの HTML ID。

*Dispid*<br/>
設定するプロパティのディスパッチ ID。

*pVar*<br/>
新しいプロパティ値を含む VARIANT へのポインター。

*コントロール*<br/>
ActiveX コントロールの`IDispatch`インターフェイスへのポインター。

*を使用します。*<br/>
設定するプロパティの名前を含む文字列。

## <a name="cdhtmldialogsetelementhtml"></a><a name="setelementhtml"></a>ダイアログ::セットエレメントHtml

HTML`innerHTML`要素のプロパティを設定します。

```cpp
void SetElementHtml(
    LPCTSTR szElementId,
    BSTR bstrText);

void SetElementHtml(
    IUnknown* punkElem,
    BSTR bstrText);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
HTML 要素の ID。

*テキスト*<br/>
`innerHTML` プロパティの新しい値。

*パンクレム*<br/>
HTML`IUnknown`要素のポインター。

## <a name="cdhtmldialogsetelementproperty"></a><a name="setelementproperty"></a>プロパティを設定します。

HTML 要素のプロパティを設定します。

```cpp
void SetElementProperty(
    LPCTSTR szElementId,
    DISPID dispId,
    VARIANT* pVar);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
HTML 要素の ID。

*Dispid*<br/>
設定するプロパティのディスパッチ ID。

*pVar*<br/>
プロパティの新しい値です。

## <a name="cdhtmldialogsetelementtext"></a><a name="setelementtext"></a>ダイアログ::テキストを設定します。

HTML`innerText`要素のプロパティを設定します。

```cpp
void SetElementText(
    LPCTSTR szElementId,
    BSTR bstrText);

void SetElementText(
    IUnknown* punkElem,
    BSTR bstrText);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
HTML 要素の ID。

*テキスト*<br/>
`innerText` プロパティの新しい値。

*パンクレム*<br/>
HTML`IUnknown`要素のポインター。

## <a name="cdhtmldialogsetexternaldispatch"></a><a name="setexternaldispatch"></a>ダイアログ::外部ディスパッチを設定します。

ホストのインターフェイスを`IDispatch`設定します。

```cpp
void SetExternalDispatch(IDispatch* pdispExternal);
```

### <a name="parameters"></a>パラメーター

*外部*<br/>
新しい`IDispatch`インターフェイス。

## <a name="cdhtmldialogsethostflags"></a><a name="sethostflags"></a>ダイアログ::セットホストフラグ

ホスト UI フラグを設定します。

```cpp
void SetHostFlags(DWORD dwFlags);
```

### <a name="parameters"></a>パラメーター

*dwFlags*<br/>
可能な値については、Windows SDK の[「DOCHOSTUIFLAG」](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753277\(v=vs.85\))を参照してください。

## <a name="cdhtmldialogshowcontextmenu"></a><a name="showcontextmenu"></a>ダイアログ::コンテキストメニューを表示します。

コンテキスト メニューが表示されようとしているときに呼び出されます。

```
STDMETHOD(ShowContextMenu)(
    DWORD dwID,
    POINT* ppt,
    IUnknown* pcmdtReserved,
    IDispatch* pdispReserved);
```

### <a name="parameters"></a>パラメーター

*Dwid*<br/>
次*を参照*してください。 [IDocHostUIHandler::ShowContextMenu](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753264\(v=vs.85\))

*Ppt*<br/>
Windows SDK`IDocHostUIHandler::ShowContextMenu`の*ppt*を参照してください。

*pcmdt予約済み*<br/>
Windows SDK の`IDocHostUIHandler::ShowContextMenu`*pcmdt 予約*済みを参照してください。

*pdisp 予約済み*<br/>
Windows SDK の`IDocHostUIHandler::ShowContextMenu`*「pdisp 予約済み*」を参照してください。

### <a name="return-value"></a>戻り値

S_FALSEを返します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明[されているように](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753264\(v=vs.85\))、CDHtmlDialog の実装です。

## <a name="cdhtmldialogshowui"></a><a name="showui"></a>ダイアログ::ショーUI

ホストの UI を表示します。

```
STDMETHOD(ShowUI)(
    DWORD dwID,
    IOleInPlaceActiveObject* pActiveObject,
    IOleCommandTarget* pCommandTarget,
    IOleInPlaceFrame* pFrame,
    IOleInPlaceUIWindow* pDoc);
```

### <a name="parameters"></a>パラメーター

*Dwid*<br/>
Windows SDK[の](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753265\(v=vs.85\))*DwID*を参照してください。

*オブジェクトを使用します。*<br/>
の「d *pActiveObject」*`IDocHostUIHandler::ShowUI`を参照してください。

*をクリックします。*<br/>
Windows SDK の`IDocHostUIHandler::ShowUI` *p コマンドターゲット*を参照してください。

*フレーム*<br/>
Windows SDK`IDocHostUIHandler::ShowUI`の*pFrame*を参照してください。

*pDoc*<br/>
の *「」の「pDoc」*`IDocHostUIHandler::ShowUI`を参照してください。

### <a name="return-value"></a>戻り値

S_FALSEを返します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、CDHtmlDialog の[IDocHostUIHandler::ShowUI](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753265\(v=vs.85\))の実装です。

## <a name="cdhtmldialogtranslateaccelerator"></a><a name="translateaccelerator"></a>ダイアログ::変換アクセラレータ

メニュー アクセラレータ キー メッセージを処理するために呼び出されます。

```
STDMETHOD(TranslateAccelerator)(
    LPMSG lpMsg,
    const GUID* pguidCmdGroup,
    DWORD nCmdID);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
Windows SDK[の](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753266\(v=vs.85\))*lpMsg*を参照してください。

*グループ化*<br/>
の *「」*`IDocHostUIHandler::TranslateAccelerator`を参照してください。

*をクリックします。*<br/>
Windows SDK の`IDocHostUIHandler::TranslateAccelerator` *nCmdID*を参照してください。

### <a name="return-value"></a>戻り値

S_FALSEを返します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、CDHtmlDialog の[IDocHostUIHandler::翻訳アクセラレータ](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753266\(v=vs.85\))の実装です。

## <a name="cdhtmldialogtranslateurl"></a><a name="translateurl"></a>ダイアログ::翻訳Url

読み込む URL を変更するために呼び出されます。

```
STDMETHOD(TranslateUrl)(
    DWORD dwTranslate,
    OLECHAR* pchURLIn,
    OLECHAR** ppchURLOut);
```

### <a name="parameters"></a>パラメーター

*dw翻訳*<br/>
Windows SDK の *「DwTranslate」*[を](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753267\(v=vs.85\))参照してください。

*プチュリン*<br/>
Windows SDK`IDocHostUIHandler::TranslateUrl`*の「pchURLIn」* を参照してください。

*を実行する*<br/>
の *「」*`IDocHostUIHandler::TranslateUrl`を参照してください。

### <a name="return-value"></a>戻り値

S_FALSEを返します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明[されているように](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753267\(v=vs.85\))、CDHtmlDialog の実装です。

## <a name="cdhtmldialogupdateui"></a><a name="updateui"></a>ダイアログ::アップデートUI

コマンドの状態が変更されたことをホストに通知するために呼び出されます。

```
STDMETHOD(UpdateUI)(void);
```

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、CDHtmlDialog の[IDocHostUIHandler::UpdateUI](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753268\(v=vs.85\))の実装です。

## <a name="see-also"></a>関連項目

[サンプルの検索](../../overview/visual-cpp-samples.md)<br/>
[DDX_DHtml Helper マクロ](#ddx_dhtml_helper_macros)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)
