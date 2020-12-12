---
description: 詳細については、「コンパイラエラー C2598」を参照してください。
title: コンパイラ エラー C2598
ms.date: 11/04/2016
f1_keywords:
- C2598
helpviewer_keywords:
- C2598
ms.assetid: 40777c62-39ba-441e-b081-f49f94b43547
ms.openlocfilehash: 9ba2a37ee3acb841b340449e9a922ed98e3c9d24
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97120088"
---
# <a name="compiler-error-c2598"></a>コンパイラ エラー C2598

リンケージ指定はグローバルスコープである必要があります

リンケージ指定子がローカルスコープで宣言されています。

次の例では、C2598 が生成されます。

```cpp
// C2598.cpp
// compile with: /c
void func() {
   extern "C" int func2();   // C2598
}

extern "C" int func( int i );
```
