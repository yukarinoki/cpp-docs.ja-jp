---
title: トラッカー |Microsoft ドキュメント
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
ms.openlocfilehash: 6f0a0cc52e3a5150702af4acd293def38df758fd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="trackers"></a>トラッカー
[CRectTracker](../mfc/reference/crecttracker-class.md)クラスには、四角形のアイテムをアプリケーションに、さまざまな表示スタイルを提供することにより、ユーザーのユーザー インターフェイスが用意されています。 これらのスタイルが実線、斜線、または破線の罫線; を含めるアイテムをカバーするハッチ パターン外部または枠線内にあることができるハンドルのサイズを変更します。 トラッカーは多くの場合で使用される OLE アイテムと共にから派生したオブジェクトは、`COleClientItem`です。 トラッカーの四角形は、アイテムの現在の状態の視覚的な手掛かりを付与します。  
  
 MFC OLE サンプル[OCLIENT](../visual-cpp-samples.md)トラッカーとコンテナー アプリケーションの観点から見た OLE クライアント アイテムを使用して共通のインターフェイスを示しています。 さまざまなスタイルのデモとトラッカー オブジェクトの権限は、MFC の一般的なサンプルを参照してください。[トラッカー](../visual-cpp-samples.md)です。  
  
 OLE アプリケーションでのトラッカーの実装の詳細については、次を参照してください[トラッカー: OLE アプリケーションでのトラッカーの実装。](../mfc/trackers-implementing-trackers-in-your-ole-application.md)  
  
## <a name="see-also"></a>関連項目  
 [OLE](../mfc/ole-in-mfc.md)   
 [COleClientItem クラス](../mfc/reference/coleclientitem-class.md)
