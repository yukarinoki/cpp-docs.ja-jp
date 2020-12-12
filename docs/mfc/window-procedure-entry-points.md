---
description: '詳細情報: ウィンドウプロシージャのエントリポイント'
title: ウィンドウ プロシージャのエントリ ポイント
ms.date: 11/04/2016
helpviewer_keywords:
- state management, window procedures
- MFC, managing state data
- window procedure entry points
- entry points, window procedures
ms.assetid: a6b46a7f-6e42-45f2-9ae6-82e19fc57148
ms.openlocfilehash: 2c2e5dc5d37a2e6f187e694d39205c4cd95b3810
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97214482"
---
# <a name="window-procedure-entry-points"></a>ウィンドウ プロシージャのエントリ ポイント

MFC ウィンドウプロシージャを保護するには、モジュールの静的リンクを特別なウィンドウプロシージャの実装と共に使用します。 リンクは、モジュールが MFC とリンクされている場合に自動的に発生します。 このウィンドウプロシージャは、AFX_MANAGE_STATE マクロを使用して、有効なモジュール状態を適切に設定し、 `AfxWndProc` を呼び出します。これは、適切に派生した `WindowProc` オブジェクトのメンバー関数に委任さ `CWnd` れます。

## <a name="see-also"></a>関連項目

[MFC モジュールの状態データの管理](../mfc/managing-the-state-data-of-mfc-modules.md)
