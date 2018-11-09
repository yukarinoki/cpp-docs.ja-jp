---
title: Improper Access to a Union (共用体への不適切なアクセス)
ms.date: 11/04/2016
ms.assetid: b273d984-62a8-4003-9a87-bf0149d3f2dd
ms.openlocfilehash: a08f2c9aa76d0d2f2370dd45f9eb9ace77ceb76c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50642957"
---
# <a name="improper-access-to-a-union"></a>Improper Access to a Union (共用体への不適切なアクセス)

**ANSI 3.3.2.3** 共用体オブジェクトのメンバーが異なる型のメンバーを使用してアクセスされます

2 の型の 1 つの共用体が宣言され、一方の値が格納されていても、もう一方の型で共用体にアクセスできる場合、結果は信頼できません。

たとえば、**float** と `int` の共用体が宣言されます。 **float** 値が保存されますが、プログラムは `int` として値にアクセスします。 このような場合、値は **float** 値の内部ストレージによって異なります。 整数値は信頼できません。

## <a name="see-also"></a>参照

[構造体、共用体、列挙体、ビット フィールド](../c-language/structures-unions-enumerations-and-bit-fields.md)