---
title: クラスを表示します。
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
ms.openlocfilehash: d7f3b7c43d98c4f2c42d0c27c8e224f33e4b3301
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81749128"
---
# <a name="clistview-class"></a>クラスを表示します。

リスト コントロールと、リスト コントロール機能をカプセル化するクラス[である CListCtrl](../../mfc/reference/clistctrl-class.md)の使用を簡略化します。

## <a name="syntax"></a>構文

```
class CListView : public CCtrlView
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[を表示します。](#clistview)|`CListView` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[次のリストビュー::リストCtrl](#getlistctrl)|ビューに関連付けられているリスト コントロールを返します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[次の項目を表示します。](#removeimagelist)|指定したイメージ リストをリスト ビューから削除します。|

## <a name="remarks"></a>解説

このアーキテクチャの詳細については[、CView](../../mfc/reference/cview-class.md)クラスの概要と、そこで引用されている相互参照を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CCtrlView](../../mfc/reference/cctrlview-class.md)

`CListView`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxcview.h

## <a name="clistviewclistview"></a><a name="clistview"></a>を表示します。

`CListView` オブジェクトを構築します。

```
CListView();
```

## <a name="clistviewgetlistctrl"></a><a name="getlistctrl"></a>次のリストビュー::リストCtrl

ビューに関連付けられているリスト コントロールへの参照を取得します。

```
CListCtrl& GetListCtrl() const;
```

### <a name="return-value"></a>戻り値

ビューに関連付けられているリスト コントロールへの参照。

### <a name="example"></a>例

[!code-cpp[NVC_MFCListView#7](../../atl/reference/codesnippet/cpp/clistview-class_1.cpp)]

## <a name="clistviewremoveimagelist"></a><a name="removeimagelist"></a>次の項目を表示します。

指定したイメージ リストをリスト ビューから削除します。

```cpp
void RemoveImageList(int nImageList);
```

### <a name="parameters"></a>パラメーター

*一覧*<br/>
削除するイメージの 0 から始まるインデックス。

## <a name="see-also"></a>関連項目

[MFC サンプル行一覧](../../overview/visual-cpp-samples.md)<br/>
[クラスを表示します。](../../mfc/reference/cctrlview-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラスを表示します。](../../mfc/reference/cctrlview-class.md)
