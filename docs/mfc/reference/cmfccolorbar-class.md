---
title: CMFCColorBar クラス
ms.date: 11/04/2016
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
ms.openlocfilehash: 7b63fb66b800bd758c7f4c89c553e857ad9bbfbc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367768"
---
# <a name="cmfccolorbar-class"></a>CMFCColorBar クラス

この`CMFCColorBar`クラスは、ドキュメントまたはアプリケーションの色を選択できるドッキング コントロール バーを表します。

## <a name="syntax"></a>構文

```
class CMFCColorBar : public CMFCPopupMenuBar
```

## <a name="members"></a>メンバー

### <a name="protected-constructors"></a>プロテクト コンストラクター

|名前|説明|
|----------|-----------------|
|[CMFC カラー バー::CMFC カラー バー](#cmfccolorbar)|`CMFCColorBar` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[を変更します。](#contexttosize)|カラー バー コントロールのボタンを含めるために必要な垂直および水平の余白を計算し、それらのボタンの位置を調整します。|
|[コントロールの作成](#createcontrol)|カラー バー コントロール ウィンドウを作成し、`CMFCColorBar`オブジェクトにアタッチし、指定した色のパレットを含むコントロールのサイズを変更します。|
|[CMFCカラーバー::作成](#create)|カラー バー コントロール ウィンドウを作成し、オブジェクト`CMFCColorBar`にアタッチします。|
|[自動ボタンを有効にする](#enableautomaticbutton)|自動ボタンの表示/非表示を切り替えます。|
|[他のボタンを有効にします。](#enableotherbutton)|ユーザーが色を選択できるようにするダイアログ ボックスの表示を有効または無効にします。|
|[カラーバー::取得カラー](#getcolor)|現在選択されている色を取得します。|
|[をクリックします。](#getcommandid)|現在のカラー バー コントロールのコマンド ID を取得します。|
|[カラーバー::ハイライトされた色を取得します。](#gethighlightedcolor)|カラー ボタンにフォーカスがあることを示す色を取得します。つまり、ボタンは*ホット*です。|
|[バー::ゲッツマージン](#gethorzmargin)|左右のカラー セルとクライアント領域境界の間のスペースである水平マージンを取得します。|
|[を使用します。](#getvertmargin)|上または下のカラー セルとクライアント領域境界の間のスペースである垂直方向の余白を取得します。|
|[CMFCカラーバー::イステアオフ](#istearoff)|現在のカラー バーがドッキング可能かどうかを示します。|
|[カラーバー::セットカラー](#setcolor)|現在選択されている色を設定します。|
|[カラーバー::セットカラーネーム](#setcolorname)|指定した色の新しい名前を設定します。|
|[を設定します。](#setcommandid)|カラー バー コントロールの新しいコマンド ID を設定します。|
|[カラーを設定します。](#setdocumentcolors)|現在のドキュメントで使用されている色のリストを設定します。|
|[セットホーズマージン](#sethorzmargin)|左右のカラー セルとクライアント領域境界の間のスペースである水平マージンを設定します。|
|[CMFCカラーバー::セットバーマージン](#setvertmargin)|上または下のカラー セルとクライアント領域境界の間のスペースである垂直方向の余白を設定します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[場所を調整します。](#adjustlocations)|カラー バー コントロールのカラー ボタンの位置を調整します。|
|[を変更します。](#allowchangetextlabels)|カラー ボタンのテキスト ラベルを変更できるかどうかを示します。|
|[を表示します。](#allowshowonlist)|カスタマイズプロセス中に、カラー バー コントロール オブジェクトをツール バー リストに表示できるかどうかを示します。|
|[CMFCカラーバー::カルクサイズ](#calcsize)|レイアウト計算プロセスの一部としてフレームワークによって呼び出されます。|
|[パレットの作成](#createpalette)|指定した色の配列の色を使用してパレットを初期化します。|
|[コントロール のサイズを変更します。](#getcolorgridsize)|カラー バー コントロールのグリッド内の行数と列数を計算します。|
|[カラー バー::エクストラハイトを取得します。](#getextraheight)|現在のカラー バーで[**その他**]ボタン、ドキュメントの色などのユーザー インターフェイス要素を表示するために必要な高さを計算します。|
|[色の色](#initcolors)|指定したパレットまたはシステムの既定のパレットの色を使用して、色の配列を初期化します。|
|[キーの種類](#onkey)|ユーザーがキーボード ボタンを押したときに、フレームワークによって呼び出されます。|
|[コントロール バー::オンセンド コマンド](#onsendcommand)|ポップアップ コントロールの階層を閉じるために、フレームワークによって呼び出されます。|
|[をクリックします。](#onupdatecmdui)|アイテムが表示される前に、カラー バー コントロールのユーザー インターフェイス項目を有効または無効にするために、フレームワークによって呼び出されます。|
|[カラー バー::カラー ダイアログ](#opencolordialog)|色のダイアログ ボックスを開きます。|
|[リビルド](#rebuild)|カラー バー コントロールを完全に再描画します。|
|[パレットを選択します。](#selectpalette)|指定されたデバイス コンテキストの論理パレットを、現在のカラー バー コントロールの親ボタンのパレットに設定します。|
|[を設定します。](#setproplist)|保護された`m_pWndPropList`データ メンバーを、プロパティ グリッド コントロールへの指定されたポインターに設定します。|
|[をクリックします。](#showcommandmessagestring)|ステータス バーのメッセージ行を更新するカラー バー コントロールを所有するフレーム ウィンドウを要求します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|`m_bInternal`|マウス イベントを処理するかどうかを決定するブール型フィールド。 通常、マウス イベントは、このフィールドが TRUE でカスタマイズ モードが FALSE の場合に処理されます。|
|`m_bIsEnabled`|コントロールが有効かどうかを示すブール値。|
|`m_bIsTearOff`|カラー バー コントロールがドッキングをサポートするかどうかを示すブール値。|
|`m_BoxSize`|カラー バー グリッド内のセルのサイズを指定する[CSize](../../atl-mfc-shared/reference/csize-class.md)オブジェクト。|
|`m_bShowDocColorsWhenDocked`|カラー バーがドッキングされているときにドキュメントの色を表示するかどうかを示すブール値。 詳細については[、「CMFC カラー バー::ドキュメントカラーの設定」を参照してください](#setdocumentcolors)。|
|`m_bStdColorDlg`|標準のシステム カラー ダイアログ ボックスまたは[CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md)ダイアログ ボックスを表示するかどうかを示すブール値。 詳細については[、「CMFC カラー バー::その他のボタンを有効にする](#enableotherbutton)」を参照してください。|
|`m_ColorAutomatic`|現在の自動カラーを格納する[COLORREF](/windows/win32/gdi/colorref)です。 詳細については[、「CMFC カラー バー::その他のボタンを有効にする](#enableotherbutton)」を参照してください。|
|`m_ColorNames`|RGB カラーのセットを名前に関連付ける[CMap](../../mfc/reference/cmap-class.md)オブジェクト。|
|`m_colors`|カラー バー コントロールに表示される色を含む[カラーレフ](/windows/win32/gdi/colorref)値の[CArray](../../mfc/reference/carray-class.md)です。|
|`m_ColorSelected`|カラー バー コントロールから現在選択されている色を指定する[COLORREF](/windows/win32/gdi/colorref)値。|
|`m_lstDocColors`|ドキュメントで現在使用されている色を含む[COLORREF](/windows/win32/gdi/colorref)値の[CList](../../mfc/reference/clist-class.md)です。|
|`m_nCommandID`|色のボタンのコマンド ID である符号なし整数。|
|`m_nHorzMargin`|色のグリッド内のカラー ボタン間の水平方向の余白を表す整数。|
|`m_nHorzOffset`|カラー ボタンの中央に向く水平方向のオフセットを示す整数。 この値は、ボタンに色に加えてテキストまたはイメージが表示される場合に有効です。|
|`m_nNumColumns`|カラー バー コントロール グリッドの列数を示す整数。|
|`m_nNumColumnsVert`|垂直方向の色のグリッド内の列の数を表す整数。|
|`m_nNumRowsHorz`|水平方向の色のグリッド内の列数を表す整数。|
|`m_nRowHeight`|色のグリッド内のカラー ボタンの行の高さを表す整数。|
|`m_nVertMargin`|色のグリッド内のカラー ボタン間の垂直マージンを表す整数。|
|`m_nVertOffset`|カラー ボタンの中心に向ける垂直方向のオフセットを示す整数。 この値は、ボタンに色に加えてテキストまたはイメージが表示される場合に有効です。|
|`m_Palette`|カラー バー コントロールで使用される色の[CPalette](../../mfc/reference/cpalette-class.md)です。|
|`m_pParentBtn`|現在のボタンの親である[CMFCColorButton](../../mfc/reference/cmfccolorbutton-class.md)オブジェクトへのポインター。 この値は、カラー ボタンがツール バー コントロールの階層内にある場合、または色プロパティ グリッド コントロール内にある場合に有効です。|
|`m_pParentRibbonBtn`|リボン上にあり、現在のボタンの親ボタンである[CMFCRibbonColorButton](../../mfc/reference/cmfcribboncolorbutton-class.md)オブジェクトへのポインター。 この値は、カラー ボタンがツール バー コントロールの階層内にある場合、または色プロパティ グリッド コントロール内にある場合に有効です。|
|`m_pWndPropList`|[オブジェクトへの](../../mfc/reference/cmfcpropertygridctrl-class.md)ポインター。|
|`m_strAutoColor`|**[自動**] ボタンに表示されるテキストを表す[CString](../../atl-mfc-shared/reference/cstringt-class.md)です。 詳細については[、「CMFC カラー バー::自動ボタンを有効にする](#enableautomaticbutton)」を参照してください。|
|`m_strDocColors`|ドキュメントの色ボタンに表示されるテキストを表す[CString です](../../atl-mfc-shared/reference/cstringt-class.md)。 詳細については[、「CMFC カラー バー::ドキュメントカラーの設定」を参照してください](#setdocumentcolors)。|
|`m_strOtherColor`|*もう一方*のボタンに表示されるテキストを表す[CString](../../atl-mfc-shared/reference/cstringt-class.md)です。 詳細については[、「CMFC カラー バー::その他のボタンを有効にする](#enableotherbutton)」を参照してください。|

## <a name="remarks"></a>解説

通常、`CMFCColorBar`オブジェクトを直接作成するわけではありません。 代わりに[、(](../../mfc/reference/cmfccolormenubutton-class.md)メニューやツール バーで使用される) クラスまたは[CMFCColorButton クラス](../../mfc/reference/cmfccolorbutton-class.md)は、オブジェクト`CMFCColorBar`を作成します。

この`CMFCColorBar`クラスには、次の機能があります。

- ドキュメントの色の一覧を自動的に調整します。

- ドキュメントの状態と共に、状態を保存および復元します。

- 「自動」ボタンを管理します。

- クラス[コントロールを](../../mfc/reference/cmfccolorpickerctrl-class.md)使用して、カスタム色を選択します。

- "ティアオフ" 状態をサポートします ([クラス](../../mfc/reference/cmfccolormenubutton-class.md)を使用して作成する場合)。

アプリケーションに機能`CMFCColorBar`を組み込むには、次の手順を実行します。

1. 通常のメニュー ボタンを作成し、そのボタンに ID_CHAR_COLOR などの ID を割り当てます。

1. フレーム ウィンドウ クラスで[、CFrameWndEx:::OnShowPopupMenu メソッド](../../mfc/reference/cframewndex-class.md#onshowpopupmenu)をオーバーライドし、通常のメニュー ボタンを[CMFCColorMenuButton クラス](../../mfc/reference/cmfccolormenubutton-class.md)オブジェクトに置き換えます[(CMFCツールバー::置換ボタン](../../mfc/reference/cmfctoolbar-class.md#replacebutton)を呼び出します)。

1. すべてのスタイルを設定し、有効またはクラスの作成中`CMFCColorBar`にオブジェクトの機能[を無効にします](../../mfc/reference/cmfccolormenubutton-class.md)。 フレームワーク`CMFCColorMenuButton`がメソッドを呼び`CMFCColorBar`出した後、オブジェクトは`CreatePopupMenu`動的に作成されます。

ユーザーがカラー バー コントロール ボタンをクリックすると、フレームワークは`ON_COMMAND`マクロを使用して、カラー バー コントロールの親に通知します。 マクロの command ID パラメーターは、手順 1 (この例ではID_CHAR_COLOR) でカラー バー コントロール ボタンに割り当てた値です。 詳細については、「[クラス、CMFC](../../mfc/reference/cmfccolormenubutton-class.md)カラー ボタン クラス[、CMFCColorPickerCtrl クラス](../../mfc/reference/cmfccolorpickerctrl-class.md)[、CFrameWndEx クラス](../../mfc/reference/cframewndex-class.md)、および[CMFCColorButton Class](../../mfc/reference/cmfccolorbutton-class.md)[CMFCToolBar クラス」を](../../mfc/reference/cmfctoolbar-class.md)参照してください。

## <a name="example"></a>例

クラスのさまざまなメソッドを使用してカラー バーを構成する方法を次の例`CMFCColorBar`に示します。 このメソッドは、水平マージンと垂直マージンを設定し、もう一方のボタンを有効にし、カラーバーコントロールウィンドウを作成し、現在選択されている色を設定します。 この例は、[新しいコントロールのサンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_NewControls#1](../../mfc/reference/codesnippet/cpp/cmfccolorbar-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#2](../../mfc/reference/codesnippet/cpp/cmfccolorbar-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[ツールバー](../../mfc/reference/cmfcbasetoolbar-class.md)

[CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)

[CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md)

[CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxカラーバー.h

## <a name="cmfccolorbaradjustlocations"></a><a name="adjustlocations"></a>場所を調整します。

カラー バー コントロールのカラー ボタンの位置を調整します。

```
virtual void AdjustLocations();
```

### <a name="remarks"></a>解説

このメソッドは、メッセージ処理中にフレームワークWM_SIZE呼び出されます。

## <a name="cmfccolorbarallowchangetextlabels"></a><a name="allowchangetextlabels"></a>を変更します。

カラー ボタンのテキスト ラベルを変更できるかどうかを示します。

```
virtual BOOL AllowChangeTextLabels() const;
```

### <a name="return-value"></a>戻り値

常に FALSE です。

### <a name="remarks"></a>解説

既定では、このメソッドは常に FALSE を返します。 テキスト ラベルの変更を有効にするには、このメソッドをオーバーライドします。

## <a name="cmfccolorbarallowshowonlist"></a><a name="allowshowonlist"></a>を表示します。

カスタマイズプロセス中に、カラー バー コントロール オブジェクトをツール バー リストに表示できるかどうかを示します。

```
virtual BOOL AllowShowOnList() const;
```

### <a name="return-value"></a>戻り値

常に TRUE。

### <a name="remarks"></a>解説

既定では、このメソッドは常に TRUE を返します。 別の動作を実装するには、このメソッドをオーバーライドします。

## <a name="cmfccolorbarcalcsize"></a><a name="calcsize"></a>CMFCカラーバー::カルクサイズ

レイアウト計算プロセスの一部としてフレームワークによって呼び出されます。

```
virtual CSize CalcSize(BOOL bVertDock);
```

### <a name="parameters"></a>パラメーター

*bVertDock*<br/>
[in]カラー バー コントロールが垂直方向にドッキングされることを指定する場合は TRUE。カラー バー コントロールが水平方向にドッキングされることを指定する場合は FALSE。

### <a name="return-value"></a>戻り値

カラー バー コントロールのカラー ボタンの配列のサイズ。

## <a name="cmfccolorbarcmfccolorbar"></a><a name="cmfccolorbar"></a>CMFC カラー バー::CMFC カラー バー

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
[in]フレームワークがカラー バー コントロールに表示する色の配列。

*色*<br/>
[in]最初に選択された色。

*lpsz 自動カラー*<br/>
[in]*自動*(既定) の色のボタンのテキスト ラベル、または NULL。

自動ボタンの標準ラベルは **[自動]** です。

*その他の色*<br/>
[in]*他*のボタンのテキスト ラベルで、色の選択肢が増えるか、NULL を表示します。

もう一方のボタンの標準ラベルは **[その他の色..]** です。

*カラー*<br/>
[in]ドキュメントの色ボタンのテキスト ラベル。 ドキュメントのカラー パレットには、ドキュメントで現在使用されているすべての色が表示されます。

*カラー*<br/>
[in]ドキュメントが現在使用している色のリスト。

*nColumns*<br/>
[in]色の配列が持つ列の数。

*ヌロウズドックホルツ*<br/>
[in]カラー バーが水平方向にドッキングされている場合の行数。

*nコルドックヴェルト*<br/>
[in]カラー バーが垂直にドッキングされている場合に表示される列の数。

*カラー自動*<br/>
[in]自動ボタンをクリックしたときにフレームワークが適用する既定の色。

*nコマンドID*<br/>
[in]カラー バー コントロールのコマンド ID。

*親の親*<br/>
[in]親ボタンへのポインター。

*src*<br/>
[in]新しい`CMFCColorBar``CMFCColorBar`オブジェクトにコピーされる既存のオブジェクト。

*コマンド ID*<br/>
[in]コマンド ID。

## <a name="cmfccolorbarcontexttosize"></a><a name="contexttosize"></a>を変更します。

カラー バー コントロールのボタンを含めるために必要な垂直および水平の余白を計算し、それらのボタンの位置を調整します。

```
void ContextToSize(
    BOOL bSquareButtons = TRUE,
    BOOL bCenterButtons = TRUE);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*bスクエアボタン*|[in]カラー バー コントロールのボタンの形状を正方形に指定する場合は TRUE。それ以外の場合は FALSE。 既定値は TRUE です。|
|*bセンターボタン*|[in]カラー バー コントロール ボタンの面のコンテンツを中央揃えにする場合は TRUE。それ以外の場合は FALSE。 既定値は TRUE です。|

### <a name="remarks"></a>解説

## <a name="cmfccolorbarcreate"></a><a name="create"></a>CMFCカラーバー::作成

カラー バー コントロール ウィンドウを作成し、オブジェクト`CMFCColorBar`にアタッチします。

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

*Dwstyle*<br/>
[in][ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)のビットごとの組み合わせ (OR)

*nID*<br/>
[in]コマンド ID。

*をクリックします。*<br/>
[in]色のパレットへのポインター。 既定値は NULL です。

*nColumns*<br/>
[in]カラー バー コントロールの列数。 既定値は 0 です。

*ヌロウズドックホルツ*<br/>
[in]カラー バー コントロールが水平方向にドッキングされたときの行数。 既定値は 0 です。

*nコルドックヴェルト*<br/>
[in]カラー バー コントロールが垂直方向にドッキングされたときの列数。 既定値は 0 です。

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

オブジェクトを`CMFCColorBar`構築するには、クラス コンストラクターを呼び出し、次にこのメソッドを呼び出します。 この`Create`メソッドは、Windows コントロールを作成し、色の一覧を初期化します。

## <a name="cmfccolorbarcreatecontrol"></a><a name="createcontrol"></a>コントロールの作成

カラー バー コントロール ウィンドウを作成し、`CMFCColorBar`オブジェクトにアタッチし、コントロール ウィンドウのサイズを変更して、指定した色のパレットを含めます。

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

*Rect*<br/>
[in]カラー バー コントロールの描画場所を指定する外接する四角形。

*nID*<br/>
[in]コントロール ID。

*nColumns*<br/>
[in]カラー バー コントロールの列の理想的な数。 このメソッドは、指定した色のパレットに合わせてその数を変更します。 デフォルトは -1 で、このパラメーターが指定されていない。

*をクリックします。*<br/>
[in]カラーのパレットへのポインター、または NULL。 このパラメーターが NULL の場合、このメソッドは、20 色が指定された場合と同様にカラー バー コントロールのサイズを計算します。 既定値は NULL です。

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは *、rect* *、nColumns、* および*pPalette*パラメーターを使用して、カラー バー コントロール内の適切な数または行と列を計算し[、CMFCColorBar::Create](#create)メソッドを呼び出します。

## <a name="cmfccolorbarcreatepalette"></a><a name="createpalette"></a>パレットの作成

指定した色の配列の色を使用してパレットを初期化します。

```
static BOOL CreatePalette(
    const CArray<COLORREF, COLORREF>& arColors,
    CPalette& palette);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*アカラーズ*|[in]色の配列。|
|*パレット (palette)*|[in]色のパレット。|

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合は FALSE。

## <a name="cmfccolorbarenableautomaticbutton"></a><a name="enableautomaticbutton"></a>自動ボタンを有効にする

自動ボタンの表示/非表示を切り替えます。

```
void EnableAutomaticButton(
    LPCTSTR lpszLabel,
    COLORREF colorAutomatic,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>パラメーター

*ラベル*<br/>
[in]*自動*(既定) の色のボタンのテキスト ラベル、または NULL。

自動ボタンの標準ラベルは **[自動]** です。

*カラー自動*<br/>
[in]自動ボタンをクリックしたときにフレームワークが適用する既定の色。

*b 有効にする*<br/>
[in]自動ボタンを有効にする場合は TRUE。FALSE を指定すると、自動ボタンが無効になります。 既定値は TRUE です。

### <a name="remarks"></a>解説

自動ボタンのテキスト ラベルは *、lpszLabel*パラメーターが NULL の場合、または*bEnable*パラメーターが FALSE の場合に削除されます。

## <a name="cmfccolorbarenableotherbutton"></a><a name="enableotherbutton"></a>他のボタンを有効にします。

ユーザーが色を選択できるようにするダイアログ ボックスの表示を有効または無効にします。

```
void EnableOtherButton(
    LPCTSTR lpszLabel,
    BOOL bAltColorDlg=TRUE,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>パラメーター

*ラベル*<br/>
[in]*他*のボタンのテキスト ラベルで、色の選択肢が増えるか、NULL を表示します。

このボタンの標準ラベルは **[その他の色..]** です。

*アルトカラードグルグ*<br/>
[in]True を指定すると[、CMFCColorDialog ダイアログ](../../mfc/reference/cmfccolordialog-class.md)ボックスが表示されます。FALSE を指定すると、標準の[[CColorDialog] ダイアログ](../../mfc/reference/ccolordialog-class.md)ボックスが表示されます。 既定値は TRUE です。

*b 有効にする*<br/>
[in]ボタンを有効にする場合は TRUE。FALSE を指定すると、ボタンが無効になります。 既定値は TRUE です。

## <a name="cmfccolorbargetcolor"></a><a name="getcolor"></a>カラーバー::取得カラー

現在選択されている色を取得します。

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>戻り値

現在選択されている色。

## <a name="cmfccolorbargetcolorgridsize"></a><a name="getcolorgridsize"></a>コントロール のサイズを変更します。

カラー バー コントロールのグリッド内の行数と列数を計算します。

```
CSize GetColorGridSize(BOOL bVertDock) const;
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*bVertDock*|[in]垂直にドッキングされたカラー バー コントロールの計算を実行する場合は TRUE。それ以外の場合は、水平方向にドッキングされたコントロールの計算を実行します。|

### <a name="return-value"></a>戻り値

コンポーネントに列数が`cx`含まれ、そのコンポーネントに行数`cy`が含まれている[CSize](../../atl-mfc-shared/reference/csize-class.md)オブジェクト。

## <a name="cmfccolorbargetcommandid"></a><a name="getcommandid"></a>をクリックします。

現在のカラー バー コントロールのコマンド ID を取得します。

```
UINT GetCommandID() const;
```

### <a name="return-value"></a>戻り値

コマンド ID。

### <a name="remarks"></a>解説

ユーザーが新しい色を選択すると、フレームワークは、オブジェクトの親に通知するWM_COMMANDメッセージでコマンド ID`CMFCColorBar`を送信します。

## <a name="cmfccolorbargetextraheight"></a><a name="getextraheight"></a>カラー バー::エクストラハイトを取得します。

現在のカラー バーで、その他のユーザー インターフェイス要素 **([その他]** ボタンやドキュメントの色など) を表示するために必要な高さを計算します。

```
int GetExtraHeight(int nNumColumns) const;
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*列数*|[in]カラー バー コントロールにドキュメントの色が含まれている場合、ドキュメントの色のグリッドに表示する列の数。 それ以外の場合、この値は使用されません。|

### <a name="return-value"></a>戻り値

必要な追加の高さの計算。

## <a name="cmfccolorbargethighlightedcolor"></a><a name="gethighlightedcolor"></a>カラーバー::ハイライトされた色を取得します。

カラー ボタンにフォーカスがあることを示す色を取得します。つまり、ボタンは*ホット*です。

```
COLORREF GetHighlightedColor() const;
```

### <a name="return-value"></a>戻り値

RGB 値。

### <a name="remarks"></a>解説

## <a name="cmfccolorbargethorzmargin"></a><a name="gethorzmargin"></a>バー::ゲッツマージン

左右のカラー セルとクライアント領域境界の間のスペースである水平マージンを取得します。

```
int GetHorzMargin();
```

### <a name="return-value"></a>戻り値

水平マージン。

## <a name="cmfccolorbargetvertmargin"></a><a name="getvertmargin"></a>を使用します。

上または下のカラー セルとクライアント領域境界の間のスペースである垂直方向の余白を取得します。

```
int GetVertMargin() const;
```

### <a name="return-value"></a>戻り値

垂直マージン。

## <a name="cmfccolorbarinitcolors"></a><a name="initcolors"></a>色の色

指定したパレットまたはシステムの既定のパレットで色の配列を初期化します。

```
static int InitColors(
    CPalette* pPalette,
    CArray<COLORREF, COLORREF>& arColors);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*をクリックします。*|[in]パレット オブジェクトへのポインター、または NULL。 このパラメーターが NULL の場合、このメソッドはオペレーティング システムの既定のパレットを使用します。|
|*アカラーズ*|[in]色の配列。|

### <a name="return-value"></a>戻り値

色の配列内の要素の数。

## <a name="cmfccolorbaristearoff"></a><a name="istearoff"></a>CMFCカラーバー::イステアオフ

現在のカラー バーがドッキング可能かどうかを示します。

```
BOOL IsTearOff() const;
```

### <a name="return-value"></a>戻り値

現在のカラー バー コントロールがドッキング可能な場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

カラー バー コントロールがドッキング可能な場合は、コントロール バーを切り離して別の場所にドッキングできます。

## <a name="cmfccolorbaronkey"></a><a name="onkey"></a>キーの種類

ユーザーがキーボード ボタンを押したときに、フレームワークによって呼び出されます。

```
virtual BOOL OnKey(UINT nChar);
```

### <a name="parameters"></a>パラメーター

*Nchar*<br/>
[in]ユーザーが押したキーの仮想キー コード。

### <a name="return-value"></a>戻り値

このメソッドが指定されたキーを処理する場合は TRUE。それ以外の場合は FALSE。

## <a name="cmfccolorbaronsendcommand"></a><a name="onsendcommand"></a>コントロール バー::オンセンド コマンド

ポップアップ コントロールの階層を閉じるために、フレームワークによって呼び出されます。

```
virtual BOOL OnSendCommand(const CMFCToolBarButton* pButton);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*ボタン*|[in]ツール バー上に存在するコントロールへのポインター。|

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合は FALSE。

## <a name="cmfccolorbaronupdatecmdui"></a><a name="onupdatecmdui"></a>をクリックします。

アイテムが表示される前に、カラー バー コントロールのユーザー インターフェイス項目を有効または無効にするために、フレームワークによって呼び出されます。

```
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,
    BOOL bDisableIfNoHndler);
```

### <a name="parameters"></a>パラメーター

*pターゲット*<br/>
[in]更新するユーザー インターフェイス項目を含むウィンドウへのポインター。

*ノフドラー*<br/>
[in]メッセージ マップでハンドラーが定義されていない場合にユーザー インターフェイス項目を無効にする場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

アプリケーションのユーザーがユーザー インターフェイス項目をクリックすると、そのアイテムを有効または無効にする必要があるかどうかを確認する必要があります。 コマンド メッセージのターゲットは、ON_UPDATE_COMMAND_UIコマンド ハンドラーを実装することによって、この情報を提供します。 このメソッドは、コマンドの処理に役立ちます。 詳細については、「 [CCmdUI クラス](../../mfc/reference/ccmdui-class.md)」を参照してください。

## <a name="cmfccolorbaropencolordialog"></a><a name="opencolordialog"></a>カラー バー::カラー ダイアログ

色のダイアログ ボックスを開きます。

```
virtual BOOL OpenColorDialog(
    const COLORREF colorDefault,
    COLORREF& colorRes);
```

### <a name="parameters"></a>パラメーター

*カラーデフォルト*<br/>
[in]色ダイアログ ボックスが開いたときに既定で選択される色。

*カラーレス*<br/>
[アウト]ユーザーが選択した色。

### <a name="return-value"></a>戻り値

ユーザーが色を選択した場合は TRUE。FALSE の場合、ユーザーが色のダイアログ ボックスをキャンセルしました。

### <a name="remarks"></a>解説

## <a name="cmfccolorbarrebuild"></a><a name="rebuild"></a>リビルド

カラー バー コントロールを完全に再描画します。

```
virtual void Rebuild();
```

## <a name="cmfccolorbarselectpalette"></a><a name="selectpalette"></a>パレットを選択します。

指定されたデバイス コンテキストの論理パレットを、現在のカラー バー コントロールの親ボタンのパレットに設定します。

```
CPalette* SelectPalette(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*pDC*|[in]現在のカラー バー コントロールの親ボタンのデバイス コンテキストへのポインター。|

### <a name="return-value"></a>戻り値

現在のカラー バー コントロールの親ボタンのパレットに置き換えられるパレットへのポインター。

## <a name="cmfccolorbarsetcolor"></a><a name="setcolor"></a>カラーバー::セットカラー

現在選択されている色を設定します。

```
void SetColor(COLORREF color);
```

### <a name="parameters"></a>パラメーター

*色*<br/>
[in]RGB カラー値。

## <a name="cmfccolorbarsetcolorname"></a><a name="setcolorname"></a>カラーバー::セットカラーネーム

指定した色の新しい名前を設定します。

```
static void SetColorName(
    COLORREF color,
    const CString& strName);
```

### <a name="parameters"></a>パラメーター

*色*<br/>
[in]カラーの RGB 値。

*strName*<br/>
[in]指定した色の新しい名前。

### <a name="remarks"></a>解説

このメソッドは、アプリケーション内のすべての`CMFCColorBar`オブジェクトで指定された色の名前を変更します。

## <a name="cmfccolorbarsetcommandid"></a><a name="setcommandid"></a>を設定します。

カラー バー コントロールの新しいコマンド ID を設定します。

```
void SetCommandID(UINT nCommandID);
```

### <a name="parameters"></a>パラメーター

*nコマンドID*<br/>
[in]コマンド ID。

### <a name="remarks"></a>解説

カラー バー コントロールのコマンド ID を変更し、その ID が変更されたことをコントロールの親ウィンドウに通知します。

## <a name="cmfccolorbarsetdocumentcolors"></a><a name="setdocumentcolors"></a>カラーを設定します。

現在のドキュメントで使用されている色のリストを設定します。

```
void SetDocumentColors(
    LPCTSTR lpszCaption,
    CList<COLORREF,COLORREF>& lstDocColors,
    BOOL bShowWhenDocked=FALSE);
```

### <a name="parameters"></a>パラメーター

*一方、一時おくもみ*<br/>
[in]カラー バー コントロールがドッキングされていない場合に表示されるキャプション。

*カラー*<br/>
[in]現在のドキュメントの色を置き換える色のリスト。

*ドッキング時に表示*<br/>
[in]TRUE を指定すると、カラー バー コントロールがドッキングされたときにドキュメントの色が表示されます。それ以外の場合は FALSE。 既定値は FALSE です。

### <a name="remarks"></a>解説

*ドキュメントの色*は、現在ドキュメントで使用されている色です。 フレームワークはドキュメントの色のリストを自動的に保持しますが、このメソッドを使用してリストを変更できます。

## <a name="cmfccolorbarsethorzmargin"></a><a name="sethorzmargin"></a>セットホーズマージン

左右のカラー セルとクライアント領域の境界との間のスペースである水平マージンを設定します。

```
void SetHorzMargin(int nHorzMargin);
```

### <a name="parameters"></a>パラメーター

*nホルズマージン*<br/>
[in]水平方向の余白 (ピクセル単位)。

### <a name="remarks"></a>解説

既定では[、CMFCColorBar::CMFCColorBar](#cmfccolorbar)コンストラクターは、水平方向のマージンを 4 ピクセルに設定します。

## <a name="cmfccolorbarsetproplist"></a><a name="setproplist"></a>を設定します。

保護された`m_pWndPropList`データ メンバーを、プロパティ グリッド コントロールへの指定されたポインターに設定します。

```
void SetPropList(CMFCPropertyGridCtrl* pWndList);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*一覧*|[in]プロパティ グリッド コントロール オブジェクトへのポインター。|

## <a name="cmfccolorbarsetvertmargin"></a><a name="setvertmargin"></a>CMFCカラーバー::セットバーマージン

上または下のカラー セルとクライアント領域境界の間のスペースである垂直方向の余白を設定します。

```
void SetVertMargin(int nVertMargin);
```

### <a name="parameters"></a>パラメーター

*nヴェルトマージン*<br/>
[in]垂直方向の余白 (ピクセル単位)。

### <a name="remarks"></a>解説

既定では[、CMFCColorBar::CMFCColorBar](#cmfccolorbar)コンストラクターは、垂直マージンを 4 ピクセルに設定します。

## <a name="cmfccolorbarshowcommandmessagestring"></a><a name="showcommandmessagestring"></a>をクリックします。

ステータス バーのメッセージ行を更新するカラー バー コントロールを所有するフレーム ウィンドウを要求します。

```
virtual void ShowCommandMessageString(UINT uiCmdId);
```

### <a name="parameters"></a>パラメーター

*uiCmdId*<br/>
[in]コマンド ID。 (このパラメーターは無視されます。

### <a name="remarks"></a>解説

このメソッドは、WM_SETMESSAGESTRING メッセージをカラー バー コントロールの所有者に送信します。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)
