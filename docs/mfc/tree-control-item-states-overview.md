---
title: ツリー コントロール項目の状態の概要 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- states, CTreeCtrl items
- tree controls [MFC], item states overview
- CTreeCtrl class [MFC], item states
ms.assetid: 2db11ae0-0d87-499d-8c1f-5e0dbe9e94c8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: be5c0d3e477103edaf31bafed01265a509e48ad1
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43198342"
---
# <a name="tree-control-item-states-overview"></a>ツリー コントロール項目の状態の概要
ツリー コントロール内の各アイテム ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) は現在の状態があります。 たとえば、項目選択できます、無効になっている、展開、およびなど。 ほとんどの場合、ツリー コントロール項目の選択などのユーザー操作を反映するように、項目の状態が自動的に設定します。 ただし、設定することも、項目の状態を使用して、 [SetItemState](../mfc/reference/ctreectrl-class.md#setitemstate)メンバー関数を使用して、項目の現在の状態の取得、 [GetItemState](../mfc/reference/ctreectrl-class.md#getitemstate)メンバー関数。 項目の状態の完全な一覧を参照してください。[ツリー ビュー コントロール定数](/windows/desktop/Controls/tree-view-control-item-states)Windows SDK に含まれています。  
  
 アイテムの現在の状態がで指定された、*状態*パラメーター。 ツリー コントロール項目の選択や、項目にフォーカスを設定など、ユーザーの操作を反映するように、項目の状態を変更する可能性があります。 さらに、アプリケーションでは、無効にするか、またはアイテムを非表示にオーバーレイ画像または状態のイメージを指定したり、項目の状態を変更します。  
  
 指定またはアイテムの状態を変更すると、*取得*どの状態ビットを設定すると、パラメーターを指定し、*状態*パラメーターには、これらのビットの新しい値が含まれています。 たとえば、次の例が、親アイテムの現在の状態を変更 (で指定された*hParentItem*) で、`CTreeCtrl`オブジェクト (`m_treeCtrl`) に`TVIS_EXPANDPARTIAL`:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#71](../mfc/codesnippet/cpp/tree-control-item-states-overview_1.cpp)]  
  
 状態を変更する別の例は、アイテムのオーバーレイのイメージを設定することです。 これを実現する*取得*含める必要があります、`TVIS_OVERLAYMASK`値、および *%n 状態*1 ベース イメージのインデックス、オーバーレイ シフトを使用して 8 ビットを左に含める必要があります、 [INDEXTOOVERLAYMASK](/windows/desktop/api/commctrl/nf-commctrl-indextooverlaymask)マクロです。 インデックスには、0 をオーバーレイ画像を指定しない場合があります。 オーバーレイ画像する必要がありますに加えオーバーレイのイメージのツリー コントロールの一覧に以前の呼び出しによって、 [CImageList::SetOverlayImage](../mfc/reference/cimagelist-class.md#setoverlayimage)関数。 関数を追加するには、イメージの 1 から始まるインデックスを指定しますこれからマクロを使用するインデックスです。 ツリー コントロールでは、最大 4 つのオーバーレイ画像を持つことができます。  
  
 項目の状態のイメージを設定する*取得*含める必要があります、`TVIS_STATEIMAGEMASK`値、および*状態*1 から始まるインデックスのシフト状態のイメージを使用して、12 ビットを左に含める必要があります、 [INDEXTOSTATEIMAGEMASK](/windows/desktop/api/commctrl/nf-commctrl-indextostateimagemask)マクロ。 インデックスは、状態の画像を含まないように指定する 0 にできます。 イメージのオーバーレイと状態の詳細については、次を参照してください。[ツリー コントロールのイメージ リスト](../mfc/tree-control-image-lists.md)します。  
  
## <a name="see-also"></a>関連項目  
 [CTreeCtrl の使い方](../mfc/using-ctreectrl.md)   
 [コントロール](../mfc/controls-mfc.md)

