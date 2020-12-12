---
description: '詳細情報: CListView クラス'
title: CListView クラス
ms.date: 11/04/2016
f1_keywords:
- CListView
- AFXCVIEW/CListView
- AFXCVIEW/CListView::CListView
- AFXCVIEW/CListView::GetListCtrl
- AFXCVIEW/CListView::RemoveImageList
helpviewer_keywords:
- CListView [MFC], CListView
- CListView [MFC], GetListCtrl
- CListView [MFC], RemoveImageList
ms.assetid: 7626bdb2-a1b8-4eab-b631-6743710a8432
ms.openlocfilehash: 5576a0997c84e8f5639911a1120a6645e720a7cf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97259566"
---
# <a name="clistview-class"></a>CListView クラス

リストコントロールと、リストコントロールの機能をカプセル化するクラスである [CListCtrl](../../mfc/reference/clistctrl-class.md)の使用を、MFC のドキュメント/ビューアーキテクチャと共に簡略化します。

## <a name="syntax"></a>構文

```
class CListView : public CCtrlView
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CListView:: CListView](#clistview)|`CListView` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CListView:: GetListCtrl](#getlistctrl)|ビューに関連付けられているリストコントロールを返します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CListView:: RemoveImageList](#removeimagelist)|リストビューから指定されたイメージリストを削除します。|

## <a name="remarks"></a>解説

このアーキテクチャの詳細については、「 [CView](../../mfc/reference/cview-class.md) クラスの概要」と「相互参照」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CCtrlView](../../mfc/reference/cctrlview-class.md)

`CListView`

## <a name="requirements"></a>要件

**ヘッダー:** afxcview

## <a name="clistviewclistview"></a><a name="clistview"></a> CListView:: CListView

`CListView` オブジェクトを構築します。

```
CListView();
```

## <a name="clistviewgetlistctrl"></a><a name="getlistctrl"></a> CListView:: GetListCtrl

ビューに関連付けられているリストコントロールへの参照を取得するには、このメンバー関数を呼び出します。

```
CListCtrl& GetListCtrl() const;
```

### <a name="return-value"></a>戻り値

ビューに関連付けられたリストコントロールへの参照。

### <a name="example"></a>例

[!code-cpp[NVC_MFCListView#7](../../atl/reference/codesnippet/cpp/clistview-class_1.cpp)]

## <a name="clistviewremoveimagelist"></a><a name="removeimagelist"></a> CListView:: RemoveImageList

リストビューから指定されたイメージリストを削除します。

```cpp
void RemoveImageList(int nImageList);
```

### <a name="parameters"></a>パラメーター

*nImageList*<br/>
削除するイメージの0から始まるインデックス。

## <a name="see-also"></a>関連項目

[MFC のサンプル行リスト](../../overview/visual-cpp-samples.md)<br/>
[CCtrlView クラス](../../mfc/reference/cctrlview-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CCtrlView クラス](../../mfc/reference/cctrlview-class.md)
