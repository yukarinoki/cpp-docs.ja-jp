---
title: オーバーライド可能な CWinApp のメンバー関数
ms.date: 11/04/2016
helpviewer_keywords:
- overriding [MFC], overridable functions in CWinApp
- application class [MFC]
- CWinApp class [MFC], overridables
ms.assetid: 07183d5e-734b-45d9-a8b6-9dde4adac0b4
ms.openlocfilehash: 28ba243bd755e25db5f2cb03d08013f082fbc918
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447266"
---
# <a name="overridable-cwinapp-member-functions"></a>オーバーライド可能な CWinApp のメンバー関数

[CWinApp](../mfc/reference/cwinapp-class.md)には、いくつかのキーオーバーライド可能なメンバー関数が用意されています (`CWinApp` は、これらのメンバーを `CWinApp` 派生元のクラス[CWinThread](../mfc/reference/cwinthread-class.md)からオーバーライドします)。

- [InitInstance](../mfc/initinstance-member-function.md)

- [[実行]](../mfc/run-member-function.md)

- [ExitInstance](../mfc/exitinstance-member-function.md)

- [OnIdle](../mfc/onidle-member-function.md)

オーバーライドする必要がある `CWinApp` メンバー関数は `InitInstance`だけです。

## <a name="see-also"></a>参照

[CWinApp: アプリケーション クラス](../mfc/cwinapp-the-application-class.md)
