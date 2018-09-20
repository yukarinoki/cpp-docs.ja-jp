---
title: 'ドラッグ アンド ドロップ: ドロップ ソースの実装 |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OLE drag and drop [MFC], initiating drag operations
- drag and drop [MFC], calling DoDragDrop
- OLE drag and drop [MFC], drop source
- OLE drag and drop [MFC], calling DoDragDrop
- drag and drop [MFC], initiating drag operations
- drag and drop [MFC], drop source
ms.assetid: 0ed2fda0-63fa-4b1e-b398-f1f142f40035
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 71f82bbd975f5ff24f3b254abc46e5e6ffa3a34a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46427655"
---
# <a name="drag-and-drop-implementing-a-drop-source"></a>ドラッグ アンド ドロップ: ドロップ ソースの実装

この記事では、データをドラッグ アンド ドロップ操作を提供するアプリケーションを取得する方法について説明します。

ドロップ ソースの基本的な実装では、比較的単純です。 最初の手順では、どのようなイベントは、ドラッグ操作の開始を決定します。 ユーザー インターフェイスのガイドラインとして、選択したデータのドラッグ操作の開始の定義を推奨、 **WM_LBUTTONDOWN**選択したデータ内のポイントで発生するイベントです。 MFC OLE サンプル[OCLIENT](../visual-cpp-samples.md)と[HIERSVR](../visual-cpp-samples.md)これらのガイドラインに従ってください。

場合は、アプリケーションがコンテナーであり、選択したデータは、リンクされた、または型の埋め込みオブジェクト`COleClientItem`、呼び出すその`DoDragDrop`メンバー関数。 それ以外の場合、構築、`COleDataSource`オブジェクトで、選択した場合、それを初期化し、データ ソース オブジェクトの`DoDragDrop`メンバー関数。 使用して、アプリケーションが、サーバーの場合は、`COleServerItem::DoDragDrop`します。 標準的なドラッグ アンド ドロップ動作をカスタマイズする方法については、この記事を参照してください。[ドラッグ アンド ドロップ: カスタマイズ](../mfc/drag-and-drop-customizing.md)します。

場合`DoDragDrop`返します**行った**、ソース ドキュメントからソース データをすぐに削除します。 他の戻り値の`DoDragDrop`ドロップ ソースに影響がありません。

詳細については次を参照してください:

- [ドロップ ターゲットの実装](../mfc/drag-and-drop-implementing-a-drop-target.md)

- [カスタマイズのドラッグ アンド ドロップ](../mfc/drag-and-drop-customizing.md)

- [作成と破棄 OLE データ オブジェクトとデータ ソース](../mfc/data-objects-and-data-sources-creation-and-destruction.md)

- [OLE データ オブジェクトとデータ ソースを操作します。](../mfc/data-objects-and-data-sources-manipulation.md)

## <a name="see-also"></a>関連項目

[ドラッグ アンド ドロップ (OLE)](../mfc/drag-and-drop-ole.md)<br/>
[された](../mfc/reference/coledatasource-class.md#dodragdrop)<br/>
[クラス](../mfc/reference/coleclientitem-class.md#dodragdrop)<br/>
[CView::OnDragLeave](../mfc/reference/cview-class.md#ondragleave)

