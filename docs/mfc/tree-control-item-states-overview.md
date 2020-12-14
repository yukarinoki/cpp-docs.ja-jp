---
description: '詳細情報: ツリーコントロール項目の状態の概要'
title: ツリー コントロール項目の状態の概要
ms.date: 11/04/2016
helpviewer_keywords:
- states, CTreeCtrl items
- tree controls [MFC], item states overview
- CTreeCtrl class [MFC], item states
ms.assetid: 2db11ae0-0d87-499d-8c1f-5e0dbe9e94c8
ms.openlocfilehash: bfc8f7783fdaafcb66e29040a316028d96bd86c1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264025"
---
# <a name="tree-control-item-states-overview"></a>ツリー コントロール項目の状態の概要

ツリーコントロール ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) の各項目には現在の状態があります。 たとえば、項目の選択、無効化、展開などを行うことができます。 ほとんどの場合、ツリーコントロールは項目の状態を自動的に設定して、項目の選択などのユーザー操作を反映します。 ただし、 [SetItemState](../mfc/reference/ctreectrl-class.md#setitemstate) メンバー関数を使用して項目の状態を設定し、 [GetItemState](../mfc/reference/ctreectrl-class.md#getitemstate) メンバー関数を使用して項目の現在の状態を取得することもできます。 項目の状態の完全な一覧については、「Windows SDK の [ツリービューコントロール定数](/windows/win32/Controls/tree-view-control-item-states) 」を参照してください。

項目の現在の状態は、 *nState* パラメーターによって指定されます。 項目を選択したり、項目にフォーカスを設定するなど、ユーザーの操作を反映するために、ツリーコントロールが項目の状態を変更することがあります。 さらに、アプリケーションは、項目の状態を変更して、項目を無効または非表示にしたり、オーバーレイイメージまたは状態イメージを指定したりすることがあります。

項目の状態を指定または変更する場合、 *nStateMask* パラメーターは設定する状態ビットを指定し、 *nState* パラメーターにはそれらのビットの新しい値を格納します。 たとえば、次の例では、オブジェクト () の親アイテム ( *hParentItem* によって指定) の現在の状態 `CTreeCtrl` をに変更し `m_treeCtrl` `TVIS_EXPANDPARTIAL` ます。

[!code-cpp[NVC_MFCControlLadenDialog#71](../mfc/codesnippet/cpp/tree-control-item-states-overview_1.cpp)]

状態を変更するもう1つの例は、項目のオーバーレイイメージを設定することです。 これを実現するには、 *nStateMask* に値を含める必要があり `TVIS_OVERLAYMASK` ます。 *NState* には、 [INDEXTOOVERLAYMASK](/windows/win32/api/commctrl/nf-commctrl-indextooverlaymask) マクロを使用して8ビット左にシフトするオーバーレイイメージの1から始まるインデックスを含める必要があります。 オーバーレイイメージを指定しない場合、インデックスは0になることがあります。 前の [CImageList:: SetOverlayImage](../mfc/reference/cimagelist-class.md#setoverlayimage) 関数の呼び出しによって、オーバーレイイメージがツリーコントロールのオーバーレイイメージの一覧に追加されている必要があります。 関数は、追加するイメージの1から始まるインデックスを指定します。これは、INDEXTOOVERLAYMASK マクロで使用されるインデックスです。 ツリーコントロールは、最大4つのオーバーレイイメージを持つことができます。

項目の状態のイメージを設定するには、 *nStateMask* に値を含める必要があり `TVIS_STATEIMAGEMASK` ます。 *NState* には、 [INDEXTOSTATEIMAGEMASK](/windows/win32/api/commctrl/nf-commctrl-indextostateimagemask) マクロを使用して、左側の12ビットに移動した状態イメージの1から始まるインデックスを含める必要があります。 状態イメージを指定しない場合、インデックスは0になることがあります。 オーバーレイと状態のイメージの詳細については、「 [ツリーコントロールのイメージリスト](../mfc/tree-control-image-lists.md)」を参照してください。

## <a name="see-also"></a>関連項目

[CTreeCtrl の使い方](../mfc/using-ctreectrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
