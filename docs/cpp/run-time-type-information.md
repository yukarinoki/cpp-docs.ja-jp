---
title: ランタイム型情報
ms.custom: index-page
ms.date: 11/04/2016
helpviewer_keywords:
- RTTI compiler option
- run-time type information
- run time, type checking
- type information, run-time type checking
- run-time checks, type checking
ms.assetid: becbd0e5-0439-4c61-854f-8a74f7160c54
ms.openlocfilehash: b6d3652539572f094d0e7139e6672402341c956d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87232236"
---
# <a name="run-time-type-information"></a>ランタイム型情報

実行時型情報 (RTTI: Run-Time Type Information) は、プログラムの実行中にオブジェクトの型を決定するための機能です。 クラス ライブラリの多くのベンダーがこの機能を独自に実装していたことから、RTTI が C++ 言語に追加されましたが、 これによってライブラリの間に非互換性が発生しました。 したがって、実行時型情報を言語レベルでサポートする必要があります。

RTTI についてわかりやすく説明するため、ここでは対象をポインターに限定しています。 ただし、ここで説明する概念は参照にも適用されます。

C++ 言語には、実行時型情報を扱う 3 つの主要要素があります。

- [Dynamic_cast](../cpp/dynamic-cast-operator.md)演算子。

   ポリモーフィック型を変換します。

- [Typeid](../cpp/typeid-operator.md)演算子。

   オブジェクトの正確な型を特定します。

- [Type_info](../cpp/type-info-class.md)クラス。

   演算子によって返される型情報を保持するために使用され **`typeid`** ます。

## <a name="see-also"></a>関連項目

[キャスト](../cpp/casting.md)
