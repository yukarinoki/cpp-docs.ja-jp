---
title: コンパイラ エラー C3286 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3286
dev_langs:
- C++
helpviewer_keywords:
- C3286
ms.assetid: 554328c8-cf44-4f7d-a8d2-def74d28ecdd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9ea2a6dcccd6de6d4fc3081106123f4ab37f71a2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46052915"
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