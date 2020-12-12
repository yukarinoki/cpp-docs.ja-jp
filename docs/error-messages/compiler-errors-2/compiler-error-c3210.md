---
description: 詳細については、「コンパイラエラー C3210」を参照してください。
title: コンパイラ エラー C3210
ms.date: 11/04/2016
f1_keywords:
- C3210
helpviewer_keywords:
- C3210
ms.assetid: c6e9d309-fabc-4e7d-b526-be20d9fe3f6a
ms.openlocfilehash: 5349a7ea8677a8a55511f514e74251375a262fb7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97173910"
---
# <a name="compiler-error-c3210"></a>コンパイラ エラー C3210

' type ': アクセス宣言は基底クラスのメンバーにのみ適用できます

[Using 宣言](../../cpp/using-declaration.md)が正しく指定されませんでした。

## <a name="example"></a>例

次の例では、C3210 が生成されます。

```cpp
// C3210.cpp
// compile with: /c
struct A {
protected:
   int i;
};

struct B {
   using A::i;   // C3210
};

struct C : public A {
   using A::i;   // OK
};
```
