---
title: キャスト演算子
ms.custom: index-page
ms.date: 11/04/2016
helpviewer_keywords:
- operators [C++], casting
- casting operators [C++]
ms.assetid: 16240348-26bc-4f77-8eab-57253f00ce52
ms.openlocfilehash: eac274a0207be675b8d13532c3110c6e71bd55c9
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190103"
---
# <a name="casting-operators"></a>キャスト演算子

C++ 言語には、固有のキャスト演算子がいくつかあります。 これらの演算子は、以前のスタイルの C 言語のキャストが持つあいまいさと危険性の一部を取り除くことを目的としています。 このような演算子を次に示します。

- [dynamic_cast](../cpp/dynamic-cast-operator.md)ポリモーフィックな型の変換に使用されます。

- [static_cast](../cpp/static-cast-operator.md)非ポリモーフィック型の変換に使用されます。

- [const_cast](../cpp/const-cast-operator.md)**Const**、 **volatile**、および **__unaligned**属性を削除するために使用します。

- [reinterpret_cast](../cpp/reinterpret-cast-operator.md)ビットを簡単に再解釈するために使用されます。

- [safe_cast](../extensions/safe-cast-cpp-component-extensions.md)検証可能C++な MSIL を生成するために/cli で使用されます。

これらの演算子は以前のスタイルキャストと同じ危険をもたらすため、 **const_cast**と**reinterpret_cast**を最後の手段として使用します。 それでも、これらは、以前のスタイルのキャストを完全に置き換えるために必要です。

## <a name="see-also"></a>参照

[キャスト](../cpp/casting.md)
