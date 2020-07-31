---
title: __unaligned
ms.date: 12/17/2018
f1_keywords:
- __unaligned_cpp
- __unaligned
- _unaligned
helpviewer_keywords:
- __unaligned keyword [C++]
ms.assetid: 0cd83aad-1840-47e3-ad33-59bfcbe6375b
ms.openlocfilehash: 2ab94a44d08165ca6e8f394278e24d7c8d201398
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223500"
---
# <a name="__unaligned"></a>__unaligned

**Microsoft 固有**。 修飾子を使用してポインターを宣言すると、 **`__unaligned`** コンパイラは、ポインターがアラインされていないデータをアドレスと見なします。 その結果、プラットフォームに適したコードが生成され、ポインターを介して、整列されていない読み取りと書き込みが処理されます。

## <a name="remarks"></a>解説

この修飾子は、ポインターによってアドレス指定されるデータの配置を表します。ポインター自体は、固定されていると見なされます。

キーワードの必須は、 **`__unaligned`** プラットフォームと環境によって異なります。 データを適切にマークしないと、パフォーマンスの低下からハードウェア障害まで、問題が発生する可能性があります。 **`__unaligned`** 修飾子が x86 プラットフォームに対して無効です。

以前のバージョンとの互換性のために、 **`_unaligned`** **`__unaligned`** コンパイラオプションの [ [ `/Za` \( 言語拡張を無効にする](../build/reference/za-ze-disable-language-extensions.md)] が指定されていない場合、はのシノニムになります。

アラインメントの詳細については、次のトピックを参照してください。

- [`align`](../cpp/align-cpp.md)

- [`alignof` 演算子](../cpp/alignof-operator.md)

- [`pack`](../preprocessor/pack.md)

- [`/Zp`(構造体メンバーの配置)](../build/reference/zp-struct-member-alignment.md)

- [構造体の配置例](../build/x64-software-conventions.md#examples-of-structure-alignment)

## <a name="see-also"></a>関連項目

[キーワード](../cpp/keywords-cpp.md)
