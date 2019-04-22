---
title: CMFCColorButton クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCColorButton
- AFXCOLORBUTTON/CMFCColorButton
- AFXCOLORBUTTON/CMFCColorButton::CMFCColorButton
- AFXCOLORBUTTON/CMFCColorButton::EnableAutomaticButton
- AFXCOLORBUTTON/CMFCColorButton::EnableOtherButton
- AFXCOLORBUTTON/CMFCColorButton::GetAutomaticColor
- AFXCOLORBUTTON/CMFCColorButton::GetColor
- AFXCOLORBUTTON/CMFCColorButton::SetColor
- AFXCOLORBUTTON/CMFCColorButton::SetColorName
- AFXCOLORBUTTON/CMFCColorButton::SetColumnsNumber
- AFXCOLORBUTTON/CMFCColorButton::SetDocumentColors
- AFXCOLORBUTTON/CMFCColorButton::SetPalette
- AFXCOLORBUTTON/CMFCColorButton::SizeToContent
- AFXCOLORBUTTON/CMFCColorButton::IsDrawXPTheme
- AFXCOLORBUTTON/CMFCColorButton::OnDraw
- AFXCOLORBUTTON/CMFCColorButton::OnDrawBorder
- AFXCOLORBUTTON/CMFCColorButton::OnDrawFocusRect
- AFXCOLORBUTTON/CMFCColorButton::OnShowColorPopup
- AFXCOLORBUTTON/CMFCColorButton::RebuildPalette
- AFXCOLORBUTTON/CMFCColorButton::UpdateColor
- AFXCOLORBUTTON/CMFCColorButton::m_bEnabledInCustomizeMode
helpviewer_keywords:
- CMFCColorButton [MFC], CMFCColorButton
- CMFCColorButton [MFC], EnableAutomaticButton
- CMFCColorButton [MFC], EnableOtherButton
- CMFCColorButton [MFC], GetAutomaticColor
- CMFCColorButton [MFC], GetColor
- CMFCColorButton [MFC], SetColor
- CMFCColorButton [MFC], SetColorName
- CMFCColorButton [MFC], SetColumnsNumber
- CMFCColorButton [MFC], SetDocumentColors
- CMFCColorButton [MFC], SetPalette
- CMFCColorButton [MFC], SizeToContent
- CMFCColorButton [MFC], IsDrawXPTheme
- CMFCColorButton [MFC], OnDraw
- CMFCColorButton [MFC], OnDrawBorder
- CMFCColorButton [MFC], OnDrawFocusRect
- CMFCColorButton [MFC], OnShowColorPopup
- CMFCColorButton [MFC], RebuildPalette
- CMFCColorButton [MFC], UpdateColor
- CMFCColorButton [MFC], m_bEnabledInCustomizeMode
ms.assetid: 9fdf34ae-4cc5-4c5e-9d89-1c50e8a73699
ms.openlocfilehash: c0c9ad79342f2013aa071240c684fce168e55c9e
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "58780003"
---
# <a name="cmfccolorbutton-class"></a>CMFCColorButton クラス

`CMFCColorButton`と[CMFCColorBar クラス](../../mfc/reference/cmfccolorbar-class.md)カラー ピッカー コントロールを実装するクラスを組み合わせて使用します。

## <a name="syntax"></a>構文

```
class CMFCColorButton : public CMFCButton
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CMFCColorButton::CMFCColorButton](#cmfccolorbutton)|新しい `CMFCColorButton` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCColorButton::EnableAutomaticButton](#enableautomaticbutton)|有効にし、通常の色のボタンの上に配置された「自動」のボタンを無効にします。 (標準のシステムの自動ボタンのラベルは**自動**)。|
|[CMFCColorButton::EnableOtherButton](#enableotherbutton)|有効にし、標準のカラー ボタンの下にある、「その他」ボタンを無効にします。 ("Other"ボタンのラベルは、標準的なシステム**その他の色**)。|
|[CMFCColorButton::GetAutomaticColor](#getautomaticcolor)|現在の自動の色を取得します。|
|[CMFCColorButton::GetColor](#getcolor)|ボタンの色を取得します。|
|[CMFCColorButton::SetColor](#setcolor)|ボタンの色を設定します。|
|[CMFCColorButton::SetColorName](#setcolorname)|色の名前を設定します。|
|[CMFCColorButton::SetColumnsNumber](#setcolumnsnumber)|カラー ピッカー ダイアログ ボックスで、列の数を設定します。|
|[CMFCColorButton::SetDocumentColors](#setdocumentcolors)|カラー ピッカー ダイアログ ボックスに表示されるドキュメントに固有の色の一覧を指定します。|
|[CMFCColorButton::SetPalette](#setpalette)|標準の表示の色のパレットを指定します。|
|[CMFCColorButton::SizeToContent](#sizetocontent)|テキストとイメージのサイズに応じて、ボタン コントロールのサイズを変更します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CMFCColorButton::IsDrawXPTheme](#isdrawxptheme)|Windows XP の visual スタイルで現在のカラー ボタンを表示するかどうかを示します。|
|[CMFCColorButton::OnDraw](#ondraw)|ボタンのイメージを表示するためにフレームワークによって呼び出されます。|
|[CMFCColorButton::OnDrawBorder](#ondrawborder)|ボタンの境界線を表示するためにフレームワークによって呼び出されます。|
|[CMFCColorButton::OnDrawFocusRect](#ondrawfocusrect)|ボタンにフォーカスがあるときに、フォーカスの四角形を表示するためにフレームワークによって呼び出されます。|
|[CMFCColorButton::OnShowColorPopup](#onshowcolorpopup)|カラー ピッカー ダイアログ ボックスが表示されるときに、フレームワークによって呼び出されます。|
|[CMFCColorButton::RebuildPalette](#rebuildpalette)|初期化します、`m_pPalette`パレットを指定または既定のシステム パレット データ メンバーを保護します。|
|[CMFCColorButton::UpdateColor](#updatecolor)|カラー ピッカー ダイアログ ボックスのパレットから色を選択すると、フレームワークによって呼び出されます。|

### <a name="data-members"></a>データ メンバー

|名前|説明|
|----------|-----------------|
|`m_bAltColorDlg`|ブール値。 TRUE の場合、フレームワークが表示されます、 [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md)色 ダイアログ ボックスの場合に、*他*ボタンをクリックすると、FALSE の場合、システムの色 ダイアログ ボックスまたはします。 既定値は TRUE です。 詳細については、次を参照してください。 [CMFCColorButton::EnableOtherButton](#enableotherbutton)します。|
|`m_bAutoSetFocus`|ブール値。 TRUE の場合、フレームワークは、メニューが表示されたら、または FALSE の場合がフォーカスを変更していないときに、[色] メニュー、フォーカスを設定します。 既定値は TRUE です。|
|[CMFCColorButton::m_bEnabledInCustomizeMode](#m_benabledincustomizemode)|色のボタンのカスタマイズ モードが有効になっているかどうかを示します。|
|`m_Color`|A [COLORREF](/windows/desktop/gdi/colorref)値。 現在選択されている色が含まれています。|
|`m_ColorAutomatic`|A [COLORREF](/windows/desktop/gdi/colorref)値。 現在選択されている既定の色が含まれています。|
|`m_Colors`|A [CArray](../../mfc/reference/carray-class.md)の[COLORREF](/windows/desktop/gdi/colorref)値。 現在使用できる色が含まれています。|
|`m_lstDocColors`|A [CList](../../mfc/reference/clist-class.md)の[COLORREF](/windows/desktop/gdi/colorref)値。 現在のドキュメントの色が含まれています。|
|`m_nColumns`|整数。 色の選択メニューでの色のグリッドに表示する列の数が含まれています。|
|`m_pPalette`|ポインターを[CPalette](../../mfc/reference/cpalette-class.md)します。 現在の色の選択メニューで利用できる色が含まれています。|
|`m_pPopup`|ポインターを[CMFCColorPopupMenu クラス](../../mfc/reference/cmfccolorpopupmenu-class.md)オブジェクト。 色のボタンをクリックすると表示される色の選択メニュー。|
|`m_strAutoColorText`|文字列。 色の選択メニューで「自動」のボタンのラベル。|
|`m_strDocColorsText`|文字列。 ドキュメントの色を表示する色の選択メニュー ボタンのラベル。|
|`m_strOtherText`|文字列。 色の選択メニューで「その他」ボタンのラベルです。|

## <a name="remarks"></a>Remarks

既定で、`CMFCColorButton`クラスをカラー ピッカー ダイアログ ボックスを開くプッシュ ボタンと同様に動作します。 カラー ピッカー ダイアログ ボックスには、小さなカラー ボタンと、カスタム カラー ピッカーを表示する、「その他」ボタンの配列が含まれています。 ("Other"ボタンのラベルは、標準的なシステム**その他の色**)。ユーザーが、新しい色を選択すると、`CMFCColorButton`オブジェクトの変更が反映され、選択した色が表示されます。

コードで直接、またはを使用して、色のボタン コントロールを作成、 **ClassWizard**ツールとダイアログ ボックスのテンプレート。 色のボタン コントロールを直接作成する場合は、追加、`CMFCColorButton`変数を呼び出して、コンス トラクター、アプリケーション、および`Create`のメソッド、`CMFCColorButton`オブジェクト。 使用する場合、 **ClassWizard**、追加、`CButton`アプリケーションには、変数から変数の種類を変更および`CButton`に`CMFCColorButton`します。

カラー ピッカー ダイアログ ボックス ( [CMFCColorBar クラス](../../mfc/reference/cmfccolorbar-class.md)) によって表示される、 [CMFCColorButton::OnShowColorPopup](#onshowcolorpopup)メソッド フレームワーク、`OnLButtonDown`イベント ハンドラー。 [CMFCColorButton::OnShowColorPopup](#onshowcolorpopup)カスタム色の選択をサポートするメソッドをオーバーライドすることができます。

`CMFCColorButton`オブジェクトが親 WM_COMMAND を送信することで、色が変更されていることを通知します |BN_CLICKED 通知します。 親を使用して、 [CMFCColorButton::GetColor](#getcolor)現在の色を取得します。

## <a name="example"></a>例

次の例は、さまざまなメソッドを使用してカラー ボタンを構成する方法を示します、`CMFCColorButton`クラス。 メソッドは、色のボタンと、列の数の色を設定し、自動およびその他のボタンを有効にします。 この例は、[ステータス バーのデモ サンプル](../../overview/visual-cpp-samples.md)します。

[!code-cpp[NVC_MFC_StatusBarDemo#10](../../mfc/reference/codesnippet/cpp/cmfccolorbutton-class_1.h)]
[!code-cpp[NVC_MFC_StatusBarDemo#11](../../mfc/reference/codesnippet/cpp/cmfccolorbutton-class_2.cpp)]

## <a name="requirements"></a>必要条件

**ヘッダー:** afxcolorbutton.h

##  <a name="cmfccolorbutton"></a>  CMFCColorButton::CMFCColorButton

新しい `CMFCColorButton` オブジェクトを構築します。

```
CMFCColorButton();
```

##  <a name="enableautomaticbutton"></a>  CMFCColorButton::EnableAutomaticButton

有効にまたは、カラー ピッカー コントロールの「自動」ボタンを無効にし、自動 (既定値) の色を設定します。

```
void EnableAutomaticButton(
    LPCTSTR lpszLabel,
    COLORREF colorAutomatic,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>パラメーター

*lpszLabel*<br/>
[in]自動ボタンのテキストを指定します。

*colorAutomatic*<br/>
[in]自動ボタンの既定の色を指定する RGB 値を指定します。

*bEnable*<br/>
[in]自動ボタンが有効になっているかどうかを指定します。

### <a name="remarks"></a>Remarks

##  <a name="enableotherbutton"></a>  CMFCColorButton::EnableOtherButton

有効または通常の色のボタンの下に表示される"other"ボタンを無効にします。

```
void EnableOtherButton(
    LPCTSTR lpszLabel,
    BOOL bAltColorDlg=TRUE,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>パラメーター

*lpszLabel*<br/>
[in]ボタンのテキストを指定します。

*bAltColorDlg*<br/>
[in]指定するかどうか、 [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md)  ダイアログ ボックスまたはシステムの色 ダイアログ ボックスを開いたときに、ユーザーがボタンをクリックします。

*bEnable*<br/>
[in]「その他」ボタンが有効になっているかどうかを指定します。

### <a name="remarks"></a>Remarks

「その他」の色 ダイアログ ボックスを表示するボタンをクリックします。 場合、 *bAltColorDlg*パラメーターが true の場合、 [CMFCColorDialog クラス](../../mfc/reference/cmfccolordialog-class.md)が表示されます。 それ以外の場合、システムの色 ダイアログ ボックスが表示されます。

##  <a name="getautomaticcolor"></a>  CMFCColorButton::GetAutomaticColor

自動 (既定値) の現在の色を取得します。

```
COLORREF GetAutomaticColor() const;
```

### <a name="return-value"></a>戻り値

現在の自動の色を表す RGB 値。

### <a name="remarks"></a>Remarks

現在の自動の色が設定され、 [CMFCColorButton::EnableAutomaticButton](#enableautomaticbutton)メソッド。

##  <a name="getcolor"></a>  CMFCColorButton::GetColor

現在選択されている色を取得します。

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>戻り値

RGB 値。

### <a name="remarks"></a>Remarks

##  <a name="isdrawxptheme"></a>  CMFCColorButton::IsDrawXPTheme

Windows XP の visual スタイルで現在のカラー ボタンを表示するかどうかを示します。

```
BOOL IsDrawXPTheme() const;
```

### <a name="return-value"></a>戻り値

Visual スタイルがサポートされており、Windows XP の visual スタイルで現在のカラー ボタンが表示される場合は TRUE。それ以外の場合、FALSE です。

##  <a name="m_benabledincustomizemode"></a>  CMFCColorButton::m_bEnabledInCustomizeMode

カラー ボタンをカスタマイズ モードに設定します。

```
BOOL m_bEnabledInCustomizeMode;
```

### <a name="remarks"></a>Remarks

カスタマイズ ダイアログ ボックスのページにカラー ボタンを追加 (または、ユーザーがカスタマイズするときに別の色の選択を行うことを許可する) 必要がある場合は、設定して、ボタンを有効に、`m_bEnabledInCustomizeMode`メンバーを TRUE にします。 既定では、このメンバーは FALSE に設定します。

##  <a name="ondraw"></a>  CMFCColorButton::OnDraw

ボタンの画像を表示するためにフレームワークによって呼び出されます。

```
virtual void OnDraw(
    CDC* pDC,
    const CRect& rect,
    UINT uiState);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]ボタンのイメージを表示するために使用されるデバイス コンテキストへのポインター。

*rect*<br/>
[in]ボタンの外接する四角形にします。

*uiState*<br/>
[in]ボタンのビジュアル状態を指定します。

### <a name="remarks"></a>Remarks

レンダリング プロセスをカスタマイズするには、このメソッドをオーバーライドします。

##  <a name="ondrawborder"></a>  CMFCColorButton::OnDrawBorder

ボタンの境界線を表示するためにフレームワークによって呼び出されます。

```
virtual void OnDrawBorder(
    CDC* pDC,
    CRect& rectClient,
    UINT uiState);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]境界線の描画に使用するデバイス コンテキストへのポインター。

*rectClient*<br/>
[in]指定されているデバイス コンテキスト内の四角形、 *pDC*を描画するボタンの境界を定義するパラメーター。

*uiState*<br/>
[in]ボタンのビジュアル状態を指定します。

### <a name="remarks"></a>Remarks

色のボタンの境界線の外観をカスタマイズするには、この関数をオーバーライドします。

##  <a name="ondrawfocusrect"></a>  CMFCColorButton::OnDrawFocusRect

ボタンにフォーカスがあるときに、フォーカスの四角形を表示するためにフレームワークによって呼び出されます。

```
virtual void OnDrawFocusRect(
    CDC* pDC,
    const CRect& rectClient);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]フォーカスされた四角形を描画するために使用するデバイス コンテキストへのポインター。

*rectClient*<br/>
[in]指定されたデバイス コンテキスト内の四角形、 *pDC*ボタンの境界を定義するパラメーター。

### <a name="remarks"></a>Remarks

フォーカスされた四角形の外観をカスタマイズするには、このメソッドをオーバーライドします。

##  <a name="onshowcolorpopup"></a>  CMFCColorButton::OnShowColorPopup

ポップアップ カラー バーが表示される前に呼び出されます。

```
virtual void OnShowColorPopup();
```

### <a name="remarks"></a>Remarks

##  <a name="rebuildpalette"></a>  CMFCColorButton::RebuildPalette

初期化します、`m_pPalette`パレットを指定または既定のシステム パレット データ メンバーを保護します。

```
void RebuildPalette(CPalette* pPal);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*pPal*|[in]論理パレットまたは NULL へのポインター。 NULL の場合、既定のシステム パレットが使用されます。|

##  <a name="setcolor"></a>  CMFCColorButton::SetColor

ボタンの色を指定します。

```
void SetColor(COLORREF color);
```

### <a name="parameters"></a>パラメーター

*色*<br/>
[in]RGB 値。

### <a name="remarks"></a>Remarks

##  <a name="setcolorname"></a>  CMFCColorButton::SetColorName

色の名前を指定します。

```
static void SetColorName(
    COLORREF color,
    const CString& strName);
```

### <a name="parameters"></a>パラメーター

*色*<br/>
[in]色の RGB 値。

*strName*<br/>
[in]色の名前。

### <a name="remarks"></a>Remarks

色の名前の一覧は、アプリケーションごとにグローバルです。 その結果、このメソッドは移動するには、そのパラメーター [CMFCColorBar::SetColorName](../../mfc/reference/cmfccolorbar-class.md#setcolorname)します。

##  <a name="setcolumnsnumber"></a>  CMFCColorButton::SetColumnsNumber

ユーザーの色の選択プロセス中に、ユーザーに表示される色の一覧に表示される列の数を定義します。

```
void SetColumnsNumber(int nColumns);
```

### <a name="parameters"></a>パラメーター

*nColumns*<br/>
[in]列の数を指定します。

### <a name="remarks"></a>Remarks

ユーザーは、定義済みの色の一覧が表示されるポップアップ カラー バーから色を選択することができます。 このメソッドを使用すると、テーブルの列の数を定義できます。

##  <a name="setdocumentcolors"></a>  CMFCColorButton::SetDocumentColors

一連の色とセットの名前を指定します。 使用して色のセットを表示、 [CMFCColorBar クラス](../../mfc/reference/cmfccolorbar-class.md)オブジェクト。

```
void SetDocumentColors(
    LPCTSTR lpszLabel,
    CList<COLORREF,COLORREF>& lstColors);
```

### <a name="parameters"></a>パラメーター

*lpszLabel*<br/>
[in]ドキュメントの色のセットを表示するラベルを指定します。

*lstColors*<br/>
[in]RGB 値の一覧への参照。

### <a name="remarks"></a>Remarks

A`CMFCColorButton`オブジェクトに転送する RGB 値のリストを保持する、 [CMFCColorBar クラス](../../mfc/reference/cmfccolorbar-class.md)オブジェクト。 これらの色はラベルがで指定された特別なセクションに示したカラー バーが表示されたら、 *lpszLabel*パラメーター。

##  <a name="setpalette"></a>  CMFCColorButton::SetPalette

ポップアップ カラー バーに表示する標準の色を指定します。

```
void SetPalette(CPalette* pPalette);
```

### <a name="parameters"></a>パラメーター

*pPalette*<br/>
[in]色パレットへのポインター。

### <a name="remarks"></a>Remarks

##  <a name="sizetocontent"></a>  CMFCColorButton::SizeToContent

ボタン コントロールに合わせてそのテキストとイメージのサイズを変更します。

```
virtual CSize SizeToContent(BOOL bCalcOnly=FALSE);
```

### <a name="parameters"></a>パラメーター

*bCalcOnly*<br/>
[in]0 以外の場合は、ボタン コントロールの新しいサイズが計算されますが、実際のサイズは変更されません。

### <a name="return-value"></a>戻り値

A`CSize`新しいボタン コントロールのサイズを指定するオブジェクト。

### <a name="remarks"></a>Remarks

##  <a name="updatecolor"></a>  CMFCColorButton::UpdateColor

ユーザーが、ユーザーが色のボタンをクリックしたときに表示するカラー バーの色を選択、フレームワークによって呼び出されます。

```
virtual void UpdateColor(COLORREF color);
```

### <a name="parameters"></a>パラメーター

*色*<br/>
[in]ユーザーが選択した色。

### <a name="remarks"></a>Remarks

`UpdateColor`関数は、現在選択されているボタンの色を変更し、BN_CLICKED 標準通知 WM_COMMAND メッセージを送信することによって、親に通知します。 使用して、 [CMFCColorButton::GetColor](#getcolor)選択した色を取得します。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CMFCButton クラス](../../mfc/reference/cmfcbutton-class.md)<br/>
[CMFCColorBar クラス](../../mfc/reference/cmfccolorbar-class.md)<br/>
[CMFCColorButton::OnShowColorPopup](#onshowcolorpopup)<br/>
[COLORREF](/windows/desktop/gdi/colorref)<br/>
[CPalette クラス](../../mfc/reference/cpalette-class.md)<br/>
[CArray クラス](../../mfc/reference/carray-class.md)<br/>
[CList クラス](../../mfc/reference/clist-class.md)<br/>
[CString](../../atl-mfc-shared/reference/cstringt-class.md)
