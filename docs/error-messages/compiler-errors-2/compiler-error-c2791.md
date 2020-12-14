---
description: 詳細については、「コンパイラエラー C2791」を参照してください。
title: コンパイラエラー C2791
ms.date: 11/04/2016
f1_keywords:
- C2791
helpviewer_keywords:
- C2791
ms.assetid: 938ad1fb-75d9-4ce2-ad92-83d6249005b5
ms.openlocfilehash: 0f5bd93c1c6ee32399da793147a18e9225b5fcb1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297773"
---
# <a name="compiler-error-c2791"></a>コンパイラエラー C2791

' super ' が不適切に使用されています: ' class ' に基底クラスがありません。

キーワード [super](../../cpp/super.md) は、基底クラスを持たないクラスのメンバー関数のコンテキスト内で使用されました。

次の例では、C2791 が生成されます。

```cpp
// C2791.cpp
struct D {
   void mf() {
      __super::mf();   // C2791
   }
};
```
