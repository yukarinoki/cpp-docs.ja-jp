---
title: フレーム ウィンドウ クラス (アーキテクチャ) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.frame
dev_langs:
- C++
helpviewer_keywords:
- frame window classes [MFC], document/view architecture
ms.assetid: 5da01fb4-f531-46cc-914f-e422e4f07f5d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b7de72b77be9be90ca876cfef943500a0312d183
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="frame-window-classes-architecture"></a>フレーム ウィンドウ クラス (アーキテクチャ)
ドキュメント/ビュー アーキテクチャでは、フレーム ウィンドウは、ビュー ウィンドウを持つウィンドウです。 サポート コントロール バーが割り当てられています。  
  
 マルチ ドキュメント インターフェイス (MDI) アプリケーションでは、メイン ウィンドウはから派生`CMDIFrameWnd`です。 直接ドキュメントのフレームが含まれる、`CMDIChildWnd`オブジェクト。 `CMDIChildWnd`オブジェクトでは、ドキュメントのビューに含めることです。  
  
 派生したメイン ウィンドウで、シングル ドキュメント インターフェイス (SDI) アプリケーションで、 `CFrameWnd`、現在のドキュメントのビューが含まれています。  
  
 [CFrameWnd](../mfc/reference/cframewnd-class.md)  
 SDI アプリケーションのメイン フレーム ウィンドウの基本クラス。 またの基本クラスの他のすべてのフレーム ウィンドウ クラス。  
  
 [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)  
 MDI アプリケーションのメイン フレーム ウィンドウの基本クラス。  
  
 [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)  
 MDI アプリケーションのドキュメント フレーム ウィンドウの基底クラス。  
  
 [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md)  
 サーバー ドキュメントを一括で編集するときに、ビューのフレーム ウィンドウを提供します。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../mfc/class-library-overview.md)

