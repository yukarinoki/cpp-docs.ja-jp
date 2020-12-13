---
description: 詳細については、「コンパイラエラー C2233」を参照してください。
title: コンパイラ エラー C2233
ms.date: 11/04/2016
f1_keywords:
- C2233
helpviewer_keywords:
- C2233
ms.assetid: 236bdf0b-9607-4f26-a249-d8def0b1333c
ms.openlocfilehash: d111a20fa9cac5a41566f63f6e3eef0c14ef544c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338777"
---
# <a name="compiler-error-c2233"></a>コンパイラ エラー C2233

' identifier ': サイズが0の配列を含むオブジェクトの配列は無効です

配列内の各オブジェクトには、少なくとも1つの要素が含まれている必要があります。

次の例では、C2233 が生成されます。

```cpp
// C2233.cpp
// compile with: /c
class A {
   char somearray[1];
};

class B {
   char zeroarray[];
};

A array[100];   // OK
B array2[100];   // C2233
```
