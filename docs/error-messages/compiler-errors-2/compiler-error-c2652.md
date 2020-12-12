---
description: 詳細については、「コンパイラエラー C2652」を参照してください。
title: コンパイラエラー C2652
ms.date: 11/04/2016
f1_keywords:
- C2652
helpviewer_keywords:
- C2652
ms.assetid: 6e3d1a90-a989-4088-8afd-dc82f6a2d66f
ms.openlocfilehash: 6d0f85a089c527ce299e007ce04d96ac68daaf56
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286177"
---
# <a name="compiler-error-c2652"></a>コンパイラエラー C2652

' identifier ': コピーコンストラクターが無効です: 最初のパラメーターを ' identifier ' にすることはできません

コピーコンストラクターの最初のパラメーターの型は、定義されているクラス、構造体、または共用体と同じです。 最初のパラメーターには、型への参照を指定できますが、型自体は使用できません。

次の例では、C2651 が生成されます。

```cpp
// C2652.cpp
// compile with: /c
class A {
   A( A );   // C2652 takes an A
};
class B {
   B( B& );   // OK, reference to B
};
```
