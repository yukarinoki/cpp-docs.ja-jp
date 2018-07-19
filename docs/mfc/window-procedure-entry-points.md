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
ms.openlocfilehash: 315526a8f95a1d62ac89f3a76fab492c9b136715
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36956383"
---
# <a name="window-procedure-entry-points"></a>ウィンドウ プロシージャのエントリ ポイント
MFC のウィンドウ プロシージャ、特殊なウィンドウ プロシージャの実装とモジュールの静的リンクを保護します。 リンケージは、MFC とリンクすると、モジュールと自動的に発生します。 このウィンドウの手順では、AFX_MANAGE_STATE マクロを使用して、有効なモジュールの状態が正しく設定し、呼び出す`AfxWndProc`、順番にデリゲートを`WindowProc`メンバー関数は、適切な`CWnd`-派生オブジェクト。  
  
## <a name="see-also"></a>関連項目  
 [MFC モジュールの状態データの管理](../mfc/managing-the-state-data-of-mfc-modules.md)

