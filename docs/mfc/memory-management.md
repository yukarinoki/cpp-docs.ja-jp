---
title: メモリ管理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- memory [MFC]
- MFC, memory management
- memory allocation [MFC]
- memory [MFC], managing
- memory allocation [MFC], MFC
ms.assetid: 934ac81b-d630-4232-88e5-ea74f7187987
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 928a954be6a96f5026a98f724a77bebd51be27f0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33345079"
---
# <a name="memory-management"></a>メモリ管理
この記事のグループは、汎用サービスの Microsoft Foundation Class ライブラリ (MFC) メモリ管理に関連するを利用する方法を説明します。 メモリの割り当ては、次の 2 つの主なカテゴリに分類できます: フレーム割り当ておよびヒープ割り当てします。  
  
 2 つの割り当て方法の 1 つの主な違いは、こと、一般的に実際のメモリで作業するフレーム割り当てをブロック自体、ヒープ割り当ては常に表示されますへのポインターのメモリ ブロックへです。 2 つのスキームのもう 1 つの主な違いは、フレーム オブジェクトが自動的に削除されたこと、プログラマが、ヒープのオブジェクトを明示的に削除する必要があります中です。  
  
 非 MFC プログラムで Windows 用のメモリ管理については、次を参照してください。[メモリ管理](http://msdn.microsoft.com/library/windows/desktop/aa366779)Windows SDK に含まれています。  
  
## <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
  
-   [フレーム割り当て](../mfc/memory-management-frame-allocation.md)  
  
-   [ヒープ割り当て](../mfc/memory-management-heap-allocation.md)  
  
-   [配列のメモリの割り当てください。](../mfc/memory-management-examples.md)  
  
-   [ヒープから配列にメモリを解放します。](../mfc/memory-management-examples.md)  
  
-   [データ構造体のメモリの割り当てください。](../mfc/memory-management-examples.md)  
  
-   [オブジェクトのメモリの割り当てください。](../mfc/memory-management-examples.md)  
  
-   [サイズ変更可能なメモリ ブロック](../mfc/memory-management-resizable-memory-blocks.md)  
  
## <a name="see-also"></a>関連項目  
 [概念](../mfc/mfc-concepts.md)   
 [MFC の一般的なトピック](../mfc/general-mfc-topics.md)

