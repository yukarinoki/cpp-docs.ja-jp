---
title: 印刷および印刷プレビュー |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- printing [MFC]
- previewing printing
- printing [MFC]
- print preview
- printing [MFC], print preview
ms.assetid: d15059cd-32de-4450-95f7-e73aece238f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8a26bac196dbddc6c05df5850225d05f432bc566
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="printing-and-print-preview"></a>印刷および印刷プレビュー
MFC クラスを使用して、プログラムのドキュメントの印刷と印刷プレビューをサポートしています[CView](../mfc/reference/cview-class.md)です。 基本的な印刷と印刷プレビューでは、単に上書きビュー クラスの[OnDraw](../mfc/reference/cview-class.md#ondraw)メンバー関数を行うことができます。 その関数が実際のプリンターのプリンター デバイス コンテキストを画面上の表示を描画できるまたは画面にプリンターをシミュレートするデバイス コンテキストにします。  
  
 マルチページ ドキュメントの印刷とプレビュー、およびそれらにヘッダーとページ フッターを追加する、印刷されたドキュメントを改ページ調整を管理するためのコードを追加することもできます。  
  
 この一連のトピックでは、印刷の Microsoft Foundation Class ライブラリ (MFC) を実装する方法と、フレームワークに既に組み込まれている印刷のアーキテクチャを活用する方法について説明します。 アーティクルは、方法 MFC をサポートします。 印刷プレビュー機能の簡単な実装を使用し、その機能を変更する方法も説明します。  
  
## <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
  
-   [印刷](../mfc/printing.md)  
  
-   [印刷プレビューのアーキテクチャ](../mfc/print-preview-architecture.md)  
  
-   [サンプル](../visual-cpp-samples.md)  
  
## <a name="see-also"></a>関連項目  
 [ユーザー インターフェイス要素](../mfc/user-interface-elements-mfc.md)
