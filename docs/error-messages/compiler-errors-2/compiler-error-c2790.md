---
description: 詳細については、「コンパイラエラー C2790」を参照してください。
title: コンパイラエラー C2790
ms.date: 11/04/2016
f1_keywords:
- C2790
helpviewer_keywords:
- C2790
ms.assetid: 38d4fce1-ba00-413d-8bc1-e8aa43d7bc1f
ms.openlocfilehash: 0913b87f40e7f4ad2ecccb333e67bb0d76b4afde
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297803"
---
# <a name="compiler-error-c2790"></a>コンパイラエラー C2790

' super ': このキーワードはクラスメンバー関数の本体内でのみ使用できます

このエラーメッセージは、ユーザーがメンバー関数のコンテキストの外部でキーワード [super](../../cpp/super.md) を使用しようとした場合に表示されます。

次の例では、C2790 が生成されます。

```cpp
// C2790.cpp
void f() {
   __super::g();   // C2790
}
```
