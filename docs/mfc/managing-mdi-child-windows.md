---
title: MDI 子ウィンドウの管理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- MDICLIENT
dev_langs:
- C++
helpviewer_keywords:
- MDI [MFC], child windows
- child windows [MFC], and MDICLIENT window
- MDICLIENT window [MFC]
- windows [MFC], MDI
- frame windows [MFC], MDI child windows
- child windows [MFC]
- MDI [MFC], frame windows
ms.assetid: 1828d96e-a561-48ae-a661-ba9701de6bee
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: edcdcbad2b7b3e70988579786c1c8cf28f734a48
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33344936"
---
# <a name="managing-mdi-child-windows"></a>MDI 子ウィンドウの管理
MDI メイン フレーム ウィンドウ (アプリケーションごとに 1 つ) と呼ばれる特殊な子ウィンドウが含まれて、 **MDICLIENT**ウィンドウです。 **MDICLIENT**ウィンドウがメイン フレーム ウィンドウのクライアント領域を管理し、それ自体の子ウィンドウを持つ: から派生して、ドキュメント ウィンドウ`CMDIChildWnd`します。 ドキュメント ウィンドウは、フレーム ウィンドウ自体 (MDI 子ウィンドウ) であるため、独自の子こともできます。 これらすべての場合は、親ウィンドウは、その子ウィンドウを管理し、いくつかのコマンドを転送します。  
  
 MDI フレーム ウィンドウでは、フレーム ウィンドウ、管理、 **MDICLIENT**ウィンドウ、コントロール バーと共に移動します。 **MDICLIENT**ウィンドウで、さらに、すべての MDI 子フレーム ウィンドウを管理します。 次の図は、MDI フレーム ウィンドウ、間の関係を示します、 **MDICLIENT**ウィンドウ、およびその子ドキュメント フレーム ウィンドウです。  
  
 ![MDI フレーム ウィンドウに子ウィンドウ](../mfc/media/vc37gb1.gif "vc37gb1")  
MDI フレーム ウィンドウと子ウィンドウ  
  
 1 つを使用する必要がある場合、MDI フレーム ウィンドウは、現在の MDI 子ウィンドウと共にでも動作します。 MDI フレーム ウィンドウは、自分で処理を試行する前に、MDI 子ウィンドウにコマンド メッセージを代行させます。  
  
## <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
  
-   [ドキュメント フレーム ウィンドウの作成](../mfc/creating-document-frame-windows.md)  
  
-   [フレーム ウィンドウ スタイル](../mfc/frame-window-styles-cpp.md)  
  
## <a name="see-also"></a>関連項目  
 [フレーム ウィンドウの使用](../mfc/using-frame-windows.md)

