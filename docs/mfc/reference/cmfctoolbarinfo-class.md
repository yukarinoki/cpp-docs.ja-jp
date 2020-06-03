---
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
ms.openlocfilehash: 593d1665751f7322fc2a9cee307620df88d46876
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376193"
---
# <a name="cmfctoolbarinfo-class"></a>CMFCToolBarInfo クラス

さまざまな状態のツール バー イメージのリソース ID を含みます。 `CMFCToolBarInfo`は、メソッドのパラメーターとして使用されるヘルパー クラス[です](../../mfc/reference/cmfctoolbar-class.md#loadtoolbarex)。

## <a name="syntax"></a>構文

```
class CMFCToolBarInfo
```

## <a name="members"></a>メンバー

### <a name="data-members"></a>データ メンバー

|名前|説明|
|----------|-----------------|
|[CMFCツールバーインフォ::m_uiColdResID](#m_uicoldresid)|通常の (コールド) ツール バー イメージを含むツール バー ビットマップのリソース ID。|
|[ツールバーインフォ::m_uiDisabledResID](#m_uidisabledresid)|無効なツール バー イメージを含むツール バー ビットマップのリソース ID。|
|[ツール バーインフォ::m_uiHotResID](#m_uihotresid)|選択された (ホットな) ツール バー イメージを含むツール バー ビットマップのリソース ID です。|
|[ツール バーインフォ::m_uiLargeColdResID](#m_uilargecoldresid)|大きい標準のツール バー イメージを含むツール バー ビットマップのリソース ID。|
|[ツール バーインフォ::m_uiLargeDisabledResID](#m_uilargedisabledresid)|ツール バー イメージを大きく、無効にした大きいツール バー のビットマップのリソース ID。|
|[CMFCツールバーインフォ::m_uiLargeHotResID](#m_uilargehotresid)|選択した大きいツール バー イメージを含むツール バー ビットマップのリソース ID。|
|[CMFCツールバーインフォ::m_uiMenuDisabledResID](#m_uimenudisabledresid)|無効なメニュー イメージを含むツール バー ビットマップのリソース ID です。|
|[ツールバーインフォ::m_uiMenuResID](#m_uimenuresid)|メニュー イメージを含むツール バー ビットマップのリソース ID。|

## <a name="remarks"></a>解説

ツール バーのビットマップは、固定サイズの小さなツール バー イメージ (ボタン) で構成されます。 `CMFCToolBarInfo`オブジェクトに格納される各リソース ID は、1 つの状態 (選択、無効、大きい、メニューイメージなど) のツール バー イメージの完全なセットを含むビットマップです。

## <a name="inheritance-hierarchy"></a>継承階層

[CMFCToolBarInfo](../../mfc/reference/cmfctoolbarinfo-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxtoolbar.h

## <a name="cmfctoolbarinfom_uicoldresid"></a><a name="m_uicoldresid"></a>CMFCツールバーインフォ::m_uiColdResID

ツール バーのすべての標準ボタン イメージのリソース ID を指定します。

```
UINT m_uiColdResID;
```

## <a name="cmfctoolbarinfom_uidisabledresid"></a><a name="m_uidisabledresid"></a>ツールバーインフォ::m_uiDisabledResID

ツール バーのボタンを使用できないイメージのリソース ID を指定します。

```
UINT m_uiDisabledResID;
```

## <a name="cmfctoolbarinfom_uihotresid"></a><a name="m_uihotresid"></a>ツール バーインフォ::m_uiHotResID

ツール バーのすべての強調表示されたボタン イメージのリソース ID を指定します。

```
UINT m_uiHotResID
```

## <a name="cmfctoolbarinfom_uilargecoldresid"></a><a name="m_uilargecoldresid"></a>ツール バーインフォ::m_uiLargeColdResID

ツール バーのすべての大きい標準ボタン イメージのリソース ID を指定します。

```
UINT m_uiLargeColdResID
```

## <a name="cmfctoolbarinfom_uilargedisabledresid"></a><a name="m_uilargedisabledresid"></a>ツール バーインフォ::m_uiLargeDisabledResID

ツール バーのすべての大きな無効ボタン イメージのリソース ID を指定します。

```
UINT m_uiLargeDisabledResID;
```

## <a name="cmfctoolbarinfom_uilargehotresid"></a><a name="m_uilargehotresid"></a>CMFCツールバーインフォ::m_uiLargeHotResID

ツール バーの大きな強調表示イメージのリソース ID を指定します。

```
UINT m_uiLargeHotResID;
```

## <a name="cmfctoolbarinfom_uimenudisabledresid"></a><a name="m_uimenudisabledresid"></a>CMFCツールバーインフォ::m_uiMenuDisabledResID

ツール バーのコマンドを使用できないイメージのリソース ID を指定します。

```
UINT m_uiMenuDisabledResID;
```

## <a name="cmfctoolbarinfom_uimenuresid"></a><a name="m_uimenuresid"></a>ツールバーインフォ::m_uiMenuResID

ツール バーのすべての標準メニュー項目イメージのリソース ID を指定します。

```
UINT m_uiMenuResID;
```

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[クラス](../../mfc/reference/cmfctoolbar-class.md)
