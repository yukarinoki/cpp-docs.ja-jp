---
title: コンパイラ エラー C3072
ms.date: 11/04/2016
f1_keywords:
- C3072
helpviewer_keywords:
- C3072
ms.assetid: cdd5cb6b-c478-4698-adfa-c40188d34a18
ms.openlocfilehash: bcf2548fbe1182f7f6c4bd966ca6aa9ef9f10089
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212606"
---
# <a name="compiler-error-c3072"></a>コンパイラ エラー C3072

> 演算子 '*operator name*' を ref クラスのインスタンスに適用することはできません

単項*演算子-name*演算子を使用して、ref クラスのインスタンスをハンドル型に変換します。

CLR 型には、ネイティブ (または標準) 演算子ではなく、CLR 演算子が必要です。  詳細については、「[参照演算子の追跡](../../extensions/tracking-reference-operator-cpp-component-extensions.md)」を参照してください。

## <a name="example"></a>例

次の例では、C3072 が生成されます。

```cpp
// C3072.cpp
// compile with: /clr
ref class R {};

int main() {
   R r1;
   R^ r2 = &r1;   // C3072
   R^ r3 = %r1;   // OK
}
```
