---
description: 詳細については、「コンパイラエラー C2815」を参照してください。
title: コンパイラ エラー C2815
ms.date: 11/04/2016
f1_keywords:
- C2815
helpviewer_keywords:
- C2815
ms.assetid: d0256fd6-0721-4c99-b03c-52d96e77a613
ms.openlocfilehash: fd0ee162c10acd89e4746ea906d64ea8ef069271
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194840"
---
# <a name="compiler-error-c2815"></a>コンパイラ エラー C2815

' operator delete ': 最初の仮パラメーターは ' void * ' でなければなりませんが、' param ' が使用されました

ユーザー定義の [operator delete](../../standard-library/new-operators.md#op_delete) 関数は、型の最初の仮パラメーターを受け取る必要があり `void *` ます。

次の例では、C2815 が生成されます。

```cpp
// C2815.cpp
// compile with: /c
class CMyClass {
public:
   void mf1(int *a);
   void operator delete(CMyClass *);   // C2815
   void operator delete(void *);
};
```
