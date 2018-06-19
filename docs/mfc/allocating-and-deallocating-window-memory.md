---
title: ウィンドウ メモリの割り当て解除の割り当てと |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- memory allocation, window objects
- memory deallocation
- storage for window objects [MFC]
- memory deallocation, window memory
- window objects [MFC], deallocating memory for
- storage for window objects [MFC], allocating
ms.assetid: 7c962539-8461-4846-b5ca-fe3b15c313dc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a1364b4d29e2ccd2c9563359716eba6880df5436
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33341460"
---
# <a name="allocating-and-deallocating-window-memory"></a>ウィンドウ メモリの割り当てと解放
C++ を使用しないでください**削除**フレーム ウィンドウまたはビューを破棄する演算子です。 代わりを呼び出して、`CWnd`メンバー関数は、`DestroyWindow`です。 フレーム ウィンドウ、そのため、割り当てる必要がある演算子でヒープに**新しい**です。 フレーム ウィンドウのスタック フレームにまたはグローバルを割り当てるときに注意します。 他のウィンドウは、可能な限りのスタック フレームに割り当てる必要があります。  
  
## <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
  
-   [ウィンドウの作成](../mfc/creating-windows.md)  
  
-   [ウィンドウの破棄順序](../mfc/window-destruction-sequence.md)  
  
-   [Cwnd と hwnd の分離](../mfc/detaching-a-cwnd-from-its-hwnd.md)  
  
## <a name="see-also"></a>関連項目  
 [ウィンドウ オブジェクトの破棄](../mfc/destroying-window-objects.md)

