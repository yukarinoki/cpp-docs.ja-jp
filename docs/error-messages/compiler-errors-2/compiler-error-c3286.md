---
title: コンパイラ エラー C3286
ms.date: 11/04/2016
f1_keywords:
- C3286
helpviewer_keywords:
- C3286
ms.assetid: 554328c8-cf44-4f7d-a8d2-def74d28ecdd
ms.openlocfilehash: 4c87e98f11a560d0d92be8ea7bc624edd4e09ad2
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80201397"
---
# <a name="compiler-error-c3286"></a>コンパイラ エラー C3286

> '*指定子*': 反復変数は、ストレージクラスの指定子を持つことはできません

ストレージクラスを繰り返し変数に指定することはできません。 詳細については、「 [」](../../dotnet/for-each-in.md)の「[ストレージクラス」 (C++)](../../cpp/storage-classes-cpp.md)および「」を参照してください。

## <a name="example"></a>例

次の例では、C3286 を生成し、正しい使用法も示しています。

```cpp
// C3286.cpp
// compile with: /clr
int main() {
   array<int> ^p = { 1, 2, 3 };
   for each (static int i in p) {}   // C3286
   for each (int j in p) {}   // OK
}
```
