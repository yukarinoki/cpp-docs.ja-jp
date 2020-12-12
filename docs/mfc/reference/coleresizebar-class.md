---
description: '詳細情報: COleResizeBar クラス'
title: COleResizeBar クラス
ms.date: 11/04/2016
f1_keywords:
- COleResizeBar
- AFXOLE/COleResizeBar
- AFXOLE/COleResizeBar::COleResizeBar
- AFXOLE/COleResizeBar::Create
helpviewer_keywords:
- COleResizeBar [MFC], COleResizeBar
- COleResizeBar [MFC], Create
ms.assetid: 56a708d9-28c5-4eb0-9404-77b688d91c63
ms.openlocfilehash: bdd97e854257e2f858b52ed45f4066b26c71394d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226715"
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
|[COleResizeBar:: COleResizeBar](#coleresizebar)|`COleResizeBar` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[COleResizeBar:: Create](#create)|Windows 子ウィンドウを作成して初期化し、オブジェクトに関連付け `COleResizeBar` ます。|

## <a name="remarks"></a>解説

`COleResizeBar` オブジェクトは、ハッチ境界線と外側のサイズ変更ハンドルを持つ [CRectTracker](../../mfc/reference/crecttracker-class.md) として表示されます。

`COleResizeBar` オブジェクトは通常、 [COleIPFrameWnd](../../mfc/reference/coleipframewnd-class.md) クラスから派生したフレームウィンドウオブジェクトの埋め込みメンバーです。

詳細については、「 [アクティブ化](../../mfc/activation-cpp.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CControlBar](../../mfc/reference/ccontrolbar-class.md)

`COleResizeBar`

## <a name="requirements"></a>要件

**ヘッダー:** afxole

## <a name="coleresizebarcoleresizebar"></a><a name="coleresizebar"></a> COleResizeBar:: COleResizeBar

`COleResizeBar` オブジェクトを構築します。

```
COleResizeBar();
```

### <a name="remarks"></a>解説

`Create`を呼び出して、サイズ変更バーオブジェクトを作成します。

## <a name="coleresizebarcreate"></a><a name="create"></a> COleResizeBar:: Create

子ウィンドウを作成し、オブジェクトに関連付け `COleResizeBar` ます。

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE,
    UINT nID = AFX_IDW_RESIZE_BAR);
```

### <a name="parameters"></a>パラメーター

*pParentWnd*<br/>
サイズ変更バーの親ウィンドウへのポインター。

*dwStyle*<br/>
[ウィンドウスタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)属性を指定します。

*nID*<br/>
サイズ変更バーの子ウィンドウ ID。

### <a name="return-value"></a>戻り値

サイズ変更バーが作成された場合は0以外の。それ以外の場合は0です。

## <a name="see-also"></a>関連項目

[MFC サンプル SUPERPAD](../../overview/visual-cpp-samples.md)<br/>
[CControlBar クラス](../../mfc/reference/ccontrolbar-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[COleServerDoc クラス](../../mfc/reference/coleserverdoc-class.md)
