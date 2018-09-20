---
title: CTreeView クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CTreeView
- AFXCVIEW/CTreeView
- AFXCVIEW/CTreeView::CTreeView
- AFXCVIEW/CTreeView::GetTreeCtrl
dev_langs:
- C++
helpviewer_keywords:
- CTreeView [MFC], CTreeView
- CTreeView [MFC], GetTreeCtrl
ms.assetid: 5df583a6-d69f-42ca-9d8d-57e04558afff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a760e567718ad7a485ebe469903c7cbd566daccc
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46375399"
---
# <a name="ctreeview-class"></a>CTreeView クラス

簡単に使用およびツリー コントロールの[CTreeCtrl](../../mfc/reference/ctreectrl-class.md)MFC のドキュメント/ビュー アーキテクチャのツリー コントロールの機能をカプセル化するクラス。

## <a name="syntax"></a>構文

```
class CTreeView : public CCtrlView
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CTreeView::CTreeView](#ctreeview)|`CTreeView` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CTreeView::GetTreeCtrl](#gettreectrl)|ビューに関連付けられているツリーのコントロールを返します。|

## <a name="remarks"></a>Remarks

このアーキテクチャの詳細については、「の概要、 [CView](../../mfc/reference/cview-class.md)クラスとクロス リファレンスがあります。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CCtrlView](../../mfc/reference/cctrlview-class.md)

`CTreeView`

## <a name="requirements"></a>要件

**ヘッダー:** afxcview.h

##  <a name="ctreeview"></a>  CTreeView::CTreeView

`CTreeView` オブジェクトを構築します。

```
CTreeView();
```

##  <a name="gettreectrl"></a>  CTreeView::GetTreeCtrl

ビューに関連付けられているツリーのコントロールへの参照を返します。

```
CTreeCtrl& GetTreeCtrl() const;
```

## <a name="see-also"></a>関連項目

[CCtrlView クラス](../../mfc/reference/cctrlview-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CView クラス](../../mfc/reference/cview-class.md)<br/>
[CCtrlView クラス](../../mfc/reference/cctrlview-class.md)<br/>
[CTreeCtrl クラス](../../mfc/reference/ctreectrl-class.md)
