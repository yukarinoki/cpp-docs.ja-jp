---
title: Cmfcimageeditorパレットバークラス
ms.date: 11/04/2016
f1_keywords:
- CMFCImageEditorPaletteBar
- AFXIMAGEEDITORDIALOG/CMFCImageEditorPaletteBar
- AFXIMAGEEDITORDIALOG/CMFCImageEditorPaletteBar::GetRowHeight
- AFXIMAGEEDITORDIALOG/CMFCImageEditorPaletteBar::IsButtonExtraSizeAvailable
helpviewer_keywords:
- CMFCImageEditorPaletteBar [MFC], GetRowHeight
- CMFCImageEditorPaletteBar [MFC], IsButtonExtraSizeAvailable
ms.assetid: 3fb7ba8e-f254-4d56-b913-9941b4ed8138
ms.openlocfilehash: 007fa94269a6a42bf076d2d75a18860896503aa1
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88831165"
---
# <a name="cmfcimageeditorpalettebar-class"></a>Cmfcimageeditorパレットバークラス

イメージエディターのダイアログボックスにパレットバーの機能を提供します。

## <a name="syntax"></a>構文

```
class CMFCImageEditorPaletteBar : public CMFCToolBar
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|-|-|
|[Cmfcimageeditorパレットバー:: GetRowHeight](#getrowheight)|ツールバーボタンの高さを返します。 ( [Cmfctoolbar:: GetRowHeight](../../mfc/reference/cmfctoolbar-class.md#getrowheight)をオーバーライドします)。|
|[Cmfcimageeditorパレットバー:: IsButtonExtraSizeAvailable](#isbuttonextrasizeavailable)|拡張された境界線を持つボタンをツールバーに表示できるかどうかを決定します。 ( [Cmfctoolbar:: IsButtonExtraSizeAvailable](../../mfc/reference/cmfctoolbar-class.md#isbuttonextrasizeavailable)をオーバーライドします)。|

### <a name="remarks"></a>解説

このクラスは、コードで直接使用するためのものではありません。

フレームワークは、このクラスを使用して、イメージエディターのダイアログボックスにパレットバーを表示します。 [イメージエディター] ダイアログボックスの詳細については、「 [Cmfcimageeditordialog クラス](../../mfc/reference/cmfcimageeditordialog-class.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCBaseToolBa](../../mfc/reference/cmfcbasetoolbar-class.md)

[CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)

[Cmfcimageeditorパレットバー](../../mfc/reference/cmfcimageeditorpalettebar-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afximageeditordialog

## <a name="cmfcimageeditorpalettebargetrowheight"></a><a name="getrowheight"></a> Cmfcimageeditorパレットバー:: GetRowHeight

ツールバーボタンの高さを返します。

```
virtual int GetRowHeight() const;
```

### <a name="return-value"></a>戻り値

ツールバーの各ボタンの高さ。

## <a name="cmfcimageeditorpalettebarisbuttonextrasizeavailable"></a><a name="isbuttonextrasizeavailable"></a> Cmfcimageeditorパレットバー:: IsButtonExtraSizeAvailable

拡張された境界線を持つボタンをツールバーに表示できるかどうかを決定します。

```
virtual BOOL IsButtonExtraSizeAvailable() const;
```

### <a name="return-value"></a>戻り値

このメソッドは FALSE を返します。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CMFCImageEditorDialog クラス](../../mfc/reference/cmfcimageeditordialog-class.md)
