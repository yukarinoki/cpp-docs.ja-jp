---
description: 詳細については、「CObject からクラスを派生させるにはどうすればよいですか?」を参照してください。
title: CObject からクラスを派生するときのオーバーヘッド
ms.date: 11/04/2016
helpviewer_keywords:
- CObject class [MFC], overhead of derived classes [MFC]
ms.assetid: 9b92c98b-b3dd-48a7-9d24-c3b8554edf90
ms.openlocfilehash: 3dcedb7c15c4e02c6dc8cbb7ce0f239838d8067c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97305235"
---
# <a name="what-does-it-cost-me-to-derive-a-class-from-cobject"></a>CObject からクラスを派生するときのオーバーヘッド

[CObject](../mfc/reference/cobject-class.md)クラスからの派生のオーバーヘッドは最小限に抑えられます。 派生クラスは、4つの仮想関数と1つの [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) オブジェクトだけを継承します。

## <a name="see-also"></a>関連項目

[CObject クラス: よく寄せられる質問](../mfc/cobject-class-frequently-asked-questions.md)
