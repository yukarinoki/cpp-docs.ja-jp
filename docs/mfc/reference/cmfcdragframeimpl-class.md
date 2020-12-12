---
description: '詳細情報: CMFCDragFrameImpl クラス'
title: CMFCDragFrameImpl クラス
ms.date: 10/18/2018
f1_keywords:
- CMFCDragFrameImpl
helpviewer_keywords:
- CMFCDragFrameImpl class [MFC]
ms.assetid: 500cd824-8188-43c2-8754-b7bb46b5648a
ms.openlocfilehash: 9885b750ace86d11ca573f23c7ee1c03d8926921
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294055"
---
# <a name="cmfcdragframeimpl-class"></a>CMFCDragFrameImpl クラス

クラスは、 `CMFCDragFrameImpl` ユーザーが標準ドッキングモードでペインをドラッグしたときに表示されるドラッグ四角形を描画します。
詳細については、Visual Studio のインストールの **VC \\ atlmfc \\ src \\ mfc** フォルダーにあるソースコードを参照してください。

## <a name="syntax"></a>構文

```
class CMFCDragFrameImpl
```

## <a name="remarks"></a>解説

このクラスのオブジェクトは、各 [CPane クラス](../../mfc/reference/cpane-class.md) オブジェクトに埋め込まれます。 このため、メソッドを使用する各ペインは、 `CanFloat` ユーザーがドラッグしたときにドラッグ四角形を表示します。

ドラッグ四角形の幅を制御するには、 [AFX_GLOBAL_DATA:: m_nDragFrameThicknessFloat](afx-global-data-structure.md#m_ndragframethicknessfloat) と [AFX_GLOBAL_DATA:: m_nDragFrameThicknessDock](afx-global-data-structure.md#m_ndragframethicknessdock)を使用します。

## <a name="inheritance-hierarchy"></a>継承階層

[CMFCDragFrameImpl](../../mfc/reference/cmfcdragframeimpl-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxdragframeimpl

## <a name="cmfcdragframeimplenddrawdragframe"></a><a name="enddrawdragframe"></a> CMFCDragFrameImpl:: EndDrawDragFrame

```cpp
void EndDrawDragFrame(BOOL bClearInternalRects = TRUE);
```

### <a name="parameters"></a>パラメーター

から *bClearInternalRects*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcdragframeimplinit"></a><a name="init"></a> CMFCDragFrameImpl:: Init

```cpp
void Init(CWnd* pDraggedWnd);
```

### <a name="parameters"></a>パラメーター

から *pDraggedWnd*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcdragframeimplmovedragframe"></a><a name="movedragframe"></a> CMFCDragFrameImpl::MoveDragFrame

```cpp
void MoveDragFrame(BOOL bForceMove = FALSE);
```

### <a name="parameters"></a>パラメーター

から *Bforcemove* 、<br/>

### <a name="remarks"></a>解説

## <a name="cmfcdragframeimplplacetabpredocking"></a><a name="placetabpredocking"></a> CMFCDragFrameImpl::P laceTabPreDocking

```cpp
void PlaceTabPreDocking(
    CBaseTabbedPane* pTabbedBar,
    BOOL bFirstTime);

void PlaceTabPreDocking(CWnd* pCBarToPlaceOn);
```

### <a name="parameters"></a>パラメーター

から *pTabbedBar*<br/>

から *bFirstTime*<br/>

から *Pcbartoplace on*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcdragframeimplremovetabpredocking"></a><a name="removetabpredocking"></a> CMFCDragFrameImpl:: RemoveTabPreDocking

```cpp
void RemoveTabPreDocking(CDockablePane* pOldTargetBar = NULL);
```

### <a name="parameters"></a>パラメーター

から *Poldtargetbar*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcdragframeimplresetstate"></a><a name="resetstate"></a> CMFCDragFrameImpl:: Resetstate 出す

```cpp
void ResetState();
```

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CPane クラス](../../mfc/reference/cpane-class.md)
