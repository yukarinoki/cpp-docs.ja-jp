---
title: イメージ リストの種類 |Microsoft Docs
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
ms.openlocfilehash: 3bea24d487170ea4cac470f2244340f6b570d1ec
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46390475"
---
# <a name="types-of-image-lists"></a>イメージ リストの種類

イメージ リストの 2 種類があります ([CImageList](../mfc/reference/cimagelist-class.md)): マスクとマスク。 「マスクされていないイメージ リスト」は、1 つまたは複数のイメージを含むカラー ビットマップで構成されます。 「マスクされたイメージ一覧」は、等しいサイズの 2 つのビットマップで構成されます。 色のビットマップ イメージを含む 1 つ目は、2 番目の一連のマスクを含むモノクロ ビットマップ、ビットマップ内の各イメージのいずれか。

オーバー ロードの 1 つ、`Create`メンバー関数は、イメージ リストをマスクするかどうかを示すフラグを受け取ります。 (他のオーバー ロードは、マスクされたイメージのリストを作成します)。

マスクされていないイメージが描画されるときに、ターゲット デバイス コンテキストにコピーされます。つまり、デバイス コンテキストの既存の背景色の上に描画されます。 マスクされたイメージが描画されるときに、イメージのビットは、通常、ビットマップ内の透明な領域を作成、ターゲット デバイス コンテキストの背景色が透けて、マスクのビットと結合されます。 マスクされたイメージを描画するときに、いくつかの描画スタイルを指定できます。 たとえば、イメージは、選択したオブジェクトを示すディザーをかけることを指定できます。

## <a name="see-also"></a>関連項目

[CImageList の使い方](../mfc/using-cimagelist.md)<br/>
[コントロール](../mfc/controls-mfc.md)

