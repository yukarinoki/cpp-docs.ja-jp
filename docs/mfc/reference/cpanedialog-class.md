---
title: CPaneDialog クラス
ms.date: 11/04/2016
f1_keywords:
- CPaneDialog
- AFXPANEDIALOG/CPaneDialog
- AFXPANEDIALOG/CPaneDialog::Create
- AFXPANEDIALOG/CPaneDialog::HandleInitDialog
- AFXPANEDIALOG/CPaneDialog::SetOccDialogInfo
helpviewer_keywords:
- CPaneDialog [MFC], Create
- CPaneDialog [MFC], HandleInitDialog
- CPaneDialog [MFC], SetOccDialogInfo
ms.assetid: 48a6bb91-4b92-40f5-8907-b3270b146cf6
ms.openlocfilehash: ad1225034cc5eca8ca53b042ebe3b55db4a2cf09
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364123"
---
# <a name="cpanedialog-class"></a>CPaneDialog クラス

この`CPaneDialog`クラスは、モードレスのドッキング可能なダイアログ ボックスをサポートしています。

## <a name="syntax"></a>構文

```
class CPaneDialog : public CDockablePane
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|`CPaneDialog::CPaneDialog`|既定のコンストラクターです。|
|`CPaneDialog::~CPaneDialog`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ウィンドウダイアログ::作成](#create)|ドッキング可能なダイアログ ボックスを作成し、`CPaneDialog`オブジェクトにアタッチします。|
|`CPaneDialog::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|
|`CPaneDialog::GetThisClass`|このクラス型に関連付けられている[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|
|[ウィンドウダイアログ::ハンドルイニトダイアログ](#handleinitdialog)|[WM_INITDIALOG](/windows/win32/dlgbox/wm-initdialog)メッセージを処理します。 (再定義`CBasePane::HandleInitDialog`.)|
|`CPaneDialog::OnEraseBkgnd`|[WM_ERASEBKGND](/windows/win32/winmsg/wm-erasebkgnd)メッセージを処理します。 [(CWnd を再定義::OnEraseBkgnd](../../mfc/reference/cwnd-class.md#onerasebkgnd).)|
|`CPaneDialog::OnLButtonDblClk`|[WM_LBUTTONDBLCLK](/windows/win32/inputdev/wm-lbuttondblclk)メッセージを処理します。 [(CWnd を再定義::オンルボタンドブルクレック](../../mfc/reference/cwnd-class.md#onlbuttondblclk).)|
|`CPaneDialog::OnLButtonDown`|[WM_LBUTTONDOWN](/windows/win32/inputdev/wm-lbuttondown)メッセージを処理します。 [(CWnd を再定義::オンルボタンダウン](../../mfc/reference/cwnd-class.md#onlbuttondown).)|
|`CPaneDialog::OnUpdateCmdUI`|ダイアログ ボックス ウィンドウを更新するために、フレームワークによって呼び出されます。 [(CDockable ペインをオーバーライドします。:オンアップデートCmdUI](cdockablepane-class.md).)|
|`CPaneDialog::OnWindowPosChanging`|[WM_WINDOWPOSCHANGING](/windows/win32/winmsg/wm-windowposchanging)メッセージを処理します。 [(CWnd を再定義::オンウィンドウポスチェンジ](../../mfc/reference/cwnd-class.md#onwindowposchanging).)|
|[ウィンドウダイアログ::セットボックスダイアログインフォ](#setoccdialoginfo)|OLE コントロール コンテナであるダイアログ ボックスのテンプレートを指定します。|

## <a name="remarks"></a>解説

2`CPaneDialog`つの手順でオブジェクトを作成します。 まず、コード内にオブジェクトを構築します。 次に[、CPaneDialog::Create を](#create)呼び出します。 有効なリソース テンプレート名またはテンプレート ID を指定し、親ウィンドウへのポインターを渡す必要があります。 それ以外の場合、作成プロセスは失敗します。 ダイアログ ボックスでは、WS_CHILDとWS_VISIBLEスタイルを指定する必要があります。 WS_CLIPCHILDRENとWS_CLIPSIBLINGSスタイルも指定することをお勧めします。 詳細については、「ウィンドウ[スタイル」を](styles-used-by-mfc.md#window-styles)参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CDockablePane](../../mfc/reference/cdockablepane-class.md)

[ウィンドウダイアログ](../../mfc/reference/cpanedialog-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxpanedialog.h

## <a name="cpanedialogcreate"></a><a name="create"></a>ウィンドウダイアログ::作成

ドッキング ダイアログ ボックスを作成し、`CPaneDialog`オブジェクトにアタッチします。

```
BOOL Create(
    LPCTSTR lpszWindowName,
    CWnd* pParentWnd,
    BOOL bHasGripper,
    LPCTSTR lpszTemplateName,
    UINT nStyle,
    UINT nID,
    DWORD dwTabbedStyle= AFX_CBRS_REGULAR_TABS,
    DWORD dwControlBarStyle=AFX_DEFAULT_DOCKING_PANE_STYLE);

BOOL Create(
    LPCTSTR lpszWindowName,
    CWnd* pParentWnd,
    BOOL bHasGripper,
    UINT nIDTemplate,
    UINT nStyle,
    UINT nID);

BOOL Create(
    CWnd* pParentWnd,
    LPCTSTR lpszTemplateName,
    UINT nStyle,
    UINT nID);

BOOL Create(
    CWnd* pParentWnd,
    UINT nIDTemplate,
    UINT nStyle,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*名前をクリックします。*<br/>
[in]ドッキング ダイアログ ボックスの名前。

*pParentWnd*<br/>
[in]親ウィンドウへのポイント。

*bハスグリッパー*<br/>
[in]キャプション (グリッパー) を使用してドッキング ダイアログ ボックスを作成する場合は TRUE、それ以外の場合は FALSE。

*テンプレート名*<br/>
[in]リソース ダイアログ テンプレートの名前。

*nStyle*<br/>
[in]ウィンドウ スタイル。

*nID*<br/>
[in]コントロール ID。

*テンプレート*<br/>
[in]ダイアログ テンプレートのリソース ID。

*ドウタブードスタイル*<br/>
[in]ユーザーがこのコントロール ペインのキャプションに別のコントロール ペインをドラッグしたときに作成されるタブ付きウィンドウのスタイル。 既定値はAFX_CBRS_REGULAR_TABSです。 詳細については[、CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex)メソッドの「解説」セクションを参照してください。

*コントロール バースタイル*<br/>
[in]追加のスタイル属性。 既定値はAFX_DEFAULT_DOCKING_PANE_STYLEです。 詳細については[、CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex)メソッドの「解説」セクションを参照してください。

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

### <a name="example"></a>例

クラスでメソッドを使用する方法を`Create`次の例に`CPaneDialog`示します。 この例は、「ペイン[サイズの設定」のサンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_SetPaneSize#2](../../mfc/reference/codesnippet/cpp/cpanedialog-class_1.h)]
[!code-cpp[NVC_MFC_SetPaneSize#3](../../mfc/reference/codesnippet/cpp/cpanedialog-class_2.cpp)]

## <a name="cpanedialoghandleinitdialog"></a><a name="handleinitdialog"></a>ウィンドウダイアログ::ハンドルイニトダイアログ

[WM_INITDIALOG](/windows/win32/dlgbox/wm-initdialog)メッセージを処理します。

```
afx_msg LRESULT HandleInitDialog(
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>パラメーター

*wParam*<br/>
[in]既定のキーボード フォーカスを受け取るコントロールへのハンドル。

*lParam*<br/>
[in]追加の初期化データを指定します。

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合は FALSE。 また、TRUE は、キーボード フォーカスを*wParam*パラメーターで指定されたコントロールに設定します。FALSE を指定すると、既定のキーボード フォーカスを設定できなくなります。

### <a name="remarks"></a>解説

フレームワークは、このメソッドを使用して、コントロールとダイアログ ボックスの外観を初期化します。 フレームワークは、ダイアログ ボックスを表示する前に、このメソッドを呼び出します。

## <a name="cpanedialogsetoccdialoginfo"></a><a name="setoccdialoginfo"></a>ウィンドウダイアログ::セットボックスダイアログインフォ

OLE コントロール コンテナであるダイアログ ボックスのテンプレートを指定します。

```
virtual BOOL SetOccDialogInfo(_AFX_OCC_DIALOG_INFO* pOccDialogInfo);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[in]ダイアログ ボックス オブジェクトの作成に使用するダイアログ ボックス テンプレートへのポインター。 このパラメーターの値は、その後[COccManager::CreateDlgControls](../../mfc/reference/coccmanager-class.md#createdlgcontrols)メソッドに渡されます。

### <a name="return-value"></a>戻り値

常に TRUE。

### <a name="remarks"></a>解説

このメソッドは、OLE コントロール サイトと ActiveX コントロールを管理する[COccManager](../../mfc/reference/coccmanager-class.md)クラスをサポートします。 _AFX_OCC_DIALOG_INFO構造は、afxocc.h ヘッダー ファイルで定義されます。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CDockablePane クラス](../../mfc/reference/cdockablepane-class.md)<br/>
[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)
