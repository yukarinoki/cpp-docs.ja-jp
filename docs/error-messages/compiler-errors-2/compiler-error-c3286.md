---
title: コンパイラ エラー C3286
ms.date: 11/04/2016
f1_keywords:
- C3286
helpviewer_keywords:
- C3286
ms.assetid: 554328c8-cf44-4f7d-a8d2-def74d28ecdd
ms.openlocfilehash: 8c09ea34c7dabf2cadecad7c76d766c9496f5a5a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50461010"
---
# <a name="compiler-error-c3286"></a>コンパイラ エラー C3286

> '*指定子*': 繰り返し変数は、ストレージ クラス指定子を含めることはできません

ストレージ クラスは、繰り返し変数を指定できません。 詳細については、次を参照してください。[ストレージ クラス (C++)](../../cpp/storage-classes-cpp.md)と[ごとに、で](../../dotnet/for-each-in.md)します。

## <a name="example"></a>例

次の例では、C3286 を生成しも正しい使用法を示しています。

```cpp
// C3286.cpp
// compile with: /clr
int main() {
   array<int> ^p = { 1, 2, 3 };
   for each (static int i in p) {}   // C3286
   for each (int j in p) {}   // OK
}
```