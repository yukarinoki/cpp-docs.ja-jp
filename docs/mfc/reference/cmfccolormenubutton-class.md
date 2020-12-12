---
description: '詳細情報: CMFCColorMenuButton クラス'
title: CMFCColorMenuButton クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCColorMenuButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::CMFCColorMenuButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::EnableAutomaticButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::EnableDocumentColors
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::EnableOtherButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::EnableTearOff
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::GetAutomaticColor
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::GetColor
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::GetColorByCmdID
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::OnChangeParentWnd
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::OpenColorDialog
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::SetColor
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::SetColorByCmdID
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::SetColorName
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::SetColumnsNumber
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::CopyFrom
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::CreatePopupMenu
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::IsEmptyMenuAllowed
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::OnDraw
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::OnDrawOnCustomizeList
helpviewer_keywords:
- CMFCColorMenuButton [MFC], CMFCColorMenuButton
- CMFCColorMenuButton [MFC], EnableAutomaticButton
- CMFCColorMenuButton [MFC], EnableDocumentColors
- CMFCColorMenuButton [MFC], EnableOtherButton
- CMFCColorMenuButton [MFC], EnableTearOff
- CMFCColorMenuButton [MFC], GetAutomaticColor
- CMFCColorMenuButton [MFC], GetColor
- CMFCColorMenuButton [MFC], GetColorByCmdID
- CMFCColorMenuButton [MFC], OnChangeParentWnd
- CMFCColorMenuButton [MFC], OpenColorDialog
- CMFCColorMenuButton [MFC], SetColor
- CMFCColorMenuButton [MFC], SetColorByCmdID
- CMFCColorMenuButton [MFC], SetColorName
- CMFCColorMenuButton [MFC], SetColumnsNumber
- CMFCColorMenuButton [MFC], CopyFrom
- CMFCColorMenuButton [MFC], CreatePopupMenu
- CMFCColorMenuButton [MFC], IsEmptyMenuAllowed
- CMFCColorMenuButton [MFC], OnDraw
- CMFCColorMenuButton [MFC], OnDrawOnCustomizeList
ms.assetid: 42685704-e994-4f7b-9553-62283c27b754
ms.openlocfilehash: 4ba0934e872adc4e4b33c2ae5700ecb0fc46e6d8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327676"
---
# <a name="cmfccolormenubutton-class"></a>CMFCColorMenuButton クラス

クラスは、 `CMFCColorMenuButton` カラーピッカーダイアログボックスを起動するメニューコマンドまたはツールバーボタンをサポートしています。

## <a name="syntax"></a>構文

```
class CMFCColorMenuButton : public CMFCToolBarMenuButton
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CMFCColorMenuButton:: CMFCColorMenuButton](#cmfccolormenubutton)|`CMFCColorMenuButton` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCColorMenuButton:: Enable自動ボタン](#enableautomaticbutton)|通常の色のボタンの上にある [自動] ボタンを有効または無効にします。 ([標準システム] 自動ボタンは [ **自動**] というラベルが付いています)。|
|[CMFCColorMenuButton:: EnableDocumentColors](#enabledocumentcolors)|システムカラーではなく、ドキュメント固有の色の表示を有効にします。|
|[CMFCColorMenuButton:: EnableOtherButton](#enableotherbutton)|通常の色のボタンの下に配置される "その他" ボタンを有効または無効にします。 (標準システムの [その他] ボタンには、 **より多くの色** が付けられています)。|
|[CMFCColorMenuButton:: EnableTearOff](#enabletearoff)|色ペインを無効にする機能を有効にします。|
|[CMFCColorMenuButton:: Get自動カラー](#getautomaticcolor)|現在の自動色を取得します。|
|[CMFCColorMenuButton:: GetColor](#getcolor)|現在のボタンの色を取得します。|
|[CMFCColorMenuButton:: GetColorByCmdID](#getcolorbycmdid)|指定したコマンド ID に対応する色を取得します。|
|[CMFCColorMenuButton:: OnChangeParentWnd](#onchangeparentwnd)|親ウィンドウが変更されたときにフレームワークによって呼び出されます。|
|[CMFCColorMenuButton:: OpenColorDialog](#opencolordialog)|色の選択ダイアログボックスを開きます。|
|[CMFCColorMenuButton:: SetColor](#setcolor)|現在の色のボタンの色を設定します。|
|[CMFCColorMenuButton:: SetColorByCmdID](#setcolorbycmdid)|指定したカラーメニューボタンの色を設定します。|
|[CMFCColorMenuButton:: SetColorName](#setcolorname)|指定した色の新しい名前を設定します。|
|[CMFCColorMenuButton:: SetColumnsNumber](#setcolumnsnumber)|オブジェクトによって表示される列の数を設定し `CMFCColorBar` ます。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CMFCColorMenuButton:: CopyFrom](#copyfrom)|別のツールバーボタンを現在のボタンにコピーします。|
|[CMFCColorMenuButton:: CreatePopupMenu](#createpopupmenu)|カラーピッカーダイアログボックスを作成します。|
|[CMFCColorMenuButton:: IsEmptyMenuAllowed](#isemptymenuallowed)|空のメニューがサポートされているかどうかを示します。|
|[CMFCColorMenuButton:: OnDraw](#ondraw)|ボタン上にイメージを表示するためにフレームワークによって呼び出されます。|
|[CMFCColorMenuButton:: OnDrawOnCustomizeList](#ondrawoncustomizelist)|`CMFCColorMenuButton`ツールバーのカスタマイズダイアログボックスの一覧にオブジェクトが表示される前に、フレームワークによって呼び出されます。|

## <a name="remarks"></a>解説

元のメニューコマンドまたはツールバーボタンをオブジェクトに置き換えるには、 `CMFCColorMenuButton` オブジェクトを作成し `CMFCColorMenuButton` 、適切な [cmfccolorbar クラス](../../mfc/reference/cmfccolorbar-class.md) スタイルを設定して、 `ReplaceButton` [cmfctoolbar クラス](../../mfc/reference/cmfctoolbar-class.md) クラスのメソッドを呼び出します。 ツールバーをカスタマイズする場合は、 [Cmfctoolbarscustomizedialog:: ReplaceButton](../../mfc/reference/cmfctoolbarscustomizedialog-class.md#replacebutton) メソッドを呼び出します。

[カラーピッカー] ダイアログボックスは、 [Cmfccolormenubutton:: CreatePopupMenu](#createpopupmenu) イベントハンドラーの処理中に作成されます。 イベントハンドラーは、WM_COMMAND メッセージを親フレームに通知します。 オブジェクトは、 `CMFCColorMenuButton` 元のメニューコマンドまたはツールバーボタンに割り当てられているコントロール ID を送信します。

## <a name="example"></a>例

クラスのさまざまなメソッドを使用してカラーメニューボタンを作成および構成する方法を次の例に示し `CMFCColorMenuButton` ます。 この例では、 `CPalette` オブジェクトが最初に作成されてから、クラスのオブジェクトを構築するために使用され `CMFCColorMenuButton` ます。 その `CMFCColorMenuButton` 後、オブジェクトは自動およびその他のボタンを有効にし、その色と列の数を設定することによって構成されます。 このコードは、 [Word パッドサンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_WordPad#5](../../mfc/reference/codesnippet/cpp/cmfccolormenubutton-class_1.h)]
[!code-cpp[NVC_MFC_WordPad#6](../../mfc/reference/codesnippet/cpp/cmfccolormenubutton-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[CMFCToolBarMenuButton](../../mfc/reference/cmfctoolbarmenubutton-class.md)

[CMFCColorMenuButton](../../mfc/reference/cmfccolormenubutton-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxcolormenubutton

## <a name="cmfccolormenubuttoncmfccolormenubutton"></a><a name="cmfccolormenubutton"></a> CMFCColorMenuButton:: CMFCColorMenuButton

`CMFCColorMenuButton` オブジェクトを構築します。

```
CMFCColorMenuButton();

CMFCColorMenuButton(
    UINT uiCmdID,
    LPCTSTR lpszText,
    CPalette* pPalette=NULL);
```

### <a name="parameters"></a>パラメーター

*uiCmdID*<br/>
からボタンコマンド ID。

*lpszText*<br/>
からボタンのテキスト。

*pPalette*<br/>
からボタンのカラーパレットへのポインター。

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

最初のコンストラクターは、既定のコンストラクターです。 オブジェクトの現在の色と自動色は黒 (RGB (0, 0, 0)) に初期化されます。

2番目のコンストラクターは、ボタンを、指定したコマンド ID に対応する色に初期化します。

## <a name="cmfccolormenubuttoncopyfrom"></a><a name="copyfrom"></a> CMFCColorMenuButton:: CopyFrom

1つの [Cmfctoolbarmenubutton クラス](../../mfc/reference/cmfctoolbarmenubutton-class.md)派生オブジェクトを別のオブジェクトにコピーします。

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>パラメーター

*src*<br/>
からコピーするソースボタン。

### <a name="remarks"></a>解説

オブジェクトから派生したオブジェクトをコピーするには、このメソッドをオーバーライドし `CMFCColorMenuButton` ます。

## <a name="cmfccolormenubuttoncreatepopupmenu"></a><a name="createpopupmenu"></a> CMFCColorMenuButton:: CreatePopupMenu

カラーピッカーダイアログボックスを作成します。

```
virtual CMFCPopupMenu* CreatePopupMenu();
```

### <a name="return-value"></a>戻り値

カラーピッカーダイアログボックスを表すオブジェクト。

### <a name="remarks"></a>解説

このメソッドは、ユーザーがカラーメニューボタンを押したときにフレームワークによって呼び出されます。

## <a name="cmfccolormenubuttonenableautomaticbutton"></a><a name="enableautomaticbutton"></a> CMFCColorMenuButton:: Enable自動ボタン

通常の色のボタンの上にある [自動] ボタンを有効または無効にします。 ([標準システム] 自動ボタンは [ **自動**] というラベルが付いています)。

```cpp
void EnableAutomaticButton(
    LPCTSTR lpszLabel,
    COLORREF colorAutomatic,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>パラメーター

*lpszLabel*<br/>
からボタンが自動になったときに表示されるボタンテキストを指定します。

*colorAutomatic*<br/>
から新しい自動色を指定します。

*bEnable*<br/>
からボタンが自動であるかどうかを指定します。

### <a name="remarks"></a>解説

[自動] ボタンをクリックすると、現在の既定の色が適用されます。

## <a name="cmfccolormenubuttonenabledocumentcolors"></a><a name="enabledocumentcolors"></a> CMFCColorMenuButton:: EnableDocumentColors

システムカラーではなく、ドキュメント固有の色の表示を有効にします。

```cpp
void EnableDocumentColors(
    LPCTSTR lpszLabel,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>パラメーター

*lpszLabel*<br/>
からボタンのテキストを指定します。

*bEnable*<br/>
からドキュメント固有の色を表示する場合は TRUE。システムの色を表示する場合は FALSE。

### <a name="remarks"></a>解説

ユーザーがカラーメニューボタンをクリックしたときに、現在のドキュメントの色またはシステムパレットの色を表示するには、このメソッドを使用します。

## <a name="cmfccolormenubuttonenableotherbutton"></a><a name="enableotherbutton"></a> CMFCColorMenuButton:: EnableOtherButton

通常の色のボタンの下に配置される "その他" ボタンを有効または無効にします。 (標準システムの [その他] ボタンには、 **より多くの色** が付けられています)。

```cpp
void EnableOtherButton(
    LPCTSTR lpszLabel,
    BOOL bAltColorDlg=TRUE,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>パラメーター

*lpszLabel*<br/>
からボタンのテキストを指定します。

*Tcolordlg*<br/>
からダイアログボックスを表示する場合は TRUE を、 `CMFCColorDialog` 標準のシステムカラーダイアログボックスを表示する場合は FALSE を指定します。

*bEnable*<br/>
から[その他] ボタンを表示するには TRUE を指定します。それ以外の場合は FALSE。 既定値は TRUE です。

### <a name="remarks"></a>解説

## <a name="cmfccolormenubuttonenabletearoff"></a><a name="enabletearoff"></a> CMFCColorMenuButton:: EnableTearOff

色ペインを無効にする機能を有効にします。

```cpp
void EnableTearOff(
    UINT uiID,
    int nVertDockColumns=-1,
    int nHorzDockRows=-1);
```

### <a name="parameters"></a>パラメーター

*uiID*<br/>
からティアオフペインの ID を指定します。

*nVertDockColumns*<br/>
からティアオフ状態のときに、垂直方向にドッキングされた色ウィンドウ内の列の数を指定します。

*nHorzDockRows*<br/>
からティアオフ状態のときに、水平方向にドッキングされた色ウィンドウの行数を指定します。

### <a name="remarks"></a>解説

このメソッドを呼び出して、ボタンが押されたときにポップアップ表示されるカラーペインの "ティアオフ" 機能を有効にし `CMFCColorMenuButton` ます。

## <a name="cmfccolormenubuttongetautomaticcolor"></a><a name="getautomaticcolor"></a> CMFCColorMenuButton:: Get自動カラー

現在の自動色を取得します。

```
COLORREF GetAutomaticColor() const;
```

### <a name="return-value"></a>戻り値

現在の自動カラーを表す RGB カラー値。

### <a name="remarks"></a>解説

[Cmfccolormenubutton:: enable自動ボタン](#enableautomaticbutton)によって設定された自動色を取得するには、このメソッドを呼び出します。

## <a name="cmfccolormenubuttongetcolor"></a><a name="getcolor"></a> CMFCColorMenuButton:: GetColor

現在のボタンの色を取得します。

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>戻り値

ボタンの色。

### <a name="remarks"></a>解説

## <a name="cmfccolormenubuttongetcolorbycmdid"></a><a name="getcolorbycmdid"></a> CMFCColorMenuButton:: GetColorByCmdID

指定したコマンド ID に対応する色を取得します。

```
static COLORREF GetColorByCmdID(UINT uiCmdID);
```

### <a name="parameters"></a>パラメーター

*uiCmdID*<br/>
からコマンド ID。

### <a name="return-value"></a>戻り値

指定したコマンド ID に対応する色。

### <a name="remarks"></a>解説

アプリケーションに複数のカラーボタンがある場合に、この方法を使用します。 ユーザーが色のボタンをクリックすると、WM_COMMAND メッセージのコマンド ID が親に送信されます。 メソッドは、 `GetColorByCmdID` コマンド ID を使用して対応する色を取得します。

## <a name="cmfccolormenubuttonisemptymenuallowed"></a><a name="isemptymenuallowed"></a> CMFCColorMenuButton:: IsEmptyMenuAllowed

空のメニューがサポートされているかどうかを示します。

```
virtual BOOL IsEmptyMenuAllowed() const;
```

### <a name="return-value"></a>戻り値

空のメニューが許可される場合は0以外の。それ以外の場合は0。

### <a name="remarks"></a>解説

既定では、空のメニューがサポートされています。 派生クラスのこの動作を変更するには、このメソッドをオーバーライドします。

## <a name="cmfccolormenubuttononchangeparentwnd"></a><a name="onchangeparentwnd"></a> CMFCColorMenuButton:: OnChangeParentWnd

親ウィンドウが変更されたときにフレームワークによって呼び出されます。

```
virtual void OnChangeParentWnd(CWnd* pWndParent);
```

### <a name="parameters"></a>パラメーター

*pWndParent*<br/>
から新しい親ウィンドウへのポインター。

### <a name="remarks"></a>解説

## <a name="cmfccolormenubuttonondraw"></a><a name="ondraw"></a> CMFCColorMenuButton:: OnDraw

ボタン上にイメージを表示するためにフレームワークによって呼び出されます。

```
virtual void OnDraw(
    CDC* pDC,
    const CRect& rect,
    CMFCToolBarImages* pImages,
    BOOL bHorz=TRUE,
    BOOL bCustomizeMode=FALSE,
    BOOL bHighlight=FALSE,
    BOOL bDrawBorder=TRUE,
    BOOL bGrayDisabledButtons=TRUE);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
からデバイスコンテキストへのポインター。

*rect*<br/>
から再描画される領域の境界となる四角形。

*pImages*<br/>
からツールバーイメージのリストをポイントします。

*bHorz*<br/>
からツールバーが水平方向にドッキングされた状態であることを指定する場合は TRUE。それ以外の場合は FALSE。 既定値は TRUE です。

*Bカスタマイズの Emode*<br/>
からアプリケーションがカスタマイズモードであることを指定する場合は TRUE。それ以外の場合は FALSE。 既定値は FALSE です。

*bHighlight 表示*<br/>
からボタンが強調表示されるように指定する場合は TRUE。それ以外の場合は FALSE。 既定値は FALSE です。

*bDrawBorder*<br/>
からボタンの境界線が表示されるように指定する場合は TRUE。それ以外の場合は FALSE。 既定値は TRUE です。

*bGrayDisabledButtons*<br/>
から無効のボタンを淡色表示 (淡色表示) するように指定する場合は TRUE。それ以外の場合は FALSE。 既定値は TRUE です。

### <a name="remarks"></a>解説

## <a name="cmfccolormenubuttonondrawoncustomizelist"></a><a name="ondrawoncustomizelist"></a> CMFCColorMenuButton:: OnDrawOnCustomizeList

`CMFCColorMenuButton`ツールバーのカスタマイズダイアログボックスの一覧にオブジェクトが表示される前に、フレームワークによって呼び出されます。

```
virtual int OnDrawOnCustomizeList(
    CDC* pDC,
    const CRect& rect,
    BOOL bSelected);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
からデバイスコンテキストへのポインター。

*rect*<br/>
から描画するボタンの境界となる四角形。

*選択された bSelected*<br/>
からTRUE は、ボタンが選択された状態であることを示します。それ以外の場合は FALSE。

### <a name="return-value"></a>戻り値

ボタンの幅。

### <a name="remarks"></a>解説

このメソッドは、 `CMFCColorMenuButton` ツールバーのカスタマイズプロセス中にオブジェクトがリストボックスに表示されるときに、フレームワークによって呼び出されます。

## <a name="cmfccolormenubuttonopencolordialog"></a><a name="opencolordialog"></a> CMFCColorMenuButton:: OpenColorDialog

色の選択ダイアログボックスを開きます。

```
virtual BOOL OpenColorDialog(
    const COLORREF colorDefault,
    COLORREF& colorRes);
```

### <a name="parameters"></a>パラメーター

*colorDefault*<br/>
から色のダイアログボックスで選択されている既定の色。

*colorRes*<br/>
入出力色のダイアログボックスからユーザーが選択した色を返します。

### <a name="return-value"></a>戻り値

ユーザーが新しい色を選択した場合は0以外の。それ以外の場合は0。

### <a name="remarks"></a>解説

メニューボタンをクリックしたときに、このメソッドを呼び出して、色のダイアログボックスを開きます。 戻り値が0以外の場合は、ユーザーが選択した色が *Colorres* パラメーターに格納されます。 [Cmfccolormenubutton:: EnableOtherButton](#enableotherbutton)メソッドを使用して、標準の色のダイアログボックスと [ [CMFCColorDialog クラス](../../mfc/reference/cmfccolordialog-class.md)] ダイアログボックスを切り替えます。

## <a name="cmfccolormenubuttonsetcolor"></a><a name="setcolor"></a> CMFCColorMenuButton:: SetColor

現在の色のボタンの色を設定します。

```
virtual void SetColor(
    COLORREF clr,
    BOOL bNotify=TRUE);
```

### <a name="parameters"></a>パラメーター

<bpt id="p1">*</bpt>clr<ept id="p1">*</ept><br/>
からRGB カラー値。

*bNotify*<br/>
から関連するメニューボタンまたはツールバーボタンに *clr* パラメーターの色を適用する場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

現在の色のボタンの色を変更するには、このメソッドを呼び出します。 *Bnotify* パラメーターが0以外の場合は、関連するポップアップメニューまたはツールバーの対応するボタンの色が、 *clr* パラメーターで指定された色に変更されます。

## <a name="cmfccolormenubuttonsetcolorbycmdid"></a><a name="setcolorbycmdid"></a> CMFCColorMenuButton:: SetColorByCmdID

指定したカラーメニューボタンの色を設定します。

```
static void SetColorByCmdID(
    UINT uiCmdID,
    COLORREF color);
```

### <a name="parameters"></a>パラメーター

*uiCmdID*<br/>
からカラーメニューボタンのリソース ID。

*color*<br/>
からRGB カラー値。

## <a name="cmfccolormenubuttonsetcolorname"></a><a name="setcolorname"></a> CMFCColorMenuButton:: SetColorName

指定した色の新しい名前を設定します。

```
static void SetColorName(
    COLORREF color,
    const CString& strName);
```

### <a name="parameters"></a>パラメーター

*color*<br/>
から名前が変更された色の RGB 値。

*strName*<br/>
から色の新しい名前。

### <a name="remarks"></a>解説

## <a name="cmfccolormenubuttonsetcolumnsnumber"></a><a name="setcolumnsnumber"></a> CMFCColorMenuButton:: SetColumnsNumber

色の選択コントロール ( [Cmfccolorbar](../../mfc/reference/cmfccolorbar-class.md) オブジェクト) に表示する列の数を設定します。

```cpp
void SetColumnsNumber(int nColumns);
```

### <a name="parameters"></a>パラメーター

*nColumns*<br/>
から表示する列の数。

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCColorBar クラス](../../mfc/reference/cmfccolorbar-class.md)<br/>
[CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFCToolBarsCustomizeDialog クラス](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)<br/>
[CMFCColorButton クラス](../../mfc/reference/cmfccolorbutton-class.md)
