---
title: イメージのイメージ リストのオーバーレイ |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- overlays [MFC]
- image lists [MFC], image overlays in
- CImageList class [MFC], image overlays in
ms.assetid: aaf4e1c4-cd12-42c8-9af4-1bb458889b4e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4369fe312669f75eb8217be7a6a09c4287f7cc8b
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43210714"
---
# <a name="image-overlays-in-image-lists"></a>イメージ リストのイメージのオーバーレイ
すべてのイメージ リスト ([CImageList](../mfc/reference/cimagelist-class.md)) オーバーレイ マスクとして使用するイメージの一覧が含まれています。 「オーバーレイ マスク」は、別のイメージの上に透過的に描画されるイメージです。 任意のイメージは、オーバーレイ マスクとして使用できます。 イメージ リストごとに最大 4 つのオーバーレイ マスクを指定することができます。  
  
 オーバーレイのリストを使用してイメージのインデックスを追加する、 [SetOverlayImage](../mfc/reference/cimagelist-class.md#setoverlayimage)メンバー関数は、イメージのインデックス、およびオーバーレイ マスクのインデックス。 マスクのオーバーレイ インデックスは 1 ベースではなく 0 から始まる、することに注意してください。  
  
 1 回の呼び出しを使用してイメージ上でオーバーレイ マスクを描画した`Draw`します。 パラメーターには、描画するイメージのインデックスとオーバーレイ マスクのインデックスが含まれます。 使用する必要があります、[から](/windows/desktop/api/commctrl/nf-commctrl-indextooverlaymask)マクロ オーバーレイ マスクのインデックスを指定します。 呼び出すときに、オーバーレイのイメージを指定することも、[もう 1 つ](../mfc/reference/cimagelist-class.md#drawindirect)メンバー関数。  
  
## <a name="see-also"></a>関連項目  
 [Cimagelist の使い方](../mfc/using-cimagelist.md)   
 [コントロール](../mfc/controls-mfc.md)

