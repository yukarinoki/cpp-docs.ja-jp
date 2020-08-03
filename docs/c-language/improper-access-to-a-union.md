---
title: Improper Access to a Union (共用体への不適切なアクセス)
ms.date: 11/04/2016
ms.assetid: b273d984-62a8-4003-9a87-bf0149d3f2dd
ms.openlocfilehash: 5a804ed80c8f1ac2f5dd9a24f12c67e96e199b6b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227830"
---
# <a name="improper-access-to-a-union"></a>Improper Access to a Union (共用体への不適切なアクセス)

**ANSI 3.3.2.3** 共用体オブジェクトのメンバーが異なる型のメンバーを使用してアクセスされます

2 の型の 1 つの共用体が宣言され、一方の値が格納されていても、もう一方の型で共用体にアクセスできる場合、結果は信頼できません。

たとえば、 **`float`** と **`int`** の共用体が宣言されます。 **`float`** 値が保存されますが、プログラムでは後で **`int`** として値にアクセスします。 このような場合、値は **`float`** 値の内部ストレージによって異なります。 整数値は信頼できません。

## <a name="see-also"></a>関連項目

[構造体、共用体、列挙体、ビット フィールド](../c-language/structures-unions-enumerations-and-bit-fields.md)
