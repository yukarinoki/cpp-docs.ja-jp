---
description: '詳細情報: 代入変換'
title: 代入変換
ms.date: 11/04/2016
helpviewer_keywords:
- conversions, assignment
- assignment conversions
ms.assetid: 4ee01013-de32-4aae-b12e-0051d0cde927
ms.openlocfilehash: b9889214f160c981c57fc3174b542396d71458bd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97279963"
---
# <a name="assignment-conversions"></a>代入変換

代入演算では、代入値の型が、代入を受け取る変数の型に変換されます。 C では、変換によって情報が失われる場合でも、整数型と浮動小数点型の間で代入による変換を実行できます。 使用される変換メソッドは、「[通常の算術変換](../c-language/usual-arithmetic-conversions.md)」および以下の各セクションで説明されているように、代入に関与する型によって決まります。

- [符号付き整数型からの変換](../c-language/conversions-from-signed-integral-types.md)

- [符号なし整数型からの変換](../c-language/conversions-from-unsigned-integral-types.md)

- [浮動小数点型からの変換](../c-language/conversions-from-floating-point-types.md)

- [ポインター型との間の変換](../c-language/conversions-to-and-from-pointer-types.md)

- [他の型からの変換](../c-language/conversions-from-other-types.md)

型修飾子は変換の許容性には影響しませんが、代入の左辺で **`const`** 値は使用できません。

## <a name="see-also"></a>関連項目

[型変換](../c-language/type-conversions-c.md)
