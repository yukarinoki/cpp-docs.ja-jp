---
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
ms.openlocfilehash: 8cf92d8d4b1b113f751bee85ac2a7df6eb06afea
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375237"
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
|[カラーボタン::グループの追加](#addcolorsgroup)|色のグループを通常の色領域に追加します。|
|[カラーボタン::自動ボタンを有効にする](#enableautomaticbutton)|**[自動]** ボタンを有効にするかどうかを指定します。|
|[カラーボタンを使用します。](#enableotherbutton)|**[その他]** ボタンを有効にします。|
|[CMFCRibbonColorButton::GetAutomaticColor](#getautomaticcolor)||
|[カラーボタンをクリックします。](#getcolor)|現在選ばれている色を返します。|
|[カラーボタン::カラーボックスサイズ](#getcolorboxsize)|カラー バーに表示される色要素のサイズを返します。|
|[CMFCRibbonColorButton::GetColumns](#getcolumns)||
|[カラーボタン::ハイライトされた色](#gethighlightedcolor)|ポップアップ カラー パレットで現在選ばれている要素の色を返します。|
|[カラーボタン::すべてのカラーグループを削除します。](#removeallcolorgroups)|通常の色領域からすべての色グループを削除します。|
|[カラーボタン::セットカラー](#setcolor)|通常の色領域から色を選びます。|
|[カラーボタン::セットカラーボックスサイズ](#setcolorboxsize)|カラー バーに表示されるすべての色要素のサイズを設定します。|
|[CMFCRibbonColorButton::SetColorName](#setcolorname)||
|[CMFCRibbonColorButton::SetColumns](#setcolumns)||
|[カラーボタン::ドキュメントカラーの設定](#setdocumentcolors)|ドキュメントの色領域に表示する RGB 値の一覧を指定します。|
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

## <a name="requirements"></a>必要条件

**ヘッダー:** afxribboncolorbutton.h

## <a name="cmfcribboncolorbuttonaddcolorsgroup"></a><a name="addcolorsgroup"></a>カラーボタン::グループの追加

色のグループを通常の色領域に追加します。

```
void AddColorsGroup(
    LPCTSTR lpszName,
    const CList<COLORREF,COLORREF>& lstColors,
    BOOL bContiguousColumns=FALSE);
```

### <a name="parameters"></a>パラメーター

*名前を指定します。*<br/>
[in]グループ名。

*lst カラー*<br/>
[in]色のリスト。

*隣接列*<br/>
[in]グループ内でのカラーアイテムの表示方法を制御します。 TRUE の場合、カラー項目は垂直方向の間隔なしで描画されます。 FALSE の場合、カラー項目は垂直方向の間隔で描画されます。

### <a name="remarks"></a>解説

この関数を使用して、色のポップアップに複数の色のグループを表示します。 色をグループで表示する方法を制御できます。

## <a name="cmfcribboncolorbuttoncmfcribboncolorbutton"></a><a name="cmfcribboncolorbutton"></a>カラーボタン::CMFCリボンカラーボタン

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
[in]ユーザーがボタンをクリックしたときに実行するコマンドのコマンド ID を指定します。

*lpszText*<br/>
[in]ボタンに表示するテキストを指定します。

*を使用します。*<br/>
[in]ボタンに表示される小さいイメージの 0 から始まるインデックス。

*色*<br/>
[in]ボタンの色 (既定は黒)。

*ボタンルック*<br/>
[in]TRUE の場合、ボタンは単純な四角形として描画されます。

*インデックスを作成します。*<br/>
[in]ボタンに表示される大きなイメージの 0 から始まるインデックス。

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcribboncolorbuttonenableautomaticbutton"></a><a name="enableautomaticbutton"></a>カラーボタン::自動ボタンを有効にする

**[自動]** ボタンを有効にするかどうかを指定します。

```
void EnableAutomaticButton(
    LPCTSTR lpszLabel,
    COLORREF colorAutomatic,
    BOOL bEnable=TRUE,
    LPCTSTR lpszToolTip=NULL,
    BOOL bOnTop=TRUE,
    BOOL bDrawBorder=FALSE);
```

### <a name="parameters"></a>パラメーター

*ラベル*<br/>
[in]**[自動]** ボタンのラベル。

*カラー自動*<br/>
[in]**[自動**] ボタンの既定の色を指定する RGB 値。

*b 有効にする*<br/>
[in]**[自動**] ボタンが有効になっている場合は TRUE。無効になっている場合は FALSE。

*lpszToolTip*<br/>
[in]**[自動]** ボタンのツールチップ。

*オントップ*<br/>
[in]**[自動**] ボタンを上部、カラー パレットの前に表示するかどうかを指定します。

*ボーダーを描く*<br/>
[in]TRUE を指定すると、アプリケーションは、リボンの色のボタンのカラー バーの周囲に境界線を描画します。 カラーバーには、現在選択されている色が表示されます。 アプリケーションが境界線を描画しない場合は FALSE

## <a name="cmfcribboncolorbuttonenableotherbutton"></a><a name="enableotherbutton"></a>カラーボタンを使用します。

**[その他]** ボタンを有効にします。

```
void EnableOtherButton(
    LPCTSTR lpszLabel,
    LPCTSTR lpszToolTip=NULL);
```

### <a name="parameters"></a>パラメーター

*ラベル*<br/>
ボタンのラベル。

*lpszToolTip*<br/>
**[その他**] ボタンのツールヒント テキスト。

### <a name="remarks"></a>解説

**[その他]** ボタンは、色のグループの下に表示されるボタンです。 ユーザーが [**その他**] ボタンをクリックすると、色のダイアログが表示されます。

## <a name="cmfcribboncolorbuttongetautomaticcolor"></a><a name="getautomaticcolor"></a>カラーボタンを取得します。

現在の自動ボタンの色を取得します。

```
COLORREF GetAutomaticColor() const;
```

### <a name="return-value"></a>戻り値

現在の自動ボタンの色を表す RGB カラー値。

### <a name="remarks"></a>解説

自動ボタンの色は、メソッドに渡`colorAutomatic`されるパラメータによって設定`CMFCRibbonColorButton::EnableAutomaticButton`されます。

## <a name="cmfcribboncolorbuttongetcolor"></a><a name="getcolor"></a>カラーボタンをクリックします。

現在選ばれている色を返します。

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>戻り値

ボタンをクリックして選択した色。

## <a name="cmfcribboncolorbuttongetcolorboxsize"></a><a name="getcolorboxsize"></a>カラーボタン::カラーボックスサイズ

カラー バーに表示される色要素のサイズを返します。

```
CSize GetColorBoxSize() const;
```

### <a name="return-value"></a>戻り値

ドロップダウン カラー パレットのカラー ボタンのサイズ。

## <a name="cmfcribboncolorbuttongetcolumns"></a><a name="getcolumns"></a>カラーボタン::列を取得します。

リボンの色のボタンのギャラリー表示の行の項目数を取得します。

```
int GetColumns() const;
```

### <a name="return-value"></a>戻り値

各行のアイコンの数を返します。

### <a name="remarks"></a>解説

## <a name="cmfcribboncolorbuttongethighlightedcolor"></a><a name="gethighlightedcolor"></a>カラーボタン::ハイライトされた色

ポップアップ カラー パレットで現在選択されている要素の色を返します。

```
COLORREF GetHighlightedColor() const;
```

### <a name="return-value"></a>戻り値

ポップアップ カラー パレットで現在選択されている要素の色。

## <a name="cmfcribboncolorbuttonremoveallcolorgroups"></a><a name="removeallcolorgroups"></a>カラーボタン::すべてのカラーグループを削除します。

通常の色領域からすべての色グループを削除します。

```
void RemoveAllColorGroups();
```

## <a name="cmfcribboncolorbuttonsetcolor"></a><a name="setcolor"></a>カラーボタン::セットカラー

通常の色領域から色を選びます。

```
void SetColor(COLORREF color);
```

### <a name="parameters"></a>パラメーター

*色*<br/>
[in]設定する色。

## <a name="cmfcribboncolorbuttonsetcolorboxsize"></a><a name="setcolorboxsize"></a>カラーボタン::セットカラーボックスサイズ

カラー バーに表示されるすべての色要素のサイズを設定します。

```
void SetColorBoxSize(CSize sizeBox);
```

### <a name="parameters"></a>パラメーター

*サイズボックス*<br/>
[in]カラー パレットのカラー ボタンの新しいサイズ。

## <a name="cmfcribboncolorbuttonsetcolorname"></a><a name="setcolorname"></a>カラーボタン::カラー名を設定します。

指定した色の新しい名前を設定します。

```
static void __stdcall SetColorName(
    COLORREF color,
    const CString& strName);
```

### <a name="parameters"></a>パラメーター

*色*<br/>
[in]カラーの RGB 値。

*strName*<br/>
[in]指定した色の新しい名前。

### <a name="remarks"></a>解説

このメソッドは`CMFCColorBar::SetColorName`、アプリケーション内のすべての`CMFCColorBar`オブジェクトで指定された色の名前を変更するためです。

## <a name="cmfcribboncolorbuttonsetcolumns"></a><a name="setcolumns"></a>カラーボタン::列の設定

ユーザーの色選択プロセス中にユーザーに表示される色の表に表示される列の数を設定します。

```
void SetColumns(int nColumns);
```

### <a name="parameters"></a>パラメーター

*nColumns*<br/>
[in]各行に表示する色アイコンの数。

### <a name="remarks"></a>解説

## <a name="cmfcribboncolorbuttonsetdocumentcolors"></a><a name="setdocumentcolors"></a>カラーボタン::ドキュメントカラーの設定

ドキュメントの色領域に表示する RGB 値の一覧を指定します。

```
void SetDocumentColors(
    LPCTSTR lpszLabel,
    CList<COLORREF,COLORREF>& lstColors);
```

### <a name="parameters"></a>パラメーター

*ラベル*<br/>
[in]ドキュメントの色と共に表示されるテキスト。

*lst カラー*<br/>
[in]RGB 値のリストへの参照。

## <a name="cmfcribboncolorbuttonsetpalette"></a><a name="setpalette"></a>カラーボタン::セットパレット

カラー ボタンが表示するカラー テーブルに表示する標準色を指定します。

```
void SetPalette(CPalette* pPalette);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[in]カラー パレットへのポインター。

### <a name="remarks"></a>解説

## <a name="cmfcribboncolorbuttonupdatecolor"></a><a name="updatecolor"></a>カラーボタン::更新色

ユーザーがカラー ボタンをクリックしたときに表示されるカラー テーブルから色を選択したときに、フレームワークによって呼び出されます。

```
void UpdateColor(COLORREF color);
```

### <a name="parameters"></a>パラメーター

*色*<br/>
[in]ユーザーが選択した色。

### <a name="remarks"></a>解説

この`CMFCRibbonColorButton::UpdateColor`メソッドは、現在選択されているボタンの色を変更し、BN_CLICKED標準通知をWM_COMMANDメッセージを送信して親に通知します。 選択した色を取得するには[、CMFC リボンカラー ボタン::GetColor](#getcolor)メソッドを使用します。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[クラス](../../mfc/reference/cmfcribbongallery-class.md)
