---
title: トラッカー |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 414a7c19292e154af0b6365b766d865dca0a7dd3
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46439875"
---
# <a name="trackers"></a>トラッカー

[CRectTracker](../mfc/reference/crecttracker-class.md)クラスは、四角形のアイテムをアプリケーションにさまざまな表示スタイルを提供することで、ユーザーのユーザー インターフェイスを提供します。 これらのスタイルには、solid、斜線、または破線の罫線が含まれます。アイテムをカバーするハッチ パターン外部または境界線内にあることができるハンドルのサイズを変更します。 OLE アイテムと共にトラッカーが使用される多くの場合から派生したオブジェクトは、`COleClientItem`します。 トラッカーの四角形は、アイテムの現在の状態の視覚的な手掛かりを付与します。

MFC OLE サンプル[OCLIENT](../visual-cpp-samples.md)トラッカーとコンテナー アプリケーションの観点から見た OLE クライアント アイテムを使用して一般的なインターフェイスを示します。 さまざまなスタイルのデモと追跡ツールのオブジェクトの機能は、MFC の一般的なサンプルを参照してください。[トラッカー](../visual-cpp-samples.md)します。

OLE アプリケーションでのトラッカーの実装の詳細については、次を参照してください[トラッカー: OLE アプリケーションでのトラッカーの実装。](../mfc/trackers-implementing-trackers-in-your-ole-application.md)

## <a name="see-also"></a>関連項目

[OLE](../mfc/ole-in-mfc.md)<br/>
[COleClientItem クラス](../mfc/reference/coleclientitem-class.md)
