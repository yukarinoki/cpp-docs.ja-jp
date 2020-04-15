---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- CTreeView
- AFXCVIEW/CTreeView
- AFXCVIEW/CTreeView::CTreeView
- AFXCVIEW/CTreeView::GetTreeCtrl
helpviewer_keywords:
- CTreeView [MFC], CTreeView
- CTreeView [MFC], GetTreeCtrl
ms.assetid: 5df583a6-d69f-42ca-9d8d-57e04558afff
ms.openlocfilehash: 2ef93152c83d3bbec2b89ada0596ee612b24701b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373287"
---
# <a name="ctreeview-class"></a>クラス

ツリー コントロールと、ツリー コントロール機能をカプセル化するクラスである[CTreeCtrl](../../mfc/reference/ctreectrl-class.md)の使用を簡略化し、MFC のドキュメント ビュー アーキテクチャを使用します。

## <a name="syntax"></a>構文

```
class CTreeView : public CCtrlView
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[::Cツリービュー](#ctreeview)|`CTreeView` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[を見る::取得ツリーCtrl](#gettreectrl)|ビューに関連付けられているツリー コントロールを返します。|

## <a name="remarks"></a>解説

このアーキテクチャの詳細については[、CView](../../mfc/reference/cview-class.md)クラスの概要と、そこで引用されている相互参照を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CCtrlView](../../mfc/reference/cctrlview-class.md)

`CTreeView`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxcview.h

## <a name="ctreeviewctreeview"></a><a name="ctreeview"></a>::Cツリービュー

`CTreeView` オブジェクトを構築します。

```
CTreeView();
```

## <a name="ctreeviewgettreectrl"></a><a name="gettreectrl"></a>を見る::取得ツリーCtrl

ビューに関連付けられているツリー コントロールへの参照を返します。

```
CTreeCtrl& GetTreeCtrl() const;
```

## <a name="see-also"></a>関連項目

[クラスを表示します。](../../mfc/reference/cctrlview-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[Cビュークラス](../../mfc/reference/cview-class.md)<br/>
[クラスを表示します。](../../mfc/reference/cctrlview-class.md)<br/>
[CTreeCtrl クラス](../../mfc/reference/ctreectrl-class.md)
