---
title: 'TN032: MFC 例外処理機構 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.mfc.exceptions
dev_langs:
- C++
helpviewer_keywords:
- TN032
- MFC, exceptions
- CException class [MFC], using
ms.assetid: 0271f0aa-82cb-47a2-b7ea-e88126fc7e43
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5256f787534ab408920f7154122ae0c5934019c1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="tn032-mfc-exception-mechanism"></a>テクニカル ノート 32: MFC 例外処理機構
Visual C の以前のバージョンが、標準の C++ 例外機構をサポートしていませんし、MFC に提供されるマクロ**TRY または CATCH/THROW**代わりに使用していた。 このバージョンの Visual C には、C++ の例外を完全にサポートしています。 このノートでは、従来のマクロの高度な実装の詳細の一部について説明スタック ベースのオブジェクトを自動的にクリーンアップする方法などです。 C++ 例外のスタック アンワインド既定ではサポートされているために、このテクニカル ノートは必要ではありません。  
  
 参照してください[例外: MFC マクロと C++ 例外](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md)MFC マクロと C++ のキーワードの違いについての詳細。  
  
## <a name="see-also"></a>関連項目  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)

