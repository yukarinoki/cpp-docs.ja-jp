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
ms.openlocfilehash: 93d37b49a949ab29e0ae888d9c961da086ee4ca4
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36928597"
---
# <a name="image-overlays-in-image-lists"></a>イメージ リストのイメージのオーバーレイ
すべてのイメージ リスト ([CImageList](../mfc/reference/cimagelist-class.md)) オーバーレイ マスクとして使用するイメージの一覧が含まれています。 「オーバーレイ マスク」は、別のイメージ上に透過的に描画されるイメージです。 任意の画像は、オーバーレイ マスクとして使用できます。 イメージ リストごとに最大 4 つのオーバーレイ マスクを指定することができます。  
  
 オーバーレイ マスクの一覧を使用して、イメージのインデックスを追加する、 [SetOverlayImage](../mfc/reference/cimagelist-class.md#setoverlayimage)メンバー関数は、イメージのインデックスおよびオーバーレイ マスクのインデックス。 マスクのオーバーレイ インデックスは 1 ベースではなく 0 から始まることに注意してください。  
  
 1 回の呼び出しを使用してイメージ上にオーバーレイ マスクを描画する`Draw`です。 パラメーターには、描画するイメージのインデックスと、オーバーレイ マスクのインデックスが含まれます。 使用する必要があります、[から](http://msdn.microsoft.com/library/windows/desktop/bb761408)マクロ オーバーレイ マスクのインデックスを指定します。 呼び出すときにオーバーレイ イメージを指定することも、[もう 1 つ](../mfc/reference/cimagelist-class.md#drawindirect)メンバー関数。  
  
## <a name="see-also"></a>関連項目  
 [CImageList の使い方](../mfc/using-cimagelist.md)   
 [コントロール](../mfc/controls-mfc.md)

