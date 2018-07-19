---
title: クリッピングを行わないデバイス コンテキストを使用して |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], unclipped device context
ms.assetid: 9c020063-73da-4803-bf7b-2e1fd950c9ed
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6d4fcfbe8e8e7eb174f85ced03bec822b4968bde
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36954336"
---
# <a name="using-an-unclipped-device-context"></a>クリッピングを行わないデバイス コンテキストの使用
コントロールは、そのクライアントの四角形の外側は描画されませんがわかっている場合への呼び出しを無効にして小さくても、検知できる程度の速度の向上を実感できます`IntersectClipRect`によってになる`COleControl`です。 これを行うには、削除、 *clipPaintDC*によって返されるフラグのセットからフラグ[オン](../mfc/reference/colecontrol-class.md#getcontrolflags)です。 例えば:  
  
 [!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/cpp/using-an-unclipped-device-context_1.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#14](../mfc/codesnippet/cpp/using-an-unclipped-device-context_2.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/cpp/using-an-unclipped-device-context_3.cpp)]  
  
 選択した場合、このフラグを削除するコードが自動的に生成、**クリッピングを行わないデバイス コンテキスト** オプションを選択、[コントロール設定](../mfc/reference/control-settings-mfc-activex-control-wizard.md)ページ、MFC ActiveX コントロール ウィザードを使用して、コントロールを作成するときにします。  
  
 ウィンドウなしのアクティベーションを使用している場合は、この最適化に影響はありません。  
  
## <a name="see-also"></a>関連項目  
 [MFC ActiveX コントロール: 最適化](../mfc/mfc-activex-controls-optimization.md)

