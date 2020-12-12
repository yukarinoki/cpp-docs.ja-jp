---
description: '詳細情報: CMFCRibbonColorButton クラス'
title: CMFCRibbonColorButton クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonColorButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::CMFCRibbonColorButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::AddColorsGroup
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::EnableAutomaticButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::EnableOtherButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetAutomaticColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetColorBoxSize
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetColumns
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetHighlightedColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::RemoveAllColorGroups
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColorBoxSize
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColorName
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColumns
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetDocumentColors
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetPalette
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::UpdateColor
helpviewer_keywords:
- CMFCRibbonColorButton [MFC], CMFCRibbonColorButton
- CMFCRibbonColorButton [MFC], AddColorsGroup
- CMFCRibbonColorButton [MFC], EnableAutomaticButton
- CMFCRibbonColorButton [MFC], EnableOtherButton
- CMFCRibbonColorButton [MFC], GetAutomaticColor
- CMFCRibbonColorButton [MFC], GetColor
- CMFCRibbonColorButton [MFC], GetColorBoxSize
- CMFCRibbonColorButton [MFC], GetColumns
- CMFCRibbonColorButton [MFC], GetHighlightedColor
- CMFCRibbonColorButton [MFC], RemoveAllColorGroups
- CMFCRibbonColorButton [MFC], SetColor
- CMFCRibbonColorButton [MFC], SetColorBoxSize
- CMFCRibbonColorButton [MFC], SetColorName
- CMFCRibbonColorButton [MFC], SetColumns
- CMFCRibbonColorButton [MFC], SetDocumentColors
- CMFCRibbonColorButton [MFC], SetPalette
- CMFCRibbonColorButton [MFC], UpdateColor
ms.assetid: 6b4b4ee3-8cc0-41b4-a4eb-93e8847008e1
ms.openlocfilehash: a350339559febdc9346dcf8b342d274d00bab391
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97293717"
---
# <a name="cmfcribboncolorbutton-class"></a>CMFCRibbonColorButton クラス

`CMFCRibbonColorButton` クラスは、リボン バーに追加できるカラー ボタンを実装します。 リボンのカラー ボタンは、1 つまたは複数のカラー パレットを含むドロップダウン メニューを表示します。

## <a name="syntax"></a>構文

```
class CMFCRibbonColorButton : public CMFCRibbonGallery
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CMFCRibbonColorButton::CMFCRibbonColorButton](#cmfcribboncolorbutton)||

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCRibbonColorButton:: AddColorsGroup](#addcolorsgroup)|色のグループを通常の色領域に追加します。|
|[CMFCRibbonColorButton:: Enable自動ボタン](#enableautomaticbutton)|**[自動]** ボタンを有効にするかどうかを指定します。|
|[CMFCRibbonColorButton:: EnableOtherButton](#enableotherbutton)|**[その他]** ボタンを有効にします。|
|[CMFCRibbonColorButton::GetAutomaticColor](#getautomaticcolor)||
|[CMFCRibbonColorButton:: GetColor](#getcolor)|現在選ばれている色を返します。|
|[CMFCRibbonColorButton:: GetColorBoxSize](#getcolorboxsize)|カラー バーに表示される色要素のサイズを返します。|
|[CMFCRibbonColorButton::GetColumns](#getcolumns)||
|[CMFCRibbonColorButton:: GetHighlightedColor](#gethighlightedcolor)|ポップアップ カラー パレットで現在選ばれている要素の色を返します。|
|[CMFCRibbonColorButton:: RemoveAllColorGroups](#removeallcolorgroups)|通常の色領域からすべての色グループを削除します。|
|[CMFCRibbonColorButton:: SetColor](#setcolor)|通常の色領域から色を選びます。|
|[CMFCRibbonColorButton:: SetColorBoxSize](#setcolorboxsize)|カラー バーに表示されるすべての色要素のサイズを設定します。|
|[CMFCRibbonColorButton::SetColorName](#setcolorname)||
|[CMFCRibbonColorButton::SetColumns](#setcolumns)||
|[CMFCRibbonColorButton:: SetDocumentColors](#setdocumentcolors)|ドキュメントの色領域に表示する RGB 値の一覧を指定します。|
|[CMFCRibbonColorButton::SetPalette](#setpalette)||
|[CMFCRibbonColorButton::UpdateColor](#updatecolor)||

## <a name="remarks"></a>解説

ユーザーがリボンのカラー ボタンを押すと、カラー バーが表示されます。 既定では、このカラー バーには通常の色領域と呼ばれる色選択パレットが含まれます。 必要に応じて、カラー バーには **[自動]** ボタン (これを使用するとユーザーは既定の色を選択できます)、および **[その他]** ボタン (追加の色を含むポップアップ カラー パレットが表示されます) を表示できます。

## <a name="example"></a>例

`CMFCRibbonColorButton` クラスのさまざまなメソッドの使用方法を次の例に示します。 この例では、 `CMFCRibbonColorButton` オブジェクトの構築、大きいイメージの設定、 **[自動]** ボタンの有効化、 **[その他]** ボタンの有効化、列数の設定、カラー バーに表示されるすべての色要素のサイズの設定、通常の色領域への色グループの追加、ドキュメントの色領域に表示する RGB 値の一覧の指定方法を示します。 このコード スニペットは、「 [クライアント サンプルの描画](../../overview/visual-cpp-samples.md)」の一部です。

[!code-cpp[NVC_MFC_DrawClient#3](../../mfc/reference/codesnippet/cpp/cmfcribboncolorbutton-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)

[CMFCRibbonColorButton](../../mfc/reference/cmfcribboncolorbutton-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxribboncolorbutton.h

## <a name="cmfcribboncolorbuttonaddcolorsgroup"></a><a name="addcolorsgroup"></a> CMFCRibbonColorButton:: AddColorsGroup

色のグループを通常の色領域に追加します。

```cpp
void AddColorsGroup(
    LPCTSTR lpszName,
    const CList<COLORREF,COLORREF>& lstColors,
    BOOL bContiguousColumns=FALSE);
```

### <a name="parameters"></a>パラメーター

*lpszName*<br/>
からグループ名。

*lstColors*<br/>
から色の一覧。

*bContiguousColumns*<br/>
からグループ内の色項目の表示方法を制御します。 TRUE の場合、カラー項目は垂直方向の間隔なしで描画されます。 FALSE の場合、カラー項目は垂直方向の間隔で描画されます。

### <a name="remarks"></a>解説

この関数を使用すると、カラーポップアップに複数の色のグループが表示されるようになります。 グループ内の色の表示方法を制御できます。

## <a name="cmfcribboncolorbuttoncmfcribboncolorbutton"></a><a name="cmfcribboncolorbutton"></a> CMFCRibbonColorButton:: CMFCRibbonColorButton

`CMFCRibbonColorButton` オブジェクトを構築します。

```
CMFCRibbonColorButton();

CMFCRibbonColorButton(
    UINT nID,
    LPCTSTR lpszText,
    int nSmallImageIndex,
    COLORREF color = RGB(0, 0, 0));

CMFCRibbonColorButton(
    UINT nID,
    LPCTSTR lpszText,
    BOOL bSimpleButtonLook,
    int nSmallImageIndex,
    int nLargeImageIndex,
    COLORREF color = RGB(0, 0, 0));
```

### <a name="parameters"></a>パラメーター

*nID*<br/>
からユーザーがボタンをクリックしたときに実行されるコマンドのコマンド ID を指定します。

*lpszText*<br/>
からボタンに表示するテキストを指定します。

*nSmallImageIndex*<br/>
からボタンに表示する小さいイメージの0から始まるインデックス。

*color*<br/>
からボタンの色 (既定では黒)。

*bSimpleButtonLook*<br/>
からTRUE の場合、ボタンは単純な四角形として描画されます。

*nLargeImageIndex*<br/>
からボタンに表示される大きいイメージの0から始まるインデックス。

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcribboncolorbuttonenableautomaticbutton"></a><a name="enableautomaticbutton"></a> CMFCRibbonColorButton:: Enable自動ボタン

**[自動]** ボタンを有効にするかどうかを指定します。

```cpp
void EnableAutomaticButton(
    LPCTSTR lpszLabel,
    COLORREF colorAutomatic,
    BOOL bEnable=TRUE,
    LPCTSTR lpszToolTip=NULL,
    BOOL bOnTop=TRUE,
    BOOL bDrawBorder=FALSE);
```

### <a name="parameters"></a>パラメーター

*lpszLabel*<br/>
から **自動** ボタンのラベル。

*colorAutomatic*<br/>
から **自動** ボタンの既定の色を指定する RGB 値。

*bEnable*<br/>
から[ **自動** ] ボタンが有効な場合は TRUE。無効になっている場合は FALSE。

*lpszToolTip*<br/>
から **自動** ボタンのツールヒント。

*bOnTop*<br/>
から **自動** ボタンが一番上にあり、カラーパレットの前にあるかどうかを指定します。

*bDrawBorder*<br/>
からアプリケーションがリボンの色ボタンのカラーバーの周りに境界線を描画する場合は TRUE。 カラーバー現在選択されている色を表示します。 アプリケーションが境界線を描画しない場合は FALSE

## <a name="cmfcribboncolorbuttonenableotherbutton"></a><a name="enableotherbutton"></a> CMFCRibbonColorButton:: EnableOtherButton

**[その他]** ボタンを有効にします。

```cpp
void EnableOtherButton(
    LPCTSTR lpszLabel,
    LPCTSTR lpszToolTip=NULL);
```

### <a name="parameters"></a>パラメーター

*lpszLabel*<br/>
ボタンのラベル。

*lpszToolTip*<br/>
[ **その他** ] ボタンのツールヒントテキスト。

### <a name="remarks"></a>解説

**もう1つ** のボタンは、色のグループの下に表示されるボタンです。 ユーザーが [ **その他** ] ボタンをクリックすると、色のダイアログが表示されます。

## <a name="cmfcribboncolorbuttongetautomaticcolor"></a><a name="getautomaticcolor"></a> CMFCRibbonColorButton:: Get自動カラー

現在の自動ボタンの色を取得します。

```
COLORREF GetAutomaticColor() const;
```

### <a name="return-value"></a>戻り値

現在の自動ボタンの色を表す RGB カラー値。

### <a name="remarks"></a>解説

自動ボタンの色は、 `colorAutomatic` メソッドに渡されるパラメーターによって設定され `CMFCRibbonColorButton::EnableAutomaticButton` ます。

## <a name="cmfcribboncolorbuttongetcolor"></a><a name="getcolor"></a> CMFCRibbonColorButton:: GetColor

現在選ばれている色を返します。

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>戻り値

ボタンをクリックして選択した色。

## <a name="cmfcribboncolorbuttongetcolorboxsize"></a><a name="getcolorboxsize"></a> CMFCRibbonColorButton:: GetColorBoxSize

カラー バーに表示される色要素のサイズを返します。

```
CSize GetColorBoxSize() const;
```

### <a name="return-value"></a>戻り値

ドロップダウンカラーパレットの色ボタンのサイズ。

## <a name="cmfcribboncolorbuttongetcolumns"></a><a name="getcolumns"></a> CMFCRibbonColorButton:: GetColumns

リボンのカラーボタンのギャラリー表示の行にある項目の数を取得します。

```
int GetColumns() const;
```

### <a name="return-value"></a>戻り値

各行のアイコンの数を返します。

### <a name="remarks"></a>解説

## <a name="cmfcribboncolorbuttongethighlightedcolor"></a><a name="gethighlightedcolor"></a> CMFCRibbonColorButton:: GetHighlightedColor

ポップアップカラーパレットで現在選択されている要素の色を返します。

```
COLORREF GetHighlightedColor() const;
```

### <a name="return-value"></a>戻り値

ポップアップカラーパレットで現在選択されている要素の色。

## <a name="cmfcribboncolorbuttonremoveallcolorgroups"></a><a name="removeallcolorgroups"></a> CMFCRibbonColorButton:: RemoveAllColorGroups

通常の色領域からすべての色グループを削除します。

```cpp
void RemoveAllColorGroups();
```

## <a name="cmfcribboncolorbuttonsetcolor"></a><a name="setcolor"></a> CMFCRibbonColorButton:: SetColor

通常の色領域から色を選びます。

```cpp
void SetColor(COLORREF color);
```

### <a name="parameters"></a>パラメーター

*color*<br/>
から設定する色。

## <a name="cmfcribboncolorbuttonsetcolorboxsize"></a><a name="setcolorboxsize"></a> CMFCRibbonColorButton:: SetColorBoxSize

カラー バーに表示されるすべての色要素のサイズを設定します。

```cpp
void SetColorBoxSize(CSize sizeBox);
```

### <a name="parameters"></a>パラメーター

*サイズボックス*<br/>
からカラーパレットの色ボタンの新しいサイズ。

## <a name="cmfcribboncolorbuttonsetcolorname"></a><a name="setcolorname"></a> CMFCRibbonColorButton:: SetColorName

指定した色の新しい名前を設定します。

```
static void __stdcall SetColorName(
    COLORREF color,
    const CString& strName);
```

### <a name="parameters"></a>パラメーター

*color*<br/>
から色の RGB 値。

*strName*<br/>
から指定した色の新しい名前。

### <a name="remarks"></a>解説

`CMFCColorBar::SetColorName`このメソッドはを呼び出すため、このメソッドは、アプリケーション内のすべてのオブジェクトの指定された色の名前を変更し `CMFCColorBar` ます。

## <a name="cmfcribboncolorbuttonsetcolumns"></a><a name="setcolumns"></a> CMFCRibbonColorButton:: SetColumns

ユーザーのカラー選択プロセス中にユーザーに表示される色の表に表示される列の数を設定します。

```cpp
void SetColumns(int nColumns);
```

### <a name="parameters"></a>パラメーター

*nColumns*<br/>
から各行に表示するカラーアイコンの数。

### <a name="remarks"></a>解説

## <a name="cmfcribboncolorbuttonsetdocumentcolors"></a><a name="setdocumentcolors"></a> CMFCRibbonColorButton:: SetDocumentColors

ドキュメントの色領域に表示する RGB 値の一覧を指定します。

```cpp
void SetDocumentColors(
    LPCTSTR lpszLabel,
    CList<COLORREF,COLORREF>& lstColors);
```

### <a name="parameters"></a>パラメーター

*lpszLabel*<br/>
からドキュメントの色と共に表示されるテキスト。

*lstColors*<br/>
からRGB 値のリストへの参照。

## <a name="cmfcribboncolorbuttonsetpalette"></a><a name="setpalette"></a> CMFCRibbonColorButton:: SetPalette

カラーボタンに表示される色テーブルに表示する標準の色を指定します。

```cpp
void SetPalette(CPalette* pPalette);
```

### <a name="parameters"></a>パラメーター

*pPalette*<br/>
からカラーパレットへのポインター。

### <a name="remarks"></a>解説

## <a name="cmfcribboncolorbuttonupdatecolor"></a><a name="updatecolor"></a> CMFCRibbonColorButton:: UpdateColor

ユーザーが色のボタンをクリックしたときに表示されるカラーテーブルから色を選択すると、フレームワークによって呼び出されます。

```cpp
void UpdateColor(COLORREF color);
```

### <a name="parameters"></a>パラメーター

*color*<br/>
からユーザーが選択した色。

### <a name="remarks"></a>解説

メソッドは、 `CMFCRibbonColorButton::UpdateColor` 現在選択されているボタンの色を変更し、BN_CLICKED 標準通知を含む WM_COMMAND メッセージを送信することによってその親に通知します。 [CMFCRibbonColorButton:: GetColor](#getcolor)メソッドを使用して、選択した色を取得します。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonGallery クラス](../../mfc/reference/cmfcribbongallery-class.md)
