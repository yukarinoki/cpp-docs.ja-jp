---
title: ドキュメント/ビュー アーキテクチャの利点 |Microsoft ドキュメント
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
ms.openlocfilehash: 45065b38128a2e3239b1fd10ded490fdcbcb3eac
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="advantages-of-the-documentview-architecture"></a>ドキュメント/ビュー アーキテクチャの利点
MFC ドキュメント/ビュー アーキテクチャを使用する主な利点は、アーキテクチャが同一のドキュメントの複数のビューを特にもサポートしています。 (複数のビューの必要はありません、ドキュメント/ビューの少量のオーバーヘッドは、アプリケーションで過剰な場合を回避できますアーキテクチャ。 [ドキュメント/ビュー アーキテクチャの代替手段](../mfc/alternatives-to-the-document-view-architecture.md))。  
  
 たとえば、アプリケーションにより、ユーザーがスプレッドシート形式またはグラフ形式で数値データを表示します。 同時に両方の生データ、スプレッドシート形式と、データから生成されるグラフを表示する場合があります。 1 つのウィンドウ内の分割ペインまたは個別のフレーム ウィンドウでは、それぞれのビューを表示します。 今すぐスプレッドシートと参照データをユーザーが編集できると仮定しますの変更は即座にグラフに反映します。  
  
 MFC では、スプレッドシートのビューとグラフ ビューはに基づいて CView から派生した異なるクラスです。 両方のビューは、1 つのドキュメント オブジェクトに関連付けられたになります。 ドキュメントは、データを格納 (または、データベースから取得)。 両方のビューは、ドキュメントにアクセスし、そこから取得したデータを表示します。  
  
 ユーザーが、オブジェクトの呼び出しを表示するビューのいずれかを更新するときに`CDocument::UpdateAllViews`です。 その関数はすべてのドキュメントのビューに通知し、各ビューは、ドキュメントの最新のデータを使用してそれ自体を更新します。 1 回だけ呼び出す`UpdateAllViews`さまざまなビューを同期します。  
  
 このシナリオが困難になりますデータの分離を使用しないコードから見ると、ビューには、自分でデータが格納されている場合に特にです。 ドキュメント/ビューでは簡単です。 フレームワークはほとんどの連携作業します。  
  
## <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
  
-   [ドキュメント/ビューに代わる方法](../mfc/alternatives-to-the-document-view-architecture.md)  
  
-   [CDocument](../mfc/reference/cdocument-class.md)  
  
-   [CView](../mfc/reference/cview-class.md)  
  
-   [CDocument::UpdateAllViews](../mfc/reference/cdocument-class.md#updateallviews)  
  
-   [CView::GetDocument](../mfc/reference/cview-class.md#getdocument)  
  
## <a name="see-also"></a>関連項目  
 [ドキュメント/ビュー アーキテクチャ](../mfc/document-view-architecture.md)

