---
title: イメージのイメージ リストのオーバーレイ |Microsoft ドキュメント
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
ms.openlocfilehash: 55a55a6e015a2f8c1613a85717c030737712c4da
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="image-overlays-in-image-lists"></a>イメージ リストのイメージのオーバーレイ
すべてのイメージ リスト ([CImageList](../mfc/reference/cimagelist-class.md)) オーバーレイ マスクとして使用するイメージの一覧が含まれています。 「オーバーレイ マスク」は、別のイメージ上に透過的に描画されるイメージです。 任意の画像は、オーバーレイ マスクとして使用できます。 イメージ リストごとに最大 4 つのオーバーレイ マスクを指定することができます。  
  
 オーバーレイ マスクの一覧を使用して、イメージのインデックスを追加する、 [SetOverlayImage](../mfc/reference/cimagelist-class.md#setoverlayimage)メンバー関数は、イメージのインデックスおよびオーバーレイ マスクのインデックス。 マスクのオーバーレイ インデックスは 1 ベースではなく 0 から始まることに注意してください。  
  
 1 回の呼び出しを使用してイメージ上にオーバーレイ マスクを描画する**描画**です。 パラメーターには、描画するイメージのインデックスと、オーバーレイ マスクのインデックスが含まれます。 使用する必要があります、[から](http://msdn.microsoft.com/library/windows/desktop/bb761408)マクロ オーバーレイ マスクのインデックスを指定します。 呼び出すときにオーバーレイ イメージを指定することも、[もう 1 つ](../mfc/reference/cimagelist-class.md#drawindirect)メンバー関数。  
  
## <a name="see-also"></a>関連項目  
 [CImageList の使い方](../mfc/using-cimagelist.md)   
 [コントロール](../mfc/controls-mfc.md)

