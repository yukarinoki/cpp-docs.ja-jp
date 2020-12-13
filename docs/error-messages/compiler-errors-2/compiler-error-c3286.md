---
description: 詳細については、「コンパイラエラー C3286」を参照してください。
title: コンパイラ エラー C3286
ms.date: 11/04/2016
f1_keywords:
- C3286
helpviewer_keywords:
- C3286
ms.assetid: 554328c8-cf44-4f7d-a8d2-def74d28ecdd
ms.openlocfilehash: 38e3b405f9093baa266cf56e5bfc7f44c7566206
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339225"
---
# <a name="compiler-error-c3286"></a>コンパイラ エラー C3286

> '*指定子*': 反復変数は、ストレージクラスの指定子を持つことはできません

ストレージクラスを繰り返し変数に指定することはできません。 詳細については、「 [」](../../dotnet/for-each-in.md)の「[ストレージクラス (C++)](../../cpp/storage-classes-cpp.md) 」および「」を参照してください。

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
