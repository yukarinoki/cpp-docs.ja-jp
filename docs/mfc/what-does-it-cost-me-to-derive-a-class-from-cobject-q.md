---
title: CObject からクラスを派生するときのオーバーヘッド
ms.date: 11/04/2016
helpviewer_keywords:
- CObject class [MFC], overhead of derived classes [MFC]
ms.assetid: 9b92c98b-b3dd-48a7-9d24-c3b8554edf90
ms.openlocfilehash: 8f83bf9ee522487761aaa865a8315a174a47302d
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79446045"
---
# <a name="what-does-it-cost-me-to-derive-a-class-from-cobject"></a>CObject からクラスを派生するときのオーバーヘッド

[CObject](../mfc/reference/cobject-class.md)クラスからの派生のオーバーヘッドは最小限に抑えられます。 派生クラスは、4つの仮想関数と1つの[CRuntimeClass](../mfc/reference/cruntimeclass-structure.md)オブジェクトだけを継承します。

## <a name="see-also"></a>参照

[CObject クラス: Q & A 集](../mfc/cobject-class-frequently-asked-questions.md)
