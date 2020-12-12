---
description: '詳細については、次を参照してください: __unaligned'
title: __unaligned
ms.date: 12/17/2018
f1_keywords:
- __unaligned_cpp
- __unaligned
- _unaligned
helpviewer_keywords:
- __unaligned keyword [C++]
ms.assetid: 0cd83aad-1840-47e3-ad33-59bfcbe6375b
ms.openlocfilehash: f5afd0c6c1a506cbaeb03d497e64eac743ecc4df
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97145757"
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

- [`/Zp` (構造体メンバーの配置)](../build/reference/zp-struct-member-alignment.md)

- [構造体の配置例](../build/x64-software-conventions.md#examples-of-structure-alignment)

## <a name="see-also"></a>関連項目

[キーワード](../cpp/keywords-cpp.md)
