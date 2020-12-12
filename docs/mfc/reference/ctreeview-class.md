---
description: '詳細情報: CTreeView クラス'
title: CTreeView クラス
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
ms.openlocfilehash: 3e50f912f03d5214e8ec238844b3288691a4f326
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318521"
---
# <a name="ctreeview-class"></a>CTreeView クラス

ツリーコントロールと、ツリーコントロールの機能をカプセル化する [CTreeCtrl](../../mfc/reference/ctreectrl-class.md)クラスを、MFC のドキュメント/ビューアーキテクチャで簡単に使用できるようにします。

## <a name="syntax"></a>構文

```
class CTreeView : public CCtrlView
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CTreeView:: CTreeView](#ctreeview)|`CTreeView` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CTreeView:: Treeview](#gettreectrl)|ビューに関連付けられているツリーコントロールを返します。|

## <a name="remarks"></a>解説

このアーキテクチャの詳細については、「 [CView](../../mfc/reference/cview-class.md) クラスの概要」と「相互参照」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CCtrlView](../../mfc/reference/cctrlview-class.md)

`CTreeView`

## <a name="requirements"></a>要件

**ヘッダー:** afxcview

## <a name="ctreeviewctreeview"></a><a name="ctreeview"></a> CTreeView:: CTreeView

`CTreeView` オブジェクトを構築します。

```
CTreeView();
```

## <a name="ctreeviewgettreectrl"></a><a name="gettreectrl"></a> CTreeView:: Treeview

ビューに関連付けられているツリーコントロールへの参照を返します。

```
CTreeCtrl& GetTreeCtrl() const;
```

## <a name="see-also"></a>関連項目

[CCtrlView クラス](../../mfc/reference/cctrlview-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CView クラス](../../mfc/reference/cview-class.md)<br/>
[CCtrlView クラス](../../mfc/reference/cctrlview-class.md)<br/>
[CTreeCtrl クラス](../../mfc/reference/ctreectrl-class.md)
