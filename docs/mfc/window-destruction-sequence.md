---
title: ウィンドウの破棄順序 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- destruction, windows
- destroying windows
- sequence [MFC], window destruction
- CWnd objects [MFC], destruction sequence
- sequence [MFC]
- windows [MFC], destroying
ms.assetid: 2d819196-6240-415f-a308-db43745e616c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3b1c67d5a6391bbfc91bbce0d06a6bb58350e9a0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33382610"
---
# <a name="window-destruction-sequence"></a>ウィンドウの破棄順序
ユーザーがウィンドウの既定値であるフレーム ウィンドウを閉じるときに、MFC フレームワーク[OnClose](../mfc/reference/cwnd-class.md#onclose)ハンドラーの呼び出し[DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow)です。 Windows のウィンドウが破棄されるときに呼び出されます最後のメンバー関数は、 [OnNcDestroy](../mfc/reference/cwnd-class.md#onncdestroy)、呼び出しを行って、クリーンアップ処理によって、[既定](../mfc/reference/cwnd-class.md#default)メンバーが、Windows のクリーンアップを実行する関数を呼び出す最後に、仮想メンバー関数[PostNcDestroy](../mfc/reference/cwnd-class.md#postncdestroy)です。 [CFrameWnd](../mfc/reference/cframewnd-class.md)の実装`PostNcDestroy`C++ ウィンドウ オブジェクトを削除します。  
  
## <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
  
-   [割り当てとウィンドウのメモリを解放します。](../mfc/allocating-and-deallocating-window-memory.md)  
  
-   [Cwnd と hwnd の分離](../mfc/detaching-a-cwnd-from-its-hwnd.md)  
  
## <a name="see-also"></a>関連項目  
 [ウィンドウ オブジェクトの破棄](../mfc/destroying-window-objects.md)

