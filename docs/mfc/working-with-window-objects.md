---
title: ウィンドウ オブジェクトの操作
ms.date: 11/04/2016
helpviewer_keywords:
- child windows [MFC], working with
- window objects [MFC], working with
ms.assetid: f73aa254-90e3-46a9-8e9b-d78b7054a331
ms.openlocfilehash: c696d880ffa69b0a0399c5282621546c5783ebe4
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57265640"
---
# <a name="working-with-window-objects"></a>ウィンドウ オブジェクトの操作

Windows の呼び出しの 2 種類のアクティビティの使用。

- Windows メッセージの処理

- ウィンドウでの描画

独自の子ウィンドウを含む任意のウィンドウでの Windows メッセージを処理するために、[関数へのメッセージの割り当て](../mfc/reference/mapping-messages-to-functions.md)C++ window クラスに、メッセージをマップを参照してください。 メッセージ ハンドラー メンバー関数を記述し、クラス。

ビューで、発生 framework アプリケーションで描画のほとんどが[OnDraw](../mfc/reference/cview-class.md#ondraw)ウィンドウの内容を描画する必要があるたびに、メンバー関数が呼び出されます。 ウィンドウがビューの子である場合は、可能性がありますを委任するいくつかのビューの描画を子ウィンドウさせて`OnDraw`ウィンドウのメンバー関数のいずれかを呼び出します。

いずれの場合も、描画のデバイス コンテキストを必要があります。 ストックのペン、ブラシ、および、ウィンドウに関連付けられているデバイス コンテキストに含まれるその他のグラフィック オブジェクトを使用することができます。 または、これらのオブジェクトを取得する必要がある特殊効果を変更することができます。 好きなように設定する、デバイス コンテキストを持つメンバー関数を呼び出してクラスの[CDC](../mfc/reference/cdc-class.md) (デバイス コンテキスト クラス) 線、図形、およびテキストを描画するためには色; を使用して、座標系を使用します。

## <a name="what-do-you-want-to-know-more-about"></a>方法については、するして操作を行います

- [メッセージの処理とのマッピング](../mfc/message-handling-and-mapping.md)

- [ビューの描画](../mfc/drawing-in-a-view.md)

- [デバイス コンテキスト](../mfc/device-contexts.md)

- [グラフィック オブジェクト](../mfc/graphic-objects.md)

## <a name="see-also"></a>関連項目

[Window オブジェクト](../mfc/window-objects.md)
