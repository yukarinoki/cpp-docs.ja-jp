---
title: ツリー コントロール項目の状態の概要 |Microsoft ドキュメント
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
ms.openlocfilehash: 3bc62308642492aa00a139fb15cc9e6cdcfc3247
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="tree-control-item-states-overview"></a>ツリー コントロール項目の状態の概要
ツリー コントロール内の各項目 ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) が現在の状態。 たとえば、項目選択できます、無効になっている、展開、およびなど。 ほとんどの場合、ツリー コントロール項目の選択などのユーザー操作を反映するように、アイテムの状態が自動的に設定します。 ただし、設定することも、アイテムの状態を使用して、 [SetItemState](../mfc/reference/ctreectrl-class.md#setitemstate)メンバー関数を使用して、アイテムの現在の状態の取得、 [GetItemState](../mfc/reference/ctreectrl-class.md#getitemstate)メンバー関数。 項目の状態の一覧については、次を参照してください。[ツリー ビュー コントロール定数](http://msdn.microsoft.com/library/windows/desktop/bb759985)Windows SDK に含まれています。  
  
 アイテムの現在の状態がで指定された、`nState`パラメーター。 ツリー コントロールには、アイテムの選択項目にフォーカスを設定など、ユーザーの操作を反映するように、アイテムの状態が変化します。 さらに、アプリケーションは、項目の状態を無効にするか、項目を非表示にするのにまたはオーバーレイ イメージまたは状態の画像を指定するを変更する可能性があります。  
  
 指定または項目の状態を変更するときに、`nStateMask`どの状態ビットを設定すると、パラメーターを指定し、`nState`パラメーターには、これらのビットの新しい値が含まれています。 たとえば、次の例が、親アイテムの現在の状態を変更 (で指定した`hParentItem`) で、`CTreeCtrl`オブジェクト (`m_treeCtrl`) に**コード**:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#71](../mfc/codesnippet/cpp/tree-control-item-states-overview_1.cpp)]  
  
 状態を変更する別の例は、アイテムのオーバーレイのイメージを設定することです。 これを実現する`nStateMask`含める必要があります、`TVIS_OVERLAYMASK`値、および`nState`1 ベース イメージのインデックス、オーバーレイ シフトを使用して 8 ビットを左に含める必要があります、[から](http://msdn.microsoft.com/library/windows/desktop/bb761408)マクロです。 インデックスは、するイメージのオーバーレイを指定しない場合は 0 を指定できます。 オーバーレイ イメージ必要がありますが一覧に追加されてツリー コントロールのイメージのオーバーレイの以前の呼び出しによって、 [CImageList::SetOverlayImage](../mfc/reference/cimagelist-class.md#setoverlayimage)関数。 関数を追加するには、イメージの 1 から始まるインデックスを指定しますこれで使用されるインデックス、**から**マクロです。 ツリー コントロールでは、最大で 4 つのオーバーレイ イメージを持つことができます。  
  
 項目の状態の画像を設定する`nStateMask`含める必要があります、`TVIS_STATEIMAGEMASK`値、および`nState`1 から始まるインデックスのシフト状態の画像を使用して 12 ビットを左に含める必要があります、 [INDEXTOSTATEIMAGEMASK](http://msdn.microsoft.com/library/windows/desktop/bb775597)マクロです。 インデックスは、イメージを指定していない状態 0 にすることができます。 オーバーレイと状態のイメージの詳細については、次を参照してください。[ツリー コントロールのイメージ リスト](../mfc/tree-control-image-lists.md)です。  
  
## <a name="see-also"></a>関連項目  
 [CTreeCtrl の使い方](../mfc/using-ctreectrl.md)   
 [コントロール](../mfc/controls-mfc.md)

