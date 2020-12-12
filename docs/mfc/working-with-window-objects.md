---
description: '詳細情報: ウィンドウオブジェクトの操作'
title: ウィンドウ オブジェクトの操作
ms.date: 11/04/2016
helpviewer_keywords:
- child windows [MFC], working with
- window objects [MFC], working with
ms.assetid: f73aa254-90e3-46a9-8e9b-d78b7054a331
ms.openlocfilehash: 4a8c6f2c40eadbfe53aa79683bea29847adf684f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97172592"
---
# <a name="working-with-window-objects"></a>ウィンドウ オブジェクトの操作

2種類のアクティビティに対する windows 呼び出しの操作:

- Windows メッセージの処理

- 描画 (ウィンドウに)

独自の子ウィンドウを含む任意のウィンドウで Windows メッセージを処理する方法については、「メッセージを [関数に](../mfc/reference/mapping-messages-to-functions.md) マップして、メッセージを C++ ウィンドウクラスにマップする」を参照してください。 次に、メッセージハンドラーのメンバー関数をクラスに記述します。

フレームワークアプリケーションでのほとんどの描画はビューで発生します。このビューでは、ウィンドウのコンテンツを描画する必要があるたびに、 [OnDraw](../mfc/reference/cview-class.md#ondraw) メンバー関数が呼び出されます。 ウィンドウがビューの子である場合は、 `OnDraw` ウィンドウのメンバー関数のいずれかを呼び出すことによって、一部のビューの描画を子ウィンドウに委任することができます。

どのような場合でも、描画するにはデバイスコンテキストが必要です。 ウィンドウに関連付けられているデバイスコンテキストに含まれる、ストックペン、ブラシ、およびその他のグラフィックオブジェクトを使用できます。 または、これらのオブジェクトを変更して、必要な描画効果を得ることができます。 デバイスコンテキストを好みに応じて設定し、 [CDC](../mfc/reference/cdc-class.md) (デバイスコンテキストクラス) クラスのメンバー関数を呼び出して、直線、図形、テキストを描画します。色を使用するには座標系を操作します。

## <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- [メッセージの処理とマップ](../mfc/message-handling-and-mapping.md)

- [ビューの描画](../mfc/drawing-in-a-view.md)

- [デバイス コンテキスト](../mfc/device-contexts.md)

- [グラフィック オブジェクト](../mfc/graphic-objects.md)

## <a name="see-also"></a>関連項目

[ウィンドウオブジェクト](../mfc/window-objects.md)
