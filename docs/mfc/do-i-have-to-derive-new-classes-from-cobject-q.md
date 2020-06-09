---
title: CObject から新しくクラスを派生する必要性
ms.date: 11/04/2016
helpviewer_keywords:
- derived classes [MFC], from CObject
- CObject class [MFC], when to use
ms.assetid: 26021031-feaf-424c-80d1-9547c4409d6a
ms.openlocfilehash: 371ede0f0921182c066b4cb224e66b18eb6f1208
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84616739"
---
# <a name="do-i-have-to-derive-new-classes-from-cobject"></a>CObject から新しくクラスを派生する必要性

いいえ、そうではありません。

シリアル化や動的な creatability など、提供する機能が必要な場合は、 [CObject](reference/cobject-class.md)からクラスを派生させます。 多くのデータクラスはファイルにシリアル化する必要があるため、多くの場合、それらをから派生させることをお勧めし `CObject` ます。 から派生したクラスの例につい `CObject` ては、 [Scribble サンプル](../overview/visual-cpp-samples.md)を参照してください。

## <a name="see-also"></a>関連項目

[CObject クラス: Q & A 集](cobject-class-frequently-asked-questions.md)
