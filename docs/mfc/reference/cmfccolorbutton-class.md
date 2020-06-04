---
title: クラス
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
ms.openlocfilehash: cf24c162d0eda272f73c69c434589ae6ef3332a4
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752560"
---
# <a name="cmfccolorbutton-class"></a>クラス

クラスと[CMFCColorBar クラス](../../mfc/reference/cmfccolorbar-class.md)は、カラー ピッカー コントロールを実装するために一緒に使用されます。 `CMFCColorButton`

## <a name="syntax"></a>構文

```
class CMFCColorButton : public CMFCButton
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CMFCカラーボタン::CMFCカラーボタン](#cmfccolorbutton)|新しい `CMFCColorButton` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCカラーボタン::自動ボタンを有効にする](#enableautomaticbutton)|通常のカラー ボタンの上に配置されている "自動" ボタンを有効または無効にします。 (標準システムの自動ボタンには**自動**とラベルが付いています。|
|[CMFCカラーボタン::他のボタンを有効にする](#enableotherbutton)|通常のカラー ボタンの下に配置されている "その他" ボタンを有効または無効にします。 (標準システムの「その他」ボタンには、**その他の色**のラベルが付いています。|
|[カラーボタンを取得します。](#getautomaticcolor)|現在の自動色を取得します。|
|[カラーボタンをクリックします。](#getcolor)|ボタンの色を取得します。|
|[カラーボタン::セットカラー](#setcolor)|ボタンの色を設定します。|
|[カラーボタンを設定します。](#setcolorname)|色の名前を設定します。|
|[数列番号](#setcolumnsnumber)|カラー ピッカー ダイアログ ボックスの列数を設定します。|
|[カラーの設定](#setdocumentcolors)|カラー ピッカー ダイアログ ボックスに表示されるドキュメント固有の色の一覧を指定します。|
|[カラーボタン::セットパレット](#setpalette)|標準の表示色のパレットを指定します。|
|[コンテンツのサイズ](#sizetocontent)|ボタン コントロールのテキストとイメージのサイズに応じて、ボタン コントロールのサイズを変更します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CMFCカラーボタン::イズドローエクステーマ](#isdrawxptheme)|現在の色のボタンが Windows XP のビジュアル スタイルで表示されるかどうかを示します。|
|[カラーボタン::オンドロー](#ondraw)|ボタンのイメージを表示するために、フレームワークによって呼び出されます。|
|[カラーボタン::オンドローボーダー](#ondrawborder)|ボタンの境界線を表示するために、フレームワークによって呼び出されます。|
|[カラーボタン::オンドローフォーカスレクト](#ondrawfocusrect)|ボタンにフォーカスがあるときにフォーカス四角形を表示するために、フレームワークによって呼び出されます。|
|[カラーボタン::オンショーカラーポップアップ](#onshowcolorpopup)|カラー ピッカー ダイアログ ボックスが表示されるときに、フレームワークによって呼び出されます。|
|[CMFCカラーボタン::リビルドパレット](#rebuildpalette)|保護されたデータ`m_pPalette`メンバーを、指定されたパレットまたは既定のシステム パレットに初期化します。|
|[CMFCColorButton::UpdateColor](#updatecolor)|ユーザーがカラー ピッカー ダイアログ ボックスのパレットから色を選択したときに、フレームワークによって呼び出されます。|

### <a name="data-members"></a>データ メンバー

|名前|説明|
|----------|-----------------|
|`m_bAltColorDlg`|ブール値。 TRUE の場合、フレームワークは、*他*のボタンがクリックされたとき、または FALSE の場合は、システムの色のダイアログ ボックスを[表示](../../mfc/reference/cmfccolordialog-class.md)します。 既定値は TRUE です。 詳細については[、「CMFC カラー ボタン::その他のボタンを有効にする」を参照してください](#enableotherbutton)。|
|`m_bAutoSetFocus`|ブール値。 TRUE の場合、フレームワークは、メニューが表示されるとき、または FALSE の場合はフォーカスを変更しないときに、カラー メニューにフォーカスを設定します。 既定値は TRUE です。|
|[カラーボタン:m_bEnabledInCustomizeMode](#m_benabledincustomizemode)|色のボタンに対してカスタマイズ モードが有効になっているかどうかを示します。|
|`m_Color`|[カラー参照](/windows/win32/gdi/colorref)値。 現在選択されている色が含まれます。|
|`m_ColorAutomatic`|[カラー参照](/windows/win32/gdi/colorref)値。 現在選択されている既定の色が含まれます。|
|`m_Colors`|[カラーレフ](/windows/win32/gdi/colorref)値の[CArray。](../../mfc/reference/carray-class.md) 現在使用可能な色が含まれています。|
|`m_lstDocColors`|[カラーレフ](/windows/win32/gdi/colorref)値の[C リスト](../../mfc/reference/clist-class.md)。 現在のドキュメントの色が含まれます。|
|`m_nColumns`|整数。 色選択メニューの色のグリッドに表示する列の数を格納します。|
|`m_pPalette`|[CPalette](../../mfc/reference/cpalette-class.md)へのポインター。 現在の色選択メニューで使用できる色が含まれています。|
|`m_pPopup`|[クラス](../../mfc/reference/cmfccolorpopupmenu-class.md)オブジェクトへのポインター。 カラー ボタンをクリックしたときに表示される色選択メニュー。|
|`m_strAutoColorText`|文字列。 色選択メニューの「自動」ボタンのラベル。|
|`m_strDocColorsText`|文字列。 ドキュメントの色を表示する色選択メニューのボタンのラベル。|
|`m_strOtherText`|文字列。 色選択メニューの "その他" ボタンのラベル。|

## <a name="remarks"></a>解説

既定では、`CMFCColorButton`クラスは、カラー ピッカー ダイアログ ボックスを開くプッシュ ボタンとして動作します。 カラー ピッカー ダイアログ ボックスには、小さい色のボタンの配列とカスタム カラー ピッカーを表示する "その他" ボタンがあります。 (標準システムの「その他」ボタンには、**その他の色**のラベルが付いています。ユーザーが新しい色を選択すると、オブジェクト`CMFCColorButton`に変更が反映され、選択した色が表示されます。

コード内で直接、または**ClassWizard**ツールとダイアログ ボックス テンプレートを使用して、カラー ボタン コントロールを作成します。 カラー ボタン コントロールを直接作成する場合は`CMFCColorButton`、アプリケーションに変数を追加し、オブジェクトのコンストラクター`Create`とメソッドを`CMFCColorButton`呼び出します。 **ClassWizard**を使用する場合は、`CButton`アプリケーションに変数を追加し、変数の型を に`CButton`変更します`CMFCColorButton`。

フレームワークが`OnLButtonDown`イベント ハンドラーを呼び出すと、カラー ピッカー ダイアログ ボックス ( [CMFCColorBar クラス](../../mfc/reference/cmfccolorbar-class.md)) が[CMFCColorButton::OnShowColorPopup](#onshowcolorpopup)メソッドによって表示されます。 カスタム[カラー選択を](#onshowcolorpopup)サポートするために、メソッドをオーバーライドできます。

オブジェクト`CMFCColorButton`は、そのオブジェクトにWM_COMMANDを送信することによって、色が変化していることを親に通知します。BN_CLICKED通知。 親は、現在の色を取得するために[CMFCColorButton::GetColor](#getcolor)メソッドを使用します。

## <a name="example"></a>例

`CMFCColorButton`クラスのさまざまなメソッドを使用してカラー ボタンを構成する方法を次の例に示します。 このメソッドは、カラー ボタンの色と列数を設定し、自動ボタンおよびその他のボタンを有効にします。 この例は[、ステータス バーのデモ サンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_StatusBarDemo#10](../../mfc/reference/codesnippet/cpp/cmfccolorbutton-class_1.h)]
[!code-cpp[NVC_MFC_StatusBarDemo#11](../../mfc/reference/codesnippet/cpp/cmfccolorbutton-class_2.cpp)]

## <a name="requirements"></a>必要条件

**ヘッダー:** afxcolorbutton.h

## <a name="cmfccolorbuttoncmfccolorbutton"></a><a name="cmfccolorbutton"></a>CMFCカラーボタン::CMFCカラーボタン

新しい `CMFCColorButton` オブジェクトを構築します。

```
CMFCColorButton();
```

## <a name="cmfccolorbuttonenableautomaticbutton"></a><a name="enableautomaticbutton"></a>CMFCカラーボタン::自動ボタンを有効にする

カラー ピッカー コントロールの [自動] ボタンを有効または無効にし、自動 (既定) の色を設定します。

```cpp
void EnableAutomaticButton(
    LPCTSTR lpszLabel,
    COLORREF colorAutomatic,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>パラメーター

*ラベル*<br/>
[in]自動ボタンのテキストを指定します。

*カラー自動*<br/>
[in]自動ボタンの既定の色を指定する RGB 値。

*b 有効にする*<br/>
[in]自動ボタンを有効にするか無効にするかを指定します。

### <a name="remarks"></a>解説

## <a name="cmfccolorbuttonenableotherbutton"></a><a name="enableotherbutton"></a>CMFCカラーボタン::他のボタンを有効にする

通常のカラーボタンの下に表示される「その他」ボタンを有効または無効にします。

```cpp
void EnableOtherButton(
    LPCTSTR lpszLabel,
    BOOL bAltColorDlg=TRUE,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>パラメーター

*ラベル*<br/>
[in]ボタンのテキストを指定します。

*アルトカラードグルグ*<br/>
[in]ユーザーがボタンをクリックしたときに[、CMFCColorDialog ダイアログ](../../mfc/reference/cmfccolordialog-class.md)ボックスまたはシステム の色のダイアログ ボックスを開くかどうかを指定します。

*b 有効にする*<br/>
[in][その他] ボタンを有効にするか無効にするかを指定します。

### <a name="remarks"></a>解説

[その他] ボタンをクリックして、色のダイアログ ボックスを表示します。 *パラメーターが*TRUE の場合は、[クラス](../../mfc/reference/cmfccolordialog-class.md)が表示されます。それ以外の場合は、[システムの色] ダイアログ ボックスが表示されます。

## <a name="cmfccolorbuttongetautomaticcolor"></a><a name="getautomaticcolor"></a>カラーボタンを取得します。

現在の自動 (既定) の色を取得します。

```
COLORREF GetAutomaticColor() const;
```

### <a name="return-value"></a>戻り値

現在の自動色を表す RGB 値。

### <a name="remarks"></a>解説

現在の自動色は、メソッドによって設定[されます](#enableautomaticbutton)。

## <a name="cmfccolorbuttongetcolor"></a><a name="getcolor"></a>カラーボタンをクリックします。

現在選択されている色を取得します。

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>戻り値

RGB 値。

### <a name="remarks"></a>解説

## <a name="cmfccolorbuttonisdrawxptheme"></a><a name="isdrawxptheme"></a>CMFCカラーボタン::イズドローエクステーマ

現在の色のボタンが Windows XP のビジュアル スタイルで表示されるかどうかを示します。

```
BOOL IsDrawXPTheme() const;
```

### <a name="return-value"></a>戻り値

VISUAL スタイルがサポートされ、現在の色のボタンが Windows XP のビジュアル スタイルで表示される場合は TRUE。それ以外の場合は FALSE。

## <a name="cmfccolorbuttonm_benabledincustomizemode"></a><a name="m_benabledincustomizemode"></a>カラーボタン:m_bEnabledInCustomizeMode

カラー ボタンをカスタマイズ モードに設定します。

```
BOOL m_bEnabledInCustomizeMode;
```

### <a name="remarks"></a>解説

カスタマイズ ダイアログのページに色のボタンを追加する必要がある場合 (またはカスタマイズ中に別の色を選択できるようにする場合)、メンバーを TRUE`m_bEnabledInCustomizeMode`に設定してボタンを有効にします。 既定では、このメンバは FALSE に設定されています。

## <a name="cmfccolorbuttonondraw"></a><a name="ondraw"></a>カラーボタン::オンドロー

ボタンのイメージをレンダリングするために、フレームワークによって呼び出されます。

```
virtual void OnDraw(
    CDC* pDC,
    const CRect& rect,
    UINT uiState);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]ボタンのイメージをレンダリングするために使用されるデバイス コンテキストへのポイント。

*Rect*<br/>
[in]ボタンに境界を設定する四角形。

*ui状態*<br/>
[in]ボタンの表示状態を指定します。

### <a name="remarks"></a>解説

レンダリング プロセスをカスタマイズするには、このメソッドをオーバーライドします。

## <a name="cmfccolorbuttonondrawborder"></a><a name="ondrawborder"></a>カラーボタン::オンドローボーダー

ボタンの境界線を表示するために、フレームワークによって呼び出されます。

```
virtual void OnDrawBorder(
    CDC* pDC,
    CRect& rectClient,
    UINT uiState);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]境界線の描画に使用するデバイス コンテキストへのポイント。

*レクトクライアント*<br/>
[in]描画するボタンの境界を定義する*pDC*パラメーターで指定されるデバイス コンテキスト内の四角形。

*ui状態*<br/>
[in]ボタンの表示状態を指定します。

### <a name="remarks"></a>解説

カラー ボタンの境界線の外観をカスタマイズするには、この関数をオーバーライドします。

## <a name="cmfccolorbuttonondrawfocusrect"></a><a name="ondrawfocusrect"></a>カラーボタン::オンドローフォーカスレクト

ボタンにフォーカスがあるときにフォーカス四角形を表示するために、フレームワークによって呼び出されます。

```
virtual void OnDrawFocusRect(
    CDC* pDC,
    const CRect& rectClient);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]フォーカス四角形の描画に使用するデバイス コンテキストへのポインター。

*レクトクライアント*<br/>
[in]ボタンの境界を定義する*pDC*パラメーターで指定されたデバイス コンテキスト内の四角形。

### <a name="remarks"></a>解説

フォーカスの四角形の外観をカスタマイズするには、このメソッドをオーバーライドします。

## <a name="cmfccolorbuttononshowcolorpopup"></a><a name="onshowcolorpopup"></a>カラーボタン::オンショーカラーポップアップ

ポップアップ カラー バーが表示される前に呼び出されます。

```
virtual void OnShowColorPopup();
```

### <a name="remarks"></a>解説

## <a name="cmfccolorbuttonrebuildpalette"></a><a name="rebuildpalette"></a>CMFCカラーボタン::リビルドパレット

保護されたデータ`m_pPalette`メンバーを、指定されたパレットまたは既定のシステム パレットに初期化します。

```cpp
void RebuildPalette(CPalette* pPal);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*pパル*|[in]論理パレットへのポインターまたは NULL。 NULL の場合、デフォルトのシステムパレットが使用されます。|

## <a name="cmfccolorbuttonsetcolor"></a><a name="setcolor"></a>カラーボタン::セットカラー

ボタンの色を指定します。

```cpp
void SetColor(COLORREF color);
```

### <a name="parameters"></a>パラメーター

*色*<br/>
[in]RGB 値。

### <a name="remarks"></a>解説

## <a name="cmfccolorbuttonsetcolorname"></a><a name="setcolorname"></a>カラーボタンを設定します。

色の名前を指定します。

```
static void SetColorName(
    COLORREF color,
    const CString& strName);
```

### <a name="parameters"></a>パラメーター

*色*<br/>
[in]カラーの RGB 値。

*strName*<br/>
[in]色の名前。

### <a name="remarks"></a>解説

色名のリストは、アプリケーションごとにグローバルです。 その結果、このメソッドは、そのパラメーターを[CMFCColorBar::SetColorName](../../mfc/reference/cmfccolorbar-class.md#setcolorname)に転送します。

## <a name="cmfccolorbuttonsetcolumnsnumber"></a><a name="setcolumnsnumber"></a>数列番号

ユーザーの色選択プロセス中にユーザーに表示される色のテーブルに表示される列の数を定義します。

```cpp
void SetColumnsNumber(int nColumns);
```

### <a name="parameters"></a>パラメーター

*nColumns*<br/>
[in]列の数を指定します。

### <a name="remarks"></a>解説

ユーザーは、定義済みの色のテーブルを表示するポップアップ カラー バーから色を選択できます。 このメソッドは、テーブル内の列数を定義するために使います。

## <a name="cmfccolorbuttonsetdocumentcolors"></a><a name="setdocumentcolors"></a>カラーの設定

色のセットとセットの名前を指定します。 色のセットは[、CMFCColorBar クラス](../../mfc/reference/cmfccolorbar-class.md)オブジェクトを使用して表示されます。

```cpp
void SetDocumentColors(
    LPCTSTR lpszLabel,
    CList<COLORREF,COLORREF>& lstColors);
```

### <a name="parameters"></a>パラメーター

*ラベル*<br/>
[in]ドキュメントの色のセットと共に表示するラベルを指定します。

*lst カラー*<br/>
[in]RGB 値のリストへの参照。

### <a name="remarks"></a>解説

オブジェクト`CMFCColorButton`は[、CMFCColorBar クラス](../../mfc/reference/cmfccolorbar-class.md)オブジェクトに転送される RGB 値のリストを保持します。 カラー バーが表示されると、これらの色は*lpszLabel*パラメーターでラベルを指定する特殊なセクションに表示されます。

## <a name="cmfccolorbuttonsetpalette"></a><a name="setpalette"></a>カラーボタン::セットパレット

ポップアップ カラー バーに表示する標準色を指定します。

```cpp
void SetPalette(CPalette* pPalette);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[in]カラー パレットへのポインター。

### <a name="remarks"></a>解説

## <a name="cmfccolorbuttonsizetocontent"></a><a name="sizetocontent"></a>コンテンツのサイズ

ボタン コントロールのサイズをテキストとイメージに合わせて変更します。

```
virtual CSize SizeToContent(BOOL bCalcOnly=FALSE);
```

### <a name="parameters"></a>パラメーター

*唯一の時間*<br/>
[in]0 以外の場合、ボタン コントロールの新しいサイズは計算されますが、実際のサイズは変更されません。

### <a name="return-value"></a>戻り値

新`CSize`しいボタン コントロールのサイズを指定するオブジェクト。

### <a name="remarks"></a>解説

## <a name="cmfccolorbuttonupdatecolor"></a><a name="updatecolor"></a>カラーボタン::更新色

ユーザーがカラー ボタンをクリックしたときに表示されるカラー バーから色を選択したときに、フレームワークによって呼び出されます。

```
virtual void UpdateColor(COLORREF color);
```

### <a name="parameters"></a>パラメーター

*色*<br/>
[in]ユーザーが選択した色。

### <a name="remarks"></a>解説

この`UpdateColor`関数は、現在選択されているボタンの色を変更し、BN_CLICKED標準通知をWM_COMMANDメッセージを送信して親に通知します。 選択した色を取得するには[、CMFCColorButton::GetColor](#getcolor)メソッドを使用します。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[クラス](../../mfc/reference/cmfcbutton-class.md)<br/>
[CMFCColorBar クラス](../../mfc/reference/cmfccolorbar-class.md)<br/>
[カラーボタン::オンショーカラーポップアップ](#onshowcolorpopup)<br/>
[COLORREF](/windows/win32/gdi/colorref)<br/>
[Cパレットクラス](../../mfc/reference/cpalette-class.md)<br/>
[Cアレイクラス](../../mfc/reference/carray-class.md)<br/>
[CList クラス](../../mfc/reference/clist-class.md)<br/>
[Cstring](../../atl-mfc-shared/reference/cstringt-class.md)
