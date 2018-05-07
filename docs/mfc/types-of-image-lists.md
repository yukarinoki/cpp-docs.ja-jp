---
title: イメージ リストの種類 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- lists [MFC], image
- image lists [MFC], types of
- CImageList class [MFC], types
ms.assetid: bee5e7c3-78f5-4037-a136-9c50d67cdee5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8988dc55bbbaa1d446ee14bf78a0cd799b422834
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="types-of-image-lists"></a>イメージ リストの種類
イメージ リストの 2 種類があります ([CImageList](../mfc/reference/cimagelist-class.md)): マスクとマスク。 「マスクされていないイメージ リスト」は、1 つまたは複数のイメージを含むカラー ビットマップで構成されます。 「マスクされたイメージ リスト」は、等しいサイズの 2 つのビットマップで構成されます。 1 つは、イメージを含むカラー ビットマップ、2 番目の一連のマスクを含むモノクロ ビットマップ-最初のビットマップのイメージごとに 1 つです。  
  
 オーバー ロードのいずれか、**作成**メンバー関数はイメージ リストをマスクするかどうかを示すフラグを受け取ります。 (他のオーバー ロードは、マスクされたイメージのリストを作成します)。  
  
 マスクされていないイメージが描画されると、対象のデバイス コンテキストにコピーされます。つまり、デバイス コンテキストの既存の背景色上に描画されます。 マスクされたイメージが描画されると、イメージのビットは、ターゲット デバイス コンテキストの背景色が透けてビットマップの透明な領域を通常生成した、マスクのビットと結合されます。 マスクされたイメージを描画するときに、いくつかの描画スタイルを指定できます。 たとえば、選択したオブジェクトを示すために、イメージ、ディザリングすることを指定できます。  
  
## <a name="see-also"></a>関連項目  
 [CImageList の使い方](../mfc/using-cimagelist.md)   
 [コントロール](../mfc/controls-mfc.md)

