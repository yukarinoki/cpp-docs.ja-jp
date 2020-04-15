---
title: CSmartDockingInfo クラス
ms.date: 11/19/2018
f1_keywords:
- CSmartDockingInfo
- AFXDOCKINGMANAGER/CSmartDockingInfo
- AFXDOCKINGMANAGER/CSmartDockingInfo::CopyTo
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_bUseThemeColorInShading
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_clrBaseBackground
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_clrToneDest
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_clrToneSrc
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_clrTransparent
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_nCentralGroupOffset
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_sizeTotal
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_uiMarkerBmpResID
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_uiMarkerLightBmpResID
helpviewer_keywords:
- CSmartDockingInfo [MFC], CopyTo
- CSmartDockingInfo [MFC], m_bUseThemeColorInShading
- CSmartDockingInfo [MFC], m_clrBaseBackground
- CSmartDockingInfo [MFC], m_clrToneDest
- CSmartDockingInfo [MFC], m_clrToneSrc
- CSmartDockingInfo [MFC], m_clrTransparent
- CSmartDockingInfo [MFC], m_nCentralGroupOffset
- CSmartDockingInfo [MFC], m_sizeTotal
- CSmartDockingInfo [MFC], m_uiMarkerBmpResID
- CSmartDockingInfo [MFC], m_uiMarkerLightBmpResID
ms.assetid: cab04f38-4bc1-4378-9337-c56fc87fbd68
ms.openlocfilehash: c0ccb9f728add37230cbfd88cc8f6c9b1696fa2e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318225"
---
# <a name="csmartdockinginfo-class"></a>CSmartDockingInfo クラス

スマート ドッキング マーカーの外観を定義します。

## <a name="syntax"></a>構文

```
class CSmartDockingInfo : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|`CSmartDockingInfo::CSmartDockingInfo`|既定のコンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[Cスマートドッキングインフォ::コピート](#copyto)|現在のスマート ドッキング情報パラメーターを指定された[CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md)オブジェクトにコピーします。|

### <a name="data-members"></a>データ メンバー

|名前|説明|
|----------|-----------------|
|[Cスマートドッキングインフォ:m_bUseThemeColorInShading](#m_busethemecolorinshading)|フレームワークがスマート ドッキング マーカーを表示するときに、現在のテーマの色を使用するかどうかを指定します。|
|[Cスマートドッキングインフォ::m_clrBaseBackground](#m_clrbasebackground)|スマート ドッキング マーカーの基本背景色を指定します。|
|[Cスマートドッキングインフォ::m_clrToneDest](#m_clrtonedest)|スマート ドッキング マーカー`m_clrToneSrc`ビットマップで置き換える色を指定します。|
|[Cスマートドッキングインフォ::m_clrToneSrc](#m_clrtonesrc)|スマート ドッキング マーカー ビットマップの色を指定します。|
|[Cスマートドッキング情報::m_clrTransparent](#m_clrtransparent)|透明な場合のスマート ドッキング マーカー ビットマップの色を指定します。|
|[Cスマートドッキングインフォ::m_nCentralGroupOffset](#m_ncentralgroupoffset)|中央グループの四角形の境界からのスマート ドッキング マーカーの中央グループのオフセットを指定します。|
|[Cスマートドッキングインフォ::m_sizeTotal](#m_sizetotal)|グループ内のすべてのスマート ドッキング マーカーの合計サイズを指定します。|
|[Cスマートドッキング情報::m_uiMarkerBmpResID](#m_uimarkerbmpresid)|強調表示されていないスマート ドッキング マーカーに対してフレームワークが使用するビットマップのリソース ID を定義します。|
|[Cスマートドッキングインフォ::m_uiMarkerLightBmpResID](#m_uimarkerlightbmpresid)|強調表示されているスマート ドッキング マーカーに対してフレームワークが使用するビットマップのリソース ID を定義します。|

## <a name="remarks"></a>解説

フレームワークは、スマート ドッキング マーカーを内部で処理します。 次の図は、標準のスマート ドッキング マーカーを示しています。

![スマート ドッキングの標準マーカー](../../mfc/reference/media/nextsdmarkers.png "スマート ドッキングの標準マーカー")

この図の左側の図は、タブへのドッキングが有効になっていない中央グループのスマート ドッキング マーカーを示しています。 中央の画像は、右端のスマートドッキングマーカーを示しています。 右側の画像は、タブへのドッキングが有効になっている中央グループのスマートドッキングマーカーを示しています。 中央グループのスマート ドッキング マーカーには、メイン のビットマップと 5 つのスマート ドッキング マーカー ビットマップがあります。

スマート ドッキング マーカーの次のパラメーターをカスタマイズできます。

- 色 たとえば、図のマーカーの青い色を、ユーザー定義の色に置き換えることができます。

- 透明度の色。

- 境界の四角形の境界からの中央グループのスマート ドッキング マーカーのオフセット。

- 中央グループを表すメイン ビットマップ。

- 通常のスマート ドッキング マーカーと強調表示されたスマート ドッキング マーカーを表すビットマップ。

次の図は、カスタマイズされたスマート ドッキング マーカーの例を示しています。

![スマート ドッキングのカスタム マーカー](../../mfc/reference/media/nextsdmarkerscustom.png "スマート ドッキングのカスタム マーカー")

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxDockingManager.h

## <a name="csmartdockinginfocopyto"></a><a name="copyto"></a>Cスマートドッキングインフォ::コピート

現在のスマート ドッキング パラメーターを指定された[CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md)オブジェクトにコピーします。

```
void CopyTo(CSmartDockingInfo& params);
```

### <a name="parameters"></a>パラメーター

*params*<br/>
[アウト]現在のスマート`CSmartDockingInfo`ドッキング パラメーターが設定されている型のオブジェクト。

## <a name="csmartdockinginfom_busethemecolorinshading"></a><a name="m_busethemecolorinshading"></a>Cスマートドッキングインフォ:m_bUseThemeColorInShading

フレームワークがスマート ドッキング マーカーを表示するときに、現在のテーマの色を使用するかどうかを指定します。

```
BOOL m_bUseThemeColorInShading;
```

### <a name="remarks"></a>解説

TRUE の場合、マーカーは現在のテーマの色を使用して描画されます。それ以外の場合は、マーカーは水色で描画されます。

既定値は FALSE です。

## <a name="csmartdockinginfom_clrbasebackground"></a><a name="m_clrbasebackground"></a>Cスマートドッキングインフォ::m_clrBaseBackground

スマート ドッキング マーカーの基本背景色を指定します。

```
COLORREF m_clrBaseBackground;
```

## <a name="csmartdockinginfom_clrtonedest"></a><a name="m_clrtonedest"></a>Cスマートドッキングインフォ::m_clrToneDest

スマート ドッキング マーカー`m_clrToneSrc`ビットマップで置き換える色を指定します。

```
COLORREF m_clrToneDest;
```

### <a name="remarks"></a>解説

プログラムによってマーカー ビットマップの色を変更するには、この値を設定します。 たとえば、フレームワークに付属する標準マーカーの色を変更する場合は、この値を目的の色に設定します。 デフォルトでは[、CSmartDockingInfo::m_clrToneSrc](#m_clrtonesrc)はRGB(61、123、241)(青みがかった色)に設定されています。

カスタム マーカーの色を変更するには、 と`m_clrToneDest`の`m_clrToneSrc`両方を指定する必要があります。

## <a name="csmartdockinginfom_clrtonesrc"></a><a name="m_clrtonesrc"></a>Cスマートドッキングインフォ::m_clrToneSrc

スマート ドッキング マーカー ビットマップの色を指定します。

```
COLORREF m_clrToneSrc;
```

### <a name="remarks"></a>解説

この値は、カスタム ビットマップの色を別の色に置き換える場合にのみ設定します。 標準 (フレームワーク提供) マーカーの色を変更する場合は、この値を設定する必要はありません。

スマート`(COLORREF)-1`ドッキング グループのメンバを空のままにします。

## <a name="csmartdockinginfom_clrtransparent"></a><a name="m_clrtransparent"></a>Cスマートドッキング情報::m_clrTransparent

透明な場合のスマート ドッキング マーカー ビットマップの色を指定します。

```
COLORREF m_clrTransparent;
```

### <a name="remarks"></a>解説

ドッキング グループにカスタム マーカーとカスタム ビットマップを表示する場合は、この値を設定する必要があります。

## <a name="csmartdockinginfom_ncentralgroupoffset"></a><a name="m_ncentralgroupoffset"></a>Cスマートドッキングインフォ::m_nCentralGroupOffset

スマート ドッキング マーカーの中央グループと中央グループ四角形の境界との間のオフセットを指定します。

```
int m_nCentralGroupOffset;
```

### <a name="remarks"></a>解説

カスタム マーカーとスマート ドッキング マーカーの中央グループの境界との間の既定のオフセットを変更する場合は、この値を指定します。 デフォルトのオフセットは 5 ピクセルです。

## <a name="csmartdockinginfom_sizetotal"></a><a name="m_sizetotal"></a>Cスマートドッキングインフォ::m_sizeTotal

中央グループ内のすべてのスマート ドッキング マーカーを囲む外接する四角形の合計サイズを指定します。

```
CSize m_sizeTotal;
```

### <a name="remarks"></a>解説

中央`m_sizeTotal`グループ マーカーの外接する四角形のサイズに設定します。 マーカーにカスタム ビットマップを使用する場合は、この値を指定する必要があります。

## <a name="csmartdockinginfom_uimarkerbmpresid"></a><a name="m_uimarkerbmpresid"></a>Cスマートドッキング情報::m_uiMarkerBmpResID

強調表示されていないカスタム スマート ドッキング マーカーに使用されるビットマップのリソース ID を定義します。

```
UINT m_uiMarkerBmpResID[AFX_SD_MARKERS_NUM];
```

### <a name="remarks"></a>解説

スマート ドッキング マーカーを表すビットマップのリソース ID をこの配列に入力します。 AFX_SD_MARKERS_NUMは現在 5 と定義されています。 配列は次のように入力します。

```cpp
params.m_uiMarkerBmpResID[0] = IDB_MARKER_LEFT;
params.m_uiMarkerBmpResID[1] = IDB_MARKER_RIGHT;
params.m_uiMarkerBmpResID[2] = IDB_MARKER_TOP;
params.m_uiMarkerBmpResID[3] = IDB_MARKER_BOTTOM;
params.m_uiMarkerBmpResID[4] = IDB_MARKER_CENTER;
```

## <a name="csmartdockinginfom_uimarkerlightbmpresid"></a><a name="m_uimarkerlightbmpresid"></a>Cスマートドッキングインフォ::m_uiMarkerLightBmpResID

強調表示されたカスタム スマート ドッキング マーカーに使用されるビットマップのリソース ID を定義します。

```
UINT m_uiMarkerLightBmpResID[AFX_SD_MARKERS_NUM];
```

### <a name="remarks"></a>解説

強調表示されたスマート ドッキング マーカーを表すビットマップのリソース ID をこの配列に入力します。 AFX_SD_MARKERS_NUMは現在 5 と定義されています。 配列は次のように入力します。

```cpp
params.m_uiMarkerLightBmpResID[0] = IDB_MARKER_LEFT_LIGHT;
params.m_uiMarkerLightBmpResID[1] = IDB_MARKER_RIGHT_LIGHT;
params.m_uiMarkerLightBmpResID[2] = IDB_MARKER_TOP_LIGHT;
params.m_uiMarkerLightBmpResID[3] = IDB_MARKER_BOTTOM_LIGHT;
params.m_uiMarkerLightBmpResID[4] = IDB_MARKER_CENTER_LIGHT;
```

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[Cオブジェクトクラス](../../mfc/reference/cobject-class.md)
