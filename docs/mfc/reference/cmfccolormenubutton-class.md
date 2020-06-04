---
title: クラス
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
ms.openlocfilehash: 9c895573c626a890facfef689fce4b516aff5115
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752521"
---
# <a name="cmfccolormenubutton-class"></a>クラス

この`CMFCColorMenuButton`クラスは、メニュー コマンドまたはツール バー ボタンをサポートし、カラー ピッカー ダイアログ ボックスを開始します。

## <a name="syntax"></a>構文

```
class CMFCColorMenuButton : public CMFCToolBarMenuButton
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[ボタン::CMFCカラーメニューボタン](#cmfccolormenubutton)|`CMFCColorMenuButton` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCカラーメニューボタン::自動ボタンを有効にする](#enableautomaticbutton)|通常のカラー ボタンの上に配置されている "自動" ボタンを有効または無効にします。 (標準システムの自動ボタンには**自動**とラベルが付いています。|
|[コントロール::ドキュメントの色を有効にします。](#enabledocumentcolors)|システム カラーではなく、ドキュメント固有の色の表示を有効にします。|
|[ボタンをクリックします。](#enableotherbutton)|通常のカラー ボタンの下に配置されている "その他" ボタンを有効または無効にします。 (標準システムの「その他」ボタンには、**その他の色**のラベルが付いています。|
|[CMFCカラーメニューボタン::イネーブルティアオフ](#enabletearoff)|カラー ペインを引き裂く機能を有効にします。|
|[コントロール:自動カラーを取得します。](#getautomaticcolor)|現在の自動色を取得します。|
|[メニューボタン::ゲットカラー](#getcolor)|現在のボタンの色を取得します。|
|[ボタン::取得カラーバイコマンドイド](#getcolorbycmdid)|指定したコマンド ID に対応する色を取得します。|
|[ボタン:オンチェンジペアレント](#onchangeparentwnd)|親ウィンドウが変更されたときに、フレームワークによって呼び出されます。|
|[ボタン::カラーダイアログ](#opencolordialog)|色選択ダイアログ ボックスを開きます。|
|[メニューボタン::セットカラー](#setcolor)|現在のカラー ボタンの色を設定します。|
|[ボタン::セットカラーバイコマンドイド](#setcolorbycmdid)|指定したカラー メニュー ボタンの色を設定します。|
|[ボタン::セットカラー名](#setcolorname)|指定した色の新しい名前を設定します。|
|[メニューボタン::列番号の設定](#setcolumnsnumber)|オブジェクトによって表示される列数を`CMFCColorBar`設定します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[ボタン::コピーから](#copyfrom)|現在のボタンに別のツール バー ボタンをコピーします。|
|[ボタン::ポップアップメニューを作成します。](#createpopupmenu)|カラー ピッカー ダイアログ ボックスを作成します。|
|[ボタン::IsEmptyメニューを許可](#isemptymenuallowed)|空のメニューがサポートされているかどうかを示します。|
|[メニューボタン::ドロー](#ondraw)|ボタンにイメージを表示するために、フレームワークによって呼び出されます。|
|[メニューボタン::オンドローオンカスタマイザ](#ondrawoncustomizelist)|ツール バーのカスタマイズ`CMFCColorMenuButton`ダイアログ ボックスの一覧にオブジェクトが表示される前に、フレームワークによって呼び出されます。|

## <a name="remarks"></a>解説

元のメニュー コマンドまたはツール バー ボタン`CMFCColorMenuButton`をオブジェクトに置`CMFCColorMenuButton`き換えるには、オブジェクトを作成し、適切な[CMFCColorBar クラス](../../mfc/reference/cmfccolorbar-class.md)スタイルを設定し、`ReplaceButton`[クラスの](../../mfc/reference/cmfctoolbar-class.md)メソッドを呼び出します。 ツール バーをカスタマイズする場合は、メソッドを呼び出[します](../../mfc/reference/cmfctoolbarscustomizedialog-class.md#replacebutton)。

カラー ピッカー ダイアログ ボックスは、イベント ハンドラーの処理中に作成[されます](#createpopupmenu)。 イベント ハンドラーは、親フレームにWM_COMMAND メッセージを通知します。 オブジェクト`CMFCColorMenuButton`は、元のメニュー コマンドまたはツールバー ボタンに割り当てられているコントロール ID を送信します。

## <a name="example"></a>例

クラスのさまざまなメソッドを使用して、カラー メニュー ボタンを作成および構成する方法を`CMFCColorMenuButton`次の例に示します。 この例では、まず`CPalette`オブジェクトを作成し、次に`CMFCColorMenuButton`クラスのオブジェクトを構築するために使用します。 その`CMFCColorMenuButton`後、オブジェクトの自動ボタンやその他のボタンを有効にし、その色と列数を設定して、オブジェクトを構成します。 このコードは[、ワード パッドのサンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_WordPad#5](../../mfc/reference/codesnippet/cpp/cmfccolormenubutton-class_1.h)]
[!code-cpp[NVC_MFC_WordPad#6](../../mfc/reference/codesnippet/cpp/cmfccolormenubutton-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[CMFCToolBarMenuButton](../../mfc/reference/cmfctoolbarmenubutton-class.md)

[CMFCColorMenuButton](../../mfc/reference/cmfccolormenubutton-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxcolorメニューボタン.h

## <a name="cmfccolormenubuttoncmfccolormenubutton"></a><a name="cmfccolormenubutton"></a>ボタン::CMFCカラーメニューボタン

`CMFCColorMenuButton` オブジェクトを構築します。

```
CMFCColorMenuButton();

CMFCColorMenuButton(
    UINT uiCmdID,
    LPCTSTR lpszText,
    CPalette* pPalette=NULL);
```

### <a name="parameters"></a>パラメーター

*UICmdID*<br/>
[in]ボタン コマンド ID。

*lpszText*<br/>
[in]ボタンのテキスト。

*をクリックします。*<br/>
[in]ボタンのカラー パレットへのポインター。

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

最初のコンストラクターは、既定のコンストラクターです。 オブジェクトの現在の色と自動色は黒(RGB(0, 0, 0)) に初期化されます。

2 番目のコンストラクターは、指定したコマンド ID に対応する色にボタンを初期化します。

## <a name="cmfccolormenubuttoncopyfrom"></a><a name="copyfrom"></a>ボタン::コピーから

派生[オブジェクト](../../mfc/reference/cmfctoolbarmenubutton-class.md)を別のクラスにコピーします。

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>パラメーター

*src*<br/>
[in]コピーするソースボタン。

### <a name="remarks"></a>解説

オブジェクトから派生したオブジェクトをコピーするには、このメソッド`CMFCColorMenuButton`をオーバーライドします。

## <a name="cmfccolormenubuttoncreatepopupmenu"></a><a name="createpopupmenu"></a>ボタン::ポップアップメニューを作成します。

カラー ピッカー ダイアログ ボックスを作成します。

```
virtual CMFCPopupMenu* CreatePopupMenu();
```

### <a name="return-value"></a>戻り値

カラー ピッカー ダイアログ ボックスを表すオブジェクト。

### <a name="remarks"></a>解説

このメソッドは、ユーザーがカラー メニュー ボタンを押したときに、フレームワークによって呼び出されます。

## <a name="cmfccolormenubuttonenableautomaticbutton"></a><a name="enableautomaticbutton"></a>CMFCカラーメニューボタン::自動ボタンを有効にする

通常のカラー ボタンの上に配置されている "自動" ボタンを有効または無効にします。 (標準システムの自動ボタンには**自動**とラベルが付いています。

```cpp
void EnableAutomaticButton(
    LPCTSTR lpszLabel,
    COLORREF colorAutomatic,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>パラメーター

*ラベル*<br/>
[in]ボタンが自動表示されたときに表示されるボタン テキストを指定します。

*カラー自動*<br/>
[in]新しい自動色を指定します。

*b 有効にする*<br/>
[in]ボタンが自動かどうかを指定します。

### <a name="remarks"></a>解説

自動ボタンは、現在の既定の色を適用します。

## <a name="cmfccolormenubuttonenabledocumentcolors"></a><a name="enabledocumentcolors"></a>コントロール::ドキュメントの色を有効にします。

システム カラーではなく、ドキュメント固有の色の表示を有効にします。

```cpp
void EnableDocumentColors(
    LPCTSTR lpszLabel,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>パラメーター

*ラベル*<br/>
[in]ボタンテキストを指定します。

*b 有効にする*<br/>
[in]ドキュメント固有の色を表示する場合は TRUE、システム カラーを表示するには FALSE を指定します。

### <a name="remarks"></a>解説

ユーザーがカラー メニュー ボタンをクリックしたときに、現在のドキュメントの色またはシステム パレットの色を表示するには、このメソッドを使用します。

## <a name="cmfccolormenubuttonenableotherbutton"></a><a name="enableotherbutton"></a>ボタンをクリックします。

通常のカラー ボタンの下に配置されている "その他" ボタンを有効または無効にします。 (標準システムの「その他」ボタンには、**その他の色**のラベルが付いています。

```cpp
void EnableOtherButton(
    LPCTSTR lpszLabel,
    BOOL bAltColorDlg=TRUE,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>パラメーター

*ラベル*<br/>
[in]ボタンテキストを指定します。

*アルトカラードグルグ*<br/>
[in]`CMFCColorDialog`ダイアログ ボックスを表示するには TRUE を指定し、標準のシステム カラー ダイアログ ボックスを表示するには FALSE を指定します。

*b 有効にする*<br/>
[in]TRUE を指定すると、"その他" ボタンが表示されます。それ以外の場合は FALSE。 デフォルトは TRUE です。

### <a name="remarks"></a>解説

## <a name="cmfccolormenubuttonenabletearoff"></a><a name="enabletearoff"></a>CMFCカラーメニューボタン::イネーブルティアオフ

カラー ペインを引き裂く機能を有効にします。

```cpp
void EnableTearOff(
    UINT uiID,
    int nVertDockColumns=-1,
    int nHorzDockRows=-1);
```

### <a name="parameters"></a>パラメーター

*Uiid*<br/>
[in]ティアオフ ペインの ID を指定します。

*列数*<br/>
[in]ティアオフ状態の間に、垂直にドッキングされたカラー ペイン内の列数を指定します。

*オーズドックロウズ*<br/>
[in]ティアオフ状態の間に、水平にドッキングされたカラー ペインの行数を指定します。

### <a name="remarks"></a>解説

ボタンが押されたときにポップアップするカラー ペインの "ティアオフ" 機能を`CMFCColorMenuButton`有効にします。

## <a name="cmfccolormenubuttongetautomaticcolor"></a><a name="getautomaticcolor"></a>コントロール:自動カラーを取得します。

現在の自動色を取得します。

```
COLORREF GetAutomaticColor() const;
```

### <a name="return-value"></a>戻り値

現在の自動色を表す RGB カラー値。

### <a name="remarks"></a>解説

このメソッドを呼び出して[、CMFCColorMenuButton::有効自動ボタン](#enableautomaticbutton)によって設定された自動色を取得します。

## <a name="cmfccolormenubuttongetcolor"></a><a name="getcolor"></a>メニューボタン::ゲットカラー

現在のボタンの色を取得します。

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>戻り値

ボタンの色。

### <a name="remarks"></a>解説

## <a name="cmfccolormenubuttongetcolorbycmdid"></a><a name="getcolorbycmdid"></a>ボタン::取得カラーバイコマンドイド

指定したコマンド ID に対応する色を取得します。

```
static COLORREF GetColorByCmdID(UINT uiCmdID);
```

### <a name="parameters"></a>パラメーター

*UICmdID*<br/>
[in]コマンド ID。

### <a name="return-value"></a>戻り値

指定したコマンド ID に対応する色。

### <a name="remarks"></a>解説

このメソッドは、アプリケーションに複数のカラー ボタンがある場合に使用します。 ユーザーがカラー ボタンをクリックすると、ボタンはWM_COMMANDメッセージのコマンド ID を親に送信します。 この`GetColorByCmdID`メソッドは、コマンド ID を使用して、対応する色を取得します。

## <a name="cmfccolormenubuttonisemptymenuallowed"></a><a name="isemptymenuallowed"></a>ボタン::IsEmptyメニューを許可

空のメニューがサポートされているかどうかを示します。

```
virtual BOOL IsEmptyMenuAllowed() const;
```

### <a name="return-value"></a>戻り値

空のメニューが許可されている場合は 0 以外の値を指定します。それ以外の場合は、ゼロ。

### <a name="remarks"></a>解説

空のメニューは、デフォルトでサポートされています。 派生クラスでこの動作を変更するには、このメソッドをオーバーライドします。

## <a name="cmfccolormenubuttononchangeparentwnd"></a><a name="onchangeparentwnd"></a>ボタン:オンチェンジペアレント

親ウィンドウが変更されたときに、フレームワークによって呼び出されます。

```
virtual void OnChangeParentWnd(CWnd* pWndParent);
```

### <a name="parameters"></a>パラメーター

*親の子*<br/>
[in]新しい親ウィンドウへのポインター。

### <a name="remarks"></a>解説

## <a name="cmfccolormenubuttonondraw"></a><a name="ondraw"></a>メニューボタン::ドロー

ボタンにイメージを表示するために、フレームワークによって呼び出されます。

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
[in]デバイス コンテキストへのポインター。

*Rect*<br/>
[in]再描画する領域に境界を設定する四角形。

*pイメージズ*<br/>
[in]ツール バー イメージの一覧へのポイント。

*bHorz*<br/>
[in]ツール バーが水平ドッキング状態であることを指定する場合は TRUE。それ以外の場合は FALSE。 デフォルトは TRUE です。

*モードをカスタマイズする*<br/>
[in]アプリケーションがカスタマイズ モードであることを指定する場合は TRUE。それ以外の場合は FALSE。 デフォルトは FALSE です。

*bハイライト*<br/>
[in]ボタンが強調表示されることを指定する場合は TRUE。それ以外の場合は FALSE。 デフォルトは FALSE です。

*ボーダーを描く*<br/>
[in]ボタンの境界線を表示する場合は TRUE。それ以外の場合は FALSE。 デフォルトは TRUE です。

*ボタン*<br/>
[in]無効なボタンが淡色表示 (淡色表示) であることを指定する場合は TRUE。それ以外の場合は FALSE。 デフォルトは TRUE です。

### <a name="remarks"></a>解説

## <a name="cmfccolormenubuttonondrawoncustomizelist"></a><a name="ondrawoncustomizelist"></a>メニューボタン::オンドローオンカスタマイザ

ツール バーのカスタマイズ`CMFCColorMenuButton`ダイアログ ボックスの一覧にオブジェクトが表示される前に、フレームワークによって呼び出されます。

```
virtual int OnDrawOnCustomizeList(
    CDC* pDC,
    const CRect& rect,
    BOOL bSelected);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]デバイス コンテキストへのポインター。

*Rect*<br/>
[in]描画するボタンに境界を設定する四角形。

*b選択済み*<br/>
[in]TRUE は、ボタンが選択状態であることを指定します。それ以外の場合は FALSE。

### <a name="return-value"></a>戻り値

ボタンの幅。

### <a name="remarks"></a>解説

このメソッドは、ツール バーのカスタマイズ`CMFCColorMenuButton`プロセス中にオブジェクトがリスト ボックスに表示されるときに、フレームワークによって呼び出されます。

## <a name="cmfccolormenubuttonopencolordialog"></a><a name="opencolordialog"></a>ボタン::カラーダイアログ

色選択ダイアログ ボックスを開きます。

```
virtual BOOL OpenColorDialog(
    const COLORREF colorDefault,
    COLORREF& colorRes);
```

### <a name="parameters"></a>パラメーター

*カラーデフォルト*<br/>
[in]色ダイアログ ボックスで選択されている既定の色。

*カラーレス*<br/>
[アウト]ユーザーが色ダイアログ ボックスから選択した色を返します。

### <a name="return-value"></a>戻り値

ユーザーが新しい色を選択した場合は 0 以外の値を指定します。それ以外の場合は、ゼロ。

### <a name="remarks"></a>解説

メニュー ボタンがクリックされたら、このメソッドを呼び出して、色のダイアログ ボックスを開きます。 戻り値が 0 以外の場合、ユーザーが選択した色は*colorRes*パラメーターに格納されます。 標準の色のダイアログ ボックスと[[CMFCColorDialog](#enableotherbutton) [クラス](../../mfc/reference/cmfccolordialog-class.md)] ダイアログ ボックスを切り替えるには、メソッドを使用します。

## <a name="cmfccolormenubuttonsetcolor"></a><a name="setcolor"></a>メニューボタン::セットカラー

現在のカラー ボタンの色を設定します。

```
virtual void SetColor(
    COLORREF clr,
    BOOL bNotify=TRUE);
```

### <a name="parameters"></a>パラメーター

*Clr*<br/>
[in]RGB カラー値。

*通知する*<br/>
[in]関連付けられたメニュー ボタンまたはツール バー ボタンに*clr*パラメーターの色を適用する場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

現在の色のボタンの色を変更します。 *bNotify*パラメーターが 0 以外の場合、関連付けられているポップアップ メニューまたはツール バーの対応するボタンの色が *、clr*パラメーターで指定された色に変更されます。

## <a name="cmfccolormenubuttonsetcolorbycmdid"></a><a name="setcolorbycmdid"></a>ボタン::セットカラーバイコマンドイド

指定したカラー メニュー ボタンの色を設定します。

```
static void SetColorByCmdID(
    UINT uiCmdID,
    COLORREF color);
```

### <a name="parameters"></a>パラメーター

*UICmdID*<br/>
[in]カラー メニュー ボタンのリソース ID。

*色*<br/>
[in]RGB カラー値。

## <a name="cmfccolormenubuttonsetcolorname"></a><a name="setcolorname"></a>ボタン::セットカラー名

指定した色の新しい名前を設定します。

```
static void SetColorName(
    COLORREF color,
    const CString& strName);
```

### <a name="parameters"></a>パラメーター

*色*<br/>
[in]名前が変更された色の RGB 値。

*strName*<br/>
[in]色の新しい名前。

### <a name="remarks"></a>解説

## <a name="cmfccolormenubuttonsetcolumnsnumber"></a><a name="setcolumnsnumber"></a>メニューボタン::列番号の設定

カラー選択コントロール[(CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md)オブジェクト) に表示する列の数を設定します。

```cpp
void SetColumnsNumber(int nColumns);
```

### <a name="parameters"></a>パラメーター

*nColumns*<br/>
[in]表示する列の数。

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CMFCColorBar クラス](../../mfc/reference/cmfccolorbar-class.md)<br/>
[クラス](../../mfc/reference/cmfctoolbar-class.md)<br/>
[クラスをカスタマイズします。](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)<br/>
[クラス](../../mfc/reference/cmfccolorbutton-class.md)
