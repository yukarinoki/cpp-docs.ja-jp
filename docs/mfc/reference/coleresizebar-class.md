---
title: クラスを変更します。
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
ms.openlocfilehash: beb0c37b6ac23310b7d5c8506fbdaf677dd74d8d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376155"
---
# <a name="coleresizebar-class"></a>クラスを変更します。

OLE の埋め込み先アイテムのサイズ変更をサポートするコントロール バーの一種です。

## <a name="syntax"></a>構文

```
class COleResizeBar : public CControlBar
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[コントロール サイズ変更バー::COle サイズ変更バー](#coleresizebar)|`COleResizeBar` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[コントロール バー::作成](#create)|Windows の子ウィンドウを作成して初期化し、オブジェクトに`COleResizeBar`関連付けます。|

## <a name="remarks"></a>解説

`COleResizeBar`オブジェクトは、ハッチングされた境界線と外側のサイズ変更ハンドルを持つ[CRectTracker](../../mfc/reference/crecttracker-class.md)として表示されます。

`COleResizeBar`オブジェクトは、通常[、COleIPFrameWnd](../../mfc/reference/coleipframewnd-class.md)クラスから派生したフレーム ウィンドウ オブジェクトの埋め込みメンバーです。

詳細については、記事「[アクティベーション](../../mfc/activation-cpp.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[コントロールバー](../../mfc/reference/ccontrolbar-class.md)

`COleResizeBar`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxole.h

## <a name="coleresizebarcoleresizebar"></a><a name="coleresizebar"></a>コントロール サイズ変更バー::COle サイズ変更バー

`COleResizeBar` オブジェクトを構築します。

```
COleResizeBar();
```

### <a name="remarks"></a>解説

サイズ`Create`変更バー オブジェクトを作成する呼び出し。

## <a name="coleresizebarcreate"></a><a name="create"></a>コントロール バー::作成

子ウィンドウを作成し、`COleResizeBar`オブジェクトに関連付けます。

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE,
    UINT nID = AFX_IDW_RESIZE_BAR);
```

### <a name="parameters"></a>パラメーター

*pParentWnd*<br/>
サイズ変更バーの親ウィンドウへのポインター。

*Dwstyle*<br/>
ウィンドウ[スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)の属性を指定します。

*nID*<br/>
サイズ変更バーの子ウィンドウ ID。

### <a name="return-value"></a>戻り値

サイズ変更バーが作成された場合は 0 以外の値を返します。それ以外の場合は 0。

## <a name="see-also"></a>関連項目

[MFC サンプル スーパーパッド](../../overview/visual-cpp-samples.md)<br/>
[CControlBar クラス](../../mfc/reference/ccontrolbar-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[COleServerDoc クラス](../../mfc/reference/coleserverdoc-class.md)
