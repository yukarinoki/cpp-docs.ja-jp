---
title: SDI と MDI |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- frame windows [MFC], SDI applications
- frame windows [MFC], MDI applications
- MFC, windows
- single document interface (SDI) [MFC], applications
- MDI [MFC], vs. SDI
ms.assetid: bb7239d9-4759-4f63-bfff-44a04b48c067
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: db63efe8d7e2622610bb56f5e6885b72b705093b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33385805"
---
# <a name="sdi-and-mdi"></a>SDI と MDI
MFC では、シングル ドキュメント インターフェイス (SDI) とマルチ ドキュメント インターフェイス (MDI) アプリケーションの両方を簡単に処理します。  
  
 SDI アプリケーションは、一度に 1 つだけ開いているドキュメント フレーム ウィンドウを許可します。 MDI アプリケーションには、複数のドキュメントのフレーム ウィンドウをアプリケーションの同じインスタンスで開くことができるようにします。 MDI アプリケーションでは、個別のドキュメントに含まれる各ウィンドウ内、複数の MDI フレーム ウィンドウ自体は、子ウィンドウを開くがします。 一部のアプリケーションで、グラフ ウィンドウやスプレッドシート ウィンドウなどのさまざまな種類の子ウィンドウができます。 その場合は、さまざまな種類の MDI 子ウィンドウがアクティブ化すると、メニュー バーは変更できます。  
  
> [!NOTE]
>  Windows 95 以降では、アプリケーションは通常、SDI、オペレーティング システムは、「ドキュメント中心」ビューを採用しているためです。  
  
 詳細については、次を参照してください。[ドキュメント、ビュー、およびフレームワーク](../mfc/documents-views-and-the-framework.md)です。  
  
## <a name="see-also"></a>関連項目  
 [クラスを使用した Windows アプリケーションの作成](../mfc/using-the-classes-to-write-applications-for-windows.md)
