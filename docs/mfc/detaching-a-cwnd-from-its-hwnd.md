---
title: Cwnd と hwnd の分離 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CWnd
dev_langs:
- C++
helpviewer_keywords:
- HWND, detaching CWnd from
- removing HWNDs from CWnds
- CWnd objects [MFC], detaching from HWND
- detaching CWnds from HWNDs
- Detach method (CWnd class)
ms.assetid: 6efadf84-0517-4a3f-acfd-216e088f19c6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a776b4ff4799750c89a322379a063030db748eec
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="detaching-a-cwnd-from-its-hwnd"></a>CWnd と HWND の分離
オブジェクトを回避する必要がある場合`HWND`リレーションシップを MFC には、別`CWnd`メンバー関数は、[デタッチ](../mfc/reference/cwnd-class.md#detach)Windows のウィンドウから C++ ウィンドウ オブジェクトを切断します。 これは、デストラクターが、オブジェクトが破棄されるときに、Windows のウィンドウを破棄することを防ぎます。  
  
## <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
  
-   [ウィンドウの作成](../mfc/creating-windows.md)  
  
-   [ウィンドウの破棄順序](../mfc/window-destruction-sequence.md)  
  
-   [割り当てとウィンドウのメモリを解放します。](../mfc/allocating-and-deallocating-window-memory.md)  
  
## <a name="see-also"></a>関連項目  
 [Window オブジェクト](../mfc/window-objects.md)

