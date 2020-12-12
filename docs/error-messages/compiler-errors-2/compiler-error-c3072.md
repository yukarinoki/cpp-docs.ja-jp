---
description: 詳細については、「コンパイラエラー C3072」を参照してください。
title: コンパイラ エラー C3072
ms.date: 11/04/2016
f1_keywords:
- C3072
helpviewer_keywords:
- C3072
ms.assetid: cdd5cb6b-c478-4698-adfa-c40188d34a18
ms.openlocfilehash: 02876a6983a47ce76f6e089bafde68af41034131
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320280"
---
# <a name="compiler-error-c3072"></a>コンパイラ エラー C3072

> 演算子 '*operator name*' を ref クラスのインスタンスに適用することはできません

単項 *演算子-name* 演算子を使用して、ref クラスのインスタンスをハンドル型に変換します。

CLR 型には、ネイティブ (または標準) 演算子ではなく、CLR 演算子が必要です。  詳細については、「 [参照演算子の追跡](../../extensions/tracking-reference-operator-cpp-component-extensions.md)」を参照してください。

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
