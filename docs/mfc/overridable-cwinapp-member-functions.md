---
title: オーバーライド可能な CWinApp のメンバー関数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CWinApp
dev_langs:
- C++
helpviewer_keywords:
- overriding [MFC], overridable functions in CWinApp
- application class [MFC]
- CWinApp class [MFC], overridables
ms.assetid: 07183d5e-734b-45d9-a8b6-9dde4adac0b4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ced9d7d5f7f49df50e028a299f83ddebdc9fc2d1
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46395135"
---
# <a name="overridable-cwinapp-member-functions"></a>オーバーライド可能な CWinApp のメンバー関数

[CWinApp](../mfc/reference/cwinapp-class.md)いくつかのキーのオーバーライド可能なメンバー関数を提供します (`CWinApp`クラスからこれらのメンバーをオーバーライド[CWinThread](../mfc/reference/cwinthread-class.md)、元の`CWinApp`派生)。

- [Initinstance 関数](../mfc/initinstance-member-function.md)

- [実行](../mfc/run-member-function.md)

- [ExitInstance](../mfc/exitinstance-member-function.md)

- [OnIdle](../mfc/onidle-member-function.md)

唯一`CWinApp`メンバー関数をオーバーライドする必要がありますが`InitInstance`します。

## <a name="see-also"></a>関連項目

[CWinApp: アプリケーション クラス](../mfc/cwinapp-the-application-class.md)
