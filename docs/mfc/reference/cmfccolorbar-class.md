---
title: CMFCColorBar クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCColorBar
- AFXCOLORBAR/CMFCColorBar
- AFXCOLORBAR/CMFCColorBar::CMFCColorBar
- AFXCOLORBAR/CMFCColorBar::ContextToSize
- AFXCOLORBAR/CMFCColorBar::CreateControl
- AFXCOLORBAR/CMFCColorBar::Create
- AFXCOLORBAR/CMFCColorBar::EnableAutomaticButton
- AFXCOLORBAR/CMFCColorBar::EnableOtherButton
- AFXCOLORBAR/CMFCColorBar::GetColor
- AFXCOLORBAR/CMFCColorBar::GetCommandID
- AFXCOLORBAR/CMFCColorBar::GetHighlightedColor
- AFXCOLORBAR/CMFCColorBar::GetHorzMargin
- AFXCOLORBAR/CMFCColorBar::GetVertMargin
- AFXCOLORBAR/CMFCColorBar::IsTearOff
- AFXCOLORBAR/CMFCColorBar::SetColor
- AFXCOLORBAR/CMFCColorBar::SetColorName
- AFXCOLORBAR/CMFCColorBar::SetCommandID
- AFXCOLORBAR/CMFCColorBar::SetDocumentColors
- AFXCOLORBAR/CMFCColorBar::SetHorzMargin
- AFXCOLORBAR/CMFCColorBar::SetVertMargin
- AFXCOLORBAR/CMFCColorBar::AdjustLocations
- AFXCOLORBAR/CMFCColorBar::AllowChangeTextLabels
- AFXCOLORBAR/CMFCColorBar::AllowShowOnList
- AFXCOLORBAR/CMFCColorBar::CalcSize
- AFXCOLORBAR/CMFCColorBar::CreatePalette
- AFXCOLORBAR/CMFCColorBar::GetColorGridSize
- AFXCOLORBAR/CMFCColorBar::GetExtraHeight
- AFXCOLORBAR/CMFCColorBar::InitColors
- AFXCOLORBAR/CMFCColorBar::OnKey
- AFXCOLORBAR/CMFCColorBar::OnSendCommand
- AFXCOLORBAR/CMFCColorBar::OnUpdateCmdUI
- AFXCOLORBAR/CMFCColorBar::OpenColorDialog
- AFXCOLORBAR/CMFCColorBar::Rebuild
- AFXCOLORBAR/CMFCColorBar::SelectPalette
- AFXCOLORBAR/CMFCColorBar::SetPropList
- AFXCOLORBAR/CMFCColorBar::ShowCommandMessageString
dev_langs:
- C++
helpviewer_keywords:
- CMFCColorBar [MFC], CMFCColorBar
- CMFCColorBar [MFC], ContextToSize
- CMFCColorBar [MFC], CreateControl
- CMFCColorBar [MFC], Create
- CMFCColorBar [MFC], EnableAutomaticButton
- CMFCColorBar [MFC], EnableOtherButton
- CMFCColorBar [MFC], GetColor
- CMFCColorBar [MFC], GetCommandID
- CMFCColorBar [MFC], GetHighlightedColor
- CMFCColorBar [MFC], GetHorzMargin
- CMFCColorBar [MFC], GetVertMargin
- CMFCColorBar [MFC], IsTearOff
- CMFCColorBar [MFC], SetColor
- CMFCColorBar [MFC], SetColorName
- CMFCColorBar [MFC], SetCommandID
- CMFCColorBar [MFC], SetDocumentColors
- CMFCColorBar [MFC], SetHorzMargin
- CMFCColorBar [MFC], SetVertMargin
- CMFCColorBar [MFC], AdjustLocations
- CMFCColorBar [MFC], AllowChangeTextLabels
- CMFCColorBar [MFC], AllowShowOnList
- CMFCColorBar [MFC], CalcSize
- CMFCColorBar [MFC], CreatePalette
- CMFCColorBar [MFC], GetColorGridSize
- CMFCColorBar [MFC], GetExtraHeight
- CMFCColorBar [MFC], InitColors
- CMFCColorBar [MFC], OnKey
- CMFCColorBar [MFC], OnSendCommand
- CMFCColorBar [MFC], OnUpdateCmdUI
- CMFCColorBar [MFC], OpenColorDialog
- CMFCColorBar [MFC], Rebuild
- CMFCColorBar [MFC], SelectPalette
- CMFCColorBar [MFC], SetPropList
- CMFCColorBar [MFC], ShowCommandMessageString
ms.assetid: 4756ee40-25a5-4cee-af7f-acab7993d1c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a8c5b1a1bd1358caa491370b2e38b35bde1f8fc7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46387520"
---
# <a name="cmfccolorbar-class"></a>CMFCColorBar クラス

`CMFCColorBar`クラスは、ドキュメントやアプリケーションで色を選択できるドッキング コントロール バーを表します。

## <a name="syntax"></a>構文

```
class CMFCColorBar : public CMFCPopupMenuBar
```

## <a name="members"></a>メンバー

### <a name="protected-constructors"></a>プロテクト コンストラクター

|名前|説明|
|----------|-----------------|
|[CMFCColorBar::CMFCColorBar](#cmfccolorbar)|`CMFCColorBar` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCColorBar::ContextToSize](#contexttosize)|カラー バー コントロールのボタンを格納する必要があり、そのボタンの位置を調整する垂直および水平方向の余白を計算します。|
|[CMFCColorBar::CreateControl](#createcontrol)|カラー バーのコントロール ウィンドウを作成しにアタッチします、`CMFCColorBar`オブジェクト、および指定されたカラー パレットを格納するコントロールのサイズを変更します。|
|[CMFCColorBar::Create](#create)|カラー バー コントロール ウィンドウを作成し、それにアタッチ、`CMFCColorBar`オブジェクト。|
|[CMFCColorBar::EnableAutomaticButton](#enableautomaticbutton)|自動ボタンの表示と非表示を切り替えます。|
|[CMFCColorBar::EnableOtherButton](#enableotherbutton)|有効または、ユーザーがその他の色を選択できるダイアログ ボックスの表示を無効にします。|
|[CMFCColorBar::GetColor](#getcolor)|現在選択されている色を取得します。|
|[CMFCColorBar::GetCommandID](#getcommandid)|現在のカラー バー コントロールのコマンド ID を取得します。|
|[CMFCColorBar::GetHighlightedColor](#gethighlightedcolor)|色のボタンにフォーカスを示す色を取得します。つまり、ボタンは*ホット*します。|
|[CMFCColorBar::GetHorzMargin](#gethorzmargin)|水平右のマージンを取得します。|
|[CMFCColorBar::GetVertMargin](#getvertmargin)|上部または下部にある色のセルとクライアント領域の境界の間のスペースは縦の余白を取得します。|
|[CMFCColorBar::IsTearOff](#istearoff)|現在のカラー バーがドッキングできるかどうかを示します。|
|[CMFCColorBar::SetColor](#setcolor)|現在選択されている色を設定します。|
|[CMFCColorBar::SetColorName](#setcolorname)|指定した色の新しい名前を設定します。|
|[CMFCColorBar::SetCommandID](#setcommandid)|カラー バー コントロールの新しいコマンド ID を設定します。|
|[CMFCColorBar::SetDocumentColors](#setdocumentcolors)|現在のドキュメントで使用される色の一覧を設定します。|
|[CMFCColorBar::SetHorzMargin](#sethorzmargin)|水平右のマージンを設定します。|
|[CMFCColorBar::SetVertMargin](#setvertmargin)|上部または下部にある色のセルとクライアント領域の境界間のスペースである縦の余白を設定します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CMFCColorBar::AdjustLocations](#adjustlocations)|カラー バー コントロールの色のボタンの位置を調整します。|
|[CMFCColorBar::AllowChangeTextLabels](#allowchangetextlabels)|色のボタンのテキスト ラベルを変更できるかどうかを示します。|
|[CMFCColorBar::AllowShowOnList](#allowshowonlist)|カラー バーのコントロール オブジェクトは、カスタマイズのプロセス中にツールバーの一覧に表示できるかどうかを示します。|
|[CMFCColorBar::CalcSize](#calcsize)|レイアウトの計算プロセスの一環としてフレームワークによって呼び出されます。|
|[CMFCColorBar::CreatePalette](#createpalette)|色の配列の指定した色でパレットを初期化します。|
|[CMFCColorBar::GetColorGridSize](#getcolorgridsize)|カラー バー コントロールのグリッドの行と列の数を計算します。|
|[CMFCColorBar::GetExtraHeight](#getextraheight)|その他のユーザー インターフェイス要素を表示します。 現在のカラー バーを必要とする追加の高さを計算、**他**ボタンやドキュメントの色。|
|[CMFCColorBar::InitColors](#initcolors)|色のカラー パレットを指定またはシステムの既定のパレットの色の配列を初期化します。|
|[CMFCColorBar::OnKey](#onkey)|ユーザーがキーボード ボタンを押したときに、フレームワークによって呼び出されます。|
|[CMFCColorBar::OnSendCommand](#onsendcommand)|ポップアップ コントロールの階層構造を閉じるために、フレームワークによって呼び出されます。|
|[CMFCColorBar::OnUpdateCmdUI](#onupdatecmdui)|有効にするか、項目が表示される前に、カラー バー コントロールのユーザー インターフェイス項目を無効にするためにフレームワークによって呼び出されます。|
|[CMFCColorBar::OpenColorDialog](#opencolordialog)|色のダイアログ ボックスを表示します。|
|[CMFCColorBar::Rebuild](#rebuild)|カラー バーのコントロールを完全に再描画します。|
|[CMFCColorBar::SelectPalette](#selectpalette)|現在のカラー バー コントロールの親のボタンのパレットを指定したデバイス コンテキストの論理パレットを設定します。|
|[CMFCColorBar::SetPropList](#setproplist)|セット、`m_pWndPropList`プロパティ グリッド コントロールに指定されたポインターへのデータ メンバーを保護します。|
|[CMFCColorBar::ShowCommandMessageString](#showcommandmessagestring)|ステータス バーにメッセージ行を更新するカラー バー コントロールを所有しているフレーム ウィンドウを要求します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|`m_bInternal`|マウス イベントを処理するかどうかを決定するブール値フィールド。 通常、このフィールドが TRUE で、カスタマイズ モードが FALSE のときに、マウス イベントは処理されます。|
|`m_bIsEnabled`|コントロールが有効になっているかどうかを示すブール値。|
|`m_bIsTearOff`|カラー バーのコントロールがドッキングをサポートしているかどうかを示すブール値。|
|`m_BoxSize`|A [CSize](../../atl-mfc-shared/reference/csize-class.md)カラー バーのグリッドでセルのサイズを指定するオブジェクト。|
|`m_bShowDocColorsWhenDocked`|カラー バーがドッキングされているときに、ドキュメントの色を表示するかどうかを示すブール値。 詳細については、次を参照してください。 [CMFCColorBar::SetDocumentColors](#setdocumentcolors)します。|
|`m_bStdColorDlg`|標準のシステム カラーのダイアログ ボックスを表示するかどうかを示すブール値、または[CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md)  ダイアログ ボックス。 詳細については、次を参照してください。 [CMFCColorBar::EnableOtherButton](#enableotherbutton)します。|
|`m_ColorAutomatic`|A [COLORREF](/windows/desktop/gdi/colorref)自動の現在の色を格納します。 詳細については、次を参照してください。 [CMFCColorBar::EnableOtherButton](#enableotherbutton)します。|
|`m_ColorNames`|[CMap](../../mfc/reference/cmap-class.md)名で色の RGB のセットを関連付けるオブジェクト。|
|`m_colors`|A [CArray](../../mfc/reference/carray-class.md)の[COLORREF](/windows/desktop/gdi/colorref)カラー バー コントロールに表示される色を含む値。|
|`m_ColorSelected`|A [COLORREF](/windows/desktop/gdi/colorref)値が、ユーザーがカラー バー コントロールで選択された現在の色。|
|`m_lstDocColors`|A [CList](../../mfc/reference/clist-class.md)の[COLORREF](/windows/desktop/gdi/colorref)ドキュメントで現在使用されている色を含む値。|
|`m_nCommandID`|色のボタンのコマンド ID は、符号なし整数。|
|`m_nHorzMargin`|色のグリッドの色のボタンの間の水平方向の余白の整数。|
|`m_nHorzOffset`|色のボタンの中心に水平方向のオフセットを示す整数。 この値はテキストまたは色だけでなくイメージ ボタンを表示する場合に重要です。|
|`m_nNumColumns`|色のカラー バー コントロールのグリッドの列の数を表す整数。|
|`m_nNumColumnsVert`|色の垂直方向にグリッドの列の数を表す整数。|
|`m_nNumRowsHorz`|色の水平方向のグリッドの列の数を表す整数。|
|`m_nRowHeight`|行の色のグリッドの色のボタンの高さの整数。|
|`m_nVertMargin`|色のグリッドの色のボタンの間の垂直方向の余白の整数。|
|`m_nVertOffset`|色のボタンの中央に縦方向のオフセットの整数。 この値はテキストまたは色だけでなくイメージ ボタンを表示する場合に重要です。|
|`m_Palette`|A [CPalette](../../mfc/reference/cpalette-class.md)のカラー バー コントロールで使用される色。|
|`m_pParentBtn`|ポインターを[CMFCColorButton](../../mfc/reference/cmfccolorbutton-class.md)は現在のボタンの親となるオブジェクト。 色のボタンがツール バー コントロールの階層では、または、カラー プロパティ グリッド コントロールでは、この値は重要です。|
|`m_pParentRibbonBtn`|ポインターを[CMFCRibbonColorButton](../../mfc/reference/cmfcribboncolorbutton-class.md)内の現在のボタンの親のボタンをリボンには、オブジェクト。 色のボタンがツール バー コントロールの階層では、または、カラー プロパティ グリッド コントロールでは、この値は重要です。|
|`m_pWndPropList`|ポインターを[CMFCPropertyGridCtrl](../../mfc/reference/cmfcpropertygridctrl-class.md)オブジェクト。|
|`m_strAutoColor`|A [CString](../../atl-mfc-shared/reference/cstringt-class.md)に表示されるテキストである、**自動**ボタンをクリックします。 詳細については、次を参照してください。 [CMFCColorBar::EnableAutomaticButton](#enableautomaticbutton)します。|
|`m_strDocColors`|A [CString](../../atl-mfc-shared/reference/cstringt-class.md)ドキュメントの色のボタンに表示されるテキストであります。 詳細については、次を参照してください。 [CMFCColorBar::SetDocumentColors](#setdocumentcolors)します。|
|`m_strOtherColor`|A [CString](../../atl-mfc-shared/reference/cstringt-class.md)に表示されるテキストである、*他*ボタンをクリックします。 詳細については、次を参照してください。 [CMFCColorBar::EnableOtherButton](#enableotherbutton)します。|

## <a name="remarks"></a>Remarks

通常、作成しないと、`CMFCColorBar`オブジェクトに直接します。 代わりに、 [CMFCColorMenuButton クラス](../../mfc/reference/cmfccolormenubutton-class.md)(メニューおよびツールバーで使用)、または[CMFCColorButton クラス](../../mfc/reference/cmfccolorbutton-class.md)作成、`CMFCColorBar`オブジェクト。

`CMFCColorBar`クラスには、次の機能が用意されています。

- ドキュメントの色の一覧が自動的に調整します。

- 保存し、ドキュメントの状態と共に、その状態を復元します。

- 「自動」のボタンを管理します。

- 使用して、 [CMFCColorPickerCtrl クラス](../../mfc/reference/cmfccolorpickerctrl-class.md)コントロールをカスタムの色を選択します。

- 「ティアオフ」状態をサポートしています (これを使用して作成された場合、 [CMFCColorMenuButton クラス](../../mfc/reference/cmfccolormenubutton-class.md))。

組み込む、`CMFCColorBar`をアプリケーションに機能します。

1. 通常のメニュー ボタンを作成し、ID、たとえば ID_CHAR_COLOR を割り当てます。

1. フレーム ウィンドウ クラスでオーバーライド、 [CFrameWndEx::OnShowPopupMenu](../../mfc/reference/cframewndex-class.md#onshowpopupmenu)メソッドと置換の通常のメニュー ボタンを[CMFCColorMenuButton クラス](../../mfc/reference/cmfccolormenubutton-class.md)オブジェクト (呼び出して[CMFCToolBar:: ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton))。

1. すべてのスタイルを設定および有効化またはの機能を無効にする、`CMFCColorBar`中にオブジェクト[CMFCColorMenuButton クラス](../../mfc/reference/cmfccolormenubutton-class.md)作成します。 `CMFCColorMenuButton`オブジェクトを動的に作成、 `CMFCColorBar` framework 呼び出し後、オブジェクト、`CreatePopupMenu`メソッド。

ユーザーは、カラー バーのコントロール ボタンをクリックすると、フレームワークを使用して、`ON_COMMAND`カラー バー コントロールの親に通知するマクロ。 マクロでは、コマンドの ID パラメーターは、手順 1 (この例では ID_CHAR_COLOR) のカラー バーのコントロール ボタンに割り当てられている値です。 詳細については、次を参照してください、 [CMFCColorMenuButton クラス](../../mfc/reference/cmfccolormenubutton-class.md)、 [CMFCColorButton クラス](../../mfc/reference/cmfccolorbutton-class.md)、 [CMFCColorPickerCtrl クラス](../../mfc/reference/cmfccolorpickerctrl-class.md)、 [CFrameWndEx クラス。](../../mfc/reference/cframewndex-class.md)、および[CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)クラス。

## <a name="example"></a>例

次の例は、さまざまなメソッドを使用してカラー バーを構成する方法を示します、`CMFCColorBar`クラス。 メソッドで、水平および垂直方向の余白を設定、その他のボタンを有効にする、カラー バー コントロールのウィンドウを作成、および現在選択されている色を設定します。 この例は、[新しいコントロール サンプル](../../visual-cpp-samples.md)します。

[!code-cpp[NVC_MFC_NewControls#1](../../mfc/reference/codesnippet/cpp/cmfccolorbar-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#2](../../mfc/reference/codesnippet/cpp/cmfccolorbar-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)

[CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)

[CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md)

[CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxcolorbar.h

##  <a name="adjustlocations"></a>  CMFCColorBar::AdjustLocations

カラー バー コントロールの色のボタンの位置を調整します。

```
virtual void AdjustLocations();
```

### <a name="remarks"></a>Remarks

このメソッドは、WM_SIZE メッセージの処理中に、フレームワークによって呼び出されます。

##  <a name="allowchangetextlabels"></a>  CMFCColorBar::AllowChangeTextLabels

色のボタンのテキスト ラベルを変更できるかどうかを示します。

```
virtual BOOL AllowChangeTextLabels() const;
```

### <a name="return-value"></a>戻り値

常に FALSE です。

### <a name="remarks"></a>Remarks

既定では、このメソッド常に FALSE を返します、つまり、テキスト ラベルを変更することはできません。 テキスト ラベルを変更を有効にするには、このメソッドをオーバーライドします。

##  <a name="allowshowonlist"></a>  CMFCColorBar::AllowShowOnList

カラー バーのコントロール オブジェクトは、カスタマイズのプロセス中にツールバーの一覧に表示できるかどうかを示します。

```
virtual BOOL AllowShowOnList() const;
```

### <a name="return-value"></a>戻り値

常に TRUE です。

### <a name="remarks"></a>Remarks

既定では、常に TRUE を返します、つまり、フレームワークは、カスタマイズのプロセス中に、カラー バー コントロールを表示することができます。 さまざまな動作を実装するには、このメソッドをオーバーライドします。

##  <a name="calcsize"></a>  CMFCColorBar::CalcSize

レイアウトの計算プロセスの一環としてフレームワークによって呼び出されます。

```
virtual CSize CalcSize(BOOL bVertDock);
```

### <a name="parameters"></a>パラメーター

*bVertDock*<br/>
[in]カラー バーのコントロールが垂直方向にドッキングされていることを指定する場合は TRUEカラー バーのコントロールが水平方向にドッキングされていることを指定する場合は FALSE。

### <a name="return-value"></a>戻り値

カラー バー コントロールのボタンの色の配列のサイズ。

##  <a name="cmfccolorbar"></a>  CMFCColorBar::CMFCColorBar

`CMFCColorBar` オブジェクトを構築します。

```
CMFCColorBar(
    const CArray<COLORREF,COLORREF>& colors,
    COLORREF color,
    LPCTSTR lpszAutoColor,
    LPCTSTR lpszOtherColor,
    LPCTSTR lpszDocColors,
    CList<COLORREF,COLORREF>& lstDocColors,
    int nColumns,
    int nRowsDockHorz,
    int nColDockVert,
    COLORREF colorAutomatic,
    UINT nCommandID,
    CMFCColorButton* pParentBtn);


CMFCColorBar(
    const CArray<COLORREF,COLORREF>& colors,
    COLORREF color,
    LPCTSTR lpszAutoColor,
    LPCTSTR lpszOtherColor,
    LPCTSTR lpszDocColors,
    CList<COLORREF,COLORREF>& lstDocColors,
    int nColumns,
    COLORREF colorAutomatic,
    UINT nCommandID,
    CMFCRibbonColorButton* pParentRibbonBtn);


CMFCColorBar(
    CMFCColorBar& src,
    UINT uiCommandID);
```

### <a name="parameters"></a>パラメーター

*色*<br/>
[in]フレームワークがカラー バー コントロールに表示される色の配列。

*色*<br/>
[in]最初に選択した色。

*lpszAutoColor*<br/>
[in]テキスト ラベル、*自動*(既定値) の色のボタン、または NULL。

自動ボタンの標準的なラベルが**自動**します。

*lpszOtherColor*<br/>
[in]テキスト ラベル、*他*ボタンが表示されるより色の選択、または NULL。

その他のボタンの標準のラベルは**他の色**。

*lpszDocColors*<br/>
[in]ドキュメントの色のボタンのテキスト ラベル。 ドキュメントのカラー パレットには、ドキュメントが現在使用されているすべての色が一覧表示します。

*lstDocColors*<br/>
[in]ドキュメントが現在使用されている色の一覧。

*nColumns*<br/>
[in]色の配列を含む列の数。

*nRowsDockHorz*<br/>
[in]カラー バーが水平方向にドッキングされている行の数。

*nColDockVert*<br/>
[in]カラー バーが垂直方向にドッキングされている列の数。

*colorAutomatic*<br/>
[in]自動ボタンをクリックすると、フレームワークが適用される既定の色。

*nCommandID*<br/>
[in]カラー バーのコントロールのコマンド id。

*pParentBtn*<br/>
[in]親ボタンへのポインター。

*src*<br/>
[in]既存の`CMFCColorBar`新しいにコピーされるオブジェクト`CMFCColorBar`オブジェクト。

*uiCommandID*<br/>
[in]コマンド id。

##  <a name="contexttosize"></a>  CMFCColorBar::ContextToSize

カラー バー コントロールのボタンを格納する必要があり、これらのボタンの位置を調整する垂直および水平方向の余白を計算します。

```
void ContextToSize(
    BOOL bSquareButtons = TRUE,
    BOOL bCenterButtons = TRUE);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*bSquareButtons*|[in]カラー バー コントロールのボタンの形状が四角形であることを指定する場合は TRUEそれ以外の場合、FALSE です。 既定値は TRUE です。|
|*bCenterButtons*|[in]カラー バーのコントロール ボタンの表示コンテンツを中央揃えにするかを指定する場合は TRUEそれ以外の場合、FALSE です。 既定値は TRUE です。|

### <a name="remarks"></a>Remarks

##  <a name="create"></a>  CMFCColorBar::Create

カラー バー コントロール ウィンドウを作成し、それにアタッチ、`CMFCColorBar`オブジェクト。

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle,
    UINT nID,
    CPalette* pPalette=NULL,
    int nColumns=0,
    int nRowsDockHorz=0,
    int nColDockVert=0);
```

### <a name="parameters"></a>パラメーター

*pParentWnd*<br/>
[in]親ウィンドウへのポインター。

*dwStyle*<br/>
[in]ビットごとの組み合わせ (OR)[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)します。

*nID*<br/>
[in]コマンド id。

*pPalette*<br/>
[in]色のパレットへのポインター。 既定では NULL です。

*nColumns*<br/>
[in]カラー バーのコントロール内の列の数。 既定値は 0 です。

*nRowsDockHorz*<br/>
[in]水平方向にドッキングしたときに、カラー バー コントロールの行の数。 既定値は 0 です。

*nColDockVert*<br/>
[in]垂直方向にドッキングしたときに、カラー バー コントロールに列の数。 既定値は 0 です。

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

構築する、`CMFCColorBar`オブジェクト、クラス コンス トラクター、このメソッドを呼び出します。 `Create`メソッドは、Windows コントロールを作成し、色の一覧を初期化します。

##  <a name="createcontrol"></a>  CMFCColorBar::CreateControl

カラー バーのコントロール ウィンドウを作成しにアタッチします、`CMFCColorBar`オブジェクト、および指定されたカラー パレットを格納するコントロールのウィンドウのサイズを変更します。

```
virtual BOOL CreateControl(
    CWnd* pParentWnd,
    const CRect& rect,
    UINT nID,
    int nColumns=-1,
    CPalette* pPalette=NULL);
```

### <a name="parameters"></a>パラメーター

*pParentWnd*<br/>
[in]親ウィンドウへのポインター。 Nll は指定できません。

*rect*<br/>
[in]カラー バーにコントロールを描画する場所を指定する外接する四角形。

*nID*<br/>
[in]コントロールの id。

*nColumns*<br/>
[in]カラー バーのコントロール内の列数に最適です。 このメソッドは、指定されたカラー パレットに合わせて列数を変更します。 既定値は、-1 で、このパラメーターが指定されていないことを意味します。

*pPalette*<br/>
[in]パレットの色、または NULL へのポインター。 このパラメーターが NULL の場合、このメソッドは、20 の色が指定した場合と、カラー バー コントロールのサイズを計算します。 既定では NULL です。

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合は FALSE です。

### <a name="remarks"></a>Remarks

このメソッドを使用して、 *rect*、 *nColumns*と*pPalette*パラメーターを適切な数または行数とカラー バーのコントロールと 呼び出し内の列を計算します[CMFCColorBar::Create](#create)メソッド。

##  <a name="createpalette"></a>  CMFCColorBar::CreatePalette

色の配列の指定した色でパレットを初期化します。

```
static BOOL CreatePalette(
    const CArray<COLORREF, COLORREF>& arColors,
    CPalette& palette);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*arColors*|[in]色の配列。|
|*パレット*|[in]色パレット。|

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合、FALSE です。

##  <a name="enableautomaticbutton"></a>  CMFCColorBar::EnableAutomaticButton

自動ボタンの表示と非表示を切り替えます。

```
void EnableAutomaticButton(
    LPCTSTR lpszLabel,
    COLORREF colorAutomatic,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>パラメーター

*lpszLabel*<br/>
[in]テキスト ラベル、*自動*(既定値) の色のボタン、または NULL。

自動ボタンの標準的なラベルが**自動**します。

*colorAutomatic*<br/>
[in]自動ボタンをクリックすると、フレームワークが適用される既定の色。

*bEnable*<br/>
[in]自動ボタンを有効にする場合は TRUE自動ボタンを無効にする場合は FALSE。 既定値は TRUE です。

### <a name="remarks"></a>Remarks

場合に自動ボタンのテキスト ラベルが削除された、 *lpszLabel*パラメーターが NULL または*bEnable*パラメーターは FALSE。

##  <a name="enableotherbutton"></a>  CMFCColorBar::EnableOtherButton

有効または、ユーザーがその他の色を選択できるダイアログ ボックスの表示を無効にします。

```
void EnableOtherButton(
    LPCTSTR lpszLabel,
    BOOL bAltColorDlg=TRUE,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>パラメーター

*lpszLabel*<br/>
[in]テキスト ラベル、*他*ボタンが表示されるより色の選択、または NULL。

このボタンの標準的なラベルは**他の色**。

*bAltColorDlg*<br/>
[in]表示する場合は True、 [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) ; ダイアログ ボックス標準を表示する場合は FALSE [CColorDialog](../../mfc/reference/ccolordialog-class.md)  ダイアログ ボックス。 既定値は TRUE です。

*bEnable*<br/>
[in]ボタンを有効にする場合は TRUEボタンを無効にする場合は FALSE。 既定値は TRUE です。

##  <a name="getcolor"></a>  CMFCColorBar::GetColor

現在選択されている色を取得します。

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>戻り値

現在選択されている色です。

##  <a name="getcolorgridsize"></a>  CMFCColorBar::GetColorGridSize

カラー バー コントロールのグリッドの行と列の数を計算します。

```
CSize GetColorGridSize(BOOL bVertDock) const;
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*bVertDock*|[in]カラー バーが垂直方向にドッキングされたコントロールであるため、計算を実行する場合は TRUEそれ以外の場合、水平方向にドッキングされたコントロールの計算を実行します。|

### <a name="return-value"></a>戻り値

A [CSize](../../atl-mfc-shared/reference/csize-class.md)オブジェクト`cx`コンポーネントには、列と元の数が含まれている`cy`コンポーネントには、行の数が含まれています。

##  <a name="getcommandid"></a>  CMFCColorBar::GetCommandID

現在のカラー バー コントロールのコマンド ID を取得します。

```
UINT GetCommandID() const;
```

### <a name="return-value"></a>戻り値

コマンド id。

### <a name="remarks"></a>Remarks

フレームワークがの親に通知する WM_COMMAND メッセージのコマンド ID を送信するユーザーは、新しい色を選択するときに、`CMFCColorBar`オブジェクト。

##  <a name="getextraheight"></a>  CMFCColorBar::GetExtraHeight

など、その他のユーザー インターフェイス要素を表示する現在のカラー バーを必要とする追加の高さを計算、**他**ボタンやドキュメントの色。

```
int GetExtraHeight(int nNumColumns) const;
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*nNumColumns*|[in]場合は、カラー バー コントロールには、ドキュメントの色、ドキュメントの色のグリッドに表示する列の数が含まれています。 それ以外の場合、この値は使用されません。|

### <a name="return-value"></a>戻り値

必要な計算の余分な高さ。

##  <a name="gethighlightedcolor"></a>  CMFCColorBar::GetHighlightedColor

色のボタンにフォーカスを示す色を取得します。つまり、ボタンは*ホット*します。

```
COLORREF GetHighlightedColor() const;
```

### <a name="return-value"></a>戻り値

RGB 値。

### <a name="remarks"></a>Remarks

##  <a name="gethorzmargin"></a>  CMFCColorBar::GetHorzMargin

水平右のマージンを取得します。

```
int GetHorzMargin();
```

### <a name="return-value"></a>戻り値

水平方向の余白。

##  <a name="getvertmargin"></a>  CMFCColorBar::GetVertMargin

上部または下部にある色のセルとクライアント領域の境界の間のスペースは縦の余白を取得します。

```
int GetVertMargin() const;
```

### <a name="return-value"></a>戻り値

縦の余白。

##  <a name="initcolors"></a>  CMFCColorBar::InitColors

指定したパレットの色とシステムの既定のパレットの色の配列を初期化します。

```
static int InitColors(
    CPalette* pPalette,
    CArray<COLORREF, COLORREF>& arColors);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*pPalette*|[in]パレット オブジェクト、または NULL へのポインター。 このパラメーターが NULL の場合、このメソッドは、オペレーティング システムの既定のパレットを使用します。|
|*arColors*|[in]色の配列。|

### <a name="return-value"></a>戻り値

色の配列内の要素の数。

##  <a name="istearoff"></a>  CMFCColorBar::IsTearOff

現在のカラー バーがドッキングできるかどうかを示します。

```
BOOL IsTearOff() const;
```

### <a name="return-value"></a>戻り値

現在のカラー バー コントロールがドッキング可能な; は、TRUE を返します。それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

カラー バーのコントロールがドッキング可能な場合は、コントロール バーから破損し、別の場所にドッキングすることができます。

##  <a name="onkey"></a>  CMFCColorBar::OnKey

ユーザーがキーボード ボタンを押したときに、フレームワークによって呼び出されます。

```
virtual BOOL OnKey(UINT nChar);
```

### <a name="parameters"></a>パラメーター

*NChar*<br/>
[in]ユーザーが押されたキーの仮想キー コード。

### <a name="return-value"></a>戻り値

このメソッドは、指定したキーを処理する場合は TRUE。それ以外の場合、FALSE です。

##  <a name="onsendcommand"></a>  CMFCColorBar::OnSendCommand

ポップアップ コントロールの階層構造を閉じるために、フレームワークによって呼び出されます。

```
virtual BOOL OnSendCommand(const CMFCToolBarButton* pButton);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*pButton*|[in]ツールバー上に存在するコントロールへのポインター。|

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合、FALSE です。

##  <a name="onupdatecmdui"></a>  CMFCColorBar::OnUpdateCmdUI

有効にするか、項目が表示される前に、カラー バー コントロールのユーザー インターフェイス項目を無効にするためにフレームワークによって呼び出されます。

```
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,
    BOOL bDisableIfNoHndler);
```

### <a name="parameters"></a>パラメーター

*pTarget*<br/>
[in]更新するユーザー インターフェイス項目を含むウィンドウへのポインター。

*持たず*<br/>
[in]メッセージ マップでハンドラーが定義されていない場合は、ユーザー インターフェイス項目を無効にする場合は TRUEそれ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

項目がかどうか、表示するか有効になっているを知る必要があります、アプリケーションのユーザーには、ユーザー インターフェイスの項目がクリックすると、または無効にします。 コマンド メッセージのターゲットは、ON_UPDATE_COMMAND_UI コマンド ハンドラーを実装することでこの情報を提供します。 このメソッドを使用して、コマンドの処理を支援します。 詳細については、次を参照してください。 [CCmdUI クラス](../../mfc/reference/ccmdui-class.md)します。

##  <a name="opencolordialog"></a>  CMFCColorBar::OpenColorDialog

色のダイアログ ボックスを表示します。

```
virtual BOOL OpenColorDialog(
    const COLORREF colorDefault,
    COLORREF& colorRes);
```

### <a name="parameters"></a>パラメーター

*colorDefault*<br/>
[in]色のダイアログ ボックスが開いたときに、既定で選択されている色です。

*colorRes*<br/>
[out]ユーザーが選択した色。

### <a name="return-value"></a>戻り値

ユーザーが、色を選択した場合は TRUE。ユーザーには、[色] ダイアログ ボックスが取り消された場合は FALSE です。

### <a name="remarks"></a>Remarks

##  <a name="rebuild"></a>  CMFCColorBar::Rebuild

カラー バーのコントロールを完全に再描画します。

```
virtual void Rebuild();
```

##  <a name="selectpalette"></a>  CMFCColorBar::SelectPalette

現在のカラー バー コントロールの親のボタンのパレットを指定したデバイス コンテキストの論理パレットを設定します。

```
CPalette* SelectPalette(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*pDC*|[in]現在のカラー バー コントロールの親のボタンのデバイス コンテキストへのポインター。|

### <a name="return-value"></a>戻り値

現在のカラー バー コントロールの親のボタンのパレットで置き換えられるパレットへのポインター。

##  <a name="setcolor"></a>  CMFCColorBar::SetColor

現在選択されている色を設定します。

```
void SetColor(COLORREF color);
```

### <a name="parameters"></a>パラメーター

*色*<br/>
[in]RGB 色の値。

##  <a name="setcolorname"></a>  CMFCColorBar::SetColorName

指定した色の新しい名前を設定します。

```
static void SetColorName(
    COLORREF color,
    const CString& strName);
```

### <a name="parameters"></a>パラメーター

*色*<br/>
[in]色の RGB 値。

*strName*<br/>
[in]指定した色の新しい名前。

### <a name="remarks"></a>Remarks

このメソッドは、すべての指定した色の名前を変更`CMFCColorBar`アプリケーション内のオブジェクト。

##  <a name="setcommandid"></a>  CMFCColorBar::SetCommandID

カラー バー コントロールの新しいコマンド ID を設定します。

```
void SetCommandID(UINT nCommandID);
```

### <a name="parameters"></a>パラメーター

*nCommandID*<br/>
[in]コマンド id。

### <a name="remarks"></a>Remarks

カラー バー コントロールのコマンド ID を変更して、ID が変更されたコントロールの親ウィンドウを通知するため、このメソッドを呼び出します。

##  <a name="setdocumentcolors"></a>  CMFCColorBar::SetDocumentColors

現在のドキュメントで使用される色の一覧を設定します。

```
void SetDocumentColors(
    LPCTSTR lpszCaption,
    CList<COLORREF,COLORREF>& lstDocColors,
    BOOL bShowWhenDocked=FALSE);
```

### <a name="parameters"></a>パラメーター

*lpszCaption*<br/>
[in]カラー バーのコントロールがドッキングされていない場合に表示されるキャプション。

*lstDocColors*<br/>
[in]現在のドキュメントの色を置換する色の一覧。

*bShowWhenDocked*<br/>
[in]カラー バーのコントロールがドッキングしているときに、ドキュメントの色を表示する場合は TRUE。それ以外の場合、FALSE です。 既定値は FALSE です。

### <a name="remarks"></a>Remarks

*ドキュメントの色*は現在のドキュメントで使用される色。 フレームワークが自動的にドキュメントの色の一覧を保持しますが、このメソッドを使用してリストを変更することができます。

##  <a name="sethorzmargin"></a>  CMFCColorBar::SetHorzMargin

左側または右側の色のセルとクライアント領域の境界の間のスペースは水平方向の余白を設定します。

```
void SetHorzMargin(int nHorzMargin);
```

### <a name="parameters"></a>パラメーター

*nHorzMargin*<br/>
[in]水平方向の余白 (ピクセル)。

### <a name="remarks"></a>Remarks

既定で、 [CMFCColorBar::CMFCColorBar](#cmfccolorbar)コンス トラクターは、4 ピクセルを水平方向の余白を設定します。

##  <a name="setproplist"></a>  CMFCColorBar::SetPropList

セット、`m_pWndPropList`プロパティ グリッド コントロールに指定されたポインターへのデータ メンバーを保護します。

```
void SetPropList(CMFCPropertyGridCtrl* pWndList);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*pWndList*|[in]プロパティ グリッド コントロール オブジェクトへのポインター。|

##  <a name="setvertmargin"></a>  CMFCColorBar::SetVertMargin

上部または下部にある色のセルとクライアント領域の境界間のスペースである縦の余白を設定します。

```
void SetVertMargin(int nVertMargin);
```

### <a name="parameters"></a>パラメーター

*nVertMargin*<br/>
[in]縦の余白 (ピクセル)。

### <a name="remarks"></a>Remarks

既定で、 [CMFCColorBar::CMFCColorBar](#cmfccolorbar)コンス トラクターは、4 ピクセルに縦の余白を設定します。

##  <a name="showcommandmessagestring"></a>  CMFCColorBar::ShowCommandMessageString

ステータス バーにメッセージ行を更新するカラー バー コントロールを所有しているフレーム ウィンドウを要求します。

```
virtual void ShowCommandMessageString(UINT uiCmdId);
```

### <a name="parameters"></a>パラメーター

*uiCmdId*<br/>
[in]コマンド id。 (このパラメーターが無視されます)

### <a name="remarks"></a>Remarks

このメソッドは、カラー バー コントロールの所有者に WM_SETMESSAGESTRING メッセージを送信します。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)
