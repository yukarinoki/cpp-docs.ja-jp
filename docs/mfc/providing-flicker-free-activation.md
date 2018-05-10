---
title: ちらつきなしのアクティベーションの提供 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], flicker-free
- flicker, MFC ActiveX controls
- activation [MFC], flicker-free
ms.assetid: bcb24b77-31d8-44a0-8c58-2ea6213b4c43
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d9d9c0108ce4afd2e65678280248488181ad34f2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="providing-flicker-free-activation"></a>ちらつきなしのアクティベーションの提供
場合は、コントロールは、非アクティブとアクティブな状態で同一の描画 (および、ウィンドウなしのアクティベーションを使用しません)、描画操作と、非アクティブの間の移行を行うときに通常発生するちらつきを除去することができます。アクティブな状態です。 これを行うには、含める、 **noFlickerActivate**によって返されるフラグのセットでフラグ[オン](../mfc/reference/colecontrol-class.md#getcontrolflags)です。 例えば:  
  
 [!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/cpp/providing-flicker-free-activation_1.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#13](../mfc/codesnippet/cpp/providing-flicker-free-activation_2.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/cpp/providing-flicker-free-activation_3.cpp)]  
  
 選択した場合にこのフラグを含めるコードが自動的に生成、**ちらつきなしのアクティベーション** オプションを選択、[制御設定](../mfc/reference/control-settings-mfc-activex-control-wizard.md)MFC ActiveX コントロール ウィザードを使用して、コントロールを作成するときのページです。  
  
 ウィンドウなしのアクティベーションを使用している場合は、この最適化に影響はありません。  
  
## <a name="see-also"></a>関連項目  
 [MFC ActiveX コントロール: 最適化](../mfc/mfc-activex-controls-optimization.md)

