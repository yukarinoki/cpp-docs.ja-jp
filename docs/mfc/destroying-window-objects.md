---
title: ウィンドウ オブジェクトの破棄 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- frame windows [MFC], destroying
- window objects [MFC], deleting
- window objects [MFC], destroying
- window objects [MFC], removing
ms.assetid: 3241fea0-c614-4a25-957d-20f21bd5fd0c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3aacb01d945429bc36543f78e3635c39ef58223d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33343377"
---
# <a name="destroying-window-objects"></a>ウィンドウ オブジェクトの破棄
注意が必要に子 windows のウィンドウで、ユーザーが終了すると、C++ ウィンドウ オブジェクトを破棄します。 これらのオブジェクトが破棄されない場合、アプリケーションはメモリを復元できません。 さいわい、フレームワークは、フレーム ウィンドウ、ビュー、およびダイアログ ボックスの作成とウィンドウの破棄を管理します。 その他のウィンドウを作成する場合を破棄します。  
  
## <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
  
-   [ウィンドウの破棄順序](../mfc/window-destruction-sequence.md)  
  
-   [割り当てとウィンドウのメモリを解放します。](../mfc/allocating-and-deallocating-window-memory.md)  
  
-   [Cwnd と hwnd の分離](../mfc/detaching-a-cwnd-from-its-hwnd.md)  
  
-   [一般的なウィンドウ作成順序](../mfc/general-window-creation-sequence.md)  
  
-   [フレーム ウィンドウの破棄](../mfc/destroying-frame-windows.md)  
  
## <a name="see-also"></a>関連項目  
 [Window オブジェクト](../mfc/window-objects.md)

