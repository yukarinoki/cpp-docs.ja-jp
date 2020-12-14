---
description: '詳細情報: トラッカー'
title: トラッカー
ms.date: 11/04/2016
helpviewer_keywords:
- trackers [MFC]
- OLE applications [MFC], trackers
- applications [OLE], trackers
- tracking OLE items [MFC]
- OLE containers [MFC], trackers
- CDC class [MFC], trackers
- CRectTracker class [MFC], implementing trackers
- OLE server applications [MFC], trackers
ms.assetid: dcd09399-6637-4621-80e5-d12670429787
ms.openlocfilehash: e82766ecfabf2b5ebb0147b9f2c462f3b4460869
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264248"
---
# <a name="trackers"></a>トラッカー

[CRectTracker](../mfc/reference/crecttracker-class.md)クラスは、さまざまな表示スタイルを提供することにより、アプリケーションとユーザーの四角形の間にユーザーインターフェイスを提供します。 これらのスタイルには、実線、ハッチ、破線などがあります。項目をカバーするハッチパターン。境界線の外側または内側に配置できる、サイズ変更ハンドル。 多くの場合、トラッカーは OLE アイテム、つまりから派生したオブジェクトと組み合わせて使用され `COleClientItem` ます。 トラッカー四角形は、項目の現在の状態を視覚的に示します。

MFC OLE サンプル [OCLIENT](../overview/visual-cpp-samples.md) は、コンテナーアプリケーションの視点から見たトラッカーと OLE クライアントアイテムを使用する共通インターフェイスを示しています。 トラッカーオブジェクトのさまざまなスタイルと機能のデモンストレーションについては、「MFC の一般的なサンプル [トラッカー](../overview/visual-cpp-samples.md)」を参照してください。

OLE アプリケーションでのトラッカーの実装の詳細については、「[トラッカー: Ole アプリケーションでのトラッカーの実装](../mfc/trackers-implementing-trackers-in-your-ole-application.md)」を参照してください。

## <a name="see-also"></a>関連項目

[OLE●ole○](../mfc/ole-in-mfc.md)<br/>
[COleClientItem クラス](../mfc/reference/coleclientitem-class.md)
