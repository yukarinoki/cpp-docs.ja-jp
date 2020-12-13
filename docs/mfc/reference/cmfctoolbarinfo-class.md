---
description: '詳細情報: CMFCToolBarInfo クラス'
title: CMFCToolBarInfo クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCToolBarInfo
- AFXTOOLBAR/CMFCToolBarInfo
- AFXTOOLBAR/CMFCToolBarInfo::m_uiColdResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiDisabledResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiHotResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiLargeColdResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiLargeDisabledResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiLargeHotResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiMenuDisabledResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiMenuResID
helpviewer_keywords:
- CMFCToolBarInfo [MFC], m_uiColdResID
- CMFCToolBarInfo [MFC], m_uiDisabledResID
- CMFCToolBarInfo [MFC], m_uiHotResID
- CMFCToolBarInfo [MFC], m_uiLargeColdResID
- CMFCToolBarInfo [MFC], m_uiLargeDisabledResID
- CMFCToolBarInfo [MFC], m_uiLargeHotResID
- CMFCToolBarInfo [MFC], m_uiMenuDisabledResID
- CMFCToolBarInfo [MFC], m_uiMenuResID
ms.assetid: 6dc84482-eaaa-491f-aa5d-dd7a57886b46
ms.openlocfilehash: 9b85ef4f39c8b42c35975a15836a21e7cc6dd6b1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331706"
---
# <a name="cmfctoolbarinfo-class"></a>CMFCToolBarInfo クラス

さまざまな状態のツール バー イメージのリソース ID を含みます。 `CMFCToolBarInfo` は、 [Cmfctoolbar:: LoadToolBarEx](../../mfc/reference/cmfctoolbar-class.md#loadtoolbarex) メソッドのパラメーターとして使用されるヘルパークラスです。

## <a name="syntax"></a>構文

```
class CMFCToolBarInfo
```

## <a name="members"></a>メンバー

### <a name="data-members"></a>データ メンバー

|名前|説明|
|----------|-----------------|
|[CMFCToolBarInfo:: m_uiColdResID](#m_uicoldresid)|標準 (コールド) のツールバーイメージを含むツールバービットマップのリソース ID。|
|[CMFCToolBarInfo:: m_uiDisabledResID](#m_uidisabledresid)|無効なツールバーイメージを含むツールバービットマップのリソース ID。|
|[CMFCToolBarInfo:: m_uiHotResID](#m_uihotresid)|選択された (ホット) ツールバーイメージを含むツールバービットマップのリソース ID。|
|[CMFCToolBarInfo:: m_uiLargeColdResID](#m_uilargecoldresid)|大きな標準のツールバーイメージを含むツールバービットマップのリソース ID。|
|[CMFCToolBarInfo:: m_uiLargeDisabledResID](#m_uilargedisabledresid)|大規模で無効なツールバーイメージを含むツールバービットマップのリソース ID。|
|[CMFCToolBarInfo:: m_uiLargeHotResID](#m_uilargehotresid)|サイズの大きい、選択されたツールバーイメージを含むツールバービットマップのリソース ID。|
|[CMFCToolBarInfo:: m_uiMenuDisabledResID](#m_uimenudisabledresid)|無効なメニューイメージを含むツールバービットマップのリソース ID。|
|[CMFCToolBarInfo:: m_uiMenuResID](#m_uimenuresid)|メニューイメージを含むツールバービットマップのリソース ID。|

## <a name="remarks"></a>解説

ツールバーの完全なビットマップは、固定サイズの小さいツールバーイメージ (ボタン) で構成されています。 オブジェクトに格納されている各リソース ID `CMFCToolBarInfo` は、1つの状態のツールバーイメージの完全なセットを含むビットマップです (たとえば、selected、disabled、large、または menu イメージ)。

## <a name="inheritance-hierarchy"></a>継承階層

[CMFCToolBarInfo](../../mfc/reference/cmfctoolbarinfo-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxtoolbar

## <a name="cmfctoolbarinfom_uicoldresid"></a><a name="m_uicoldresid"></a> CMFCToolBarInfo:: m_uiColdResID

ツールバーのすべての通常のボタンイメージのリソース ID を指定します。

```
UINT m_uiColdResID;
```

## <a name="cmfctoolbarinfom_uidisabledresid"></a><a name="m_uidisabledresid"></a> CMFCToolBarInfo:: m_uiDisabledResID

ツールバーのボタンが使用できないイメージのリソース ID を指定します。

```
UINT m_uiDisabledResID;
```

## <a name="cmfctoolbarinfom_uihotresid"></a><a name="m_uihotresid"></a> CMFCToolBarInfo:: m_uiHotResID

ツールバーの強調表示されたすべてのボタンイメージのリソース ID を指定します。

```
UINT m_uiHotResID
```

## <a name="cmfctoolbarinfom_uilargecoldresid"></a><a name="m_uilargecoldresid"></a> CMFCToolBarInfo:: m_uiLargeColdResID

ツールバーのすべての大きな標準ボタンイメージのリソース ID を指定します。

```
UINT m_uiLargeColdResID
```

## <a name="cmfctoolbarinfom_uilargedisabledresid"></a><a name="m_uilargedisabledresid"></a> CMFCToolBarInfo:: m_uiLargeDisabledResID

ツールバーのすべての大きな無効になっているボタンイメージのリソース ID を指定します。

```
UINT m_uiLargeDisabledResID;
```

## <a name="cmfctoolbarinfom_uilargehotresid"></a><a name="m_uilargehotresid"></a> CMFCToolBarInfo:: m_uiLargeHotResID

ツールバーの強調表示された大規模なすべてのイメージのリソース ID を指定します。

```
UINT m_uiLargeHotResID;
```

## <a name="cmfctoolbarinfom_uimenudisabledresid"></a><a name="m_uimenudisabledresid"></a> CMFCToolBarInfo:: m_uiMenuDisabledResID

ツールバーのコマンドを使用できないイメージのリソース ID を指定します。

```
UINT m_uiMenuDisabledResID;
```

## <a name="cmfctoolbarinfom_uimenuresid"></a><a name="m_uimenuresid"></a> CMFCToolBarInfo:: m_uiMenuResID

ツールバーのすべての標準メニュー項目イメージのリソース ID を指定します。

```
UINT m_uiMenuResID;
```

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)
