---
description: '詳細情報: Csmartdocに関する情報クラス'
title: Csmartdocに関する情報クラス
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
ms.openlocfilehash: 290f9eef208ceed425739ab26e7811c04309e057
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97345135"
---
# <a name="csmartdockinginfo-class"></a>Csmartdocに関する情報クラス

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
|[Csmartdocの "情報:: CopyTo"](#copyto)|現在のスマートドッキング情報パラメーターを、指定された [Csmartdocの情報](../../mfc/reference/csmartdockinginfo-class.md) オブジェクトにコピーします。|

### <a name="data-members"></a>データ メンバー

|名前|説明|
|----------|-----------------|
|[Csmartdocに関する情報:: m_bUseThemeColorInShading](#m_busethemecolorinshading)|フレームワークがスマートドッキングマーカーを表示するときに、現在のテーマの色を使用するかどうかを指定します。|
|[Csmartdocに関する情報:: m_clrBaseBackground](#m_clrbasebackground)|スマートドッキングマーカーの基本背景色を指定します。|
|[Csmartdocに関する情報:: m_clrToneDest](#m_clrtonedest)|`m_clrToneSrc`スマートドッキングマーカービットマップで置き換える色を指定します。|
|[Csmartdocに関する情報:: m_clrToneSrc](#m_clrtonesrc)|スマートドッキングマーカービットマップの色を指定します。|
|[Csmartdocに関する情報:: m_clrTransparent](#m_clrtransparent)|スマートドッキングマーカービットマップが透明な場合の色を指定します。|
|[Csmartdocに関する情報:: m_nCentralGroupOffset](#m_ncentralgroupoffset)|中央グループの四角形の境界からスマートドッキングマーカーの中央グループのオフセットを指定します。|
|[Csmartdocに関する情報:: m_sizeTotal](#m_sizetotal)|グループ内のすべてのスマートドッキングマーカーの合計サイズを指定します。|
|[Csmartdocに関する情報:: m_uiMarkerBmpResID](#m_uimarkerbmpresid)|強調表示されていないスマートドッキングマーカーにフレームワークが使用するビットマップのリソース Id を定義します。|
|[Csmartdocに関する情報:: m_uiMarkerLightBmpResID](#m_uimarkerlightbmpresid)|強調表示されているスマートドッキングマーカーにフレームワークが使用するビットマップのリソース Id を定義します。|

## <a name="remarks"></a>解説

フレームワークは、スマートドッキングマーカーを内部で処理します。 次の図は、標準のスマートドッキングマーカーを示しています。

![スマート ドッキングの標準マーカー](../../mfc/reference/media/nextsdmarkers.png "スマート ドッキングの標準マーカー")

この図では、左側の画像は、タブが有効になっていない中央グループのスマートドッキングマーカーを示しています。 中央の画像は、右端のスマートドッキングマーカーを示しています。 右側の画像は、タブが有効になっている中央グループのスマートドッキングマーカーを示しています。 中央グループのスマートドッキングマーカーには、メインビットマップと5つのスマートドッキングマーカービットマップがあります。

スマートドッキングマーカーの次のパラメーターをカスタマイズできます。

- 色 たとえば、図のマーカーの青い色をユーザー定義の色に置き換えることができます。

- 透明度の色。

- 境界四角形の境界から中央グループのスマートドッキングマーカーのオフセット。

- 中央のグループを表すメインビットマップ。

- 標準および強調表示されたスマートドッキングマーカーを表すビットマップ。

次の図は、カスタマイズされたスマートドッキングマーカーの例を示しています。

![スマート ドッキングのカスタム マーカー](../../mfc/reference/media/nextsdmarkerscustom.png "スマート ドッキングのカスタム マーカー")

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxDockingManager

## <a name="csmartdockinginfocopyto"></a><a name="copyto"></a> Csmartdocの "情報:: CopyTo"

現在のスマートドッキングパラメーターを、指定された [Csmartdocの情報](../../mfc/reference/csmartdockinginfo-class.md) オブジェクトにコピーします。

```cpp
void CopyTo(CSmartDockingInfo& params);
```

### <a name="parameters"></a>パラメーター

*params*<br/>
入出力 `CSmartDockingInfo` 現在のスマートドッキングパラメーターを使用して設定される型のオブジェクト。

## <a name="csmartdockinginfom_busethemecolorinshading"></a><a name="m_busethemecolorinshading"></a> Csmartdocに関する情報:: m_bUseThemeColorInShading

フレームワークがスマートドッキングマーカーを表示するときに、現在のテーマの色を使用するかどうかを指定します。

```
BOOL m_bUseThemeColorInShading;
```

### <a name="remarks"></a>解説

TRUE の場合、マーカーは現在のテーマの色を使用して描画されます。それ以外の場合、マーカーは薄い青の色で描画されます。

既定値は FALSE です。

## <a name="csmartdockinginfom_clrbasebackground"></a><a name="m_clrbasebackground"></a> Csmartdocに関する情報:: m_clrBaseBackground

スマートドッキングマーカーの基本背景色を指定します。

```
COLORREF m_clrBaseBackground;
```

## <a name="csmartdockinginfom_clrtonedest"></a><a name="m_clrtonedest"></a> Csmartdocに関する情報:: m_clrToneDest

スマートドッキングマーカービットマップ内で置き換えられる色を指定し `m_clrToneSrc` ます。

```
COLORREF m_clrToneDest;
```

### <a name="remarks"></a>解説

プログラムによってマーカービットマップの色を変更するには、この値を設定します。 たとえば、フレームワークで提供される標準マーカーの色を変更する場合は、この値を目的の色に設定します。 既定では、 [Csmartdocbluish info:: m_clrToneSrc](#m_clrtonesrc) は RGB (61、123、241) (color) に設定されています。

カスタムマーカーの色を変更するには、との両方を指定する必要があり `m_clrToneDest` `m_clrToneSrc` ます。

## <a name="csmartdockinginfom_clrtonesrc"></a><a name="m_clrtonesrc"></a> Csmartdocに関する情報:: m_clrToneSrc

スマートドッキングマーカービットマップの色を指定します。

```
COLORREF m_clrToneSrc;
```

### <a name="remarks"></a>解説

カスタムビットマップの色を別の色に置き換える場合にのみ、この値を設定します。 標準 (フレームワーク提供) のマーカーの色を変更する場合は、この値を設定する必要はありません。

`(COLORREF)-1`スマートドッキンググループのメンバーを空のままにするには、を使用します。

## <a name="csmartdockinginfom_clrtransparent"></a><a name="m_clrtransparent"></a> Csmartdocに関する情報:: m_clrTransparent

スマートドッキングマーカービットマップが透明な場合の色を指定します。

```
COLORREF m_clrTransparent;
```

### <a name="remarks"></a>解説

ドッキンググループにカスタムマーカーとカスタムビットマップを表示する場合は、この値を設定する必要があります。

## <a name="csmartdockinginfom_ncentralgroupoffset"></a><a name="m_ncentralgroupoffset"></a> Csmartdocに関する情報:: m_nCentralGroupOffset

スマートドッキングマーカーの中央グループと中央グループ四角形の境界の間のオフセットを指定します。

```
int m_nCentralGroupOffset;
```

### <a name="remarks"></a>解説

カスタムマーカーとスマートドッキングマーカーの中央グループの境界との間の既定のオフセットを変更する場合は、この値を指定します。 既定のオフセットは5ピクセルです。

## <a name="csmartdockinginfom_sizetotal"></a><a name="m_sizetotal"></a> Csmartdocに関する情報:: m_sizeTotal

中央グループ内のすべてのスマートドッキングマーカーを囲む外接する四角形の合計サイズを指定します。

```
CSize m_sizeTotal;
```

### <a name="remarks"></a>解説

`m_sizeTotal`中央グループマーカーの外接する四角形のサイズに設定します。 マーカーにカスタムビットマップを使用している場合は、この値を指定する必要があります。

## <a name="csmartdockinginfom_uimarkerbmpresid"></a><a name="m_uimarkerbmpresid"></a> Csmartdocに関する情報:: m_uiMarkerBmpResID

強調表示されていないカスタムスマートドッキングマーカーに使用されるビットマップのリソース Id を定義します。

```
UINT m_uiMarkerBmpResID[AFX_SD_MARKERS_NUM];
```

### <a name="remarks"></a>解説

この配列に、スマートドッキングマーカーを表すビットマップのリソース Id を入力します。 AFX_SD_MARKERS_NUM は現在5として定義されています。 配列には次のように入力します。

```cpp
params.m_uiMarkerBmpResID[0] = IDB_MARKER_LEFT;
params.m_uiMarkerBmpResID[1] = IDB_MARKER_RIGHT;
params.m_uiMarkerBmpResID[2] = IDB_MARKER_TOP;
params.m_uiMarkerBmpResID[3] = IDB_MARKER_BOTTOM;
params.m_uiMarkerBmpResID[4] = IDB_MARKER_CENTER;
```

## <a name="csmartdockinginfom_uimarkerlightbmpresid"></a><a name="m_uimarkerlightbmpresid"></a> Csmartdocに関する情報:: m_uiMarkerLightBmpResID

強調表示されたカスタムスマートドッキングマーカーに使用されるビットマップのリソース Id を定義します。

```
UINT m_uiMarkerLightBmpResID[AFX_SD_MARKERS_NUM];
```

### <a name="remarks"></a>解説

この配列に、強調表示されたスマートドッキングマーカーを表すビットマップのリソース Id を入力します。 AFX_SD_MARKERS_NUM は現在5として定義されています。 配列には次のように入力します。

```cpp
params.m_uiMarkerLightBmpResID[0] = IDB_MARKER_LEFT_LIGHT;
params.m_uiMarkerLightBmpResID[1] = IDB_MARKER_RIGHT_LIGHT;
params.m_uiMarkerLightBmpResID[2] = IDB_MARKER_TOP_LIGHT;
params.m_uiMarkerLightBmpResID[3] = IDB_MARKER_BOTTOM_LIGHT;
params.m_uiMarkerLightBmpResID[4] = IDB_MARKER_CENTER_LIGHT;
```

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CObject クラス](../../mfc/reference/cobject-class.md)
