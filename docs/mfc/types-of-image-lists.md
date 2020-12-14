---
description: '詳細: イメージリストの種類'
title: イメージ リストの種類
ms.date: 11/04/2016
helpviewer_keywords:
- lists [MFC], image
- image lists [MFC], types of
- CImageList class [MFC], types
ms.assetid: bee5e7c3-78f5-4037-a136-9c50d67cdee5
ms.openlocfilehash: be18a523db366813a236fd4fd94bbb001345f0d1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97263739"
---
# <a name="types-of-image-lists"></a>イメージ リストの種類

イメージリスト ([CImageList](../mfc/reference/cimagelist-class.md)) には、nonmasked とマスクの2種類があります。 "Nonmasked image list" は、1つ以上のイメージを含むカラービットマップで構成されます。 "マスクされたイメージリスト" は、同じサイズの2つのビットマップで構成されます。 1つ目はイメージを含むカラービットマップで、2つ目は、1つ目のビットマップ内の各イメージに1つずつ、一連のマスクを含むモノクロビットマップです。

メンバー関数のオーバーロードの1つ `Create` は、イメージリストがマスクされているかどうかを示すフラグを取得することです。 (他のオーバーロードは、マスクされたイメージリストを作成します)。

Nonmasked イメージが描画されると、単にターゲットデバイスコンテキストにコピーされます。つまり、デバイスコンテキストの既存の背景色に対して描画されます。 マスクされたイメージが描画されると、イメージのビットはマスクのビットと組み合わされます。通常、ビットマップ内では、ターゲットデバイスコンテキストの背景色が表示される透明な領域が生成されます。 マスクされたイメージを描画するときに、いくつかの描画スタイルを指定できます。 たとえば、選択したオブジェクトを示すために画像をディザーするように指定できます。

## <a name="see-also"></a>関連項目

[CImageList の使い方](../mfc/using-cimagelist.md)<br/>
[コントロール](../mfc/controls-mfc.md)
