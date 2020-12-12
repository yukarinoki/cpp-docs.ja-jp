---
description: 詳細については、「キャスト演算子」を参照してください。
title: キャスト演算子
ms.custom: index-page
ms.date: 11/04/2016
helpviewer_keywords:
- operators [C++], casting
- casting operators [C++]
ms.assetid: 16240348-26bc-4f77-8eab-57253f00ce52
ms.openlocfilehash: 6ab19f1b30958f4d78a97be76c15373ed9c9b620
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97308550"
---
# <a name="casting-operators"></a>キャスト演算子

C++ 言語には、固有のキャスト演算子がいくつかあります。 これらの演算子は、以前のスタイルの C 言語のキャストが持つあいまいさと危険性の一部を取り除くことを目的としています。 このような演算子を次に示します。

- [dynamic_cast](../cpp/dynamic-cast-operator.md) ポリモーフィックな型の変換に使用されます。

- [static_cast](../cpp/static-cast-operator.md) 非ポリモーフィック型の変換に使用されます。

- [const_cast](../cpp/const-cast-operator.md) 、、およびの各属性を削除するために使用 **`const`** **`volatile`** **`__unaligned`** します。

- [reinterpret_cast](../cpp/reinterpret-cast-operator.md) ビットを簡単に再解釈するために使用されます。

- [safe_cast](../extensions/safe-cast-cpp-component-extensions.md) 検証可能な MSIL を生成するために C++/CLI で使用されます。

**`const_cast`** **`reinterpret_cast`** これらの演算子は以前のスタイルキャストと同じ危険をもたらすため、とは最後の手段として使用します。 それでも、これらは、以前のスタイルのキャストを完全に置き換えるために必要です。

## <a name="see-also"></a>関連項目

[キャスト](../cpp/casting.md)
