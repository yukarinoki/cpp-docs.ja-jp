---
description: 詳細については、「コンパイラエラー C2490」を参照してください。
title: コンパイラ エラー C2490
ms.date: 11/04/2016
f1_keywords:
- C2490
helpviewer_keywords:
- C2490
ms.assetid: 9de6bddd-b2e2-4ce6-b33b-201a8c2c8c54
ms.openlocfilehash: 9638b65eb453fcc957ac2e9a947138ba1f7ac745
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339346"
---
# <a name="compiler-error-c2490"></a>コンパイラ エラー C2490

' keyword ' は ' 生 ' 属性を持つ関数では許可されていません

[生](../../cpp/naked-cpp.md)として定義された関数は、構造化例外処理を使用できません。

次の例では、C2490 が生成されます。

```cpp
// C2490.cpp
// processor: x86
__declspec( naked ) int func() {
   __try{}   // C2490, structured exception handling
}
```
