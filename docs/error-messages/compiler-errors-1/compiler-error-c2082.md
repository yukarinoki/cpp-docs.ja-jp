---
description: 詳細については、「コンパイラエラー C2082」を参照してください。
title: コンパイラ エラー C2082
ms.date: 11/04/2016
f1_keywords:
- C2082
helpviewer_keywords:
- C2082
ms.assetid: 87a6d442-157c-46e8-9bff-8388f8338ae0
ms.openlocfilehash: 957699338d253ee2438060b27a0089a654fc4f9c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316623"
---
# <a name="compiler-error-c2082"></a>コンパイラ エラー C2082

仮パラメーター 'identifier' が再定義されました

関数の仮パラメーターが、関数本体の中で再宣言されています。 エラーを解決するには、再定義を削除します。

次の例では C2082 が生成されます。

```cpp
// C2082.cpp
void func(int i) {
   int i;   // C2082
   int ii;   // OK
}
```
