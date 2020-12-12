---
description: '詳細情報: CMFCToolTipInfo クラス'
title: CMFCToolTipInfo クラス
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
ms.openlocfilehash: 06ceca500ad92d5f3a27e2740a298d9c1bbfe1cc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143430"
---
# <a name="cmfctooltipinfo-class"></a>CMFCToolTipInfo クラス

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
|[CMFCToolTipInfo:: m_bBalloonTooltip](#m_bballoontooltip)|ツールヒントの外観をバルーンにするかどうかを示すブール値変数。|
|[CMFCToolTipInfo::m_bBoldLabel](#m_bboldlabel)|ツールヒントのラベルを太字のフォントで表示するかどうかを示すブール値変数。|
|[CMFCToolTipInfo::m_bDrawDescription](#m_bdrawdescription)|ツールヒントに説明を含めるかどうかを示すブール値変数。|
|[CMFCToolTipInfo::m_bDrawIcon](#m_bdrawicon)|ツールヒントにアイコンを含めるかどうかを示すブール値変数。|
|[CMFCToolTipInfo::m_bDrawSeparator](#m_bdrawseparator)|ツールヒントのラベルとツールヒントの説明の間に区切り記号を表示するかどうかを示すブール値変数。|
|[CMFCToolTipInfo::m_bRoundedCorners](#m_broundedcorners)|ツールヒントの角を丸くするかどうかを示すブール値変数。|
|[CMFCToolTipInfo::m_bVislManagerTheme](#m_bvislmanagertheme)|ツールヒントの外観をビジュアルマネージャーで制御する必要があるかどうかを示すブール値変数 (「 [Cmfcvisualmanager クラス](../../mfc/reference/cmfcvisualmanager-class.md)」を参照)。|
|[CMFCToolTipInfo::m_clrBorder](#m_clrborder)|ツールヒントの境界線の色。|
|[CMFCToolTipInfo::m_clrFill](#m_clrfill)|ツールヒントの背景の色。|
|[CMFCToolTipInfo::m_clrFillGradient](#m_clrfillgradient)|ツールヒントのグラデーション塗りの色。|
|[CMFCToolTipInfo::m_clrText](#m_clrtext)|ツールヒントのテキストの色。|
|[CMFCToolTipInfo::m_nGradientAngle](#m_ngradientangle)|ツールヒントのグラデーション塗りの角度。|
|[CMFCToolTipInfo::m_nMaxDescrWidth](#m_nmaxdescrwidth)|ツールヒントの説明で可能な最大幅 (ピクセル)。|

## <a name="remarks"></a>解説

[CMFCToolTipCtrl クラス](../../mfc/reference/cmfctooltipctrl-class.md)、 `CMFCToolTipInfo` 、および[CTooltipManager クラス](../../mfc/reference/ctooltipmanager-class.md)を一緒に使用して、カスタマイズされたツールヒントをアプリケーションに実装します。 これらのツールヒントクラスを使用する方法の例については、 [CMFCToolTipCtrl クラス](../../mfc/reference/cmfctooltipctrl-class.md) のトピックを参照してください。

## <a name="example"></a>例

次の例では、`CMFCToolTipInfo` クラスのさまざまなメンバー変数の値を設定する方法を示します。

[!code-cpp[NVC_MFC_RibbonApp#42](../../mfc/reference/codesnippet/cpp/cmfctooltipinfo-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxtooltipctrl

## <a name="cmfctooltipinfom_bballoontooltip"></a><a name="m_bballoontooltip"></a> CMFCToolTipInfo:: m_bBalloonTooltip

すべてのツールヒントの表示スタイルを指定します。

```
BOOL m_bBalloonTooltip;
```

### <a name="remarks"></a>解説

TRUE は、ツールヒントがバルーンスタイルを使用することを示します。 FALSE は、ツールヒントが四角形スタイルを使用することを示します。

## <a name="cmfctooltipinfom_bboldlabel"></a><a name="m_bboldlabel"></a> CMFCToolTipInfo:: m_bBoldLabel

ツールヒントのテキストのフォントを太字にするかどうかを指定します。

```
BOOL m_bBoldLabel;
```

### <a name="remarks"></a>解説

太字フォントのツールヒントテキストを表示する場合は、このメンバーを TRUE に設定します。太字でないフォントを持つツールヒントラベルを表示する場合は FALSE を設定します。

## <a name="cmfctooltipinfom_bdrawdescription"></a><a name="m_bdrawdescription"></a> CMFCToolTipInfo:: m_bDrawDescription

各ツールヒントに説明テキストを表示するかどうかを指定します。

```
BOOL m_bDrawDescription;
```

### <a name="remarks"></a>解説

説明を表示するには、このメンバーを TRUE に設定します。説明を非表示にするには FALSE を設定します。 [CMFCToolTipCtrl:: SetDescription](../../mfc/reference/cmfctooltipctrl-class.md#setdescription)を呼び出すことによって、ツールヒントに説明を指定できます。

## <a name="cmfctooltipinfom_bdrawicon"></a><a name="m_bdrawicon"></a> CMFCToolTipInfo:: m_bDrawIcon

すべてのツールヒントにアイコンを表示するかどうかを指定します。

```
BOOL m_bDrawIcon;
```

### <a name="remarks"></a>解説

各ツールヒントにアイコンを表示する場合は、このメンバーを TRUE に設定します。アイコンなしでツールヒントを表示する場合は FALSE を設定します。

## <a name="cmfctooltipinfom_bdrawseparator"></a><a name="m_bdrawseparator"></a> CMFCToolTipInfo:: m_bDrawSeparator

各ツールヒントのラベルとその説明の間に区切り記号を付けるかどうかを指定します。

```
BOOL m_bDrawSeparator;
```

### <a name="remarks"></a>解説

ツールヒントのラベルと説明の間に区切り記号を表示するには、このメンバーを TRUE に設定します。区切り記号なしのツールヒントを表示するには FALSE を設定します。

## <a name="cmfctooltipinfom_broundedcorners"></a><a name="m_broundedcorners"></a> CMFCToolTipInfo:: m_bRoundedCorners

すべてのツールヒントに角を丸くするかどうかを指定します。

```
BOOL m_bRoundedCorners;
```

### <a name="remarks"></a>解説

ツールヒントに丸い角を表示するには、このメンバーを TRUE に設定します。または、ツールヒントに四角形の角を表示するには FALSE を設定します。

## <a name="cmfctooltipinfom_clrborder"></a><a name="m_clrborder"></a> CMFCToolTipInfo:: m_clrBorder

すべてのツールヒントの境界線の色を指定します。

```
COLORREF m_clrBorder;
```

## <a name="cmfctooltipinfom_clrfill"></a><a name="m_clrfill"></a> CMFCToolTipInfo:: m_clrFill

ツールヒントの背景色を指定します。

```
COLORREF m_clrFill;
```

### <a name="remarks"></a>解説

[CMFCToolTipInfo:: m_clrFillGradient](#m_clrfillgradient)が-1 の場合、ツールヒントの背景色は `m_clrFill` です。 それ以外の場合は、 `m_clrFill` グラデーションの開始色を指定し、 `m_clrFillGradient` グラデーションの終了色を指定します。 [CMFCToolTipInfo:: m_nGradientAngle](#m_ngradientangle) グラデーションの方向を決定します。

## <a name="cmfctooltipinfom_clrfillgradient"></a><a name="m_clrfillgradient"></a> CMFCToolTipInfo:: m_clrFillGradient

ツールヒントのグラデーション背景の終了色を指定します。

```
COLORREF m_clrFillGradient;
```

### <a name="remarks"></a>解説

`m_clrFillGradient`が-1 の場合、グラデーションはありません。 それ以外の場合、グラデーションの初期色は [CMFCToolTipInfo:: m_clrFill](#m_clrfill) によって指定され、グラデーションの終了色はによって指定され `m_clrFillGradient` ます。 [CMFCToolTipInfo:: m_nGradientAngle](#m_ngradientangle) グラデーションの方向を決定します。

## <a name="cmfctooltipinfom_clrtext"></a><a name="m_clrtext"></a> CMFCToolTipInfo:: m_clrText

すべてのツールヒントのテキストの色を指定します。

```
COLORREF m_clrText;
```

## <a name="cmfctooltipinfom_ngradientangle"></a><a name="m_ngradientangle"></a> CMFCToolTipInfo:: m_nGradientAngle

ツールヒントの背景にグラデーションが描画される角度を指定します。

```
int m_nGradientAngle;
```

### <a name="remarks"></a>解説

`m_nGradientAngle` ツールヒントの背景のグラデーションが水平方向からオフセットされる角度 (度単位) を指定します。 `m_nGradientAngle`が0の場合、グラデーションは左から右に描画されます。 `m_nGradientAngle`が1から360の間の場合、グラデーションはその度数だけ時計回りに回転します。 `m_nGradientAngle`が-1 (既定値) の場合、グラデーションは上から下に描画されます。 これは、 `m_nGradientAngle` を90に設定することと同じです。

[CMFCToolTipInfo:: m_clrFill](#m_clrfill) `clrFill` グラデーションの開始色を指定し、 [CMFCToolTipInfo:: m_clrFillGradient](#m_clrfillgradient)は `clrFillGradient` グラデーションの終点の色を指定します。 `m_clrFillGradient`が-1 の場合、グラデーションはありません。

## <a name="cmfctooltipinfom_nmaxdescrwidth"></a><a name="m_nmaxdescrwidth"></a> CMFCToolTipInfo:: m_nMaxDescrWidth

各ツールヒントに表示される説明の最大の幅を指定します。 説明の幅が指定された値を超えた場合、テキストは折り返されます。

```
int m_nMaxDescrWidth;
```

## <a name="cmfctooltipinfom_bvislmanagertheme"></a><a name="m_bvislmanagertheme"></a> CMFCToolTipInfo:: m_bVislManagerTheme

アプリケーションのビジュアルマネージャーがすべてのツールヒントの外観を制御するかどうかを指定します。

```
BOOL m_bVislManagerTheme;
```

### <a name="remarks"></a>解説

`m_bVislManagerTheme`が TRUE の場合、すべてのツールヒントは、アプリケーションのビジュアルマネージャーから新しい[CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md)を画面に表示する前に要求し、そのオブジェクトの値を使用して外観を決定します。 [CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md)の他のメンバーは無視されます。

## <a name="cmfctooltipinfooperator"></a><a name="operator_eq"></a> CMFCToolTipInfo:: operator =

詳細については、Visual Studio のインストールの **VC \\ atlmfc \\ src \\ mfc** フォルダーにあるソースコードを参照してください。

```
CMFCToolTipInfo& operator=(CMFCToolTipInfo& src);
```

### <a name="parameters"></a>パラメーター

から *src*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CTooltipManager クラス](../../mfc/reference/ctooltipmanager-class.md)<br/>
[CMFCToolTipCtrl クラス](../../mfc/reference/cmfctooltipctrl-class.md)
