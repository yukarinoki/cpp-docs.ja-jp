---
description: 詳細については、「コンパイラエラー C2793」を参照してください。
title: コンパイラエラー C2793
ms.date: 11/04/2016
f1_keywords:
- C2793
helpviewer_keywords:
- C2793
ms.assetid: ce35f4e8-c357-40ca-95c4-15ff001ad69d
ms.openlocfilehash: 26d38427f8d5b502df7d8a6ff4351dd00a3155eb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297747"
---
# <a name="compiler-error-c2793"></a>コンパイラエラー C2793

' token ': ':: ' の後に予期しないトークンがあります。識別子またはキーワード ' operator ' が必要です

次に続くトークンは、 `__super::` 識別子またはキーワードのみ **`operator`** です。

次の例では、C2793 が生成されます。

```cpp
// C2793.cpp
struct B {
   void mf();
};

struct D : B {
   void mf() {
      __super::(); // C2793
   }
};
```
