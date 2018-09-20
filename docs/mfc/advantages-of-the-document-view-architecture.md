---
title: ドキュメント/ビュー アーキテクチャの利点 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- views [MFC], advantages
- document/view architecture [MFC], advantages of
ms.assetid: 0bc27071-e120-4889-939c-ce1e61fb9cb3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 213fc108b11d6056df6696f92658e74a736c4a16
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46392841"
---
# <a name="advantages-of-the-documentview-architecture"></a>ドキュメント/ビュー アーキテクチャの利点

MFC ドキュメント/ビュー アーキテクチャを使用する主な利点は、アーキテクチャが同じドキュメントの複数のビューを特にもサポートしています。 (複数のビューが不要なドキュメント/ビューの少量のオーバーヘッドは、アプリケーションで過剰な場合は、回避できますアーキテクチャ。 [ドキュメント/ビュー アーキテクチャの代替手段](../mfc/alternatives-to-the-document-view-architecture.md))。

たとえば、アプリケーションにより、ユーザーがスプレッドシート形式またはグラフ形式で数値データを表示します。 ユーザーは、同時に両方の生データのスプレッドシート形式とデータに起因するグラフを表示する場合があります。 個別のフレーム ウィンドウで、または 1 つのウィンドウ内の分割ペインでは、それぞれのビューを表示します。 ようになりましたユーザーが編集できるを参照してください、スプレッドシート内のデータと変更は瞬時にグラフに反映します。

Mfc では、スプレッドシートのビューとグラフ ビューが基に CView から派生した異なるクラスです。 両方のビューは 1 つのドキュメント オブジェクトに関連付けられたになります。 ドキュメントは、データを保存 (または、データベースから取得)。 両方のビューでは、ドキュメントにアクセスし、そこから取得したデータを表示します。

ユーザーがオブジェクトの呼び出しを表示すると、ビューのいずれかを更新するときに`CDocument::UpdateAllViews`します。 その関数では、すべてのドキュメントのビューに通知し、それぞれのビューは、ドキュメントから最新のデータを使用して自身を更新します。 1 回呼び出す`UpdateAllViews`さまざまなビューを同期します。

このシナリオは、困難なデータの分離を使用しないコードをビューからビューには、自分でデータが格納されている場合に特にがあります。 ドキュメント/ビューでは簡単です。 フレームワークの調整作業のほとんどを動作します。

## <a name="what-do-you-want-to-know-more-about"></a>方法については、するして操作を行います

- [ドキュメント/ビューの代替手段](../mfc/alternatives-to-the-document-view-architecture.md)

- [CDocument](../mfc/reference/cdocument-class.md)

- [CView](../mfc/reference/cview-class.md)

- [CDocument::UpdateAllViews](../mfc/reference/cdocument-class.md#updateallviews)

- [CView::GetDocument](../mfc/reference/cview-class.md#getdocument)

## <a name="see-also"></a>関連項目

[ドキュメント/ビュー アーキテクチャ](../mfc/document-view-architecture.md)

