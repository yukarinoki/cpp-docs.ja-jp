---
description: '詳細情報: グラフィックオブジェクトをデバイスコンテキストに選択する'
title: グラフィック オブジェクトをデバイス コンテキストに選択する
ms.date: 11/04/2016
helpviewer_keywords:
- graphic objects [MFC], selecting into device context
- SelectObject method [MFC]
- GDI objects [MFC], device contexts
- lifetime, graphic objects [MFC]
- device contexts, selecting graphic objects into
- device contexts, graphic objects [MFC]
ms.assetid: cf54a330-63ef-421f-83eb-90ec7bd82eef
ms.openlocfilehash: cc2aabbcb1614fc77e5eadf9e6fba13ba377a4c7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217680"
---
# <a name="selecting-a-graphic-object-into-a-device-context"></a>グラフィック オブジェクトをデバイス コンテキストに選択する

このトピックは、ウィンドウのデバイスコンテキストでグラフィックオブジェクトを使用する場合に適用されます。 [描画オブジェクトを作成](../mfc/one-stage-and-two-stage-construction-of-objects.md)した後は、そこに格納されている既定のオブジェクトの代わりに、そのオブジェクトをデバイスコンテキストに選択する必要があります。

[!code-cpp[NVC_MFCDocViewSDI#7](../mfc/codesnippet/cpp/selecting-a-graphic-object-into-a-device-context_1.cpp)]

## <a name="lifetime-of-graphic-objects"></a>グラフィックオブジェクトの有効期間

[SelectObject](../mfc/reference/cdc-class.md#selectobject)によって返されるグラフィックオブジェクトは "temporary" です。 つまり、次にプログラムがアイドル状態になったときに、クラスの [OnIdle](../mfc/reference/cwinapp-class.md#onidle) メンバー関数によって削除されます `CWinApp` 。 によって返されたオブジェクトを1つの関数で使用しても、 `SelectObject` メインメッセージループに制御が返されない限り、問題はありません。

### <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- [グラフィック オブジェクト](../mfc/graphic-objects.md)

- [1 段階でのグラフィック オブジェクトの構築と 2 段階でのグラフィック オブジェクトの構築](../mfc/one-stage-and-two-stage-construction-of-objects.md)

- [デバイス コンテキスト](../mfc/device-contexts.md)

- [描画 (ビューで)](../mfc/drawing-in-a-view.md)

## <a name="see-also"></a>関連項目

[グラフィックオブジェクト](../mfc/graphic-objects.md)
