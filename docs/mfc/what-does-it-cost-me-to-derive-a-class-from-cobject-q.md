---
title: CObject からクラスを派生するときのオーバーヘッド
ms.date: 11/04/2016
f1_keywords:
- CObject
helpviewer_keywords:
- CObject class [MFC], overhead of derived classes [MFC]
ms.assetid: 9b92c98b-b3dd-48a7-9d24-c3b8554edf90
ms.openlocfilehash: 521b6a32e3e5b34b4da9dab3117d55a728bd8e88
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50500452"
---
# <a name="what-does-it-cost-me-to-derive-a-class-from-cobject"></a>CObject からクラスを派生するときのオーバーヘッド

クラスから派生するオーバーヘッド[CObject](../mfc/reference/cobject-class.md)は最小限です。 派生クラスは、4 つだけの仮想関数と、1 つを継承[CRuntimeClass](../mfc/reference/cruntimeclass-structure.md)オブジェクト。

## <a name="see-also"></a>関連項目

[CObject クラス: Q & A 集](../mfc/cobject-class-frequently-asked-questions.md)
