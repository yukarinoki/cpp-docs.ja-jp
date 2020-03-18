---
title: CObject から新しくクラスを派生する必要性
ms.date: 11/04/2016
helpviewer_keywords:
- derived classes [MFC], from CObject
- CObject class [MFC], when to use
ms.assetid: 26021031-feaf-424c-80d1-9547c4409d6a
ms.openlocfilehash: d38e589f371fc56f5566c56de7b19c366065a503
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79446931"
---
# <a name="do-i-have-to-derive-new-classes-from-cobject"></a>CObject から新しくクラスを派生する必要性

いいえ、そうではありません。

シリアル化や動的な creatability など、提供する機能が必要な場合は、 [CObject](../mfc/reference/cobject-class.md)からクラスを派生させます。 多くのデータクラスはファイルにシリアル化する必要があるため、多くの場合、`CObject`から派生させることをお勧めします。 `CObject`から派生したクラスの例については、 [Scribble サンプル](../overview/visual-cpp-samples.md)を参照してください。

## <a name="see-also"></a>参照

[CObject クラス: Q & A 集](../mfc/cobject-class-frequently-asked-questions.md)
