---
title: COleResizeBar クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleResizeBar
- AFXOLE/COleResizeBar
- AFXOLE/COleResizeBar::COleResizeBar
- AFXOLE/COleResizeBar::Create
dev_langs:
- C++
helpviewer_keywords:
- COleResizeBar [MFC], COleResizeBar
- COleResizeBar [MFC], Create
ms.assetid: 56a708d9-28c5-4eb0-9404-77b688d91c63
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bf1e2b447b4cfe0e2f503d2263354f3537bbb849
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46391385"
---
# <a name="coleresizebar-class"></a>COleResizeBar クラス

OLE の埋め込み先アイテムのサイズ変更をサポートするコントロール バーの一種です。

## <a name="syntax"></a>構文

```
class COleResizeBar : public CControlBar
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[COleResizeBar::COleResizeBar](#coleresizebar)|`COleResizeBar` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[COleResizeBar::Create](#create)|作成および Windows 子ウィンドウを初期化します、それを関連付ける、`COleResizeBar`オブジェクト。|

## <a name="remarks"></a>Remarks

`COleResizeBar` オブジェクトとして表示されます、 [CRectTracker](../../mfc/reference/crecttracker-class.md)破線の境界線と外部のハンドルのサイズを変更します。

`COleResizeBar` オブジェクトから派生したフレーム ウィンドウ オブジェクトの埋め込みは、通常のメンバーである、 [COleIPFrameWnd](../../mfc/reference/coleipframewnd-class.md)クラス。

詳細については、この記事を参照してください。[アクティベーション](../../mfc/activation-cpp.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CControlBar](../../mfc/reference/ccontrolbar-class.md)

`COleResizeBar`

## <a name="requirements"></a>要件

**ヘッダー:** afxole.h

##  <a name="coleresizebar"></a>  COleResizeBar::COleResizeBar

`COleResizeBar` オブジェクトを構築します。

```
COleResizeBar();
```

### <a name="remarks"></a>Remarks

呼び出す`Create`バーのサイズ変更オブジェクトを作成します。

##  <a name="create"></a>  COleResizeBar::Create

子ウィンドウを作成しに関連付けます、`COleResizeBar`オブジェクト。

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE,
    UINT nID = AFX_IDW_RESIZE_BAR);
```

### <a name="parameters"></a>パラメーター

*pParentWnd*<br/>
サイズ変更のバーの親ウィンドウへのポインター。

*dwStyle*<br/>
指定します、[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)属性。

*nID*<br/>
子ウィンドウのサイズ変更のバーの id。

### <a name="return-value"></a>戻り値

サイズ変更のバーが作成された場合は 0 以外それ以外の場合 0 を返します。

## <a name="see-also"></a>関連項目

[MFC サンプル SUPERPAD](../../visual-cpp-samples.md)<br/>
[CControlBar クラス](../../mfc/reference/ccontrolbar-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[COleServerDoc クラス](../../mfc/reference/coleserverdoc-class.md)
