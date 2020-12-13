---
description: 詳細については、「オーバーライド可能な CWinApp メンバー関数」を参照してください。
title: オーバーライド可能な CWinApp のメンバー関数
ms.date: 11/04/2016
helpviewer_keywords:
- overriding [MFC], overridable functions in CWinApp
- application class [MFC]
- CWinApp class [MFC], overridables
ms.assetid: 07183d5e-734b-45d9-a8b6-9dde4adac0b4
ms.openlocfilehash: 3958ad0edc1fbdb77e1f6ce3252fd03d7595344a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330110"
---
# <a name="overridable-cwinapp-member-functions"></a>オーバーライド可能な CWinApp のメンバー関数

[CWinApp](reference/cwinapp-class.md) は、いくつかのキーオーバーライド可能なメンバー関数 `CWinApp` を提供します (これらのメンバーは、派生元のクラス [CWinThread](reference/cwinthread-class.md)からオーバーライドし `CWinApp` ます)。

- [InitInstance](initinstance-member-function.md)

- [[実行]](run-member-function.md)

- [ExitInstance](exitinstance-member-function.md)

- [OnIdle](onidle-member-function.md)

`CWinApp`オーバーライドする必要があるメンバー関数はだけです `InitInstance` 。

## <a name="see-also"></a>関連項目

[CWinApp: Application クラス](cwinapp-the-application-class.md)
