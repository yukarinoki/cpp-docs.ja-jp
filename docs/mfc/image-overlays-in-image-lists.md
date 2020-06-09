---
title: イメージ リストのイメージのオーバーレイ
ms.date: 11/04/2016
helpviewer_keywords:
- overlays [MFC]
- image lists [MFC], image overlays in
- CImageList class [MFC], image overlays in
ms.assetid: aaf4e1c4-cd12-42c8-9af4-1bb458889b4e
ms.openlocfilehash: 861bcd5165ad0938ae6bbd77fc4a9f09095ce789
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84624474"
---
# <a name="image-overlays-in-image-lists"></a>イメージ リストのイメージのオーバーレイ

すべてのイメージリスト ([CImageList](reference/cimagelist-class.md)) には、オーバーレイマスクとして使用するイメージの一覧が含まれています。 "オーバーレイマスク" は、別のイメージに対して透過的に描画されるイメージです。 任意のイメージをオーバーレイマスクとして使用できます。 イメージリストごとに最大4つのオーバーレイマスクを指定できます。

オーバーレイマスクの一覧にイメージのインデックスを追加するには、 [SetOverlayImage](reference/cimagelist-class.md#setoverlayimage)メンバー関数、イメージのインデックス、およびオーバーレイマスクのインデックスを使用します。 オーバーレイマスクのインデックスは、0から始まるのではなく、1から始まることに注意してください。

の1回の呼び出しを使用して、イメージにオーバーレイマスクを描画し `Draw` ます。 パラメーターには、描画するイメージのインデックスとオーバーレイマスクのインデックスが含まれます。 オーバーレイマスクのインデックスを指定するには、 [INDEXTOOVERLAYMASK](/windows/win32/api/commctrl/nf-commctrl-indextooverlaymask)マクロを使用する必要があります。 [DrawIndirect](reference/cimagelist-class.md#drawindirect)メンバー関数を呼び出すときに、オーバーレイイメージを指定することもできます。

## <a name="see-also"></a>関連項目

[CImageList の使い方](using-cimagelist.md)<br/>
[制限](controls-mfc.md)
