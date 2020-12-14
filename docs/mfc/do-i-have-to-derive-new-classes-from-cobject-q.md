---
description: 詳細については、「CObject から新しいクラスを派生する必要がありますか?」を参照してください。
title: CObject から新しくクラスを派生する必要性
ms.date: 11/04/2016
helpviewer_keywords:
- derived classes [MFC], from CObject
- CObject class [MFC], when to use
ms.assetid: 26021031-feaf-424c-80d1-9547c4409d6a
ms.openlocfilehash: d37570cb62f1ee274e4cea85fc95a9221c95fd8a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97261308"
---
# <a name="do-i-have-to-derive-new-classes-from-cobject"></a>CObject から新しくクラスを派生する必要性

いいえ、そうではありません。

シリアル化や動的な creatability など、提供する機能が必要な場合は、 [CObject](reference/cobject-class.md) からクラスを派生させます。 多くのデータクラスはファイルにシリアル化する必要があるため、多くの場合、それらをから派生させることをお勧めし `CObject` ます。 から派生したクラスの例につい `CObject` ては、 [Scribble サンプル](../overview/visual-cpp-samples.md)を参照してください。

## <a name="see-also"></a>関連項目

[CObject クラス: よく寄せられる質問](cobject-class-frequently-asked-questions.md)
