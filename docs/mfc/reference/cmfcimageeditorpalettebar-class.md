---
title: クラスをイメージします。
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
ms.openlocfilehash: 33d4bc0c72718d028031ac11bc67da6aec5e4907
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374428"
---
# <a name="cmfcimageeditorpalettebar-class"></a>クラスをイメージします。

イメージ エディターダイアログ ボックスにパレット バー機能を提供します。

## <a name="syntax"></a>構文

```
class CMFCImageEditorPaletteBar : public CMFCToolBar
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|||
|-|-|
|名前|説明|
|[パレットバー::ゲットローハイト](#getrowheight)|ツール バー ボタンの高さを返します。 (CMFC ツールバーをオーバーライド[します。::ゲットローハイト](../../mfc/reference/cmfctoolbar-class.md#getrowheight).)|
|[パレットバー::ボタンエクストラサイズ利用可能](#isbuttonextrasizeavailable)|ツール バーに、拡張枠線を持つボタンを表示できるかどうかを指定します。 (CMFC ツールバーをオーバーライド[します。)](../../mfc/reference/cmfctoolbar-class.md#isbuttonextrasizeavailable)|

### <a name="remarks"></a>解説

このクラスは、コードで直接使用するためのものではありません。

フレームワークは、このクラスを使用して、イメージ エディター ダイアログ ボックスにパレット バーを表示します。 イメージ エディター ダイアログ ボックスの詳細については[、「CMFCImageEditorDialog クラス](../../mfc/reference/cmfcimageeditordialog-class.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[ツールバ](../../mfc/reference/cmfcbasetoolbar-class.md)

[CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)

[パレットバー](../../mfc/reference/cmfcimageeditorpalettebar-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afximage エディターダイアログ.h

## <a name="cmfcimageeditorpalettebargetrowheight"></a><a name="getrowheight"></a>パレットバー::ゲットローハイト

ツール バー ボタンの高さを返します。

```
virtual int GetRowHeight() const;
```

### <a name="return-value"></a>戻り値

ツール バーの各ボタンの高さ。

## <a name="cmfcimageeditorpalettebarisbuttonextrasizeavailable"></a><a name="isbuttonextrasizeavailable"></a>パレットバー::ボタンエクストラサイズ利用可能

ツール バーに、拡張枠線を持つボタンを表示できるかどうかを指定します。

```
virtual BOOL IsButtonExtraSizeAvailable() const;
```

### <a name="return-value"></a>戻り値

このメソッドは FALSE を返します。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[クラスをイメージします。](../../mfc/reference/cmfcimageeditordialog-class.md)
