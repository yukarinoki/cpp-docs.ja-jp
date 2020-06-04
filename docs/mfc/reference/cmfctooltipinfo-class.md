---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCToolTipInfo
- AFXTOOLTIPCTRL/CMFCToolTipInfo
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bBalloonTooltip
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bBoldLabel
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bDrawDescription
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bDrawIcon
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bDrawSeparator
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bRoundedCorners
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bVislManagerTheme
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_clrBorder
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_clrFill
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_clrFillGradient
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_clrText
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_nGradientAngle
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_nMaxDescrWidth
helpviewer_keywords:
- CMFCToolTipInfo [MFC], m_bBalloonTooltip
- CMFCToolTipInfo [MFC], m_bBoldLabel
- CMFCToolTipInfo [MFC], m_bDrawDescription
- CMFCToolTipInfo [MFC], m_bDrawIcon
- CMFCToolTipInfo [MFC], m_bDrawSeparator
- CMFCToolTipInfo [MFC], m_bRoundedCorners
- CMFCToolTipInfo [MFC], m_bVislManagerTheme
- CMFCToolTipInfo [MFC], m_clrBorder
- CMFCToolTipInfo [MFC], m_clrFill
- CMFCToolTipInfo [MFC], m_clrFillGradient
- CMFCToolTipInfo [MFC], m_clrText
- CMFCToolTipInfo [MFC], m_nGradientAngle
- CMFCToolTipInfo [MFC], m_nMaxDescrWidth
ms.assetid: f9d3d7f8-1f08-4342-a7b2-683860e5d2a5
ms.openlocfilehash: 000a2fd33928e59685efa6f145406542a4935819
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377333"
---
# <a name="cmfctooltipinfo-class"></a>クラス

ツールヒントの外観に関する情報を格納します。

## <a name="syntax"></a>構文

```
class CMFCToolTipInfo
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCToolTipInfo::operator =](#operator_eq)||

### <a name="data-members"></a>データ メンバー

|名前|説明|
|----------|-----------------|
|[ツールヒント情報::m_bBalloonTooltip](#m_bballoontooltip)|ツールヒントの外観をバルーンにするかどうかを示すブール値変数。|
|[CMFCToolTipInfo::m_bBoldLabel](#m_bboldlabel)|ツールヒントのラベルを太字のフォントで表示するかどうかを示すブール値変数。|
|[CMFCToolTipInfo::m_bDrawDescription](#m_bdrawdescription)|ツールヒントに説明を含めるかどうかを示すブール値変数。|
|[CMFCToolTipInfo::m_bDrawIcon](#m_bdrawicon)|ツールヒントにアイコンを含めるかどうかを示すブール値変数。|
|[CMFCToolTipInfo::m_bDrawSeparator](#m_bdrawseparator)|ツールヒントのラベルとツールヒントの説明の間に区切り記号を表示するかどうかを示すブール値変数。|
|[CMFCToolTipInfo::m_bRoundedCorners](#m_broundedcorners)|ツールヒントの角を丸くするかどうかを示すブール値変数。|
|[CMFCToolTipInfo::m_bVislManagerTheme](#m_bvislmanagertheme)|ツールヒントの外観をビジュアル マネージャーで制御するかどうかを示すブール変数です[(CMFCVisualManager クラス](../../mfc/reference/cmfcvisualmanager-class.md)を参照)。|
|[CMFCToolTipInfo::m_clrBorder](#m_clrborder)|ツールヒントの境界線の色。|
|[CMFCToolTipInfo::m_clrFill](#m_clrfill)|ツールヒントの背景の色。|
|[CMFCToolTipInfo::m_clrFillGradient](#m_clrfillgradient)|ツールヒントのグラデーション塗りの色。|
|[CMFCToolTipInfo::m_clrText](#m_clrtext)|ツールヒントのテキストの色。|
|[CMFCToolTipInfo::m_nGradientAngle](#m_ngradientangle)|ツールヒントのグラデーション塗りの角度。|
|[CMFCToolTipInfo::m_nMaxDescrWidth](#m_nmaxdescrwidth)|ツールヒントの説明で可能な最大幅 (ピクセル)。|

## <a name="remarks"></a>解説

[CMFCToolTipCtrl クラス](../../mfc/reference/cmfctooltipctrl-class.md) `CMFCToolTipInfo`、および[CTooltipManager クラス](../../mfc/reference/ctooltipmanager-class.md)を一緒に使用して、アプリケーションにカスタマイズされたツールヒントを実装します。 これらのツールヒント クラスの使用例については、「[クラスの CMFCToolTipCtrl」](../../mfc/reference/cmfctooltipctrl-class.md)を参照してください。

## <a name="example"></a>例

次の例では、`CMFCToolTipInfo` クラスのさまざまなメンバー変数の値を設定する方法を示します。

[!code-cpp[NVC_MFC_RibbonApp#42](../../mfc/reference/codesnippet/cpp/cmfctooltipinfo-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxtooltipctrl.h

## <a name="cmfctooltipinfom_bballoontooltip"></a><a name="m_bballoontooltip"></a>ツールヒント情報::m_bBalloonTooltip

すべてのツールチップの表示スタイルを指定します。

```
BOOL m_bBalloonTooltip;
```

### <a name="remarks"></a>解説

TRUE は、ツールヒントがバルーン スタイルを使用することを示し、FALSE は、ツールヒントが四角形のスタイルを使用することを示します。

## <a name="cmfctooltipinfom_bboldlabel"></a><a name="m_bboldlabel"></a>ツールヒント情報::m_bBoldLabel

ツールヒントテキストのフォントを太字にするかどうかを指定します。

```
BOOL m_bBoldLabel;
```

### <a name="remarks"></a>解説

ツールヒントのテキストを太字フォントで表示するにはこのメンバーを TRUE に設定し、太字以外のフォントでツールヒント ラベルを表示するには FALSE を設定します。

## <a name="cmfctooltipinfom_bdrawdescription"></a><a name="m_bdrawdescription"></a>ツールヒント情報::m_bDrawDescription

各ツールヒントに説明テキストを表示するかどうかを指定します。

```
BOOL m_bDrawDescription;
```

### <a name="remarks"></a>解説

説明を表示するにはこのメンバーを TRUE に設定し、説明を非表示にするには FALSE に設定します。 ツールヒントの説明を指定するには[、CMFC ツール ヒントを](../../mfc/reference/cmfctooltipctrl-class.md#setdescription)呼び出します。

## <a name="cmfctooltipinfom_bdrawicon"></a><a name="m_bdrawicon"></a>ツールヒント情報::m_bDrawIcon

すべてのツールヒントにアイコンを表示するかどうかを指定します。

```
BOOL m_bDrawIcon;
```

### <a name="remarks"></a>解説

このメンバーを TRUE に設定すると、各ツールヒントにアイコンが表示され、アイコンなしでツールヒントが表示される場合は FALSE を設定します。

## <a name="cmfctooltipinfom_bdrawseparator"></a><a name="m_bdrawseparator"></a>ツールヒント情報::m_bDrawSeparator

各ツールヒントのラベルと説明の間に区切り文字を付けるかどうかを指定します。

```
BOOL m_bDrawSeparator;
```

### <a name="remarks"></a>解説

ツールヒントのラベルと説明の間に区切り記号を表示するには、このメンバーを TRUE に設定し、区切り記号を付けのないツールヒントを表示するには FALSE を設定します。

## <a name="cmfctooltipinfom_broundedcorners"></a><a name="m_broundedcorners"></a>ツールヒント情報::m_bRoundedCorners

すべてのツールチップに角が丸いかどうかを指定します。

```
BOOL m_bRoundedCorners;
```

### <a name="remarks"></a>解説

ツールヒントに角が丸く表示される場合は、このメンバを TRUE に設定し、ツールヒントに長方形のコーナーを表示するには FALSE を設定します。

## <a name="cmfctooltipinfom_clrborder"></a><a name="m_clrborder"></a>ツールヒント情報:m_clrBorder

すべてのツールヒントの境界線の色を指定します。

```
COLORREF m_clrBorder;
```

## <a name="cmfctooltipinfom_clrfill"></a><a name="m_clrfill"></a>ツールヒント情報::m_clrFill

ツールヒントの背景の色を指定します。

```
COLORREF m_clrFill;
```

### <a name="remarks"></a>解説

[CMFC ツール ヒント情報::m_clrFillGradient](#m_clrfillgradient)が -1 の場合`m_clrFill`、ツールヒントの背景色はです。 それ以外`m_clrFill`の場合は、グラデーションの始点の色`m_clrFillGradient`を指定し、グラデーションの終了の色を指定します。 [グラデーションの方向を決定m_nGradientAngle。](#m_ngradientangle)

## <a name="cmfctooltipinfom_clrfillgradient"></a><a name="m_clrfillgradient"></a>ツールヒント情報::m_clrFillGradient

ツールヒントのグラデーション背景の終了色を指定します。

```
COLORREF m_clrFillGradient;
```

### <a name="remarks"></a>解説

-1 の場合`m_clrFillGradient`、グラデーションはありません。 それ以外の場合、グラデーションの初期色は[CMFC ツールヒント情報::m_clrFill](#m_clrfill)で指定され、グラデーション`m_clrFillGradient`の終了色は によって指定されます。 [グラデーションの方向を決定m_nGradientAngle。](#m_ngradientangle)

## <a name="cmfctooltipinfom_clrtext"></a><a name="m_clrtext"></a>ヒント::m_clrText

すべてのツールヒントのテキストの色を指定します。

```
COLORREF m_clrText;
```

## <a name="cmfctooltipinfom_ngradientangle"></a><a name="m_ngradientangle"></a>ツールヒント情報::m_nGradientAngle

ツールチップの背景にグラデーションを描画する角度を指定します。

```
int m_nGradientAngle;
```

### <a name="remarks"></a>解説

`m_nGradientAngle`ツールヒントの背景のグラデーションが水平からオフセットされる角度を度単位で指定します。 0`m_nGradientAngle`の場合、グラデーションは左から右に描画されます。 1 `m_nGradientAngle` ~ 360 の場合、グラデーションはその度だけ時計回りに回転します。 既定値`m_nGradientAngle`である -1 の場合、グラデーションは上から下に描画されます。 これは 90 に`m_nGradientAngle`設定した場合と同じです。

[m_clrFill](#m_clrfill)`clrFill`グラデーションの開始の色を指定し[、CMFC ツール ヒント情報::m_clrFillGradient](#m_clrfillgradient)`clrFillGradient`グラデーションの終わりの色を指定します。 -1 の場合`m_clrFillGradient`、グラデーションはありません。

## <a name="cmfctooltipinfom_nmaxdescrwidth"></a><a name="m_nmaxdescrwidth"></a>ヒント::m_nMaxDescrWidth

各ツールヒントに表示される説明の最大幅を指定します。 説明の幅が指定した値を超えると、テキストが折り返されます。

```
int m_nMaxDescrWidth;
```

## <a name="cmfctooltipinfom_bvislmanagertheme"></a><a name="m_bvislmanagertheme"></a>ツールヒント情報::m_bVislManagerTheme

アプリケーションのビジュアル マネージャーがすべてのツールヒントの外観を制御するかどうかを指定します。

```
BOOL m_bVislManagerTheme;
```

### <a name="remarks"></a>解説

TRUE`m_bVislManagerTheme`の場合、すべてのツールヒントは、画面に表示される前に、アプリケーションのビジュアル マネージャーから新しい[CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md)を要求し、そのオブジェクトの値を使用して外観を決定します。 [CMFC ツールヒント情報](../../mfc/reference/cmfctooltipinfo-class.md)の他のメンバーは無視されます。

## <a name="cmfctooltipinfooperator"></a><a name="operator_eq"></a>ツールヒント情報::演算子=

詳細については、Visual Studio のインストールの**\\VC\\atlmfc\\src mfc**フォルダーにあるソース コードを参照してください。

```
CMFCToolTipInfo& operator=(CMFCToolTipInfo& src);
```

### <a name="parameters"></a>パラメーター

[in]*src*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[クラス](../../mfc/reference/ctooltipmanager-class.md)<br/>
[クラス](../../mfc/reference/cmfctooltipctrl-class.md)
