---
title: リスト コントロールとリスト ビュー
ms.date: 11/04/2016
helpviewer_keywords:
- CListView class [MFC], and CListCtrl
- views [MFC], list and list control
- CListCtrl class [MFC], and CListView
- list views [MFC]
- list controls [MFC], List view
ms.assetid: 7aee1c48-b158-4399-be0b-be366993665e
ms.openlocfilehash: d308cfe83f02dcfe3687790c6638d268cc69fc24
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84621425"
---
# <a name="list-control-and-list-view"></a>リスト コントロールとリスト ビュー

便宜上、MFC はリストコントロールを2つの方法でカプセル化します。 リストコントロールを使用できます。

- 直接です。ダイアログクラスに[CListCtrl](reference/clistctrl-class.md)オブジェクトを埋め込むことによって行います。

- 間接的には、 [CListView](reference/clistview-class.md)クラスを使用します。

`CListView`では、リストコントロールを MFC のドキュメント/ビューアーキテクチャと簡単に統合できるようになっています。これにより、コントロールが編集コントロールを[カプセル化する](reference/ceditview-class.md)ようになります。コントロールは、mfc ビューのサーフェイス領域全体を占めます。 (ビューはコントロールであり、にキャスト*さ* `CListView` れます)。

オブジェクトは、 `CListView` [CCtrlView](reference/cctrlview-class.md)とその基本クラスから継承され、基になるリストコントロールを取得するためのメンバー関数を追加します。 ビューをビューとして操作するには、ビューメンバーを使用します。 リストコントロールのメンバー関数にアクセスするには、 [Getlistctrl](reference/clistview-class.md#getlistctrl)メンバー関数を使用します。 これらのメンバーは次の用途に使用します。

- リスト内の "items" を追加、削除、または操作します。

- リストコントロールの属性を設定または取得します。

基になるに対する参照を取得するには `CListCtrl` `CListView` 、 `GetListCtrl` リストビュークラスからを呼び出します。

[!code-cpp[NVC_MFCListView#4](../atl/reference/codesnippet/cpp/list-control-and-list-view_1.cpp)]

このトピックでは、リストコントロールを使用する両方の方法について説明します。

## <a name="see-also"></a>関連項目

[CListCtrl の使い方](using-clistctrl.md)<br/>
[制限](controls-mfc.md)
