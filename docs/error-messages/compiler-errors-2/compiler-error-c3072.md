---
title: コンパイラ エラー C3072
ms.date: 11/04/2016
f1_keywords:
- C3072
helpviewer_keywords:
- C3072
ms.assetid: cdd5cb6b-c478-4698-adfa-c40188d34a18
ms.openlocfilehash: 2b76fa91d739e9cc89251aaf56aa9b196e62a68d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406731"
---
# <a name="compiler-error-c3072"></a>コンパイラ エラー C3072

演算子 'operator' は ref クラスのインスタンスに適用することはできません。

単項を使用して '`operator` ' ref クラスのインスタンスをハンドル型に変換する演算子

CLR 型では、CLR 演算子、not、ネイティブ (または standard) の演算子が必要です。  詳細については、次を参照してください。[参照演算子の追跡](../../extensions/tracking-reference-operator-cpp-component-extensions.md)します。

## <a name="example"></a>例

次の例では、C3072 が生成されます。

```
// C3072.cpp
// compile with: /clr
ref class R {};

int main() {
   R r1;
   R^ r2 = &r1;   // C3072
   R^ r3 = %r1;   // OK
}
```