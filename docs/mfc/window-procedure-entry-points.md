---
title: ウィンドウ プロシージャ エントリ ポイント |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- state management, window procedures
- MFC, managing state data
- window procedure entry points
- entry points, window procedures
ms.assetid: a6b46a7f-6e42-45f2-9ae6-82e19fc57148
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1095061cce8ff8f189984aca99a06eb741a46e83
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33382074"
---
# <a name="window-procedure-entry-points"></a>ウィンドウ プロシージャのエントリ ポイント
MFC のウィンドウ プロシージャ、特殊なウィンドウ プロシージャの実装とモジュールの静的リンクを保護します。 リンケージは、MFC とリンクすると、モジュールと自動的に発生します。 このウィンドウ プロシージャを使用して、`AFX_MANAGE_STATE`マクロを呼び出し、有効なモジュールの状態を正しく設定**プロシージャ**、順番にデリゲートを、`WindowProc`メンバー関数は、適切な`CWnd`-派生。オブジェクト。  
  
## <a name="see-also"></a>関連項目  
 [MFC モジュールの状態データの管理](../mfc/managing-the-state-data-of-mfc-modules.md)

